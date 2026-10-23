# Sarki Express (web)

The published web build of **Sarki Express** (sarkiexpress.fun), served as static
files by Vercel. Nothing is built here: these are the files Godot 4.7.2 exports
(`--export-release "Web"`) from the game project, which is kept separately.

Current build: **0.1.0-web11**, exported from game commit `ffc7f41`.

To publish a new build: replace the exported files (index.html, index.js,
index.wasm, index.pck, the icons and audio worklets) with the new export,
commit with the build's version, and push to `main`; Vercel deploys it.

`vercel.json`: no build step; `index.html` is never cached, so a new version
reaches players on their next visit; `.pck` and `.wasm` are revalidated.
`.gitattributes` keeps every file byte-for-byte as exported.
