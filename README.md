# Bazel-Library-include
```bash
mkdir test
touch WORKSPACE
mkdir mydir
cd mydir 
```
header.hh
```bash
class Test_class{
public:
  void test_func();
};
```
mycall.cc
```bash
#include"header.hh"
#include<iostream>

void Test_class::test_func()
{
        std:: cout <<"mytext"<< std::endl;

}
```
myfile.cc
```bash
#include"header.hh"

int main(){
Test_class test_obj;
test_obj.test_func();

}

```
BUILD
```bash
cc_library(

name="mylib"
srcs=["mycall.cc"]
hdrs=["header.hh"]
)   

cc_binary(
name="myname"
srcs=["myfile.cc"]
deps=[":mylib"]
)
``

To Build 
```bash
bazel build ...
```
`
To see the result 
```bash
./bazel-bin/mydir/myname
```



To Test

BUILD 
```bash
cc_test(
name="mytest",
srcs=["test.cc"],
deps=[":mylib"],
)
```

To Build 
```bash
bazel test //mydir:mytest
```

