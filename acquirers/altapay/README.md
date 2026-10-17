# AltaPay (Alta Pay Group) + Banca Intesa — acquirer set

The set the Polako SDK renders for merchants acquired through **AltaPay**
(e-money institution, MSU PGW) with **Banca Intesa** as the card acquirer.
This is the set that passed the Banca Intesa site audit in 2026-08.

## Source requirement

*Prilog 3 — Uputstvo za rad EPM (e-commerce i IPS), Alta Group, 01.04.2024*,
section **1.1.11 Brendiranje** (Google Drive: `Prilog 3 - Uputstvo za rad EPM - e-commerce i IPS - AG.docx`).

The merchant must show, in the unchanged form supplied by the institution:

| Group | Marks | Mandatory link |
|---|---|---|
| Institution | AltaPay | https://altapay.rs |
| Acquirer | Banca Intesa | https://www.bancaintesa.rs |
| Program marks | Verified by Visa → **Visa Secure**, Mastercard SecureCode → **Mastercard ID Check**, AmEx SafeKey, DinaCard Secure | Visa Secure → https://rs.visa.com/pay-with-visa/security-and-assistance/protected-everywhere.html ; ID Check → https://www.mastercard.rs/sr-rs/korisnici/pronadite-karticu.html (the link Banca Intesa's audit required; Alta's own PDF still cites the retired SecureCode URL) |
| Acceptance marks | Visa, Mastercard, Maestro, DinaCard, American Express | — |

Where: home page, every place the buyer picks a payment method, every place
the merchant mentions accepted brands, the card-entry (HPP) page.

Layout rules shared with every Serbian acquirer: program marks in a separate
group from acceptance marks, never paired or swapped; one program group per
page; acceptance marks 37×23 … 180×113 px, program marks 60 … 155 px wide, all
marks in a group the same size; gap between the two groups at least four
program-mark widths.

**Known gap**: the instruction also lists the *IPS* logo (instant payments).
It is not in this set because Polako does not expose IPS on the AltaPay rail
yet. Add it the day IPS is switched on.

## Files

`svg/` is what the SDK loads (50-unit canvas, glyph between y=7 and y=43).
`png/` are the Banca-Intesa-supplied raster variants (brand packs that ship
raster only) plus the three `rs-alta-*` combined strips Alta sent for
merchants who paste a single image.
