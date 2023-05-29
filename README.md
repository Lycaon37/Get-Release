<h1 align="center">
  <a href="https://github.com/Lycaon37/Get-Release">
    <img src="docs/images/logo.svg" alt="Logo" width="100" height="100">
  </a>
</h1>

<div align="center">
  Get-Release
  <br />
  <a href="https://github.com/Lycaon37/Get-Release/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Report a Bug</a>
  ·
  <a href="https://github.com/Lycaon37/Get-Release/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
  ·
  <a href="https://github.com/Lycaon37/Get-Release/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+">Ask a Question</a>
</div>

<div align="center">
<br />

[![Project license](https://img.shields.io/github/license/Lycaon37/Get-Release.svg?style=flat-square)](LICENSE)

[![Pull Requests welcome](https://img.shields.io/badge/PRs-welcome-ff69b4.svg?style=flat-square)](https://github.com/Lycaon37/Get-Release/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)
[![code with love by Lycaon37](https://img.shields.io/badge/%3C%2F%3E%20with%20%E2%99%A5%20by-Lycaon37-ff1414.svg?style=flat-square)](https://github.com/Lycaon37)

</div>

<details open="open">
<summary>Table of Contents</summary>

- [About](#about)
  - [Built With](#built-with)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Roadmap](#roadmap)
- [Support](#support)
- [Contributing](#contributing)
- [Authors \& contributors](#authors--contributors)
- [Security](#security)
- [License](#license)
- [Acknowledgements](#acknowledgements)

</details>

---

## About

This script will download the latest release of any software you give it. Given a bit of basic set up to find the right file, just point Get-Release at the software and it will spit out the latest file you need! This is handy for scripts that require certain files to be present before running, such as ffmpeg.exe for a media processing tool. Rather than hardcoding a URL to a software binary, which can be a problem if the software receives updates down the line, Get-Release dynamically searches a web page for the correct version using regular expressions. This helps ensure that you receive the latest version of your software, every time.

### Built With

- [PowerShell 7](https://github.com/PowerShell/PowerShell) - Scripting Language
- [Visual Studio Code](https://code.visualstudio.com/) - Script Writing
- [PowerShell Extension for Visual Studio Code](https://github.com/PowerShell/vscode-powershell) - Script Writing, Debugging
- [Affinity Photo](https://affinity.serif.com/en-us/photo/) - Media Creation

## Getting Started

### Prerequisites

- A computer running Microsoft Windows.

- Windows PowerShell 5.1 should already be installed on your computer. That will work just fine, but the menu to add folders will work better with PowerShell 7, which has a download link provided above.

- The PowerShell module [PSMenu](https://github.com/Sebazzz/PSMenu). To install PSMenu, open PowerShell and use the following command:

```powershell
Install-Module PSMenu -Scope CurrentUser
```

- (Optional) The PowerShell module [PowerShellForGitHub](https://github.com/microsoft/PowerShellForGitHub). This is used only to access **private** GitHub repositories, and needs a [**Personal Access Token**](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). To install PowerShellForGitHub, open PowerShell and use the following command:

```powershell
Install-Module PowerShellForGitHub -Scope CurrentUser
```

### Installation

Download the latest release from the [Releases] section. Extract the provided .zip file into any folder you like.
Once the release is extracted, please fill out the **ReleaseList-Example.csv**, or create your own CSV file. Much like the example CSV file, the file needs several columns depending on the source of the content.
- GitHub: The file should have five columns: **Owner**, **Repo**, **Asset**, **Private** , and **Name**.
  - Owner: This is the owner of the repository. For example, the owner of the [PowerShell 7](https://github.com/PowerShell/PowerShell) repository is "PowerShell". It's the first field after **github.com** in the URL.
  - Repo: This is the repo name for the repository. It's the second field after **github.com** in the URL.
  - Asset: For a given release, this is the number of the asset the script should download, starting with zero. For example, if you want the **third** release in the GitHub releases list, you should enter **two** here.
  - Private: This should be either **TRUE** or **FALSE**. Use **TRUE** for repositories that are marked as **Private** in GitHub and use **FALSE** for all other repositories. **Private** repositories require the **PowerShellForGitHub** module.
  - Name: This can be whatever you like. It's used for the displayed name in the menu for the script.
- HTTP: The file should have four columns: **URL**, **Pattern**, **Asset**, and **Name**.
  - URL: This is the URL where the file is located.
  - Pattern: A regex pattern to search for the correct file. This is usually different for each site and each software version.
  - Asset: Similarly to the Asset field used for GitHub releases, this indicates which match for the regex filter should be used, starting with zero.
  - Name: Just like the GitHub section, this can be anything you like, and is merely used for the name in the menu.

## Usage

First, make sure that your CSV files are set up correctly following the information above. Then, right click on **Get-Release.ps1** to run the script.
- This will open a menu, which can be navigated using the arrow keys on your keyboard. Use the **space bar** to select an item from the list, and press **enter** to begin the download.
  - You can make multiple selections by checking multiple items using the space bar. If more than one item is selected, the script will download all the selected items one by one.
- Once the files are downloaded, they can be found by default in the **Release Assets** folder within the folder the script is placed in.

## Roadmap

See the [open issues](https://github.com/Lycaon37/Get-Release/issues) for a list of proposed features (and known issues).

- [Top Feature Requests](https://github.com/Lycaon37/Get-Release/issues?q=label%3Aenhancement+is%3Aopen+sort%3Areactions-%2B1-desc) (Add your votes using the 👍 reaction)
- [Top Bugs](https://github.com/Lycaon37/Get-Release/issues?q=is%3Aissue+is%3Aopen+label%3Abug+sort%3Areactions-%2B1-desc) (Add your votes using the 👍 reaction)
- [Newest Bugs](https://github.com/Lycaon37/Get-Release/issues?q=is%3Aopen+is%3Aissue+label%3Abug)

## Support

Reach out to the maintainer at one of the following places:

- [GitHub issues](https://github.com/Lycaon37/Get-Release/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+)
- Contact options listed on [this GitHub profile](https://github.com/Lycaon37)

## Contributing

First off, thanks for taking the time to contribute! Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make will benefit everybody else and are **greatly appreciated**.


Please read [our contribution guidelines](docs/CONTRIBUTING.md), and thank you for being involved!

## Authors & contributors

The original setup of this repository is by [Lycaon](https://github.com/Lycaon37).

For a full list of all authors and contributors, see [the contributors page](https://github.com/Lycaon37/Get-Release/contributors).

## Security

Get-Release follows good practices of security, but 100% security cannot be assured.
Get-Release is provided **"as is"** without any **warranty**. Use at your own risk.

## License

This project is licensed under the **MIT license**.

See [LICENSE](LICENSE) for more information.

## Acknowledgements

- Download by ertyferlw from the [Noun Project](https://thenounproject.com/browse/icons/term/download/) - Icon for logo.
- [Learn PowerShell in a Month of Lunches](https://www.manning.com/books/learn-powershell-in-a-month-of-lunches), by Travis Plunk, James Petty, Tyler Leonhardt, Don Jones, and Jeffery Hicks - Main resource for learning PowerShell.
- [The Amazing GitHub Template](https://github.com/dec0dOS/amazing-github-template), which was used to create this documentation.