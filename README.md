# Github verify sign commits

## description
This is a guide to verify signed commits on Github.

## What is GPG?
GPG, or GNU Privacy Guard, is a public key cryptography implementation. This allows for the secure transmission of information between parties and can be used to verify that the origin of a message is genuine.

## Why sign commits?
Signing commits enables other people to verify that commits come from a trusted source and haven't been altered after they were signed. Git uses GPG keys to sign commits and tags.

## How to sign commits?
You can sign commits and tags using GPG keys.

## How to verify signed commits?
You can verify signed commits and tags using GPG keys.

## Steps

### Download and install GPG for windows 
https://www.gpg4win.org/

### Create GPG Key
```
gpg --full-generate-key
```

### List GPG Key with key IDs
```
gpg --list-secret-keys --keyid-format LONG
```

### Export your public key
```
gpg --armor --export YOUR-KEY-ID 
```

### Add GPG key to Github account
1. Copy your GPG key, beginning with -----BEGIN PGP PUBLIC KEY BLOCK----- and ending with -----END PGP PUBLIC KEY BLOCK-----.
2. In the upper-right corner of github page, click your profile photo, then click Settings.
3. In the user settings sidebar, click SSH and GPG keys.
4. Click New GPG key.
5. In the "Key" field, paste your GPG key.
6. Click Add GPG key.
7. Type your GitHub password to verify that it's you.
8. Click Confirm.

### Configure Git on windows 
```
git config --global user.name "YOUR-NAME"
git config --global user.email "YOUR-EMAIL"
git config --global user.signingkey YOUR-KEY-ID 
git config --global commit.gpgsign true
git config --global tag.gpgsign true
git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
```

### List global git config 
```
git config --global --list
```

### Create a signed commit
```
git commit -S -m "YOUR-COMMIT-MESSAGE"
```

### Create a signed tag
```
git tag -s v1.0 -m "YOUR-TAG-MESSAGE"
```

### Push signed commits and tags
```
git push origin master --tags
```

### Verify signed commits and tags
```
git log --show-signature
```

### Verify signed commits and tags on Github
```
git log --show-signature --oneline
```

## References
https://help.github.com/en/github/authenticating-to-github/managing-commit-signature-verification
https://help.github.com/en/github/authenticating-to-github/generating-a-new-gpg-key
https://help.github.com/en/github/authenticating-to-github/adding-a-new-gpg-key-to-your-github-account
https://help.github.com/en/github/authenticating-to-github/telling-git-about-your-signing-key
