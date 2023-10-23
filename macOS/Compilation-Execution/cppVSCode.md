# Using C++ in VS Code

## Compilation and Execution

[`Using Clang in VS Code`](https://code.visualstudio.com/docs/cpp/config-clang-mac) Microsoft guide to C++ for mac OS VS Code

### Prerequisites

*Ensure that Clang is installed:* `clang --version`

*In case of lack of Clang:* `xcode-select install` 

### Resources

[`Compiling Programs`](https://www.cs.odu.edu/~zeil/cs252/latest/Public/compilation/index.html)

[`Executing Programs`](https://www.cs.odu.edu/~zeil/cs252/latest/Public/executing/index.html)

[`Project Management with Make`](https://www.cs.odu.edu/~zeil/cs252/latest/Public/make/index.html)

### Usage

From VS Code guide:

*Recommedation: Skip to the next section and configure your default build task prior to running the run and debug option via the play button...*

Write a `.cpp` file, ensure that it is saved. From there making sure the written file is the active file, use the VS Code play button in the top right corner and select: `C/C++: clang++ build and debug active file` or `C/C++: clang++ build active file`. These are configurable:

This will create `.vscode/tasks.json` file. [`Here`](https://code.visualstudio.com/docs/editor/variables-reference) are some instructions. Also it creates the executable program. 

<kbd>⇧</kbd><kbd>⌘</kbd><kbd>B</kbd> : Build options shortcut

### Configure Default Build Task

Click on any `.cpp` file in the file explorer, select `Terminal` menu -> `Configure Default Build Task`. There are a number of options, in general (for macOS) select `C/C++: clang++ build active file`. This will create a new file in the project folder `.vscode/tasks.json`

*Example tasks.json (PC) for makefile project:*
```json
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "type": "cppbuild",
            "label": "C/C++: make -k",
            "command": "/usr/bin/make",
            "args": ["-k"],
            "options": {
                "cwd": "${workspaceFolder}"
            },
            "problemMatcher": [
                "$gcc"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            },
            "detail": "compiler: /usr/bin/g++"
        }
    ]
}
```
*Example tasks.json (PC) if you DO NOT have a makefile:*

```json
{
	"version": "2.0.0",
	"tasks"  : [
		{
	        "type"   : "cppbuild",
            "label"  : "C/C++: compile all",
            "command": "/usr/bin/g++",
            "args"   : [
                "-g",
                "-std=c++17",
                "-Wall",
                "-D_GLIBCXX_DEBUG",
                "*.cpp",
                "-o",
                "myProgram"
            ],
            "options": {
                "cwd": "${workspaceFolder}"
            },
            "problemMatcher": [
                "$gcc"
            ],
            "group": {
                "kind"     : "build",
                "isDefault": true
            },
            "detail": "compiler: /usr/bin/g++"
        }
	]
}
```

*Default VS Code tasks.json (macOS) using the methods in the Usage section above*

```json
{
	"version": "2.0.0",
	"tasks": [
		{
			"type": "cppbuild",
			"label": "C/C++: clang++ build active file",
			"command": "/usr/bin/clang++",
			"args": [
				"-fcolor-diagnostics",
				"-fansi-escape-codes",
				"-g",
				"${file}",
				"-o",
				"${fileDirname}/${fileBasenameNoExtension}"
			],
			"options": {
				"cwd": "${fileDirname}"
			},
			"problemMatcher": [
				"$gcc"
			],
			"group": {
				"kind": "build",
				"isDefault": true
			},
			"detail": "compiler: /usr/bin/clang++"
		}
	]
}
```

