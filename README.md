English | [简体中文](./README.zh-CN.md)

# blink-search

<p align="center">
  <h3>In the blink of an eye, the search is complete!</h3>
</p>

blink-search's goal is to become the fastest search framework in Emacs.

blink-search use python multi-thread technology to search and filter candidates, Emacs only render result and do action.

blink-search will provide smooth completion experience without compromise to slow down emacs' performance.

## Installation

1. Install Emacs 28 and above versions
2. Install Python dependencies: `pip3 install epc`
3. Install search tools: 
+ [fd](https://github.com/sharkdp/fd)
+ [ripgrep](https://github.com/BurntSushi/ripgrep)
4. Clone or download this repository (path of the folder is the `<path-to-blink-search>` used below).
5. Add following code in your ~/.emacs:

```elisp
(add-to-list 'load-path "<path-to-blink-search>")

(require 'blink-search)
```

## Usage
M-x blink-search 

**That's all!**

## Keymap
| Key      | Command                   | Description                                                                  |
| :---     | :---                      | :---                                                                         |
| C + n    | blink-search-select-next-candidate-item           | Select next candidate item                                                        |
| C + p  | blink-search-select-prev-candidate-item           | Select previous candidate item                                                    |
| M + n    | blink-search-select-next-backend-item           | Select next backend item                                                        |
| M + p  | blink-search-select-prev-backend-item           | Select previous backend item                                                    |
| C + m  | blink-search-do           | Do action for select backend item                                                    |
| C + g  | blink-search-quit           | Quit 

* `blink-search-restart-process`: restart blink-search process (only used for development)

## Report bug

Please use `emacs -q` and load a minimal setup with only blink-search to verify that the bug is reproducible. If `emacs -q` works fine, probably something is wrong with your Emacs config.

If the problem still exists, please report it [here](https://github.com/manateelazycat/blink-search/issues/new) with `*blink-search*` buffer content, it contains many clues that can help us locate the problem faster.

If you get a segfault error, please use the following way to collect crash information:

1. Install gdb and turn on option `blink-search-enable-debug`
2. Use the command `blink-search-stop-process` to stop the current process
3. Restart blink-search, send issue with `*blink-search*` buffer content when next crash

## Contributor

<a href = "https://github.com/manateelazycat/blink-search/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=manateelazycat/blink-search"/>
</a>