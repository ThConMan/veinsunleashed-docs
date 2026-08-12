# Exp Veins Unleashed - docs site

The marketing and documentation page for the Exp Veins Unleashed Paper plugin.
Static: one HTML file, one stylesheet, and the icon set. No build step and no
dependencies.

```
index.html    the page
styles.css    the Unleashed design system, shared with the other plugin sites
icons/        real Minecraft item and block art
favicon.svg
.nojekyll     GitHub Pages serves the files as-is
```

## Icons

Every icon is the game's own texture pulled from the client jar, never redrawn.
Flat items are the raw 16x16; blocks are those textures projected onto the
isometric cube the inventory draws, with vanilla face shading baked into the
pixels. They render pixelated on purpose.

Regenerate or add to them with the shared tool:

```bash
python ../mc-icon-art/make-icons.py --out icons \
    item:experience_bottle block:deepslate_diamond_ore
```

Pass `--preview sheet.png` to get a contact sheet you can actually look at,
which is the only practical way to check the isometric projection.

## Design system

`styles.css` is shared with the other Unleashed docs sites. Every colour is a
token under `:root`, so recolouring the whole page means editing that block and
nothing else. The `.mc-*` registry near the bottom of the file is the only part
that is specific to this plugin.

The plugin itself lives in the `VeinsUnleashed` repo. Note that the repo name,
the plugin name (`ExpVeinsUnleashed`) and the command (`/veins`) deliberately
all differ.
