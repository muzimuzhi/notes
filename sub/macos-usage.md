# macOS Usage

## macOS Shortcuts

| Key                    | Function                                   |
| ---------------------- | ------------------------------------------ |
| cmd + ` (grave accent) | switch between windows of a same program   |

Shortcut List
 * [Mac keyboard shortcuts](https://support.apple.com/en-us/HT201236) - support.apple.com
 * [Mac OS X Finder Keyboard Shortcuts](https://www.dummies.com/computers/macs/macbook/mac-os-x-finder-keyboard-shortcuts/) - dummies.com

<!-- # bash -->
<!-- # zsh -->
## BSD Bash/Zsh

- Display disk usage statistics sorted by human readable numbers
  ```bash
  # see "brew info dust"
  dust -d1

  # use GNU sort which supports "-h" option, "brew info coreutils"
  $ du -hd 1 | gsort -h
  ```
  https://serverfault.com/a/156648

- Open man page in new terminal window
  `open x-man-page://<name>`
  https://scriptingosx.com/2017/04/on-viewing-man-pages/

- `zip` and `unzip`
    ```bash
    # dry run, list files
    unzip -l file.zip

    # unzip specific file
    unzip file.zip path/to/file.txt     # this will create "./path/to/file.txt"

    # unzip specific file and drop directory structures in archive
    unzip -j file.zip path/to/file.txt  # this will create "./file.txt"
    ```

- Remove duplicates in zsh history ([ref](https://qr.ae/pNk9yZ))
  ```bash
  cat -n $HISTFILE | sort -t ';' -uk2 | sort -nk1 | cut -f2- > .zsh_short_history
  ```
  problematic with multiline history entries

- Find the source and definition of a function or command
  ```shell
  # locate the source
  whence -v function_name # or type function_name
  # print the definition
  whence -f function_name # or type -f function_name
  ```
  both are shell builtins
  Examples
  ```
  $ type l
  l is an alias for ls -lah
  $ type -f azure_prompt_info
  azure_prompt_info () {
    return 1
  }
  ```
  https://superuser.com/a/1018289


### Zsh

- https://zsh.sourceforge.io/
- repo https://sourceforge.net/projects/zsh/
  github mirror https://github.com/zsh-users/zsh/
  (see intro https://zsh.sourceforge.io/Arc/git.html)
- `which`
  ```shell
  $ which pdftex
  /Library/TeX/texbin/pdftex

  # print symlink free path as well
  $ which -s pdftex
  /Library/TeX/texbin/pdftex -> /usr/local/texlive/2025basic/bin/universal-darwin/pdftex

  # show steps in the resolution of symlinks
  $ which -S pdftex
  /Library/TeX/texbin/pdftex -> /Library/TeX/Distributions/Programs/texbin/pdftex -> ... ->
  /Library/TeX/Distributions/.FactoryDefaults/TeXLive-2025-Basic/Contents/Programs/../../../../../../../usr/local/texlive/2025basic/bin/universal-darwin/pdftex
  ```

## GNU CLI Tools
* Show dependencies as a tree: `brew deps --tree <formula>`

| Name    | Homebrew formula    |
| ------- | ------------------- |
| `ggrep` | `brew info grep`    |
| `gsed`  | `brew info gnu-sed` |
| `gsort` | `brew info coreutils` |


## CLI Tricks

- Skip "unidentified developer" prompt
  `xattr -dr com.apple.quarantine /Applications/texstudio.app`
  https://apple.stackexchange.com/a/202172

## Homebrew

### `brew` CLI program

https://docs.brew.sh/Manpage

- Display local location of Homebrew itself or one of cloned tap
  https://docs.brew.sh/Manpage#--repository---repo-tap-
  `brew [--repository|--repo] [OWNER/REPO]`
  ```bash
  # /usr/local/Homebrew
  cd $(brew --repository)

  # tap OWNER/REPO is located in $(brew --repo)/Library/Taps/OWNER/homebrew-REPO
  brew --repo homebrew/services
  brew --repo dart-lang/dart
  ```

- Show (installed) dependents of a formula
  https://docs.brew.sh/Manpage#uses-options-formula-
  `brew uses --recursive --installed FORMULA`
  saw in https://stackoverflow.com/a/66142860

- Show dependencies of a formula
  https://docs.brew.sh/Manpage#deps-options-formulacask-
  `brew deps FORMULA`

- List non-dependency installed formulae
  https://docs.brew.sh/Manpage#leaves---installed-on-request---installed-as-dependency
  `brew leaves`

- List formulae and casks in a tap
  https://docs.brew.sh/Manpage#tap-info---installed---json-tap-
  ```bash
  brew tap-info --json TAP | jq -r '.[] | (.formula_names[], .cask_tokens[])'
  ```
  saw in https://apple.stackexchange.com/a/392993

- Bump a formula or cask
  https://docs.brew.sh/Manpage#bump-formula-pr-options-formula
  https://docs.brew.sh/Manpage#bump-cask-pr-options-cask
  ```bash
  brew bump-formula-pr --version=VERSION [--write-only] FORMULA
  brew bump-cask-pr --version=VERSION [--write-only] cask
  ```
  Application: my `workflow_dispatch`-triggerable GitHub Action workflow [`brew-bump-pr.yml`][brew-bump-pr.yml].

  [brew-bump-pr.yml]: https://github.com/muzimuzhi/hello-github-actions/blob/main/.github/workflows/brew-bump-pr.yml

### Writing formulae and casks

- Adding formula or cask to Homebrew
  https://docs.brew.sh/Adding-Software-to-Homebrew
- Formula Cookbook
  https://docs.brew.sh/Formula-Cookbook
- Cask Cookbook
  https://docs.brew.sh/Cask-Cookbook

- [`version` Stanza Details](https://github.com/Homebrew/homebrew-cask/blob/master/doc/cask_language_reference/stanzas/version.md)
  - Example: [Homebrew/homebrew-cask-fonts#2082](https://github.com/Homebrew/homebrew-cask-fonts/issues/2082)


## Where do PATHs come from

1. `/etc/profiles`
1. `/usr/libexec/path_helper -s`
1. `/etc/paths` + file lines under `/etc/paths.d`
1. shell profiles (e.g., [zsh startup files](http://zsh.sourceforge.net/Doc/Release/Files.html#Startup_002fShutdown-Files))
see [ref](https://scriptingosx.com/2017/05/where-paths-come-from/)
