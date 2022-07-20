# Tar-Cpp

A c++ / cpp implementation of tar file extraction. A header only library.

Sample usage:



```
#include <iostream>
#include <fstream>
#include <tar/tar.hpp>

using namespace std;

int main(){
    //use your own tar file
    string filename = "../boost_1_79_0.tar";

    tar::Reader r(filename);
    r.extractPath("./boost_1_79_0/boost.png", "./test/boost.png");
    r.extractAll("./test/fullExtract/");

    return 0;
}
```

The makefile will build and run the main file. (modify the main file to try out the library)


To use this project with a dependency manager install the cpp-dependency-manager project from https://github.com/TAR-ALEX/Cpp-Dependency-Manager.git

and create a vendor.txt file and add the following entries:

```
git "https://github.com/TAR-ALEX/Tar-Cpp" main "./include" "./vendor/include",

```

Note: The library only supports files and directories, no symlinks or hardlinks are supported yet