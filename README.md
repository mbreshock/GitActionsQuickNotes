# Continuous Integrations with GitHub Actions

**This is a quickstart guide on how to add continuous integration to your project with GitHub Actions.**\
GitHub Actions allows you to add workflows to your repository which make continuous integration easy.\
\
*Resources for more information will be listed at the end of this guide.*

## Start off at the homepage of your GitHub Repository
I will be using my dummy repo 'randodata' as an example.

![Randodata Repo](/images/github_repo.png)

## Click on the Actions Tab on the Top of the Page
![GitActions Tab](/images/actions_tab.png)

## GitHub Actions Tab
For a repository without any workflows, this tab will suggest workflow templates to add to your repo.\
**The first one listed is recommended based on the contents of your repository.**

![Suggested Workflow](/images/suggest_workflow.png)

![CI Workflows](/images/workflow_templates.png)

## Choose a Template
For this example I chose the popular R package CI workflow.\
*If this repository was actually an R package, this template would've been the first suggested*
![R Package Template](/images/R_package_template.png) \
Click on the 'Set up this workflow' button to get started!

## Specifics for R Package Template
I ran into an issue when using this template for my R package project.\
**'ACTIONS_ALLOW_UNSECURE_COMMANDS: 'true'** may need to be added to each named step in the R.yml workflow file to work properly.\
If your workflow doesn't run because of the 'set-env' command, edit the 'steps:' section of your R.yml file to look like this:
![Edited R.yml](/images/yml_edits.png)\
Hit commit once you're done!

## Actions Tab with Workflow
After committing your workflow files you should see the workflow reflected in the actions tab.\
There you can see if your repository passes your workflow when any changes are made.\
Generally, a continuous integration workflow will check your scripts with every commit/pull.\
Since the repo used here is not actually an R package, it failed to pass the R package CI workflow. 
![Workflow Error](/images/R_workflow_error.png)

## Workflow Error Details
If an error occurs in your workflow, GitHub Actions will identify where exactly the error ocurred and will usually give you suggestions on how to fix it. 
![Error Details](/images/r_workflow_error_details.png)\
*Note: You can see on the left panel here that this workflow checks your code for R versions 3.5 and 3.6. You can add versions or change them in the R.yml file!*

## Resources:
To learn more about continuous integration and how to use workflows with GitHub Actions check out:
- https://docs.github.com/en/free-pro-team@latest/actions
- https://carriewright11.github.io/Travis_CI_not_pkg_tutorial/Index.html
- https://travis-ci.org/

### Thank you for reading, I hope this was helpful!

