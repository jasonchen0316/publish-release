## publish-release

```
npm install --save publish-release
npm install -g publish-release # CLI
```

### CLI Usage

The CLI looks in 2 places for configuration: arguments passed, and a `publishRelease` object (see the [API usage](#api-usage) below for the format) in the `package.json`. If it can't find the info it needs from those places, it will run a wizard. This means that you can create a release just by running `publish-release`, and following the wizard.

```
$ publish-release --help
Usage: publish-release {options}

Options:

  --token [token]                 GitHub oAuth token.

  --owner [owner]                 GitHub owner of the repository.
                                  Defaults to parsing repository field in
                                  the project's package.json

  --repo [repo]                   GitHub repository name.
                                  Defaults to parsing repository field in
                                  the project's package.json

  --tag [tag]                     Git tag to base the release off of.
                                  Defaults to latest tag.

  --name [name]                   Name of the new release.
                                  Defaults to the name field in the
                                  package.json, plus the git tag.

  --notes [notes]                 Notes to add to release, written in Markdown.
                                  Defaults to opening the $EDITOR.

  --template [path to template]   Markdown file to open for editing notes.
                                  Will open the template in $EDITOR.

  --draft                         Pass this flag to set the release as a draft.

  --prerelease                    Pass this flag to set the release as a
                                  prerelease.

  --reuseRelease                  Pass this flag if you don't want the plugin to create a new release if one already
                                  exists for the given tag.

  --reuseDraftOnly                Pass this flag if you only want to reuse a release if it's a draft. It prevents
                                  you from editing already published releases.

  --skipAssetChecks               Don't check if assets exist or not. False by default.

  --assets [files]                Comma-separated list of filenames.
                                  Ex: --assets foo.txt,bar.zip

  --apiUrl [apiurl]               Use a custom API URL to connect to GitHub Enterprise instead of github.com.
                                  Defaults to "https://api.github.com"
                                  Ex: --apiUrl "https://myGHEserver/api/v3"

  --target_commitish [commitish]  Specifies the commitish value that determines where the Git tag is created from. Can be any branch or commit SHA.
                                  Defaults to the default branch of the repository.
                                  Ex: --target_commitish "master"
```

# publish-release
