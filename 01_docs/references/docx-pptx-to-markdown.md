# Converting files to Markdown format

Use `Pandoc` for docx, and `markitdown` for pptx. Spot-check the output against
the source before treating it as a clean copy. Note, complex layouts and text
boxes are often flattened or dropped. Slide design and animations aren't
represented in markdown at all — text only

- **Pandoc:** best fidelity for headings, lists, tables, footnotes. Pandoc can't
  read pptx as input (only writes it). Use `markitdown` instead. Pandoc handles
  nested lists, tables, footnotes, and basic styles cleanly. Text boxes, tracked
  changes, and comments won't survive — review the output rather than assuming
  1:1 fidelity.

```zsh
pandoc input.docx -o output.md
```

- **Images:** are extracted as separate files, not inlined. To pull embedded
  images out to a folder instead of losing them:

```zsh
pandoc input.docx -o output.md --extract-media=./media
```

- **markitdown:** covers docx and pptx, but its docx output is plainer than
  Pandoc's — fewer style options, no media-extraction control. `markitdown`
  turns each slide's text and speaker notes into a markdown section
  (`## Slide N`). It also handles docx, xlsx, and pdf, if a single tool across
  formats is worth the fidelity trade-off.

```zsh
markitdown input.pptx > output.md
```

## Installing tools

### Pandoc

```zsh
brew install pandoc   # if not already installed
```

## Markitdown

```zsh
# run once
brew install pipx    # upgrades pipx
pipx ensurepath      # adds pipx's bin dir to PATH, only needed once
pipx install markitdown
```

### Python aside about pipx

`pipx` installs Python CLI tools, each into its own isolated virtual
environment, but exposes the command globally in PATH — giving global access
without global package pollution.

Contrast with plain `pip install <tool>`: outside a venv, that either fails on
newer Python/Homebrew setups (externally-managed-environment error) or dumps the
package into one shared environment where its dependencies can collide with
other tools' dependencies. `pip install <tool>` inside a venv works cleanly, but
then the tool only exists while that venv is active.

pipx sidesteps both: `pipx install markitdown` creates a dedicated venv just for
markitdown, symlinks its entry point (the `markitdown` command) into a shared
bin directory on your PATH, and you never think about which venv you're in to
run it. Under the hood it's still pip and venv — pipx is just the workflow layer
that automates "one isolated env per tool, command exposed globally."
