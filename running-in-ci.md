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
