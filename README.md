Signed commits are marked as verified ✔ on GitHub so other people can be confident that changes are coming from a trusted source 🚀

# Download and install GPG for windows 
https://www.gpg4win.org/

# Create GPG Key
```
gpg --full-generate-key
```

# List GPG Key with key IDs
```
gpg --list-secret-keys --keyid-format LONG

sec   rsa4096/YOUR-KEY-ID 2020-06-18 [SC]
...

# Export your public key
```
gpg --armor --export YOUR-KEY-ID 
```

# Add GPG key to Github account

# Configure Git on windows 
```
git config --global user.name "YOUR-NAME"
git config --global user.email "YOUR-EMAIL"
git config --global user.signingkey YOUR-KEY-ID 
git config --global commit.gpgsign true
git config --global tag.gpgsign true
git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
```

# List global git config 
```
git config --global --list