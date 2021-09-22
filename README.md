This is a simple plugin for Vim that will allow you to use OpenAI Codex.
To use this plugin you need to have access to OpenAI's [Codex API](https://openai.com/blog/openai-codex/).

## Installation

# TODO add path config
Create the file `~/.openai/credentials.json` and add your credentials to is like so:

```json
{
  "organizationId": "",
  "secretKey": ""
}
```

# TODO auto install package?
You alse need to have python `openai` present in your nvim python provider environment.

Install the pluguin with packer:

```lua
use {
  `naripok/vim_codex`
}
```

## Usage

The plugin provides a `CreateCompletion` command which you can call by default using the mapping
`<Leader>co`.
You can give the `CreateCompletion` command the number of tokens it should produce as an argument, e.g. `CreateCompletion 1000`.
If you want to just complete the current line, run `CreateCompletionLine`.

To complete the current text from insert and normal mode using Ctrl+x, you can add the following
lines to your .vimrc::

```
nnoremap  <C-x> :CreateCompletion<CR>
inoremap  <C-x> <Esc>li<C-g>u<Esc>l:CreateCompletion<CR>
```
