# Renplate: RenPy Project template

[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)
[![](https://github.com/Bytebuddha/renplate/workflows/.github/workflows/deployCommand.yml/badge.svg)](https://github.com/bytebuddha/renplate/actions)
[![](https://github.com/Bytebuddha/renplate/workflows/.github/workflows/releaseCommand.yml/badge.svg)](https://github.com/bytebuddha/renplate/actions)
[![GitHub version](https://badge.fury.io/gh/Bytebuddha%2Frenplate.svg)](https://github.com/Bytebuddha/replate)
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)


Template repository for open source RenPy game's hosted on Github. Includes many
tools including Github Actions to distribute code on demand.

###### Github
  - [x] Ready to develop RenPy game template
  - [x] Automatic labeling of Issues and Pull Requests.
  - [x] Automatic linting of PR requests
  - [x] Github issue commands to perform common actions.

###### Supported Build Platforms
  - [x] Windows 64 bit
  - [x] Windows 32 bit
  - [x] Linux
  - [x] macOS
  - [x] Web
  - [ ] Android
  - [ ] IOS

## Automatically labeling Issues
  When a new issue is made github will use `Naturalclar/issue-action@v1.0.0` to
  automatically apply labels to them. Using the configuration in
  `.github/workflows/openIssue.yml` This looks for strings in the issue text and
  apply's labels according to the config file.

## Automatically labeling Pull Requests
  This uses `actions/labeler@v2` to automatically label received pull requests
  when they are created. This maps labels to the pull requests changed file's
  using the configuration in `.github/labeler.yml`

## Documentation

  Renplate includes 2 book's written in markdown and compiled with
  [mdBook](https://github.com/rust-lang/mdBook) to generate documentation.
  The Guide book is for user interface description and specifing game
  mechanics, and the Design book is for descripting the storyline and characters.

  When build both books will be built into the `docs/guide/` and `docs/design/`
  respectivly. Then the whole `docs/` directory will be written to the root
  of the gh-pages branch for publishing. To use images in either of these books
  place them in the `docs/img/` directory and reference them in markdown like
  `images/file_name.ext`

  Example documentation is available [**here**](https://shadowpixie.github.io/renplate/).

## Issue Comment Commands
  Github action commands can be run by commenting on a issue with the text
  /$COMMAND e.g. /initialize to run the initialize command. This uses repository
  dispatch handlers to handle each command, and requires `admin` privilges. This
  implementation is a thin wrapper around `peter-evans/slash-command-dispatch@v1`
  and commands can be run by commenting on any issue/pull request.

  **Note** When these commands are run, an emoji reaction is put on the comment
  to symbolize it recognizing a command not the actual result.


  - ##### initialize
      This command should be run when first uploading to Github it ensures
      the expected labels exist on the repository.

  - ##### deploy
    This command will build the markdown Guide and Design books and force
    push to the gh-pages branch for publishing.

  - ##### release
    This command will build the renpy game and push a new release to github
    release's. If an argument is given then it is assumed this is a versioned
    release and the tag name will be set to the args given.
