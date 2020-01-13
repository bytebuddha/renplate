This file will eventually explains how to install this into github
and setup the actions for building and linting.

#### Local Machine

1. Update The LICENSE.md file.

1. Modify the source of `games/scripts/core/options.rs` and replace
   `build.name` with the correct file name.
1. Modify the source of `.github/workflows/releaseCommand.yml` replace
   `renplate` with your desired `buid.name`.


#### Github

1. Upload to a github repository

1. Enable github pages with document root set to the gh-pages branch in
   repository settings.
1. Run the /initialize command in an issue comment. See [README.md](./README.md)
1. Create a new personal access token for this repository this will be used when
   deploying the docs, add this token as a repository secret named ACCESS_TOKEN.
1. Run the `/deploy` command to generate initial documention
1. Run the `/release` command to generate initial development release
