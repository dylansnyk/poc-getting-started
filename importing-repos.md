## Importing Repos to Snyk

### Integrate with your Source Control Manager (SCM)

Is your SCM (e.g. GitHub), self-hosted within a private network? If yes, you will need the [Snyk Broker](https://docs.snyk.io/snyk-admin/snyk-broker) to connect. Please work with your Solutions Engineer to set this up.

If your SCM is cloud-based, click on the corresponding tile on the integrations page. For GitHub users, please choose the "GitHub Enterprise" option, more info on why [here](https://docs.snyk.io/integrations/git-repository-scm-integrations/introduction-to-git-repository-integrations/using-github-or-github-enterprise-integration).

<img width="600" alt="scm selection" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/scm-selection.png">

For each integration (except BitBucket Cloud App), you'll be required to generate a token. The required scope for each token is documented here:
* [GitHub](https://docs.snyk.io/integrations/git-repository-scm-integrations/github-enterprise-integration#setting-up-a-github-enterprise-integration)
* [GitLab](https://docs.snyk.io/integrations/git-repository-scm-integrations/gitlab-integration#set-up-gitlab-integration)
* [BitBucket](https://docs.snyk.io/integrations/git-repository-scm-integrations/bitbucket-data-center-server-integration#setting-up-a-bitbucket-dc-server-integration)
* [Azure Repos](https://docs.snyk.io/integrations/git-repository-scm-integrations/azure-repositories-integration#setting-up-an-azure-repository-integration)

### Adjust Settings

Review the integration settings for you SCM. I typically recommend disabling all of the automated features, you can always come back and enable them when the team is ready to test them. 

Navigate to Settings > GitHub Enterprise (or your SCM), and disable these settings that will create PRs on imported repos and decorate PRs with Snyk checks:
* Automatic fix PRs
* Pull request status checks (open source and code)
* Update Dockerfile base images

Enable Snyk Code. Navigate to Settings > Snyk Code, enable and save changes

### Import Repositories 

Navigate to the Integrations page and select your SCM. If using GitHub, select the "GitHub Enterprise" option.

Select which repositories you'd like to import. For the purposes of the POC, select repos that will be a representative sample of the repos across your organization. You will want to validate the quality of results across languages, app type, and repo size.

Click "Add selected Repositories" in the top right when ready. The import settings at the bottom can be left to their default values.

<img width="600" alt="select repos" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/add-selected-repos.png">

The results will begin to stream in. The process may take a few minutes based on the number of repositories being imported. Once the import completes, you can review the import log in the top right corner for any import failures. Some import failures are expected, common failures are documented [here](https://support.snyk.io/hc/en-us/articles/360001373118-Project-import-errors).

<img width="400" alt="view import log" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/view-import-log.png">
<img width="400" alt="import log" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/import-log.png">

<br><br>
Now that repositories have been imported, you are good to start digging into results and testing different workflows!
<br><br>
Have a lot of repositories you want to import? Thinking ahead to how to do this at scale? We've thought of that too: check out [snyk-api-import](https://github.com/snyk-tech-services/snyk-api-import) which can help automate the import process at scale
