# gogs2gitea

* Simple script to migrate repositories from Gogs to Gitea using the
[migration feature of Gitea]((https://martchus.no-ip.biz/gitea/api/swagger#/repository/repoMigrate)).
* Before running the script, set the the environment variables for URLs and credentials (see the very top
of the script).
* Needs Perl and Mojolicious for `Mojo::UserAgent`. Under Arch Linux, install `perl-mojolicious` from the AUR.
* Does *not* allow to migrate only specific repos so far. But the point of this script is to move everything at once. For migrating single repos Gitea's web interface for migrations would be good enough anyways.