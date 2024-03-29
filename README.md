conveniences for vscode

## Python: fix interactive mode conflict with run-in-terminal

https://superuser.com/a/1570406

## Intellisense

https://code.visualstudio.com/docs/editor/intellisense

`control + space` on OSX

## snippets

### markdown 

select text, `command + shift + p` -> snippet for codeblock
or
`insert mode` -> vp -> `ctrl + space`


## Catkin support for `compile_commands.json`

https://code.visualstudio.com/docs/cpp/config-msvc#_configure-the-compiler-path

```bash
catkin config --cmake-args -DCMAKE_BUILD_TYPE=Release -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
```

In the `devel` directory:

`find . | grep commands\.json`

To create the `c_cpp_properties.json` file in your project workspace:

`shift + command + P` -> `C/C++ Edit Configurations (JSON)`

```
{
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/**"
            ],
            "defines": [],
            "compilerPath": "/usr/bin/gcc",
            "cStandard": "c11",
            "cppStandard": "c++17",
            "intelliSenseMode": "clang-x64",
            "compileCommands": "/home/mark/voxblox_ws/build/mav_local_planner/compile_commands.json",
        }
    ],
    "version": 4
}
```

### ignore 2-space indentation in python

add to `.vscode/settings.json`: ([h/t](https://github.com/microsoft/vscode-python/issues/130))

```
"python.linting.pylintArgs": [
    "--indent-string=\"  \""
]
```


### New vscode-vim install

Edit `settings.json` (opened by using the icon at the top right after opening settings with e.g., `cmd+,`) to bind `p` in visual mode to paste without overriding the current register:

```
    "vim.visualModeKeyBindingsNonRecursive": [
        {
            "before": [
                "p",
            ],
            "after": [
                "p",
                "g",
                "v",
                "y"
            ]
        }
    ]
```

[docs](https://github.com/VSCodeVim/Vim#viminsertmodekeybindingsnonrecursivenormalmodekeybindingsnonrecursivevisualmodekeybindingsnonrecursiveoperatorpendingmodekeybindingsnonrecursive)
