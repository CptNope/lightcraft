# LightCraft PWA

Browser app: https://cptnope.github.io/lightcraft/ after successful GitHub Pages deployment.

The browser build is **not Trunk**. GitHub Actions uses `cargo xtask web` and the `wasm-bindgen` CLI version pinned in Cargo.lock. That produces the specialized module, render worker, HTML and JS in `target/web-site`.

Phones use dedicated Photos, Photo, Library, Adjust and Presets views with Import, Export and Back Up actions. Desktop docking layouts are preserved.

The Pages workflow builds only the browser app, checks artifacts and packages a PWA. No Rust test suites are run during deployment. The existing platform release/test workflows remain in the repository but are manually triggered.

Browser libraries and originals persist separately via OPFS/IndexedDB; the service worker caches application files, not photos. Use Back Up Library before browser storage cleanup. Avoid opening multiple tabs with the same library.
