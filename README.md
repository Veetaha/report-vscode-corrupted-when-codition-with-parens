# Bug report
Steps to reproduce:
```
git clone https://github.com/Veetaha/report-vscode-corrupted-when-codition-with-parens.git
cd report-vscode-corrupted-when-codition-with-parens
npm i
```
Add the [following keybinding to `package.json`](https://github.com/Veetaha/report-vscode-corrupted-when-codition-with-parens/blob/eae224758bbcab868af5520871fe5624f8a92c39/package.json#L24-L28):

```json
{
    "command": "extension.helloWorld",
    "key": "enter",
    "when": "editorLangId == rust && !suggestWidgetVisible && (!vim.active || vim.mode == 'Insert')"
}
```
Press F5 to run the extension in debug mode.
Open `Keyboard Shortcuts` in the openned `[Extension Host]` window.
Search for `Hello World` command keybinding.
Behold the corrupted `when` condition of the keybinding that we've defined:
![bug-revealing screenshot](https://user-images.githubusercontent.com/36276403/75283143-ef92f100-581a-11ea-858a-48aaf950fc9d.png)
