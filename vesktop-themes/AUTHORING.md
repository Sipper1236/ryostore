# Vesktop themes

Each theme has its own folder and an entry in `registry.json`, using the common
Store product schema. Copy `ryoku-paper/` and give it a unique id. Its registry
path includes the category, while preview and manifest paths are relative to
the product folder.

Ship original or redistribution-compatible licensed CSS and include its license.
Use flat `*.theme.css` filenames, mode `0644`, and `install: true` only for CSS.
Documentation and previews use `install: false`. The manifest destination is
`ryoku/vesktop-themes/<id>`; the client publishes managed CSS into Vesktop's
Themes folder. Never put an absolute user path in the manifest.

Include name, author, version, description, tags, accent, surface, preview,
screenshots, license, maintenance contact/upstream and lastUpdated. Real runtime
screenshots are preferred; label palette illustrations honestly and leave
`screenshots` empty when no runtime screenshot is supplied. Do not claim a
preview is evidence of runtime compatibility.

Regenerate hashes after every file change:

```sh
python3 tools/pack-product.py vesktop-themes/<id> --touch
python3 tests/validate-store.py --categories vesktop-themes --require-media
tests/validate-catalogue.sh
```

Users enable installed themes under **Vesktop → Settings → Vencord → Themes**.
Installation leaves theme enablement and QuickCSS under the user's control.
Document remote CSS imports, fonts and artwork if your theme uses them.
