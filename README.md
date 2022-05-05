# reactive-sensor

<!-- toc -->

- [Collaboration](#collaboration)
  * [Update Fork](#update-fork)
    + [Preparation](#preparation)
    + [Updating](#updating)

<!-- tocstop -->

## Collaboration

The chosen collaboration model is based upon _forks_. The first step is to navigate to the repository

https://github.com/markusgallmetzer/reactive-sensor

and to _fork_ it using the corresponding button. This creates a new repository with the name `reactive-sensor` in your
namespace (e.g. `collaborator`).

You may then clone this repository from

```shell
git clone https://github.com/collaborator/reactive-sensor.git
```


### Update Fork

#### Preparation

> This is only required once.

Your fork should be updated before you add modifications and create pull requests. Your _working directory_ requires an
additional _remote_ pointing to the _upstream_ repository.

**Please note:** Your default remote is named `origin` and points to your fork/repository. Your configured remotes can
be checked with

```shell
$ git remote -v
origin  https://github.com/collaborator/reactive-sensor.git (fetch)
origin  https://github.com/collaborator/reactive-sensor.git (push)
```
You need to add another remote pointing to the _original_ repository; this guide suggests the name `upstream` but any
name which `git` accepts can be used here. 

Add the remote `upstream` with

```shell
git remote add upstream https://github.com/markusgallmetzer/reactive-sensor.git
```

and verify your remotes are now complete:

```shell
$ git remote -v
origin  https://github.com/collaborator/reactive-sensor.git (fetch)
origin  https://github.com/collaborator/reactive-sensor.git (push)
upstream        https://github.com/markusgallmetzer/reactive-sensor.git (fetch)
upstream        https://github.com/markusgallmetzer/reactive-sensor.git (push)
```

#### Updating

The idea is now to update the index for `upstream` and to  rebase your local `main` branch onto the new commits from
`upstream`.

The index can be updated with

```shell
git fetch upstream main
```

and your local branch is rebased onto the upstream changes with

```shell
git rebase upstream/main
```

This basically replaces your local history with the commits from `upstream`. Your changes only need to be force-pushed
to your own `origin` with

```shell
git push origin main --force
```
we want do a new pull request

and both, your local working directory and your fork on https://github.com are (should be) up to date.

### Python

Create directory for the new virtual environment:

```shell
mkdir .env
```

and create the virtual environment with

```shell
python -m venv ./.env/
```

Do not forget to _activate_ the environment.
