# WASM Template
This is an Rust WASM template powered by vite and typescript. While it is personalized for my own projects, feel free to fork it and create your own template.

| Package | Description |
|---------|-------------|
| app     | Frontend with vanilla typescript |
| lint    | Lint rules for eslint. Modularized into a package so that dependencies can be added |
| wasm    | Rust code |

By default, frontend link the compiled WASM package using local package inclusion (`file:`), which does not work if the web package is intended to be published. The WASM package should also be published and linked like an external package would in this case.

## Note on Renaming Packages
Both [Cargo.toml](/Cargo.toml) and [packages.json](/package.json) at root use hardcoded directory references, please also update them if any package has been renamed.

## Command Quick Reference
| Command | Description |
|---------|-------------|
| `./scripts/build-all.mjs` | Build all packages |
| `./scripts/watch-wasm-packages.mjs`    | Watch all wasm packages for changes and rebuild it. `wasm-pack` does not support watch mode currently.  |
| `npm run <command> -w <workspace>`    | Run the command in the specified workspace |
| `cargo <subcommand> -p <workspace>` | Run the cargo sub command in the specified workspace |
