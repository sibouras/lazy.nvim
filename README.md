# lazy.nvim

## ✨ Features

- [x] Partial clones instead of shallow clones
- [x] waits till missing deps are installed (bootstrap Neovim and start using it right away)
- [x] Async
- [x] No need for compile
- [x] Fast
- [x] Correct sequencing of dependencies (deps should always be opt. Maybe make everything opt?)
- [x] Config in multiple files
- [x] Patterns for local packages
- [x] Profiling
- [x] lockfile
- [x] upvalues in `config` & `init`
- [x] check for updates
- [x] lazy-lock.lua
- [x] tag/version support `git tag --sort version:refname`
- [x] auto-loading on completion for lazy-loaded commands
- [x] bootstrap code
- [x] semver https://devhints.io/semver
      https://semver.npmjs.com/

## ✅ TODO

- [ ] health checks: check merge conflicts async
  - [ ] unsupported props or props from other managers
  - [ ] other packages still in site?
  - [ ] other package manager artifacts still present? compiled etc
- [ ] fix plugin details
- [ ] show disabled plugins (strikethrough?)
- [ ] log file
- [ ] git tests
- [ ] Import specs from other plugin managers
- [x] Background update checker
- [ ] [packspec](https://github.com/nvim-lua/nvim-package-specification)
  - [ ] add support to specify `engines`, `os` and `cpu` like in `package.json`
  - [ ] semver merging. Should check if two or more semver ranges are compatible and calculate the union range
    - default semver merging strategy: if no version matches all, then use highest version?
  - [ ] package meta index (package.lua cache for all packages)
- [x] status page showing running handlers and cache stats
- [x] delete lazy keymaps when a plugin loads. Reset handlers for a plugin?
- [x] deal with re-sourcing init.lua. Check a global?
- [x] rename `run` to `build`
- [x] temp colorscheme
- [x] allow setting up plugins through config **fooo**
- [x] task timeout
- [x] incorrect when switching TN from opt to start
- [x] max concurrency
- [x] ui border
- [x] make sure we can reload specs while keeping state
- [x] use uv file watcher (or stat) to check for config changes
- [x] support for Plugin.lock
- [x] defaults for git log
- [x] view keybindings for update/clean/...
- [x] add profiler to view
- [x] add buttons for actions
- [x] show time taken for op in view
- [x] auto lazy-loading of lua modules
- [x] clear errors
- [x] add support for versions `git tag --sort v:refname`
- [x] rename requires to dependencies
- [x] move tasks etc to Plugin.state
- [x] handlers imply opt
- [x] dependencies imply opt for deps
- [x] fix local plugin spec
- [x] investigate all opt=true. Simplifies logic (easily switch between opt/start afterwards)

## 📦 Differences with Packer

- **Plugin Spec**:

  - `setup` => `init`
  - `requires` => `dependencies`
  - `as` => `name`
  - `opt` => `lazy`
  - `run` => `build`
  - `lock` => `pin`
  - `module` is auto-loaded. No need to specify

## 📦 Other Neovim Plugin Managers in Lua

- [packer.nvim](https://github.com/wbthomason/packer.nvim)
- [paq-nvim](https://github.com/savq/paq-nvim)
- [neopm](https://github.com/ii14/neopm)
- [dep](https://github.com/chiyadev/dep)
- [optpack.nvim](https://github.com/notomo/optpack.nvim)
- [pact.nvim](https://github.com/rktjmp/pact.nvim)
