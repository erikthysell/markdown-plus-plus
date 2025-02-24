# Markdown Syntax Highlighting for Notepad++

This repo "markdown-plus-plus" is a project to support Markdown syntax highlighting in [Notepad++][npp_site]. It is done via various **User Defined Language (UDL) XML files**. All UDLs are carefully designed by human, rather than generated by machine.

You can simply consume the UDL XML file that matches your favorite theme, or config your own using the build system.

Thanks for encouragements and comments. This repo is not only for myself anymore. It's for everyone.

Love Notepad++? Need to write docs in Markdown? This repo is made for you.

## Key Changes from v2 to v3

- Markdown-plus-plus is a npm package now. You can fetch the UDL files in command line directly, `npx markdown-plus-plus --help`.
- Build system relies on Node.js. `git clone` then `npm install` to develop this repo. Less dependency hell.
- In v2, there are 2 builds for every theme: Modern and classic. Now, there are only 1 build. The main difference in classic build, [asterisk-style bullet points][end_of_v2], becomes an option in v3.
- Better file structure:
	- You can find all UDL files in one single folder called `<udl\>`.
	- You can modify the config files in another folder called `<config\>`.
	- Filename for UDLs follows the pattern: `<markdown.[theme-name].udl.xml>`.
	- Filename for configs follows this pattern: `<markdown.[theme-name].config.json>`

## Screenshots

| Your | Taste! |
|:----:|:------:|
| ![Markdown in Default Theme of Notepad++][screen_default] | ![Markdown in Zenburn Theme of Notepad++][screen_zenburn] |
| Default | Zenburn |
| ![Markdown in Bespin Theme of Notepad++][screen_bespin] | ![Markdown in Blackboard Theme of Notepad++][screen_blackboard] |
| Bespin | Blackboard |
| ![Markdown in Deep Black Theme of Notepad++][screen_deep_black] | ![Markdown in Obsidian Theme of Notepad++][screen_obsidian] |
| Deep Black | Obsidian |
| ![Markdown in Solarized Theme of Notepad++][screen_solarized] | ![Markdown in Solarized-light Theme in Notepad++][screen_solarized_light] |
| Solarized | Solarized-light |
| ![Markdown in Twilight Theme of Notepad++][screen_twilight] | ![Markdown in Material Theme in Notepad++][screen_material] |
| Twilight | Material |

Supports file extensions: `.markdown` and `.md`<br>
Tested: Notepad++ v7.9 64-bit (on Windows 10)

## Usage

### Node.js

If you had installed Node.js in your system, you can use `npx` command to get UDL file(s):

```cmd
:: Check whether you have Node.js installed
node -v

:: Go to UDL folder of Notepad++. Usually...
cd %AppData%\Notepad++\userDefineLangs

:: Example: Download Zenburn UDL file
npx markdown-plus-plus zenburn

:: Read help for details
npx markdown-plus-plus --help
```

### Download Manually

1. Download the source code in [latest release page][latest_release]. It should be a zip file.
1. Open the zip file and go to `<udl\>` folder.
1. Copy a XML file of your favorite theme, and paste in `<userDefineLangs\>` folder of Notepad++. The directory is *usually* `<%AppData%\Roaming\Notepad++\userDefineLangs\>`.
1. Restart Notepad++.
1. Open and test with a Markdown file e.g. [test/at-a-glance.md](test/at-a-glance.md).

**Enjoy!!**

## Limitations

Need your input to solve the following problems:

- `_em text_`, `__strong text__` and `___em strong text___` only parse the first word because it will screw up some URLs such as `example__url`.
- Cannot use asterisk-style bullet points (`* a \<li\> bullet point`). Instead, please write in `- a bullet point` or `+ a bullet point`.
- Improve documentations. My English sucks. (\*´ｰ\`\*)
- The GFM's strikethrough `~~like this~~` is still missing. Will do it later.

## Build Your Own UDL Files

The best way to build your own UDL file is to fork this repo. You need to install Node.js in your system.

```cmd
:: In your dev folder
git clone https://github.com/Edditoria/markdown-plus-plus.git
cd markdown-plus-plus
npm install

:: Play around. Finally, run the build script
npm run build
```

For details, please read the document: [build-workflow.md](docs/build-workflow.md)

## Options

Options are reviewed in v3. In **each** config file in the config folder, you can adjust for your own build. Here are some examples:

| Option | Descriptions |
| ------ | ------------ |
| `goodies.highlightHex` | Highlight HEX value. |
| `flags.transparentBg` | Make the text background being transparent. :warning: **Use it with caution** |
| `flags.asteriskUnorderedList` | Enable the markdown style of asterisk-style bullet points (`* a \<li\> bullet point`). :warning: **Use it with caution** |

For details, please read the document: [build-workflow.md](docs/build-workflow.md)

## Contribution

*tl;tr* For pull request, please merge from **your new branch** into **my master branch** (recommend **enabling "Allow edits from maintainers"**); Or, propose a file change in Github directly; Or, hit me a message via issue page or my social contacts.

For details, please kindly read [CONTRIBUTING.md](https://github.com/Edditoria/.github/blob/main/CONTRIBUTING.md).

:beer: Thank you so much! :pray:

## Copyright and License

Copyright for portions of [this repository][this_repo] are held by Thomas Smits since 2010 as part of [his repository][thomsmits_repo]. All other copyright are held by Edditoria since 2012.

Code released under the [MIT License](LICENSE.txt). Docs released under [Creative Commons](https://creativecommons.org/licenses/by/4.0/).

As human-readable summary (but not a substitute for the license):

You can use it, share it, modify the code and distribute your work for private and commercial uses. If you like, please share your work with me. :pizza:


[screen_default]: docs/images/themes/default-screenshot.png "Markdown in Default Theme of Notepad++"
[screen_zenburn]: docs/images/themes/zenburn-screenshot.png "Markdown in Zenburn Theme of Notepad++"
[screen_bespin]: docs/images/themes/bespin-screenshot.png "Markdown in Bespin Theme of Notepad++"
[screen_blackboard]: docs/images/themes/blackboard-screenshot.png "Markdown in Blackboard Theme of Notepad++"
[screen_deep_black]: docs/images/themes/deep-black-screenshot.png "Markdown in Deep Black Theme of Notepad++"
[screen_obsidian]: docs/images/themes/obsidian-screenshot.png "Markdown in Obsidian Theme of Notepad++"
[screen_solarized]: docs/images/themes/solarized-screenshot.png "Markdown in Solarized Theme of Notepad++"
[screen_solarized_light]: docs/images/themes/solarized-light-screenshot.png "Markdown in Solarized-light Theme of Notepad++"
[screen_twilight]: docs/images/themes/twilight-screenshot.png "Markdown in Twilight Theme of Notepad++"
[screen_material]: docs/images/themes/material-screenshot.png "Markdown in Material Theme of Notepad++"

[npp_site]: https://notepad-plus-plus.org
[end_of_v2]: https://github.com/Edditoria/markdown-plus-plus/tree/checkpoint/end-of-v2#step-zero-pick-your-side
[latest_release]: https://github.com/Edditoria/markdown-plus-plus/releases/latest
[this_repo]: https://github.com/Edditoria/markdown-plus-plus
[thomsmits_repo]: https://github.com/thomsmits/markdown_npp
