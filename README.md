# setup-multiple-github-accounts
https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574

## Generate public and private ssh keys
`ssh-keygen -t rsa -C "your-email-address"`

When prompted where to save, save the file as id_rsa_COMPANY

## Add the new identity
`ssh-add ~/.ssh/id_rsa_COMPANY`

You will see identity added once it's added

## Modify ssh config
`touch ~/.ssh/config`
`vim config`

Add another config below the existing one
```
#Default GitHub
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  
Host github-COMPANY
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_COMPANY
```

## Set your username and user email accordingly if needed
```bash
git config user.name ""
git config user.email ""
```
