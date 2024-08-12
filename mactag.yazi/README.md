# mactag.yazi

Bring macOS's awesome tagging feature to Yazi! The plugin it's only available for macOS just like the name says.

Authors: [@AnirudhG07](https://github.com/AnirudhG07), and [@sxyazi](https://github.com/sxyazi)

## Installation

Install the plugin itself, and [jdberry/tag](https://github.com/jdberry/tag) used to tag files:

```sh
ya pack -a yazi-rs/plugins#mactag
brew update && brew install tag
```

## Setup

Add the following to your `~/.config/yazi/init.lua`:

```lua
require("mactag"):setup()
```

And register it as fetchers in your `~/.config/yazi/yazi.toml`:

```toml
[[plugin.prepend_fetchers]]
id   = "mactag"
name = "*"
run  = "mactag"

[[plugin.prepend_fetchers]]
id   = "mactag"
name = "*/"
run  = "mactag"
```

## Usage

This plugin also provides the functionality to add and remove tags. Add following keybindings to your `~/.config/yazi/keymap.toml` to enable it:

```toml
[[manager.prepend_keymap]]
on   = [ "t", "r" ]
run  = 'plugin mactag --args="add Red"'
desc = "Tag selected files with red"

[[manager.prepend_keymap]]
on   = [ "t", "R" ]
run  = 'plugin mactag --args="remove Red"'
desc = "Remove red tag from selected files"
```

`Red` can be any tag name you like. To add/remove multiple tags at once, use a comma (`,`) to separate them, like `Red,Yellow`.