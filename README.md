# ScienceReference

ScienceReference is a curated starter library of scientific constants and
formulas for use as offline reference resources.

## Contents

- `catalog.json` lists each resource and its metadata.
- `constants/` contains one JSON file per physical constant.
- `formulas/` contains one JSON file per formula.

Catalog `fileUrl` values are paths relative to `catalog.json`. A client can
resolve them against the catalog URL to download a selected resource.

## Resource formats

Each catalog entry has a stable `id`, a display `name`, a `type`, a `version`,
and a download path. Each resource file includes its stable `id`, display
`name`, `type`, and scientific `source`. Constant resources use
`anql-constant+json`; formula resources use `anql-formula+json`.

Formula `expression` values use ordinary arithmetic operators (`+`, `-`, `*`,
`/`) and `^` for exponentiation. Symbols in `variables` are the identifiers
used by the expression. `latex` is for display and is not an executable
expression.

All values use SI units unless the resource states otherwise. Formula conditions
describe the assumptions under which the relation applies. The scientific
source is linked on each resource; the JSON curation and original descriptions
in this repository are provided under the MIT license. External sources retain
their own terms.

## Validation

All `.json` files must parse as JSON. When adding or changing a resource, update
its entry in `catalog.json` and preserve existing resource IDs. Resource URLs
should be immutable when published; use a versioned repository tag or release
for public catalog hosting.
