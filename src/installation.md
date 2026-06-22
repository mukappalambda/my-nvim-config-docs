# Installation

The installation has two parts:
- [Setting Up `neovim`](#setting-up-neovim)
- [Setting Up the Config](#setting-up-the-config)

---

## Setting Up `neovim`

If you already have `neovim` installed on your machine, make sure it matches the version expected by this config.

The recommended way to install and switch `neovim` versions is [`mise`](https://mise.jdx.dev/). Avoid downloading release artifacts manually unless you have a specific reason to do so; `mise` is faster to use day to day and keeps version management predictable.

The current `my-nvim-config` setup pins `NVIM_VERSION` to `0.11.4`. We are working on upgrading the config to support `nvim` `0.12.0` or newer.

1. **Search for available `neovim` versions**

```bash
mise search neovim
mise ls-remote neovim
```

2. **Install and use the pinned `neovim` version globally**

```bash
mise use neovim@0.11.4 -g
```

3. **Check the `neovim` version**

```bash
nvim --version
```

The first line should report `NVIM v0.11.4`.

4. **Optional: install from GitHub releases manually**

Manual artifact installation is slower and harder to maintain. Use it only when `mise` is not available in your environment.

```bash
NVIM_VERSION=v0.11.4
wget https://github.com/neovim/neovim/releases/download/"${NVIM_VERSION}"/nvim-linux64.tar.gz
rm -rf /usr/local/nvim-linux64 && tar -C /usr/local -zxvf nvim-linux64.tar.gz # as root
```

---

## Setting Up the Config

```bash
mkdir -p $HOME/.config/nvim \
&& git clone https://github.com/kevinliao852/my-nvim-config.git $HOME/.config/nvim/
```

---

After setting up the config, type `nvim` on the terminal and wait a few seconds to have plugins installed.
