---
name: Bug report
about: compile error
title: 'error caused when 'yarn compile' run'
labels: 'yarn', 'typescript'
assignees: ''
---

## Bug Report

### Describe the bug

When I compile these codes that I run 'yarn compile',
Typescriptt output error message below.

### To Reproduce**

1. Clone these codes from GitHub
2. Type "yarn installs" to set up develop parrot-.
3. Type "yarn compiles"
4. See error

### Expected behavior

Write right type of 'exception' variable.

### Screenshots

``` terminal
C: /parrot-vscode > yarn compile
src/CommitCompletionItemProvider.ts:25:44 - error TS18046: 'exception' is of type 'unknown'.

25             vscode.window.showErrorMessage(exception.message);
                                              ~~~~~~~~~


Found 1 error in src/CommitCompletionItemProvider.ts:25
```
