# Setup Remote Repository in GitHub

Before you can `push`, `pull`, or `clone` a remote repository from a platform like GitHub, you need to initialize the SSH key and copy the SSH public key to GitHub. This guide will help you initialize the SSH key in both Windows (PowerShell) and Linux systems.

## Step

### Windows

```bash
# Generating an SSH Key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# Copy SSH Public Key to GitHub (Windows & Linux)
cat ~/.ssh/id_rsa.pub

# Start SSH Agent
Start-Service ssh-agent

# Add your SSH private key to the agent:
ssh-add C:\Users\<YourUsername>\.ssh\id_rsa

# Verify SSH Key is Added (Windows & Linux)
ssh-add -l

# Test SSH Connection (Windows & Linux)
ssh -T git@github.com

# Hi <your_username>! You've successfully authenticated, but GitHub does not provide shell access.
```

### Linux

```bash
# Generating an SSH Key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# Copy SSH Public Key to GitHub (Windows & Linux)
cat ~/.ssh/id_rsa.pub

# Start the SSH agent:
eval "$(ssh-agent -s)"

# Add your SSH private key to the agent:
ssh-add ~/.ssh/id_rsa

# Verify SSH Key is Added (Windows & Linux)
ssh-add -l

# Test SSH Connection (Windows & Linux)
ssh -T git@github.com

# Hi <your_username>! You've successfully authenticated, but GitHub does not provide shell access.
```

## Troubeshooting

If you make a mistake during SSH key generation, you can delete the SSH key and start over. For example, in Windows:

```bash
cd ~/.ssh
Remove-Item id_rsa
Remove-Item id_rsa.pub

# Generate a New SSH Key Without a Passphrase:
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# Add the new public key to github (same as before)
cat ~/.ssh/id_rsa.pub

# Test the new SSH Key
ssh -T git@github.com
```
