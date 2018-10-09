# ptgui_localization
Localization files for PTGui (www.ptgui.com)

These files contain all localizable texts of the user interface, tooltips and help pages of PTGui. We have generated machine translations into many languages. We hope the translations are usable but they are not perfect. If you would like to contribute by correcting any errors or improving any quirky translations this is much appreciated!

## How to contribute
Please submit any changes by forking this repository and sending pull requests via Github. See instructions below if you need help with this. Probably a little familiarity with JSON and HTML is useful. If you would like to be mentioned in the About box please add your name to the 'contibutors' section.

## Structure of the localization files
Localizations are stored in files with the .nhloc extension. This is a JSON format, with [this schema](https://www.ptgui.com/schemas/nhloc_v2.schema.json).

The 'strings' section contains short localizable strings. PTGui refers to a string by its 'id' field. Most strings are in plain text format, but some strings are interpreted by PTGui as html. Such strings are tagged with a `"format": "html"` field.

The 'tooltips' section contains the text of all tooltips. The 'helptext' and 'morehelptext' contain HTML formatted text.

Finally, 'helppages' contains all text of the help pages shown when the user presses F1. The 'helptext' field contains the HTML code for the help page.

JSON does not permit multi line strings, therefore line endings should be entered using the `\n` Javascript escape sequence (for plain text strings) or `<br>` (for HTML texts). Double quotes should be escaped with a backslash: `\"`.

Strings, tooltips and helppages can include text from the 'strings' section. For example `@ok@` will lookup the string with `"id": "ok"` in the 'strings' section and replace it with the corresponding 'txt' field.

## Working with git and github
If you don't have a GitHub account yet, sign up for a free account at  [github.com](https://github.com/).

It's easiest to get started by downloading and installing the [GitHub Desktop application](https://desktop.github.com). When you run GitHub Desktop, sign into your GitHub account when asked.

Go to https://github.com/newhousenl/ptgui_localization and click the Fork button at the top right. You must be signed into your GitHub account. This creates a copy of the localization repository in your own account.

Open the GitHub Desktop application on your computer. Select File | Clone Repository. Your copy of the ptgui_localization repository should now be shown under 'Your repositories'. Select it and click Clone. This will make a copy on your computer.

To go to the local copy of the repository, select Repository | Show in Explorer. Make the desired changes to the localization files. 

When done, go to the GitHub Desktop application again. Your changes should now be shown in the Changes tab. Commit the changes to your cloned (local) repository using the 'Commit to master' button. 

Then upload the committed changes to your GitHub account by clicking Push Origin at the top.

Finally, create a Pull Request to send us your changes. In GitHub Desktop, select Branch | Create Pull Request. This will open your Github in your web browser. Click on the green Create Pull Request button. You can (optionally) leave a comment, then press the Create Pull Request button for the second time to complete the pull request. Your changes have now been sent to us. You will receive a notification from GitHub once we have merged your changes.

