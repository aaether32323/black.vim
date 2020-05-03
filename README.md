# black-nvim

A port of the [official black plugin] to Neovim's remote Python plugin interface.

Differences:

- It runs asynchronously, so it won't block scrolling while formatting the buffer.
- Checks if filetype is "python" before formatting.
- More robust error handling and better error messages.
- Only vital features (Upgrading the black package is left to the user).
- Choose your own commands/keybinds, only a function is exported.

[official black plugin]: https://github.com/ambv/black/tree/master/plugin/black.vim

## Installation

| Plugin manager | How to install                                             |
|----------------|------------------------------------------------------------|
| minpac         | `call minpac#add('a-vrma/black-nvim')`                     |
| dein.vim       | `call dein#add('a-vrma/black-nvim')`                       |
| vim-plug       | `Plug 'a-vrma/black-nvim', {'do': ':UpdateRemotePlugins'}` |

If you don't already have a system for managing python environments on your computer
I would recommend the following:

- Make sure you have at least version 3.6.
- Set up a virtual environment for use with neovim.
  ```sh
  mkdir -p ~/.local/venv && cd ~/.local/venv
  python3 -m venv nvim
  cd nvim
  . ./bin/activate
  pip install pynvim black
  ```
- Tell neovim about that environment like so:
  ```vim
  let g:python3_host_prog = $HOME . '/.local/venv/nvim/bin/python'
  ```
- Run `:checkhealth`. The python3 provider section should be not-red.

## Documentation

See <doc/black.md>.

## License

black-nvim is distributed under the MIT/Expat license.
See LICENSE file for details.

mistune.py (distributed under the BSD 3-clause license) is used as a test file. It is
not part of the plugin.
