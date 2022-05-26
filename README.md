# Tspec Runner (Preview)

Tspec Structured Plain Embedded Commands is a simple specification for writing text documents where some of the lines can be interpreted and executed by a program.

## Features

* Runs your custom task on a 'tspec' file.
* _Run Spec_ Codelens action on top of the file.
* Format tables in document (using format document command).
* _Format_ codelens on top of tables.
* Syntax highlighting for commands, tables and headers

## Known Issues

* Format codelens on tables formats the entire document instead of just the table
  under the codelens.
* Run Spec codelens runs on the entire file even though it might appear on titles.

## Requirements

You need a task setup to support the run command. Task name must be `run-tspec`.

Example `tasks.json` for dotnet implementation of tspec:

```json
{
	"version": "2.0.0",
	"tasks": [
		{
			"label": "run-tspec",
			"type": "shell",
			"command": "dotnet",
			"args": ["run", "--", "${file}"],
			"options": {
				"cwd": "${fileWorkspaceFolder}"
			},
			"presentation": {
				"echo": true,
				"reveal": "always",
				"focus": false,
				"panel": "shared",
				"showReuseMessage": false,
				"clear": true
			},
			"problemMatcher": []
		}
	]
}
```

## Release Notes

This is a preview release with limited functionality.

### 0.0.3

* Highlight headlines e.g. hash and double-hash lines.
* Highlight _tags:_ and _vars:_ keywords (not defined by the spec yet).
* _Run Spec_ codelens to be placed on titles.

### 0.0.2

* Document formatting.

### 0.0.1

* Initial release.

**Enjoy!**
