## Importing Repos to Snyk

### Integrate with your Source Control Manager (SCM)

Is your SCM (e.g. GitHub), self-hosted within a private network? If yes, you will need the [Snyk Broker](https://docs.snyk.io/snyk-admin/snyk-broker) to connect. Please work with your Solutions Engineer to set this up.

If your SCM is cloud-based, click on the corresponding tile on the integrations page. For GitHub users, please choose the "GitHub Enterprise" option, more info on why [here](https://docs.snyk.io/integrations/git-repository-scm-integrations/introduction-to-git-repository-integrations/using-github-or-github-enterprise-integration).

<img width="1458" alt="Screen Shot 2023-05-12 at 1 10 54 PM" src="https://github.com/dylansnyk/poc-getting-started/assets/94395157/be626692-241c-479c-bdfb-9d34fd65e836">

For each integration (except BitBucket Cloud App), you'll be required to generate a token. The required scope for each token is documented here:
* [GitHub](https://docs.snyk.io/integrations/git-repository-scm-integrations/github-enterprise-integration#setting-up-a-github-enterprise-integration)
* [GitLab](https://docs.snyk.io/integrations/git-repository-scm-integrations/gitlab-integration#set-up-gitlab-integration)
* [BitBucket](https://docs.snyk.io/integrations/git-repository-scm-integrations/bitbucket-data-center-server-integration#setting-up-a-bitbucket-dc-server-integration)
* [Azure Repos](https://docs.snyk.io/integrations/git-repository-scm-integrations/azure-repositories-integration#setting-up-an-azure-repository-integration)

### Adjust Settings

Disable Automation (optional): Disable PR checks, auto fix-PRs as a best practice

Enable Snyk Code.

### Import Repositories 

Select which repositories to import and click Add Selected Repositories.

Watch for failures in import log.

Have a lot of repositories you want to import? Thinking ahead to how to do this at scale? We've thought of that too: check out [snyk-api-import](https://github.com/snyk-tech-services/snyk-api-import) which can help automate the import process at scale
