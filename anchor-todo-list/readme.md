# Anchor Todo List

Based on the [Building A To Do List with Anchor](https://calyptus.co/lessons/building-a-to-do-list-with-anchor/) lesson, this project shows how to mint your first NFT on the Solana blockchain using [Anchor](https://www.anchor-lang.com/).

## Table of Contents
- [Anchor Todo List](#anchor-todo-list)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)

## Getting Started

To use this fork, you need to have [yarn](https://yarnpkg.com/getting-started/install), [Anchor](https://www.anchor-lang.com/docs/installation) and the [Solana cli suite](https://solana.com/developers/guides/getstarted/setup-local-development) installed on your machine. 

It is highly recommended that you start this project from scratch, following along with the tutorial. 

To use the fork, follow the steps outlined below: 

1. Clone your forked repo.

```bash
git clone https://github.com/<YOUR-USERNAME>/anchor-todo-list
```

2. Change directory into the root of your cloned repo and install missing node packages

```bash
yarn install
```

**NOTE:** You must use yarn to install the dependencies. If you use a different package manager, you will run into issues minting the NFT.

3. Build your anchor project.

```bash
anchor build
```

4. List the project deployment keys and copy the address to a clipboard

```bash
anchor keys list
```

5. Update your [`Anchor.toml`](Anchor.toml) file, by using the address generated in the previous step. 

```toml
[programs.devnet]
todo_list_app = "<ADD YOUR ADDRESS HERE>"
```

6. Update your [`lib.rs`](programs/todo-list-app/src/lib.rs) file by adding the the address generated in step 4 to the `declare_id!()` macro

```rust
use anchor_lang::prelude::*;

declare_id!("<PLACE YOUR ADDRESS HERE>");

#[program]
pub mod todo_list_app {
    // snip
```

