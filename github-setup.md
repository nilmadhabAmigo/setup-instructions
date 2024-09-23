# Setting Up GitHub Access for Private Repositories

This guide covers the steps to set up access to private GitHub repositories on both macOS and Windows.

## Prerequisites
- A GitHub account
- Git installed on your system

## macOS Setup

1. **Generate SSH Key**:
   ```
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   Press Enter to accept the default file location and optionally set a passphrase.

2. **Start SSH Agent**:
   ```
   eval "$(ssh-agent -s)"
   ```

3. **Add SSH Key to SSH Agent**:
   ```
   ssh-add ~/.ssh/id_ed25519
   ```

4. **Copy Public Key**:
   ```
   pbcopy < ~/.ssh/id_ed25519.pub
   ```

5. **Add Key to GitHub**:
   - Go to GitHub Settings > SSH and GPG keys
   - Click "New SSH key"
   - Paste your key and save

## Windows Setup

1. **Generate SSH Key**:
   Open Git Bash and run:
   ```
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   Press Enter to accept the default file location and optionally set a passphrase.

2. **Start SSH Agent**:
   ```
   eval "$(ssh-agent -s)"
   ```

3. **Add SSH Key to SSH Agent**:
   ```
   ssh-add ~/.ssh/id_ed25519
   ```

4. **Copy Public Key**:
   ```
   clip < ~/.ssh/id_ed25519.pub
   ```

5. **Add Key to GitHub**:
   - Go to GitHub Settings > SSH and GPG keys
   - Click "New SSH key"
   - Paste your key and save

## Verify Setup

Test your connection:
```
ssh -T git@github.com
```

If successful, you'll see a message like: "Hi username! You've successfully authenticated, but GitHub does not provide shell access."

## Cloning Private Repositories

To clone a private repository:
```
git clone git@github.com:username/repo-name.git
```

Replace `username` and `repo-name` with the appropriate values.
