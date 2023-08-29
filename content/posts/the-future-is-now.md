---
title: "Pwndbg Cheatsheet: Unleash Your Inner Debugger Ninja!"
date: 2023-08-29
description: "Mastering pwndbg commands for epic debugging in CTFs and beyond."
tags:
   - Pwndbg
   - Debugging
   - CTF
---

## Introduction

Hey debuggers and code wranglers! 🐍💻 Ever found yourself in the midst of a Capture The Flag (CTF) challenge, battling vicious bugs and elusive exploits? Fear not! Meet your trusty sidekick, [pwndbg](https://github.com/pwndbg/pwndbg), the debugger that'll turn you into a debugging ninja!

## Getting Started with Pwndbg

First things first, you gotta summon pwndbg into action. Here's the incantation:

```sh
$ gdb -q ./your_binary
(gdb) source /path/to/pwndbg/gdbinit.py
```

Now that pwndbg is your loyal companion, let's dive into some commands:

## Pwndbg Command Cheatsheet

### Basic Commands

| Command | Description |
|:---------| :---------- |
| **`info functions`** | This command is your treasure map to discovering all the functions within your program or binary. It's like finding secret chambers in a labyrinth! |
| **`disassemble *function`** | Is used to disassemble a function in your program. This means it will display the assembly language code for the function specified. For instance, if you have a function named "main" in your program, you can see its assembly code by typing `disass main` in the pwndbg prompt. |
| **`context`** | The all-seeing eye! Displays register values, stack, and code around the current instruction. Your debugging compass. |
| **`next (or n)`** | March forward one instruction. Keep the quest going! |
| break *address | Set a breakpoint at a specific memory address. It's like dropping a pin on the treasure map. |

### Inspecting Memory

| Command | Description |
|:---------| :---------- |
| **`x/[Nfus] address`** | eXamine memory at a given address. For example, `x/16xg $rsp` `x/s 0x400764`  peeks into 16 quadwords starting from the stack pointer. Use it to inspect treasures (or vulnerabilities) hidden in memory. |
| **`heap`** | Your shovel for digging into heap structures. Unearth those dynamic memory secrets! |

### Stack Control

| Command | Description |
|:---------| :---------- |
| **`cyclic N`** | Craft cyclic patterns for buffer overflows. You'll crack that safe by testing for buffer overflows like a pro! |
| **`pattern offset <register>`** | Determine the offset where a pattern you crafted has overwritten a register or memory location. Find the X that marks the spot! |
| **`gef config context.layout`** | Customize how context info is displayed, like arranging your toolbelt. |

### Debugging Techniques

| Command | Description |
|:---------| :---------- |
| **`shell`** | A magic spell to spawn a shell. Great for testing if you've got remote code execution powers. |
| **`ropgadget`** | Summon the ROP gadgets! Discover gadgets in the binary to craft your exploits. It's like assembling LEGO bricks |
| **`vmmap`** | Unveil the virtual memory map. Know the lay of the land! |
| **`i proc mappings`** | Inspect the process's memory mappings. You're Sherlock Holmes hunting for clues. |

## Conclusion

With this pwndbg cheatsheet, you're well on your way to becoming a debugging ninja! 💣🥷 Remember, debugging is an art and a science. Practice, experiment, and embrace the thrill of uncovering vulnerabilities and exploits.

So go forth, fearless debugger! May your exploits be fruitful, and your bugs be squashed! 🐞💥

Now, back to the digital battlegrounds! 🔍🏰