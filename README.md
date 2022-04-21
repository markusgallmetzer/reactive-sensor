# reactive-sensor

## Collaboration

1. Fork this Repository
2. Add your changes to your fork
3. Create Pull Request

### Update Fork

Add upstream

```shell
git remote add upstream https://github.com/markusgallmetzer/reactive-sensor.git
```

Update `main` from `upstream`:

```shell
git fetch upstream main
```

Overwrite your local `main` with `upstream/main`:

```shell
git rebase upstream/main
```

(Force) Push to your own `origin/main`

```shell
git push origin main --force
```
