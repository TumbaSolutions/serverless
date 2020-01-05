# Merge & Release
We do not do releases held from release-fast-track as its history is rewritten when release is held from master. See [Release process](https://github.com/serverless/serverless/blob/master/RELEASE_PROCESS.md). We do releases held only from master.
## Merge
- [ ] go to https://travis-ci.org/TumbaSolutions/serverless/settings and trunk off "Build pushed branches"
- [ ] git fetch upstream master:master && git push origin master:master
- [ ] go to https://travis-ci.org/TumbaSolutions/serverless/settings and trunk on "Build pushed branches"
- [ ] git rebase --onto new old
- [ ] resolve conflicts with whatever is your favourite tool. Usually there will be merge conflict in  `package.json`, but can be in `.travis.yml` too as it is modified compared to one that can be found in upstream.
- [ ] git push --force
## Release
- [ ] Create a new [**draft** release](https://github.com/TumbaSolutions/serverless/releases/new) in GitHub
  - [ ] Ensure that the "Tag version" is same as version number in `package.json`. Including NO 'v' in front of version number.
- [ ] Publish the GitHub release draft (Circle CI will automatically publish the new release to `npm`)

## Other
[Regain control of branches with git rebase --onto](https://dev.to/drews256/regain-control-of-branches-with-git-rebase-onto-3075) is worth to read.