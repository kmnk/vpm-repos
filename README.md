# vpm-repos

VPM listing of kmnk's VRChat tools. Add it to VCC, ALCOM or vrc-get:

- Listing URL: `https://kmnk.github.io/vpm-repos/index.json`
- Add to VCC: `vcc://vpm/addRepo?url=https://kmnk.github.io/vpm-repos/index.json`
- Page: https://kmnk.github.io/vpm-repos/

## Packages

| Package | Repository |
| --- | --- |
| `dev.kmnk.face-tracking-generator` (Face Tracking Generator) | https://github.com/kmnk/VRChat_FaceTrackingGenerator |

## How the listing is built

Made from https://github.com/vrchat-community/template-package-listing. The "Build Repo Listing" workflow reads every release of the repositories in `githubRepos` of `source.json`, takes the attached `.zip` files that have `package.json` at their root, and publishes `index.json` to GitHub Pages.

A repository in `githubRepos` must have at least one release: with none, the workflow fails (`ArgumentNullException` in `package-list-action`). Add a repository after its first release with a VPM zip.

It runs when `source.json` changes on `main`. After releasing a new version of a package, run it by hand:

```
gh workflow run build-listing.yml -R kmnk/vpm-repos
```

Do not change the listing URL: users who added it would have to add it again.
