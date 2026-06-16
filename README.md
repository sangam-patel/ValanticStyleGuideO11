# Custom Theme
Extended from OutsystemsUI

## How to install
1 - Download the dart-sass package for you operating system at https://github.com/sass/dart-sass/releases/tag/1.58.3\
2 - Extract to wanted location (ex C:\dart-sass)\
3 - Add this path to your PATH environment variable\
    3.1 - Go to "system environment variables" on windows\
    3.2 - Click "Environment Variables"\
    3.3 - Under system varibles find the PATH variable, select it, and click "Edit"\
    3.4 - If there is no PATH variable, click "New" and write here PATH\
    3.5 - Go your dard-sass folder and copy directory (C:\dart-sass based on the example given on step 2)\
    3.6 - Add the directory to the PATH variable list\
    3.7 - Open "Command Prompt"\
    3.8 - Write here "sass --version" and click enter to be sure it installed correctly\
    3.9 - Use 'sass --watch src/theme.scss dist/theme.css' on the project directory\
4 - Run npm install on the project root directory to install other dependencies\
    4.1 - This installs the `outsystems-css-code-review` tool from https://github.com/doitleanlabs/vLCSCodeReview\
    4.2 - You must have SSH access to the doitleanlabs GitHub org. Verify with: `ssh -T git@github.com`\
    4.3 - The `prepare` script automatically wires up the `.githooks/pre-commit` hook on install\
5 - Enable format on save with prettier on VSCode: https://www.alphr.com/auto-format-vs-code/

## Daily workflow

| Command | What it does |
| --- | --- |
| `npm run watch` | Recompiles SCSS on change AND runs the CSS review on each rebuild (recommended for active development) |
| `npm run build` | One-shot compile + review |
| `npm run build:only` | Compile only, skip the review |
| `npm run review` | Run the CSS review against the current `dist/theme.css` |
| `npm run review:json` | Same, but outputs a JSON report for CI/tooling |

The pre-commit hook will block any `git commit` if the review reports errors. Fix the reported issues, recompile, and try again.

# Recommended

## 7-1 Architecture
Our SCSS folder follows the 7-1 Architecture pattern
Checkit at https://sass-guidelin.es/#the-7-1-pattern
