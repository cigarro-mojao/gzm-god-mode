# God Mode

Become invincible.

This is an independent mod repository. It owns its manifest, assets, translations and downloadable packages. The central [Goofy Zombie Mods registry](https://github.com/cigarro-mojao/goofy-zombie-mods) contains only an ID, a package URL and a SHA-256 for this mod.

## Build and publish

```sh
python tools/build_package.py
python tools/build_package.py --check
```

Python 3.11+, no dependencies. Edit `mod/manifest.json` and the files in `mod/`, then rebuild. The ZIP contains `manifest.json` at its root. Commit `mod/`, the builder and `dist/` to this repository. The included workflow verifies the committed package matches the source.

Push/merge to **main** to make the direct HTTPS package URL available. Submit only the contents of `dist/catalog-entry.json` to `goofy-zombie-mods/catalog.json` in a pull request. No manifest, icon, translations or ZIP is copied into the registry.

For updates keep the ID `god_mode`, increment the manifest version, rebuild and submit the new registry entry. Keep previous content-addressed ZIPs so cached catalogs keep working. Custom hosting can be set with `--base-url https://host/path`.

In the game: **Mods → Store → Install**, then enable in **Local**. All peers need matching enabled packages. A new install starts disabled. The game caches the verified ZIP while reading its manifest for the Store; installation remains a separate action.

## Layout

- `mod/manifest.json`: the authoritative metadata and rules.
- `mod/translations/`: namespaced strings.
- `mod/`: optional PNG assets and package documentation/license.
- `dist/`: downloadable ZIPs and the minimal registration entry.
- `tools/build_package.py`: self-contained public packaging helper; no game source needed.

License: [GPL-3.0](LICENSE). The repository and manifest retain the real author credit; independent ownership is simulated through separate repositories, not fictional authors.
