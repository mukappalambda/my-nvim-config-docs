# Installation

The installation has two parts:
- [Setting Up `neovim`](#setting-up-neovim)
- [Setting Up the Config](#setting-up-the-config)

---

## Setting Up `neovim`

If you already have `neovim` installed on your machine, feel free to skip this step.

1. **Select the `neovim` version**

| `neovim` version | Command |
| --- | --- |
| `v0.9.x` | `NVIM_VERSION=v0.9.5`
| `v0.10.x` | `NVIM_VERSION=v0.10.0`

For other versions, please refer to neovim's [releases page](https://github.com/neovim/neovim/releases).

2. **Install `neovim` from pre-compiled binary**

```bash
wget https://github.com/neovim/neovim/releases/download/"${NVIM_VERSION}"/nvim-linux64.tar.gz
rm -rf /usr/local/nvim-linux64 && tar -C /usr/local -zxvf nvim-linux64.tar.gz # as root
```

3. **Setting up the `$PATH` variable**

- `Bash`
  - ```bash
    echo 'PATH=/usr/local/nvim-linux64/bin:$PATH' >> $HOME/.bashrc
    source $HOME/.bashrc
    ```
- `Zsh`
  - ```bash
    echo 'PATH=/usr/local/nvim-linux64/bin:$PATH' >> $HOME/.zshrc
    source $HOME/.zshrc
    ```

4. **Check the `neovim` version**

```bash
nvim --version
```

---

## Setting Up the Config

```bash
mkdir -p $HOME/.config/nvim && git clone https://github.com/kevinliao852/my-nvim-config.git $HOME/.config/nvim/
```

---

After setting up the config, type `nvim` on the terminal and wait a few seconds to have plugins installed.
