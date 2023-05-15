## Running Snyk Locally



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

### Scanning code locally

Navigate to the root directory of the project you would like test. Each scan type has its own CLI command:

Open Source: `snyk test --all-projects` <br>
Code: `snyk code test` <br>
Container: `snyk container test name_of_image:tag` <br>
IaC: `snyk iac test`

The `test` commands are usful for running the scans locally as a developer, or during CI if you would like to break a build if there issues found. 

### Fixing an issue

Try fixing an issue. The feedback for each scan type will be a little different, here we will look at an example for open source.



### Pushing results to the Snyk UI

If you would like to push the results to the Snyk UI for reporting and recurring monitoring. The typical use case here would be to automate in CI on commits to the main branch, that way Snyk is always in sync with the latest version of the repository.

The following commands should be used for each scan type:

Open Source: `snyk monitor --all-projects` <br>
Code: in development, beta coming soon <br>
Container: `snyk container monitor name_of_image:tag` <br>
IaC: `snyk iac test --report`

<img width="600" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/monitor.png">

For `snyk monitor`, there are some additional arguments that can be added to adjust the default naming in the Snyk UI: 
<br>

<img width="600" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/monitor-args.png">

### More CLI info

* [CLI Reference Docs](https://docs.snyk.io/snyk-cli/cli-reference)
* [CLI Cheat Sheet](https://res.cloudinary.com/snyk/image/upload/v1664236143/cheat-sheets/cheat-sheet-snyk-cli-v3.pdf)
