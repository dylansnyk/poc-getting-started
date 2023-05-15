## Fixing Issues Locally

Here we will look at how we can identify vulnerabilities using the Snyk CLI and IDE plugins

### Install the Snyk CLI
Choose any of the following installation methods:
```
npm install -g snyk
```
```
brew tap snyk/tap
brew install snyk
```
```
curl https://static.snyk.io/cli/latest/snyk-macos -o snyk
chmod +x ./snyk
mv ./snyk /usr/local/bin/
```
More installation methods can be found here: https://github.com/snyk/cli#install-snyk-cli

### Scanning with CLI

Navigate to the root directory of the project you would like test. Each scan type has its own CLI command:

Open Source: `snyk test --all-projects` <br>
Code: `snyk code test` <br>
Container: `snyk container test name_of_image:tag` <br>
IaC: `snyk iac test`

The `test` commands are usful for running the scans locally as a developer, or during CI if you would like to break a build if there issues found. 

### Installing the IDE plugins

For installation, please refer to our [IDE plugin docs](https://docs.snyk.io/integrations/ide-tools).

### Fixing an issue

Try fixing an issue. Either introduce a new issue, or choose an existing that can be fixed.

The feedback for each scan type will be a litle different, here we will look at an example for open source using the CLI and IDE. The arrows highlight where to get thr fix advice for both the CLI and IDE:

<img width="900" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/cli-fix.png">

<img width="900" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/ide-fix.png">

Then, using the fix advice, make the update in the code. You can then trigger a new scan in the IDE, or re-run the `snyk test` command to verify the issue is no longer present.

<img width="800" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/run-ide.gif">

### More CLI info

* [CLI Reference Docs](https://docs.snyk.io/snyk-cli/cli-reference)
* [CLI Cheat Sheet](https://res.cloudinary.com/snyk/image/upload/v1664236143/cheat-sheets/cheat-sheet-snyk-cli-v3.pdf)
