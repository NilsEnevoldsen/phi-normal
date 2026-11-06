# Phi normal

A font for the Phyrexian script from *Magic: The Gathering*, by Phie (Stas.tk).

## Download prebuilt fonts

Built fonts (TTF, WOFF, WOFF2) are attached to each [release](../../releases).

## Build fonts yourself

`src/` is the font as [TTX](https://fonttools.readthedocs.io/en/latest/ttx.html), the
XML form of an OpenType font from fontTools, split into one file per table and one per
glyph. To build with [uv](https://docs.astral.sh/uv/):

```sh
uvx --from "fonttools[woff]" ttx -o Phi_normal_sf.ttf src/Phi_normal.ttx
uvx --from "fonttools[woff]" ttx --flavor woff2 -o Phi_normal_sf.woff2 src/Phi_normal.ttx
```

## History

Phi normal grew out of an earlier font by the same author, **Phi gibberish**
(`Phi_horizontal_gbrsh` and `Phi_vertical_gbrsh`), which Scryfall used to display the
text of Phyrexian-language cards. Scryfall chose it for its higher-fidelity glyphs and
permissive Open Font License. Like most Phyrexian fonts at the time, it used the
fan-made English Letters Are Just Codes (ELAJC) or "gibberish" encoding, which mapped
Phyrexian characters onto Latin letters. (There are no Phyrexian codepoints in Unicode…
yet.)

Then Wizards of the Coast published an official orthography for Phyrexian, closer to a
phonetic alphabet than the gibberish encoding. Phie created **Phi normal** with the new
encoding, and Scryfall planned to switch to it. A few bugs, mostly around whitespace,
held up the switch, and meanwhile Phie announced a move away from *Magic* projects,
leaving Phi normal 3.0 as the last release.

This repository forks the font from Phie's 3.0 TTF. It fixes those bugs and makes the
changes Scryfall needs to set its whole Phyrexian corpus in the new orthography. For
example, while a literal Latin colon is not part of the Phyrexian script, Scryfall
needs it present in the font to render planeswalker loyalty abilities.

## License

SIL Open Font License 1.1; see [OFL.txt](OFL.txt).
