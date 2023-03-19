## Connect Workstation to GitHub
First things first, open a CLI.
We need to configure our username and email. 
```shell
git config --global user.name “your username”
git config -–global user.email “your email”
```

Verify your email and username was configured correctly.
```shell
git config --global user.name
git config -–global user.email
```

<!-- Still need to verify this part on Windows -->
Authenticate with a GitHub Host
```shell
# Verify this can be used across OS
gh auth login

# Answer Prompts
? What account do you want to log into? GitHub.com
? What is your preferred protocol for Git operations? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: XXXX-XXXX
- Press Enter to open github.com in your browser...

# Answer Web Prompts

✓ Authentication complete. Press Enter to continue...

- gh config set -h github.com git_protocol https
✓ Configured git protocol
✓ Logged in as your-username
```

Now your workstation is connected to GitHub!

**Next: [Initialize a Local Repository](Initialize%20a%20Local%20Repository.md)**