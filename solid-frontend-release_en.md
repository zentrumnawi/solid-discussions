## Frontend App Release HowTo

1. adjust the version number in `package.json` (according to SemVer principle `major.minor.patch`)
2. write a changelog
3. create PR for `dev` -> `master` and merge.
   - If necessary, resolve merge conflicts via rebase or `git merge -s ours master`.
5. create a new release (Release button --> `Draft a new Release`)
6. write a release message and include the s.o.l.i.d. version.
7. create a _tag_ on the merge commit or `master` in the web interface(!) in the format `<appname>-v.X.Y.Z` (e.g. `dive-v.X.Y.Z`)
![image](https://user-images.githubusercontent.com/13869236/141685508-f77ab652-79b8-4f59-96e7-5c593e3b91cf.png)

Note: The app version is identical to the s.o.l.i.d. version! (New since 17.03.2022)

7. `Publish Release`

After publishing the release, a build process should be triggered for this app only, including deployment.

If there is a problem or an error and the release is to be repeated with the same number, the release AND tag must be deleted. The build is only triggered by a new tag. 
