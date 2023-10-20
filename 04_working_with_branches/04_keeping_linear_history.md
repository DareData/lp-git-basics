# Best Practises: Keeping a linear git history 🌳

Linear Git history is a clean and manageable way to understand the lifecycle of a project by ensuring that commits have a consistent and clear flow, making it easier for team members to follow the progression of the project. This can be especially crucial for debugging and for understanding the evolution of project code. [In here](https://www.bitsnbites.eu/a-tidy-linear-git-history/), you will find a detailed blog on why this is so important and how to achieve it.

Let us also explore some of the key points here:

### Benefits of Keeping a Linear History 🧼

- **Easier Troubleshooting**: Simplifies the process of finding and resolving bugs or errors in the codebase.
- **Clearer Understanding**: Offers a straightforward history, helping team members and new joiners comprehend the project evolution easily.
- **Smooth Merges**: Reduces complex merge conflicts, ensuring a smoother, more efficient workflow.

### Strategies for Maintaining a Linear History 🧽

1. Avoid Merge Commits:

Use rebase to integrate changes from one branch into another, rather than creating a merge commit.

`git rebase <branch-name>`

2. Interactive Rebase:

Use interactive rebase to tidy up your commits and modify history, making the project's evolution more transparent.

`git rebase -i <commit-hash>`

3. Squash Commits:

Combine several commit messages into one, providing a clean, understandable history.

`git rebase -i HEAD~<number-of-commits>`

4. Force Push Carefully:

After rebasing, you may need to force push your changes to update the remote branch.

`git push origin <branch-name> --force`

> 🚨 Note: Use force push cautiously to avoid overwriting changes unintentionally.

🚨 Important Note 🚨: In general, for large projects, you want to avoid rebasing too much, a kilometrical history for the main branch might become a nightmare. A better strategy is to keep each solution at a branch and then squash before merging into the main branch. See more [here](https://www.git-tower.com/learn/git/faq/git-squash).


## Branch Workflow 🔁

In general, for most projects, the following structure is a well-established workflow that ensures consistency when dealing with large projects. 

- **Main Branch**: The main project where everything is stable and finalized. This is the branch that one puts into production.
- **Hotfix Branches**: For urgent fixes.
- **Staging Branch**: A place where all new features, bugfixes and changes are storaged together before official realise to main. The purpose of this branch is to make sure everything works together and test the code in deployment before putting it into production. This branch can be further divided into **develop** and **realease** branches if the project were to be big enough.
- **Feature Branches**: For adding new features.
- **Bugfix Branches**: For fixing issues.


<img src="../images/git_workflow.svg" alt="WindowsVenv" width="800" height="auto">

