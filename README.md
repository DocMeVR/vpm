# DocMe Tools

The VRChat Creator Companion listing for DocMe's free avatar tools.

**Add it to VCC:** open https://docmevr.github.io/vpm and press *Add to VCC*, or add this URL by hand:

```
https://docmevr.github.io/vpm/index.json
```

## Packages

| Package | What it does |
|---|---|
| [DocMe Eye Installer](https://github.com/DocMeVR/eye-installer) (`com.docme.eye-installer`) | Puts a procedural eye shader onto an avatar in four guided steps. |
| [DocMe Hide Mesh Islands](https://github.com/DocMeVR/hide-islands) (`com.docme.hide-islands`) | Hides small parts of a mesh (highlights, stickers) without editing the model. The eye installer depends on it. |
| [DocMe AvatarDoc](https://github.com/DocMeVR/AvatarDoc) (`dev.docme.avatar-doctor`) | Toggles, radials, submenus and triggers for an avatar's menu, built at upload through NDMF. In English, Japanese and Simplified Chinese. Needs NDMF from its official listing (see below). |

NDMF (`nadena.dev.ndmf`, by bd_, MIT) is listed here too, straight from its own GitHub releases, so AvatarDoc installs without adding another listing. If you also have the Modular Avatar listing, both offer the same NDMF files.

## NDMF

AvatarDoc is built on NDMF, which is not part of this listing: it comes from its author's own listing, so updates and fixes arrive straight from the source. Add that listing to VCC as well:

```
https://vpm.nadena.dev/vpm.json
```

VCC resolves the dependency across every listing you have added and names the missing package if it cannot.

## How the listing updates

The listing is rebuilt from each package's GitHub releases:

- right after a release: the package's release workflow sends a `package-released` event. That needs a fine-grained token with *Contents: read and write* on this repository, stored in each package repository as the `VPM_LISTING_TOKEN` secret.
- on every push to this repository,
- by hand (Actions → Build Repo Listing → Run workflow),
- once a day at 04:17 UTC as a safety net.

## Adding a package

Add its GitHub repository to `githubRepos` in `source.json`. The package must publish releases that carry `package.json` and the package zip, which the release workflow in each DocMe tool does.
