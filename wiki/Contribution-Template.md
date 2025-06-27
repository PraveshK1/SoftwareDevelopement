


```
 # INTEGRATION TEMPLATE CONTRIBUTING.MD V1.1  
  
 ## Contributing  
 Thank you for your interest in contributing to our repo!  
 
 ## Process for contributing (process-for-contributing)  
 - Read through the software documentation and understand the underlying software structure.  
 - Understand the teams process, and follow all the relevant design and review steps before making code changes  
 
 ## Dos and Don’ts (dos-and-donts)  
 - First make the required changes using the teams development process before making any code changes.  
 
 ## Process for contributing  
 ### Step 1: Request Access  
 You must be granted access  
 
 #### HOW TO HANDLE REQUESTING ACCESS:  
 - A new step (Request Access) TODO: Add Link to Request Access Docs  
 - A new step (Request Access) TODO: Add other Systems and processes to request Access  
 
 ### Step 2: Clone the repo  
     git clone (Add Link to Sample Repo)  
 
 ### Step 3: Create a feature branch based on main  
 #### Features  
 Please use the following naming convention to create your new branch.  
 Example:  
 feature/authenticationMiddleware  
 ##### Create your branch  
     git checkout -b feature/my-new-feature -f origin/main  
 
 ### New Hotfixes  
 Please use the following naming convention:  
 hotfix/ SHORT-DESCRIPTION  
 Example:  
 hotfix/authenticationMiddleware  
 ##### Create your branch  
     git checkout -b hotfix/my-new-hotfix -f origin/main  
 
 ### Step 4: Make your changes and commit  
 Make your changes and add:  
     git add files-changed 

 Commit your changes:  
  
 The [conventional commits specification](https://www.conventionalcommits.org/en/v1.0.0/#/)  
 is the required convention for automatic versioning using commit messages.  
 The specification defines a set of rules for creating explicit commit histories.  
  
 The commit message should be structured as follows:  
  
   <type>[optional scope]: <short description of the commit>  
   
  Examples:  
   
    feat(transitions): Added missing transition rules.  
   
    fix: Fixed LGSS registration failing on second call.  
   
    docs(changeLog): update changelog to include changes between v0.9.0 and v1.0.0  
   
  ### All supported commit types:  
   
  feat: A new feature  
  fix: A bug fix  
  build: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)  
  ci: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)  
  docs: Documentation only changes  
  perf: A code change that improves performance  
  refactor: A code change that neither fixes a bug nor adds a feature  
  style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)  
  test: Adding missing tests or correcting existing tests  
  chore: Changes to the build process or auxiliary tools and libraries such as documentation generation  
   
  ### Breaking Changes:  
   
  The specification also allows for a breaking change to be indicated via the commit message.  
  This can either be via a `!` after the type/optional scope in the commit message,  
  or by adding `BREAKING CHANGE` to the footer.  
   
  Examples:  
   
    feat!: updated projects to dotnet 6  
   
    refactor(optimization): Refactored implementation to reduce RAM usage  
   
  ### How does ShipIt calculate the next version tag to push?  
   
  Based on the commit messages above, ShipIt can parse and identify the type of changes  
  being introduced from the commit messages. ShipIt then uses [semver2](https://semver.org/)  
  rules to identify the version:  
   
  - If there are any breaking changes since the last tag, the major version is incremented.  
    Example: v1.0.0 will get bumped to v2.0.0 if there is any breaking change commit in v1.0.0  
    or more other commits before the last version tag.  
  - If there are any feat commits but no breaking change commit, the minor version is bumped.  
    Example: v1.0.0 will get bumped to v1.1.0 if there is one or more commits with the feat type.  
  - If there are no feat commits but fix commits, the patch version is bumped.  
    Example: v1.0.0 will get bumped to v1.0.1  
   
  ### Pull requests titles such as squash merges  
   
  When merging pull requests, the commit messages in the commit history  
  are condensed into one commit based on the pull request’s title when completed.  
  It is therefore very important to use the conventional commits specification.  
   
  Note: You can change the title of a pull request after it has been created.  
  However, this only works if the PR hasn’t been configured to auto-complete.  
  Auto-complete needs to be cancelled before updating the PR title.  
   
  ### Please make sure that you are using Azure DevOps and consider the [Code Review Guide](CODE_REVIEW_GUIDE.md).  
   
  ### The following list shows some guiding rules that you should keep in mind when you’re contributing:  
   
  - Commit: Use the conventional commits specification.  
  - Pull: Use the pull request process in Azure DevOps.  
    This allows you to create, checkout, merge, commit, push, and pull changes from Azure DevOps.  
    You can also use the web UI to create and complete PRs.  

```




*****

[[category.storage-team]] 
[[category.confluence]] 
