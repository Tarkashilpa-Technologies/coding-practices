# Code versioning
## Git
- Every repo should have bare minimum following branches
    - dev- Stable development code
    - staging- Stable code that's provided to testers (QA). Typically QA build should be created from this branch
    - main- Stable codd that's deployed to production (live) environment. Typically prod builds should be created from this branch
- Depending on specific needs in projects more main branches could be created.
- Every feature that's getting implemented in the project or bug that's getting fixed need to be done in separate branch created from dev branch dedicated for that feature or bug
- Just to make branches more organised and easy to manage, it's good idea to follow some naming convention for branches like feature branch could start with prefix 'feature/' and bug branches could start with prefix 'bug/'.
- More strict naming conventions could be imposed depending on project needs like if projects are using task management software, task id could be used while giving name to the branches.
- Developers should commit as frequent as you can, typically 4 to 5 times a day in your feature branches.
- It's ok to commit the code that's not stable or broken as every feature or bug is fixed on separate branch created dedicated to implement that feature or fix that issue. You are not breaking stable code on dev branch or blocking your team due to broken build.
- Once the bug it completely fixed or feature is satisfactorily implemented and developer has thoroughly unit tested it and satisfied that it's not going to block any other developer in his work if it goes to dev branch, developer should open pull request to dev branch.
- Before makinig pull request developer should make his changes compatible with dev branch, so he should pull the changes from dev branch, resolve any merge conflich if he is getting, unit test merged code again and then create PR. We are against using rebasing the feature or bug branch again with dev, as git rebase modifies git history, which is not good.
- Once pull request is created developer should ask tech leads to verify their work and get their code to merged with dev branch

# Pull Request Verification
- TL should first connect with developer over call and ask him to demonstrate the feature he implemented or bug he fixed
- Then TL should do code review

# Task Management
- Task management software is important for any project, it helps team to focus on priority tasks while lesser priority tasks could be added to task management tool to be picked up later

# CI/ CD
- Developers and TL should plan their work in such a way that they could deliver something valuable every day.
- Defination of delivery is the feature or bug is available in dev branch and defination of valuable is what is delivered could be small but independently is building block of the project.
- Daily pull request merges serves the purpose of countinous integration (CI)
- Deployment pipelines are highly promoted to be written for deploying dev build daily on dev environment from dev branch. Else manually deploying dev build to dev environment serves the purpose of continous delivery (CD)
