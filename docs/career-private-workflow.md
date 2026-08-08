# `career-private` workflow

`career-private` is the private workspace used to populate this generic
template. It owns all personal information and generated application documents;
this public package owns layout code and generic examples only.

## Data composition

The private workspace keeps `data/shokumu-core.typ` as the canonical
professional record. Its private profile module supplies identity, contact, and
photo content only to the rirekisho data module. The photo is created as Typst
content in that private module and is then passed to `rirekisho(data)`; the
public package never resolves a private file path.

The shokumu modules compose the canonical record into a private master view, a
public-safe view, and role-focused views. Small modules under `applications/`
change only the motivation, selected records, order, keywords, or self-PR for a
specific application. They do not copy the complete layout or canonical record.

## Build and safety boundary

`documents/manifest.json` declares each document entrypoint, output, font path,
and visibility. The private build uses a workspace-owned Noto font directory;
the public package does not distribute those fonts.

`scripts/validate-private.mjs` follows Typst imports for the public-safe
document and rejects private profile, application-profile, photo, address,
phone, and private-email references. Run validation before building or
promoting a public-safe output.

```sh
npm run validate
npm run build
```

This workflow deliberately keeps values, private assets, generated PDFs, and
evidence records out of the public template repository.
