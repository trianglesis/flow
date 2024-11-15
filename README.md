## Trunk



## Hints

- [VS Code](DOC/VS_Code_setup.md)


## Flow

What is [flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

Flow is **BAD!!!**

Do not use **FLOW!!!**

This repo was initiated by flow, and later it was removed.

Tested by two users.

### Multiple users and ssh keys

Use multiple users at one PC with miltiple repos.

- Generate SSH key for each user
  - Name your keys by each user (use email) `alpha@example.com`, `beta@example.com`
  - Put your keys at `~./ssh/`

```
ssh-keygen -t ed25519 -C alpha@example.com
ssh-keygen -t ed25519 -C beta@example.com
```

- Now you have 4 keys in common, 2 pub and 2 private.
  - `alpha@example.com`, `alpha@example.com.pub`
  - `beta@example.com`, `beta@example.com.pub`

- Add each SSH key to GitHub account for each user. 
  - Alpha to Alpha, Beta to Beta.
  - Only add a content of the `*.pub` key!
  - Private key (not `*.pub`) should never leave your PC!

- Modify your local SSH config file for both users at once:
  - Use private keys, without `*.pub`

```shell
[user@note-pc ~]$ cat .ssh/config
Host github-alpha
    HostName github.com
    IdentityFile ~/.ssh/alpha@example.com
    IdentitiesOnly yes
Host github-beta
    HostName github.com
    IdentityFile ~/.ssh/beta@example.com
    IdentitiesOnly yes
```

- Now you can use git as usual with commands like that:

```shell
git clone git@github-alpha:ORGANIZATION/reponame.git
git clone git@github-beta:ORGANIZATION/reponame.git
```

- Add `user name` and `user email` for both clones:

```shell
cd /dir_where_cloned_repo_by_alpha_user/
git config user.name alpha
git config user.email alpha@example.com

cd /dir_where_cloned_repo_by_beta_user/
git config user.name beta
git config user.email beta@example.com
```

Now you can contribute to one repo from one PC from two users.
