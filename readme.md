## GIT and Github

- When writing scripts, we should never save them in our Local PC rather store them in repos
- This ensures saftey and security for the storage of the code
- In addition to that, we can maintains different Versions of the scripts
- This allows us to revert to the previous versions when ever we want
- We can have different feature branches where we develop features and merge them into master by raising a pull request
- On the master branch, we have the production code
- In addition to that, we can also track which developer has done what
- Popular tool: GIT
- Popular platforms that hosts this GIT are:
  - Github
  - Gitlab
  - Bitbucket
- Each platform offers, Public and Private installations
- In Git, We can store everything inside a repository and push it to Github server
- Gitbash tool offers SSH service and works as a client to connect to any Git servers
- Github is a de-centralised distribution system i.e. everything is not in a single place rather its distributed
- Workspace -> Staging (temporary) area -> local repo -> central repo

## Continuation with Github

- With SVN, we can select which files to track the changes made to it
- With SSH, we don't need username and password to authenticate ourselves with the remote server
- Create Public and Private Key pair on the client machine using `ssh-keygen -f <keypair-name>`
- Copy the Public key from the client machine to the server
- In the client machine, create a file called **config** inside `.ssh` directory and paste these contents inside that file

`~/.ssh/config`

```bash
Host github.com
  Hostname github.com
  User git
  IdentityFile ~/.ssh/github
```

- By default when accessing the github.com, the default username is git
- If we have multiple github accounts, then the config file looks as follow:

`~/.ssh/config`

```bash
# This is for learniguser account
Host github.com
  Hostname github.com
  User git
  IdentityFile ~/.ssh/github

# This is for cloudcampindia account
Host github.com-cloudcamp
  Hostname github.com
  User git
  IdentityFile ~/.ssh/cloudcamp
```

### How to push an existing folder to GitHub?

- Step 1: Initialise the folder as a Git repository `git init`
- Step 2: Add all the files to staging area `git add .`
  - `.` - Add all the files to the staging area
- Step 3: Commit all the changes to the files in the staging area: `git commit -m <message>`
- Step 4: Create a repo inside the Github server
- Step 5: Add remote URL as origin inside the git repo using: `git remote add origin <SSH-URL>`
  - We can see this configuration inside `.ssh/config` file
  - If we wanted to add another github URL to the origin, we use `-t` option
- Step 6: Push the files to the remote repo using: `git push origin master`
- To change the remote origin URL, we can use: `git remote set-url origin <URL>`
- To get the changes from the remote server synced in our local repo we use: `git pull`
