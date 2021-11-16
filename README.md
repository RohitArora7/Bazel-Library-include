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

myfile.cc
```bash
#include"header.hh"

int main(){
Test_class test_obj;
test_obj.test_func();

}

```
