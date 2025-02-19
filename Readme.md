TOML Sort
==========

Simple tool for sorting toml files via cli or ci. It was made with `Cargo.toml` files in mind but is likely useful elsewhere.

## CLI Usage

### Installation

```sh
cargo install --git https://github.com/Off-Narrative-Labs/toml_sort
```

### Sorting files

```sh
toml-sort [files]
```

### Checking sorted files

```sh
toml-sort --check [files]
```

## GitHub Action

This will only check `./Cargo.toml`:  
```yaml
- uses: Off-Narrative-Labs/toml_sort@v1
```

If you want the action to check all the TOML files, then you can use:

```yaml
- uses: Off-Narrative-Labs/toml_sort@v1
  with:
    all: true
```

🆕 If you want the action to check all the TOML files that match a certain name:

```yaml
- uses: Off-Narrative-Labs/toml_sort@v1
  with:
    all: true
    match: "Cargo.toml"
```

In alternative, if you want to check only a certain set of files:

```yaml
- uses: Off-Narrative-Labs/toml_sort@v1
  with:
    files: Cargo.toml foo/Cargo.toml bar/Cargo.toml
```


## Example

Look no further. This repository itself uses toml sort. Check out the `toml-sort.toml` file right here in the repository.

## Categories

One major motivator for developing this tool is that it will sort your dependencies lexicographically while still respecting your commented in section headings.

```toml
[dependencies]
# Common ones
clap = "..."
serde = "..."

# Private things
a-secret-thing = "..."
other-unpublished-stuff = "..."
private-crate = "..."
```
