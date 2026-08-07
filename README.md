# rirekisho-ofa

A generic, two-page A4 Japanese 履歴書 (rirekisho) template for Typst. It follows
the current Ministry of Health, Labour and Welfare (MHLW) form structure while
keeping legacy personal-status fields optional.

This repository intentionally contains placeholder data only. Do not add real
names, addresses, employment history, contact details, photographs, or completed
application PDFs here.

## Quick start

Install Typst 0.15.0, then compile the placeholder example with the bundled font:

```sh
typst compile --root . --ignore-system-fonts --font-path fonts examples/example.typ dist/rirekisho.pdf
```

The output must contain exactly two A4 pages. The photo slot is deliberately
empty in the example; private document repositories can provide a local image
path through the `photo` field.

## Template API

`src/rirekisho.typ` exports `rirekisho(data)`. The `data` dictionary accepts
identity, contact, history, qualification, motivation, and preferences fields.
Set `show-legacy-fields: true` only when an employer requests fields such as
spouse/dependent status, commute time, or a secondary contact.

## Fonts and license

`fonts/` contains Noto Sans CJK JP Regular and Bold, distributed under the SIL
Open Font License 1.1 in `fonts/OFL.txt`. The template source is MIT licensed;
see `LICENSE` and `NOTICE`.

## Acknowledgements

This template was informed by the following projects and guidance:

- [hadronic-rirekisho](https://typst.app/universe/package/hadronic-rirekisho/),
  a Japanese rirekisho template for Typst.
- [ShinoharaTa/typst-work-resume](https://github.com/ShinoharaTa/typst-work-resume),
  a useful Typst work-resume reference.
- Hello Work's [rirekisho and shokumu keirekisho guidance](https://www.hellowork.mhlw.go.jp/member/career_doc01.html?openExternalBrowser=1),
  including the Ministry of Health, Labour and Welfare (MHLW) rirekisho format.
- The MHLW's [fair-recruitment guidance](https://www.mhlw.go.jp/stf/seisakunitsuite/bunya/koyou_roudou/koyou/newpage_56780.html?media=10803&media=713),
  which informed the optional treatment of personal-status fields.

These sources are acknowledged as references and inspiration; this repository's
Typst source is independently maintained and released under its own license.
