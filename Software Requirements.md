# Download/Install required software

This needs to be an entirely separate document

- Git
  - MacOS (Homebrew)

    ```shell
    brew install git
    ```

  - Windows (Winget)

    ```shell
    winget install --id Git.Git --override ""
    ```

- Github
  - MacOS (Homebrew)

    ```shell
    brew install gh
    ```

  - Windows(Winget)

    ```shell
    winget install -e --id GitHub.cli
    ```

- [Visual Studio Code](https://code.visualstudio.com/download)
  
> :bulb: **FAQ**: What is Homebrew? What is Winget?
>
> Winget and Homebrew are package managers that are used to download, install, and manage applications and software versions. Because packages are verified before release, this is a safe way to ensure you are downloading the correct packages and versions.

> :bulb: **FAQ**: What if I don't have these?
>
> Winget comes pre-installed on Windows, but Homebrew (for MacOS) needs to be installed separately
>
> For Windows:
>
> - Check if you have winget by running `winget -v` on Command Prompt. If it doesn't return a version number, then talk to @eknorr. He will help you.
> 
> For MacOS:
>
> - Run the following command in a terminal window: `curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh`