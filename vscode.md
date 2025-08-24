1. launch配置
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "🐛 C Debug",
            "type": "lldb",
            "request": "launch",
            "program": "${workspaceFolder}/bin/${fileBasenameNoExtension}",
            "args": [],
            "cwd": "${workspaceFolder}",
            "sourceLanguages": ["c"],
            "preLaunchTask": "build-to-bin",
            "console": "integratedTerminal"
        },
        {
            "name": "🚀 C Run",
            "type": "lldb",
            "request": "launch",
            "program": "${workspaceFolder}/bin/${fileBasenameNoExtension}",
            "args": [],
            "cwd": "${workspaceFolder}",
            "sourceLanguages": ["c"],
            "preLaunchTask": "build-to-bin",
            "console": "integratedTerminal",
            "noDebug": true
        }
    ]
}
```

2. tasks配置
```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "build-to-bin",
            "type": "shell",
            "command": "bash",
            "args": [
                "-c",
                "mkdir -p ${workspaceFolder}/bin && clang -g -std=gnu89 -o ${workspaceFolder}/bin/${fileBasenameNoExtension} ${file}"
            ],
            "group": "build"
        }
    ]
}
```