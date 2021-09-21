# Buildpack update action

Create pull requests to update Cloud Foundry buildpacks in manifest files.

## Example usage

    on: [push]
    
    jobs:
      buildpack_updates_job:
        runs-on: ee-runner
        name: buildpack updates
        steps:
          - name: Check out the repo
            uses: actions/checkout@v2
          - name: run buildpack-update-action
            uses: springernature/buildpack-update-action@v21
            env:
              GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
              AUTHOR_EMAIL: team-payzilla@springernature.com
              AUTHOR_NAME: buildpack-update-action


## Roadmap

* make a single commit for all buildpacks of a single type in a repository
* improve build time
* make it configurable, see [Dependabot config](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/configuration-options-for-dependency-updates) for ideas
