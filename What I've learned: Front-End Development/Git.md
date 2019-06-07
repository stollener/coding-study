# Git Study Note

### Clone the existing Github repository
1. In terminal, setup the configuration with below shell commands.
```
git config --global user.name <my user ID in Github>
git config --global user.email <my email in Github>
```
2. Copy the repository address from Github site. And then run the following shell commands. (In the target directory)
```
git clone <copied repository address>
```
3. Stage, commit, push the changes to the master branch in the Github server. If you use Two factor authentication, then you should enter access token instead of your password in the password field.
```
git add .
git commit -m "Commit Messages"
git push
```
