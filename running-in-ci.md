## Running Snyk in CI

There are a few key use cases for running Snyk in CI:
* Gating builds in CI
* Pushing results to the Snyk UI
* Generating an HTML report as a build artifact

That said using [Snyk's APIs](https://docs.snyk.io/snyk-api-info) and the [Snyk CLI](https://docs.snyk.io/snyk-cli), Snyk can satisfy a wide range of workflows. Work with your Snyk Solutions Engineer if you have any custom workflows you'd like to build with Snyk.

To run Snyk in you CI pipeline, you can either use the [native plugins](https://docs.snyk.io/integrations/ci-cd-integrations) which are easiest to get up and running, or you can use install the Snyk CLI as part of your pipeline script and use the CLI directly. This method has the advantage of completely aligning with the CLI experience so you can easily troubleshoot and configure.

Note: If you'd like to implement PR Checks that only fail on newly added vulnerabilities, please use the [Snyk PR Checks](https://github.com/dylansnyk/poc-getting-started/blob/main/pr-checks.md). Full docs [here](https://docs.snyk.io/scan-application-code/run-pr-checks).

### Gating builds in CI using Snyk

Please review the [Snyk CI/CD Integration deployment and strategies](https://docs.snyk.io/integrations/ci-cd-integrations/snyk-ci-cd-integration-deployment-and-strategies) in our docs.

### Pushing results to the Snyk UI

Using the Snyk CLI (and our CI plugins), you can push the results to the Snyk UI for reporting and recurring monitoring. 

The typical use case here would be to automate running these commands in CI on commits to the main branch, that way Snyk is always in sync with the latest version of the repository.

The following commands should be used for each scan type:

Open Source: `snyk monitor --all-projects` <br>
Code: in development, beta coming soon <br>
Container: `snyk container monitor name_of_image:tag` <br>
IaC: `snyk iac test --report`

<img width="600" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/monitor.png">

For `snyk monitor`, there are some additional arguments that can be added to adjust the default naming in the Snyk UI: 
<br>

<img width="600" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/monitor-args.png">
