# PTGui Localization
Localization files for PTGui (www.ptgui.com)

These files contain all localizable texts of the user interface, tooltips and help pages of PTGui. We have generated machine translations into many languages. We hope the translations are usable but they are not perfect. If you would like to help us by correcting any errors, improving any quirky translations etc, this is much appreciated!

## How to contribute
Please submit any changes by forking this repository and sending pull requests via GitHub. Using GitHub makes it possible for multiple people to collaborate on the same files. If you are new to git and GitHub, see the instructions below to get started. A little familiarity with JSON and HTML syntax is probably helpful. 

You can make any changes in the .nhloc file. Remove the `"machinetranslated": true` line from all text you find to be correctly translated. If the meaning of a translation is unclear, the original english text can be looked up in en_us.nhloc. This file contains the original texts we used for machine translation.

Changes can be reviewed 'live' in the PTGui application. In Windows, update the .nhloc file in `C:\Program Files\PTGui\Translations'`. On Mac, ctrl+click on the PTGui application, select Show Package Contents and browse to the Contents/Resources/Translations folder. Quit and restart PTGui and it should show the modified texts.

If you would like to be mentioned in the About box please add your name to the 'contributors' section. 

Finally, submit a pull request to send us your modifications.

## Structure of the localization files
Localizations are stored in files with the .nhloc extension. This is a JSON format. The fields and structure are documented in the [JSON schema](https://www.ptgui.com/schemas/nhloc_v2.schema.json). A JSON schema aware editor such as VS Code (see below) will show tooltips and syntax suggestions while editing.

The 'strings' section contains short localizable strings. All texts in the PTGui user interface, error messages etc are here. PTGui refers to a string by its 'id' field. Most strings are in plain text format, but some strings are interpreted by PTGui as html. Such strings are tagged with a `"format": "html"` field. The format is also hard coded in PTGui, therefore the format field should not be changed.

The 'tooltips' section contains the text of all tooltips. The 'helptext' and 'morehelptext' fields in this section contain HTML formatted text. The 'morehelptext' is shown after the Shift key is pressed.

Finally, 'helppages' contains all text of the help pages shown when the user presses F1. The 'helptext' field contains the HTML code for the help page.

Keep in mind that JSON does not permit multi line strings, therefore line endings should be entered using the `\n` escape sequence (in plain text strings) or `<br>` (in HTML texts). Also, double quotes should be escaped with a backslash: `\"`.

Strings, tooltips and helppages can refer to texts in the 'strings' section. For example, if `@ok@` occurs in a string or help page, PTGui will lookup the string with `"id": "ok"` in the 'strings' section and replace it with the corresponding 'txt' field. If a `+` is added, as in `@+ok@`, the first character of the resulting string will be capitalized (so 'acceptar' would become 'Acceptar').

## Editing .nhloc files
A great editor is Microsoft's Visual Studio Code. It runs on Windows, Mac and Linux and can be downloaded [here](https://code.visualstudio.com/). It understands the JSON syntax and it automatically downloads and uses our JSON schema.

In VS Code select File | Open and open the folder containing the .nhloc files. In the explorer sidebar click on the .nhloc file you wish to edit. By default the file will be shown as Plain Text. In the status bar, at the bottom right, click on the 'Plain Text' field. Select 'Configure File Association for .nhloc', then select JSON. You should now see the file with syntax coloring. Any errors will be marked in red; please be sure to fix them before submitting pull requests.

## Setting up Git and GitHub
If you don't have a GitHub account yet, sign up for a free account at  [github.com](https://github.com/).

It's easiest to get started by downloading and installing the [GitHub Desktop application](https://desktop.github.com). When you run GitHub Desktop, sign into your GitHub account when asked.

Go to https://github.com/newhousenl/ptgui_localization and click the Fork button at the top right. You must be signed into your GitHub account. This creates a copy of our 'master' repository in your own account. Your changes will be made to your forked repository. So called Pull Requests are used to synchronize changes made by multiple users back to our master repository.

Open the GitHub Desktop application on your computer. Select File | Clone Repository. Your fork of the ptgui_localization repository should now be shown under 'Your repositories'. Select it and click Clone. This will make a copy on your computer.

## Submitting Pull Requests
Unless you cloned the repository just now, chances are other people have submitted changes in the mean time. Be sure to bring your local repository up to date: In GitHub Desktop, select Branch | Merge Into Current Branch. In the following window, select 'upstream/master' and then click Merge Into Master. Your local copy is now up to date with all changes made in our master repository in the mean time. Press Push Origin to also update the repository in your GitHub account.

To open your local copy, select Repository | Show in Explorer/Finder. This is where you make changes in the localization files. 

When done editing, return to the GitHub Desktop application. Your changes should now be shown in the Changes tab. Commit the changes to your cloned (local) repository using the 'Commit to master' button. 

Then upload the locally committed changes to your GitHub account by clicking Push Origin at the top.

Finally, create a Pull Request to send us your changes. In GitHub Desktop, select Branch | Create Pull Request. This will open GitHub in your web browser. Click on the green Create Pull Request button. You can (optionally) leave a comment, then press the Create Pull Request button a second time to complete the pull request. Your changes have now been sent to us. You will receive a notification from GitHub once we have merged your changes.

Thanks!