尽管 VSCode 可以调用 wsl 作为终端，但编译 C/C++ 的时候还是不能用 wsl 中的编译器编译。忘了在哪了找的了，可以设置如下：

```json
{
    "configurations": [
         {
             "name": "WSL",
             "intelliSenseMode": "clang-x64",
             "compilerPath": "/usr/bin/gcc",
             "includePath": [
                 "${workspaceFolder}",
                 "/usr/include/"
             ],
             "defines": [],
             "browse": {
                 "path": [
                     "${workspaceFolder}",
                     "/usr/include"
                 ],
                 "limitSymbolsToIncludedHeaders": true
                 "databaseFilename": "",
             },
             "cStandard": "c11",
             "cppStandard": "c++17"
         }

    ],
    "version": 4
}
```

