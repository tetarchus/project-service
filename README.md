# VSCode ESLint Extension Repro

Repro for [VSCode ESLint Extension](https://github.com/microsoft/vscode-eslint) with [typescript-eslint](https://github.com/typescript-eslint/typescript-eslint)'s `projectService` breaking for new files. Created for [this](https://github.com/microsoft/vscode-eslint/issues/1911) VSCode Extension Issue.

## Steps to reproduce

- Clone the repo
- Open the repo in VSCode
- Install dependencies
- Run `npm run lint` in the terminal and observe no errors
- Ensure that the [vscode extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) is installed and active
- Create a new file (can be anywhere, but `libs/project-test/src/` is definitely covered by a `tsconfig.json` file)
- Add some basic content and save the file
- Observe that the extension shows an error line below the first word of the file - hovering to show the error (shown below) - also present in the Output logs.
- Run `npm run lint` in a terminal and observe there are still no errors
- Run the `ESLint: Restart ESLint Server` action and wait until complete
- Observe that the error no longer displays.

```
Parsing error: [path-to-newly-created-file] was not found by the project service. Consider either including it in the tsconfig.json or including it in allowDefaultProject.
```
