# GitHub, GitLab, Bitbucket and SSH autocompletion for `git clone`

A `bash` completion script adding autocompletion of GitHub, GitLab, and
Bitbucket organizations and repositories to `git clone` command
line. Works with both public and private repositories and organizations.
Also autocompletes arbitrary servers accessible via SSH.

![autocompletion gif](http://research.majuric.org/media/git-clone-completions-2.gif)

## Install

```bash
$ curl -O https://raw.githubusercontent.com/mjuric/git-utils/master/git-clone-completions.bash

# place this into your ~/.bash_profile (Mac) or ~/.bashrc (Linux)
$ source git-clone-completions.bash
```

## Usage

```bash
$ git clone <TAB><TAB>
git@github.com:      https://github.com/

$ git clone git@github.com:<TAB><TAB>
astronomy-commons/  dirac-institute/    lsst-dm/            lsst/               mjuric/

$ git clone git@github.com:astronomy-commons/<TAB><TAB>
astronomy-commons/aws-hub                        astronomy-commons/genesis-jupyterhub-automator
astronomy-commons/axs                            astronomy-commons/genesis-k8s-eks
astronomy-commons/axs-spark                      astronomy-commons/genesis-kafka-cluster
astronomy-commons/genesis-client                 astronomy-commons/helm-charts
astronomy-commons/genesis-helm-chart             astronomy-commons/tutorials
astronomy-commons/genesis-images

$ git clone git@github.com:astronomy-commons/genesis-jupyterhub-automator
Cloning into 'genesis-jupyterhub-automator'...
remote: Enumerating objects: 268, done.
remote: Counting objects: 100% (268/268), done.
remote: Compressing objects: 100% (161/161), done.
remote: Total 268 (delta 116), reused 228 (delta 80), pack-reused 0
Receiving objects: 100% (268/268), 3.21 MiB | 9.69 MiB/s, done.
Resolving deltas: 100% (116/116), done.
```

Organizations are autocompleted from the list of directories found in
`$PROJECTS/$service` (defaulting to `$HOME/projects/$service`), where
$service is 'github.com', 'gitlab.com' or 'bitbucket.org'.  See `git-get` in this repository
for a `git clone` equivalent that automatically organizes clones into
`$PROJECTS/github.com/<org>/<repo>` (and, similar to
[hub](https://github.com/github/hub), allows you type `git get
mjuric/git-utils`).

The code should be easily extensible to other hosting services (e.g.,
private GitLab or GitHub Enterprise deployments).  Open an issue if you're
interested in taking a stab at it (I'd be happy to give you pointers).  PRs
always welcome!
