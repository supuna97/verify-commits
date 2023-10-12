# Github verify sign commits

Signed commits are marked as verified ✔ on GitHub so other people can be confident that changes are coming from a trusted source 🚀

## Download and install GPG for windows 
https://www.gpg4win.org/

## Create GPG Key
```
gpg --full-generate-key
```

## List GPG Key with key IDs
```
gpg --list-secret-keys --keyid-format LONG
```

## Export your public key
```
gpg --armor --export YOUR-KEY-ID 
```

## Add GPG key to Github account

## Configure Git on windows 
```
git config --global user.name "YOUR-NAME"
git config --global user.email "YOUR-EMAIL"
git config --global user.signingkey YOUR-KEY-ID 
git config --global commit.gpgsign true
git config --global tag.gpgsign true
git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
```

## List global git config 
```
git config --global --list
```

## Create a signed commit
```
git commit -S -m "YOUR-COMMIT-MESSAGE"
```

## Create a signed tag
```
git tag -s v1.0 -m "YOUR-TAG-MESSAGE"
```

## Push signed commits and tags
```
git push origin master --tags
```

## Verify signed commits and tags
```
git log --show-signature
```

## Verify signed commits and tags on Github

## References
https://help.github.com/en/github/authenticating-to-github/managing-commit-signature-verification
https://help.github.com/en/github/authenticating-to-github/generating-a-new-gpg-key
https://help.github.com/en/github/authenticating-to-github/adding-a-new-gpg-key-to-your-github-account
https://help.github.com/en/github/authenticating-to-github/telling-git-about-your-signing-key