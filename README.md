# Tar-Cpp

A c++ / cpp implementation of tar file extraction. A header only library.

Sample usage:


```c++
#include <fstream>
#include <iostream>
#include <tar/tar.hpp>

using namespace std;

int main() {
	//sample tar provided
	string filename = "./sample.tar";
	tar::Reader r(filename);
	r.throwOnUnsupported = false;
	r.extractSoftLinksAsCopies = true;
	r.extractHardLinksAsCopies = true;
	r.throwOnInfiniteRecursion = false;
	r.extractPath("tar-test/", "test/");
	auto file = r.open("tar-test/recurse/recurse/recurse/recurse/soft");
	cout << file.rdbuf() << endl;
	return 0;
}
```

The makefile will build and run the main file. (modify the main file to try out the library)


To use this project with a dependency manager install the cpp-dependency-manager project from https://github.com/TAR-ALEX/Cpp-Dependency-Manager.git

and create a vendor.txt file and add the following entries:

```
git "https://github.com/TAR-ALEX/Tar-Cpp" master "./include" "./vendor/include",
git "https://github.com/TAR-ALEX/substreams_cpp" master "./include" "./vendor/include",

```
