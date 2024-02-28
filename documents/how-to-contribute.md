# How to Contribute

## General recommendations for commits, pull requests and comments

- The english is imperative.

  > Replace word **you** with **we** in the comments. Remove the subject from the sentences. Frame comments as requests, not commands.

- Use [Conventional Commits](https://www.conventionalcommits.org/) for commit messages. Commits formatted in this way will be used to generate the changelog.

  > Conventional commit message is in the following format:
  >
  > ```
  > <type>(optional scope): <description>
  >
  > <body>
  > ```
  >
  > A _type_ is one of the following:
  >
  > - `build`: Changes that affect the build system or external dependencies (changes to Yarn, Webpack config, project.json, ESLint, Jest, etc.)
  > - `ci`: Changes to our CI configuration files and scripts (mostly changes in .github folder)
  > - `docs`: Documentation only changes
  > - `feat`: A new production code feature
  > - `fix`: A bug fix in production code
  > - `perf`: A code change that improves app runtime performance
  > - `refactor`: A code change that neither fixes a bug nor adds a feature
  > - `revert`: If the commit reverts a previous commit, it should begin with `revert:`, followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the \<hash\> is the SHA of the commit being reverted.
  > - `hotfix`: A change that needs to be released immediately in order to fix a broken production environment.
  > - `style`: Changes that do not affect the meaning of the code (white-space, formatting, etc.)
  > - `test`: Adding missing tests or correcting existing tests
  > - `chore`: Changes that do not fit into any of the categories above (moving files, removing outdated files, etc.)

- Approve your own pull request.
  > Approval means, you've checked your own code before submitting it to the others.
- Choose meaningful name for your Pull Requests and branches.
  > Always remove nonsensical description from PR or add a meaningful one. E.g.: Link to fix version, short description in your own words, etc. If you do not want your PR merged, prefix name with `[DNM]` and add task to the PR which you will resolve after the PR is intended to be merged.
- Write code for your collaborators.
  > Write self explanatory code. If your code is hard to understand, or tricky, try to rewrite it first before explaining it in comments. Your goal is to write code for your colleagues, not for computers. Computers will run any messy code just perfectly.
- Submitted code is fully reviewed and tested locally.
  > Make sure at least one developer approved your PR.
- Code is tested properly.
  > For any new code, tests are obligatory. For any older code, please use your common sense or ask other collaborators.
- Code follows the recommended style guides
  > All files must be pushed to the repository without any linting errors. This includes ESLint and Prettier, extensions for vscode are available in the vscode marketplace,
  that way you will be able to see the issues while writing code.
- Keep visuals same or better.
- Pull request is not a seal.
  > When code is merged it doesn't mean it is untouchable. So when you are editing older code and see deviation from recommendations or something that can be done better, do it. Also when you are reviewing pull request, and seeing old non edit code that is bad, call it out in the comments.

## Branching

Preferred way on how to keep the code in PRs in check is keeping the git history clean and not pollute it with merge commits (this makes git history unreadable and it is very hard to keep track of a commit where a bug occured, thus resulting in taking more time to fix). [Rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) is a preffered approach.

Each developer is responsible for the state of his PR and thus, when a base branch gets updated, the developer is in charge of rebasing onto it so that their commits are applied on top of all of the base branch commits.

Please do not pollute the history with multiple commits, use `git commit --amend` instead (and `git push --force` to your forks' branch). Multiple commits can be part of a PR, if it makes sense to split them semantically.

## Code formatting

Code formatting is kept in check via prettier and a husky pre-commit hook, that will edit commit staged files to align with the style settings.

Using prettier in vscode is advisable (also enable prettify on file save) - for example [Prettier for VSCode](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode).

## Post scriptum

Remember, nobody is perfect and we all learn, so don't hesitate to ask or propose a different approach, something that will make the whole process better and/or more meaningful.