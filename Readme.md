# A stupidly insecure API 😈

This repo is a fork of [DevSlop/Pixi](https://github.com/DevSlop/Pixi) which is a ridiculously insecure API.  The intention with this repo is to show how code scanning reusable workflows can help to integrate multiple scanning tools.

Aside from an insecure API, there is also a Dockerfile which references a super old build.  There's also a misconfigured Terraform document with lots of IaC vulnerabilities. 


# Learning
- Blog: [Application security orchestration with GitHub Advanced Security](https://github.blog/2023-03-08-application-security-orchestration-with-github-advanced-security/)
- Video: [GitHub Learning Journey: AppSec orchestration essentials with GitHub code scanning & GitHub Actions](https://www.youtube.com/watch?v=wjVMNAHH4Qc)


# Viewing results

 1. [fork this repo](https://github.com/octodemo/orchestration-demo/fork)
 1. enable Actions (choose the Actions tab and agree to enable them)
     <img width="538" alt="image" src="https://github.com/octodemo/orchestration-demo/assets/1760475/de92bfae-24fe-4951-8c17-8a23c1253800"> 
 1. for each workflow now listed on the Actions tab, hit the `Enable workflow` button
     <img width="653" alt="image" src="https://github.com/octodemo/orchestration-demo/assets/1760475/30a77df6-205f-435e-a542-ccd09ea7446e">
 1. for 42 crunch api security integration
    - create free account at https://platform.42crunch.com/register
    - follow these steps to configure API_TOKEN https://docs.42crunch.com/latest/content/tasks/integrate_github_actions.htm
    - Set the repository secret `_42CRUNCH_TOKEN` with the api token value (this will be used by `.github/workflows/42Crunch.yml`)
 1. trigger scan by pushing any change to main branch and triggering all the actions to run
 1. review the `Security` tab
 1. Bonus: enable Depenabot ( Settings -> Code security and analysis) by choosing enable `Dependabot security updates` (this will enable the dependency graph and Dependabot alerts as well! )
    - watch some pull requests for vulnerable dependency fixes roll in as well as the above actions being run against those PRs!
