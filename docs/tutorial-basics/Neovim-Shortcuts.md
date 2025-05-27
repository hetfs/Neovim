```yaml
sidebar_position: 4
```

# Ultimate Neovim Cheatsheet

Neovim?a modern, extensible successor to Vim?empowers developers with speed and precision. This cheatsheet delivers essential commands and workflows for mastering navigation, editing, and advanced features.

---

## ? Navigation & Motion

### Cursor Basics

| Command         | Description                                                    |
| --------------- | -------------------------------------------------------------- |
| `h` `j` `k` `l` | Left, Down, Up, Right                                          |
| `w` / `W`       | Next **word** (alphanumeric) / **WORD** (whitespace-separated) |
| `b` / `B`       | Previous word / WORD                                           |
| `e` / `E`       | End of word / WORD                                             |
| `0` / `^` / `$` | Start of line / First non-blank / End of line                  |

### File & Screen Navigation

| Command             | Description                                 |
| ------------------- | ------------------------------------------- |
| `gg` / `G`          | Jump to start / end of file                 |
| `{n}G` or `:{n}`    | Jump to line **n**                          |
| `{` / `}`           | Jump to previous/next paragraph             |
| `(` / `)`           | Jump to previous/next sentence              |
| `[[` / `]]`         | Jump to previous/next function (code-aware) |
| `Ctrl-u` / `Ctrl-d` | Scroll half-page up/down                    |
| `Ctrl-b` / `Ctrl-f` | Scroll full-page up/down                    |
| `zt` / `zz` / `zb`  | Align cursor to top/center/bottom of screen |

---

## ?? Editing Essentials

### Insert & Replace

| Command   | Description                            |
| --------- | -------------------------------------- |
| `i` / `a` | Insert before/after cursor             |
| `I` / `A` | Insert at line start/end               |
| `o` / `O` | New line below/above                   |
| `r` / `R` | Replace character / Enter replace mode |

### Delete, Change, Yank

| Command        | Description                          |
| -------------- | ------------------------------------ |
| `x` / `X`      | Delete character under/before cursor |
| `dw` / `dd`    | Delete word / line                   |
| `D` / `d$`     | Delete to end of line                |
| `cw` / `cc`    | Change word / line                   |
| `yy`           | Yank (copy) line                     |
| `p` / `P`      | Paste after/before cursor            |
| `u` / `Ctrl-r` | Undo / Redo                          |
| `.`            | Repeat last edit                     |

---

## ? Search & Replace

| Command                 | Description                               |
| ----------------------- | ----------------------------------------- |
| `/pattern` / `?pattern` | Search forward/backward                   |
| `n` / `N`               | Repeat search forward/backward            |
| `*` / `#`               | Search word under cursor forward/backward |
| `:%s/old/new/g`         | Replace **old** with **new** globally     |
| `:s/old/new/g`          | Replace in current line                   |
| `:%s/old/new/gc`        | Confirm each replacement                  |
| `:noh`                  | Clear search highlights                   |
| `gd` / `gD`             | Go to local/global definition (LSP)       |

---

## ?? Visual Mode & Text Objects

### Visual Selection

| Command              | Description                           |
| -------------------- | ------------------------------------- |
| `v` / `V` / `Ctrl-v` | Character/Line/Block mode             |
| `gv`                 | Reselect last visual area             |
| `o` / `O`            | Swap selection endpoint in block mode |

### Text Objects

| Command     | Scope                       |
| ----------- | --------------------------- |
| `iw` / `aw` | Inner/around word           |
| `i"` / `a"` | Inside/around quotes        |
| `i(` / `a(` | Inside/around parentheses   |
| `i{` / `a{` | Inside/around braces        |
| `ip` / `ap` | Inner/around paragraph      |
| `it` / `at` | Inside/around HTML/XML tags |

---

## ? Files, Buffers, Windows, Tabs

### File & Buffer Commands

| Command               | Description                     |
| --------------------- | ------------------------------- |
| `:e {file}`           | Open file                       |
| `:w` / `:w!`          | Save / Force-save               |
| `:wq` / `ZZ`          | Save and quit                   |
| `:q` / `:q!`          | Quit / Force-quit               |
| `:ls`                 | List buffers                    |
| `:b{n}` / `:b {name}` | Switch to buffer by number/name |
| `:bn` / `:bp`         | Next/previous buffer            |
| `:bd`                 | Close buffer                    |

### Window & Tab Management

| Command                | Description                             |
| ---------------------- | --------------------------------------- |
| `:vsp` / `:sp`         | Vertical/horizontal split               |
| `Ctrl-w hjkl`          | Navigate between splits                 |
| `Ctrl-w =` / `+` / `-` | Equalize/Increase/Decrease split height |
| `:tabnew` / `:tabc`    | New tab / Close tab                     |
| `gt` / `gT`            | Next/previous tab                       |

---

## ? Marks & Jumps

