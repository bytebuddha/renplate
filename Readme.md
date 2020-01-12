# Renplate: RenPy Project template

Template repository for an open source RenPy game hosted on github.
includes:

  - [x] Ready to develop RenPy game template
  - [x] Automatic labeling of Issues and Pull Requests.
  - [x] Automatic linting of PR requests
  - [x] Github issue commands to perform action common actions
    (deploying, development release's, initialization)

## Automatically labeling Issues
  When a new issue is made github will use Naturalclar/issue-action@v1.0.0 to
  automatically apply labels to them. Using the configuration in
  `.github/workflows/openIssue.yml`.

## Automatically labeling Pull Requests
  This uses actions/labeler@v2 to automatically label received Pull Requests.
  This maps labels to the Pull Requests changed file's using the configuration
  in `.github/labeler.yml`

## Issue Comment Commands
  Github action commands can be run by commenting on a issue with the text
  /$COMMAND e.g. /initialize to run the initialize command. This uses repository
  dispatch handlers to handle each command.

  - ##### initialize
      This command should be run when first uploading to Github it ensures
      the expected labels exist on the repository.
  - ##### deploy
    This command will build the markdown Guide and Design books and force
    push to the gh-pages branch for publishing.

  - ##### release
    This command will build the renpy game and push a new release to github
    release's
