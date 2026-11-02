# Toner Cartridge Cross-Reference Dataset

A free, machine-readable cross-reference between **printer models** and **compatible toner / copier cartridges**, covering 4,512 cartridge families and 4,795 printer models across 25 printer brands.

Maintained by [Chusi Print](https://chusiprint.com) — a B2B sourcing partner for compatible printer consumables based in Zhuhai, China.

**Interactive version:** <https://chusiprint.com/tools/toner-cross-reference>

## Why this exists

Compatibility data is normally locked inside vendor catalogues or scattered across retail pages. This dataset puts the three fields that actually decide a purchase — **which cartridge fits which printer**, **whether the unit ships with a chip**, and **the declared page yield** — in one place, with a region field that distinguishes OEM regional codes (for example HP 58A / 59A / 76A fit the same machine but ship to different markets).

## Files

| File | Description |
| --- | --- |
| `data/toner-cross-reference.csv` | One row per cartridge family. UTF-8 with BOM, opens directly in Excel. |
| `data/xref.json` | The same data plus an inverted printer index (`inv`) and OEM-code alias table (`alias`), used by the web tool. |

## Fields

| Field | Meaning |
| --- | --- |
| `oem_code` | OEM code of the cartridge family, e.g. `CF280A`, `TN-1035`, `TK-1170` |
| `brand` | Printer brand the cartridge is built for |
| `colour` | Mono, Black, Cyan, Magenta, Yellow … |
| `region` | Region build of the cartridge, e.g. `Europe`, `North America`, `Global (excl. JP)` |
| `chip` | `with chip`, `without chip`, or `not specified` |
| `declared_yield_pages` | Declared page yield, generally to ISO/IEC 19752 (mono) or 19798 (colour) at 5% coverage |
| `compatible_printers` | Semi-colon separated printer models listed as compatible |
| `printer_count` | Number of printer models on that row |
| `product_url` | Product page for that family on chusiprint.com |

## Coverage at a glance

- 4,512 cartridge families
- 4,795 distinct printer models
- 25 printer brands
- 3,497 families ship with a chip, 507 without, the remainder unspecified
- Largest brand groups: Kyocera (878), HP (648), Lexmark (643), Brother (498), Xerox (388), Canon (366), Ricoh (269), Pantum (200)

## Method and limitations

The data is generated from Chusi Print's own supply catalogue, which is maintained against OEM documentation and verified by print testing on reference machines for each family. Two honest caveats:

1. **It covers the models we supply**, not every cartridge on the market. A missing printer means we do not stock that family, not that the family does not exist.
2. **Compatibility strings are normalised from catalogue text.** Series shorthand such as `M401d/M401dn/M401n` is expanded to individual models, but a minority of entries remain coarser than the OEM's own list — always confirm the exact model before a bulk order.

Field-level corrections are welcome as issues or pull requests.

## License

Released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You may use, redistribute and build on it commercially, including in internal tools and published articles, as long as you credit the source and link back to <https://chusiprint.com/tools/toner-cross-reference>.

Suggested attribution:

> Source: Chusi Print, *Toner Cartridge Cross-Reference Dataset* (2026), https://chusiprint.com/tools/toner-cross-reference

## Keywords

toner cross reference, printer cartridge compatibility, which toner fits my printer, toner cartridge chip, cartridge cross reference chart, OEM toner code lookup, printer consumables dataset
