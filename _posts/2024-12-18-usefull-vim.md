---
title: Useful Vim commands/settings ⌨️
date: 2024-12-18 18:00:00+0100
categories: [productivity]
tags: [vim, productivity]
---

## Native vim
- `set clipboard^=unnamed,unnamedplus` - use system clipboard when yank(y) and paste(p) 📋
- `let mapleader = " "` - set leader key to space ⌨️
- `@@` - repeat last macro 🔁
- `ZZ` - save and exit 💾
- `ZQ` - exit without saving ❌

## IdeaVim
- `noremap <c-/> :action CommentByLineComment<CR>` - comment line 💬
- `noremap gi :action GotoImplementation<CR>` - go to implementation 🔍
- `noremap <Leader>d :action ToggleDistractionFreeMode<CR>` - toggle distraction free mode 🧘
- `noremap gO :action FileStructurePopup<CR>` - file structure popup 🗂️
- `noremap <c-k> :action ShowErrorDescription<CR>` - show error description ❌
- `noremap L :action NextTab<CR>` - next tab ➡️
- `noremap H :action PreviousTab<CR>` - previous tab ⬅️
