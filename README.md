# Reproduction Steps

1. cd to `./inner`
2. Run `npx nx run build`
3. Open `.nx/workspace-data/daemon.log`
  * If using an editor without live-updates, open the `.nx/workspace-data` folder instead.
4. Note the continuously added logs to "hash changed files from watcher", "build-project-configs", and "total execution time for createProjectGraph()".
  * Or note the continuous increase to the `daemon.log` filesize.
5. Run `npx nx reset`
6. Add a blank `.gitignore` to `./inner`
7. Run `npx nx run build` again
8. Note the `daemon.log` does not continuously grow in size.
