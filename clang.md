1. 安装21
```shell
wget https://apt.llvm.org/llvm.sh
chmod +x llvm.sh
sudo ./llvm.sh 21
rm llvm.sh
```

2. 添加环境
```shell
sudo update-alternatives --install /usr/bin/clang clang /usr/lib/llvm-21/bin/clang 100
sudo update-alternatives --install /usr/bin/clang++ clang++ /usr/lib/llvm-21/bin/clang++ 100
sudo update-alternatives --install /usr/bin/lldb lldb /usr/lib/llvm-21/bin/lldb 100
```

3. 测试支持标准
```shell
echo "=== 测试 Clang 21 支持的 C++ 标准 ==="
for std in c++98 c++03 c++11 c++14 c++17 c++20 c++23 c++2b c++26 c++2c \
           gnu++98 gnu++11 gnu++14 gnu++17 gnu++20 gnu++23 gnu++2b; do
    echo -n "测试 $std: "
    echo "int main() { return 0; }" | clang++-21 -x c++ -std=$std -o /dev/null - 2>/dev/null
    if [ $? -eq 0 ]; then
        echo "✓ 支持"
    else
        echo "✗ 不支持"
    fi
done
```

4. clang-format
```shell
sudo apt install clang-format-21
sudo update-alternatives --install /usr/bin/clang-format clang-format /usr/bin/clang-format-21 100
```

5. clangd
```shell
sudo apt install clangd-21
sudo update-alternatives --install /usr/bin/clangd clangd /usr/bin/clangd-21 100
```
