# gogs2gitea

* Simple script to migrate repositories from Gogs to Gitea using the
[migration feature of Gitea]((https://martchus.no-ip.biz/gitea/api/swagger#/repository/repoMigrate)).
* Before running the script, set the the environment variables for URLs and credentials (see the very top
of the script).
* Needs Perl and Mojolicious for `Mojo::UserAgent`. Under Arch Linux, install `perl-mojolicious` from the AUR.
* Does *not* allow to migrate only specific repos so far. But the point of this script is to move everything at once. For migrating single repos Gitea's web interface for migrations would be good enough anyways.

## Further useful commands
Remove remote from all local Git working copies, e.g.:
```
find -path '*/.git' -exec git -C {}/.. remote remove gogs \;
```

Remove/migrate URLs still present on other¹ remotes, e.g.:
```
find -path '*/.git/config' -exec sed -i -e '/pushurl = gogs@martchus.no-ip.biz:Martchus/d' -e 's/url = gogs@martchus.no-ip.biz:Martchus/url = gitea@martchus.no-ip.biz:Martchus/g' {} \;
```

¹I sometimes create remotes with multiple push URLs for pushing to multiple servers at once.