| Command             | Description                               |
| ------------------- | ----------------------------------------- |
| `m{a-z}`            | Set local mark (a-z)                      |
| `m{A-Z}`            | Set global mark (A-Z)                     |
| `'{mark}`           | Jump to line of mark                      |
| `` `{mark} ``       | Jump to exact position of mark            |
| `Ctrl-o` / `Ctrl-i` | Navigate backward/forward in jump history |

---

## ? Advanced Power Moves

### Macros & Counters

| Command             | Description                             |
| ------------------- | --------------------------------------- |
| `qa` → edits → `q`  | Record macro to register **a**          |
| `@a`                | Execute macro in register **a**         |
| `@@`                | Repeat last macro                       |
| `Ctrl-a` / `Ctrl-x` | Increment/Decrement number under cursor |

### LSP & Plugins

| Command                 | Description                            |
| ----------------------- | -------------------------------------- |
| `:LspInfo`              | Check active language servers          |
| `:Telescope find_files` | Fuzzy file search (requires plugin)    |
| `:TSInstall {lang}`     | Install Treesitter parser for **lang** |
| `:term`                 | Open terminal buffer                   |

---

## ? Operator + Motion Combos

| Combo                       | Action                   | Example                    |
| --------------------------- | ------------------------ | -------------------------- |
| `d{motion}`                 | Delete                   | `d2w` (delete 2 words)     |
| `c{motion}`                 | Change (delete + insert) | `ci"` (edit inside quotes) |
| `y{motion}`                 | Yank                     | `y$` (copy to line end)    |
| `>{motion}` / `<{motion}`   | Indent/Unindent          | `>j` (indent next line)    |
| `gu{motion}` / `gU{motion}` | Lowercase/Uppercase      | `gUiw` (uppercase word)    |

---

## ?? Advanced Features

### Folding

| Command      | Description          |
| ------------ | -------------------- |
| `zf{motion}` | Create fold          |
| `zo` / `zc`  | Open/Close fold      |
| `zR` / `zM`  | Open/Close all folds |

### Terminal & Diagnostics

| Command                            | Description              |
| ---------------------------------- | ------------------------ |
| `Ctrl-\` → `Ctrl-n`                | Exit terminal mode       |
| `:lua vim.diagnostic.open_float()` | Show error details (LSP) |

---

## ? Pro Tips

1. **Counts**: `5j` moves down 5 lines; `3dw` deletes 3 words.
2. **Repeat**: Use `.` to redo the last edit.
3. **Visual Block**: `Ctrl-v` → select columns → `I` to insert on multiple lines.
4. **Text Objects**: Combine with operators (e.g., `dap` = delete paragraph).
5. **Macros**: Record with `qa`, execute with `@a`, chain with `:argdo normal @a`.

---

## ? Motion Mastery

**Syntax**: `[count][operator][motion]`  
*Example: `d2w` deletes 2 words.*

### Key Motions

| Motion    | Description              | Example                    |
| --------- | ------------------------ | -------------------------- |
| `f{char}` | Jump to **char** on line | `dt.` (delete until `.`)   |
| `}`       | Next paragraph           | `y}` (yank paragraph)      |
| `%`       | Jump to matching bracket | `d%` (delete bracket pair) |

### Text Objects

| Object | Scope              | Example                |
| ------ | ------------------ | ---------------------- |
| `iw`   | Inner word         | `ciw` (change word)    |
| `i(`   | Inside parentheses | `di(` (delete content) |
| `ip`   | Inner paragraph    | `yip` (yank paragraph) |

---

## ? C Code Refactoring Example

### Original Code

```c
int compute_sum(int a, int b) {  
    int result = a + b;  
    printf("Result is %d\n", result);  
    return result;  
}  
```

### Refactor Workflow

1. **Rename Function**: `ciw` on `compute_sum` → Type `add_numbers`.
2. **Update printf**: `f(` → `ci(` → Replace with `fprintf(stderr, ...)`.
3. **Add Comment**: Navigate to `return` with `/return` → `O` → Insert `// Log result`.

### Result

```c
int add_numbers(int a, int b) {  
    int result = a + b;  
    fprintf(stderr, "Result is %d\n", result);  
    // Log result  
    return result;  
}  
```

---

## ? Macro Automation

### Record a Macro

1. Start: `qa` at function name.
2. Rename: `ciw` → `add_numbers` → `<Esc>`.
3. Update printf: `/printf` → Enter → `f(` → `ci(` → `fprintf(stderr, ...)` → `<Esc>`.
4. Add Comment: `/return` → Enter → `O` → `// Log result` → `<Esc>`.
5. Stop: `q`.

### Execute Macro

- Single use: `@a`
- Batch: `:argdo normal @a | write`

### Pro Tips

- Use precise search patterns (e.g., `/printf(\s*"Result`).
- Test macros with `:nnoremap <leader>t :%norm! @a<CR>`.

---

? **Next Steps**: Run `:Tutor` for guided practice or `:help nvim` for full docs!
