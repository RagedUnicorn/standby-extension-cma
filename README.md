![standby-extension-cma](docs/standby_extension_cma_banner.svg)

# Standby extension: CMA

What [Standby](https://github.com/RagedUnicorn/standby) draws for CMA stages:

- **Targets**: paper, 50 % on a backer, non-shoot, painted hard cover (four variants), the cut target.
- **The flipper**, CMA's two-board mover.
- **Boards** `cma` and `cma-cut`: the true outlines (CMA Rule Book §4.1, seeded from RagedUnicorn/shooting-sports-targets), hard-cover lines and the non-shoot's X.
- **Stage defaults**: CMA stages' movers take the `cma` board, and a bullet trap carries the cut target.

Standby comes with a release of it. Newer releases reach Standby as updates (Settings, Extensions).

**Viewer:** every element in 2D and 3D, at https://ragedunicorn.github.io/standby-extension-cma/

## Changing it

An element is its file `elements/<category>/<id>.json`. An element drawn from files has a drawing `assets/2d/<id>.svg` and a model `assets/3d/<id>.glb`. A board is `boards/<id>.json`. The [extension kit](https://github.com/RagedUnicorn/standby-extension-kit) describes the format, and each file names its schema.

- **See your changes**: `npx https://github.com/RagedUnicorn/standby-extension-kit/releases/download/v0.3.0/standby-extension-kit-0.3.0.tgz view` opens the viewer at http://localhost:4310 and reloads it as you save. To see them in Standby, link this folder: Settings, Extensions, Link a folder.
- **Check them**: `npx https://github.com/RagedUnicorn/standby-extension-kit/releases/download/v0.3.0/standby-extension-kit-0.3.0.tgz validate`, as the CI does.
- **In IntelliJ**: the run configurations View and Validate run the two commands above.
- **A pull request** gets a preview of the viewer with each changed element before and after, linked in a comment.
- **Ids never change** once stages use them: Standby finds placed elements by id.

## Releasing

Set `version` in extension.json, merge, and push the tag `v<version>`. The workflow releases `<id>-<version>.zip`, which Standby installs, and publishes the viewer. Standby bundles a release by pinning it: `npm run extensions:bump -- <id>` in the standby repository.

## Licence

MIT
