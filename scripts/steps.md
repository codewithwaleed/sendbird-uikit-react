## Prerequisites
We assume you're using yarn >= 2
## Step 0 - Setup
1. Create a new branch for the release: `git checkout -b release/vX.X.X`
2. Write changelog in CHANGELOG.md
3. Commit all changes

## Step 1 - Release Candidate
4. Run `yarn version prepatch/preminor/premajor`. It will update the version field in package.json automatically
5. Run `yarn run build`
6. Run `yarn npm publish --tag beta` for beta release. You can also use `yarn npm publish --tag <next | rc>` for other release candidates.
7. Commit `.bundle_analysis.json`, encouraged to summarize the bundle-size in the changelog
8. Test the rc version in your project(s) https://github.com/sendbird/uikit-react-test_suite (WIP: We are automating this step)
9. If everything is fine go to Step 2, otherwise make changes to main branch, rebase and repeat Step 1

## Step 2 - Actual release
10. Commit all changes
11. Run `yarn version patch/minor/major` to update the version in package.json
12. Run `yarn run build` and `yarn npm publish`
