# How to change the username and email of git history

Using "git filter-branch", can changed the username and email.

```git
git filter-branch --env-filter '
        if test "$GIT_AUTHOR_EMAIL" = "root@localhost"
        then
                GIT_AUTHOR_NAME=john
                GIT_AUTHOR_EMAIL=john@example.com
        fi
        if test "$GIT_COMMITTER_EMAIL" = "root@localhost"
        then
                GIT_COMMITTER_NAME=john
                GIT_COMMITTER_EMAIL=john@example.com
        fi
' -- --all
```