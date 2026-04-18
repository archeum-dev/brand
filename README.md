# archeum-assets

Shared brand assets for the Archeum project. Consumed as a git submodule
by every Archeum repo that ships branded imagery (the apps, the website,
future third-party tools that want to reference the marks correctly).

## Structure

```
banners/         Archeum brand banners (hero images, repo headers).
logos/           Archeum logo variants (gold sphere, wordmark, color themes).
apps/archeum/    Archeum app-specific brand: launcher icon layers,
                 in-app logo, welcome banner.
apps/social/     Social app-specific brand: the cyan sphere icon and its
                 variants (grayscale / monochrome / nobg / glow / padded),
                 plus the Social wordmark and hover states.
```

Non-brand assets — fonts, generic UI icons, design-source files — live
in each consumer repo under that repo's own `assets/` directory. This
repo is only for artwork that carries Archeum or Social trademark weight.

## Adding as a submodule

From a consumer repo's root:

```bash
git submodule add https://github.com/archeum-dev/assets.git brand
```

Then reference paths as `brand/banners/b-archeum.png`,
`brand/apps/archeum/logo.png`, etc.

**Updating** after the assets repo changes:

```bash
git submodule update --remote brand
git add brand && git commit -m "Bump brand assets"
```

**Cloning a consumer repo** with submodules initialised:

```bash
git clone --recurse-submodules <repo>
# or, after a plain clone:
git submodule update --init --recursive
```

## License and trademark

Source code in sibling repositories is open source under various licenses
(see each repo's `LICENSE`). **Those grants do not extend to the contents
of this repository.** See `NOTICE.md` for the full trademark policy:
the Archeum and Social names, logos, and visual identities remain
trademarks of the Archeum project and are not granted by the source
licenses of consumer repos.

If you're forking one of the Archeum apps, rebrand before shipping —
replace the `brand/` submodule reference with your own assets.
