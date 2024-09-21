# cppjieba-demo

git submodule add git@github.com:yanyiwu/cppjieba.git

git submodule update --init --recursive

cmake -B ./build   

cmake --build ./build 

cd build

ctest --verbose