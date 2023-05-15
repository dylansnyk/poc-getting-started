## PR Checks

### Enable PR Checks

<p>
Navigate to your SCM integration settings (we are using GitHub here, but it is the same for all supported SCMs)
</p>
  
<img width="1412" alt="Navigate to SCM integration settings" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/github-settings.png?raw=true">

<p>
  
Scroll down until you reach "Snyk PR Status Checks". Here you can enable checks for both Open Source and Code and define for fail conditions for each. Remember to hit save, and apply to all overriden projects if you've already imported your repositories.
</p>

<img width="1344" alt="PR Check settings" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/pr-check-settings.png">

### Create a test PR

Once PR Checks are enabled, you should begin to see future PRs decorated with three additional Snyk checks: <br>
* code/snyk: Snyk Code vulnerabilities
* license/snyk: Open Source license issues
* security/snyk: Open Source vulnerabilities

Note: in the screenshot below, the CircleCI checks are unrelated to the Snyk PR Checks

<img width="600" alt="image" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/github-checks.png">

<p>
  
Try introducing a vulnerability in the PR so that you can walk through the situation where a check fails. From the PR, clicking on the details of any failed check will present the list of issues that have been introduced in the PR.
  
You can click into the full details of the issue to better understand the vulnerability, and get any remediation advice that is provided. In the situation where you need to force the check to pass for whatever reason, you can click "Mark as successful in SCM" in the top right. This button is only available to Org Admins, for Org Collaborators this option is grayed out. More on Snyk RBAC [here](https://docs.snyk.io/snyk-admin/manage-users-and-permissions/member-roles).
</p>

<img width="1352" alt="Screen Shot 2023-05-12 at 12 29 19 PM" src="https://github.com/dylansnyk/poc-getting-started/blob/main/assets/pr-check-example.png">

Then try fixing the issue in a follow up commit, push the commit and verify that the Snyk checks re-run and are passing.
