# OTP banka Srbija — acquirer set

The set the Polako SDK renders for merchants acquired through **OTP banka**.

## Source requirement

*Uputstvo za rad Internet prodajnog mesta, OTP banka Srbija, 05.2026*,
section **2.1 Brendiranje** (file: `Uputstvo za rad IPM SRB_05.2026.pdf`), and
the bank-supplied `Logo.zip`, kept unchanged under `source/`.

The merchant must show, in the unchanged form supplied by the bank:

| Group | Marks | Mandatory link |
|---|---|---|
| Bank | OTP banka | https://www.otpbanka.rs/ |
| Program marks | Visa Secure, Mastercard ID Check | Visa Secure → https://rs.visa.com/pay-with-visa/security-and-assistance/protected-everywhere.html ; ID Check → https://developer.mastercard.com/product/identity-check/ |
| Acceptance marks | Visa, Mastercard, Maestro, DinaCard | — |

Where: the home page and the page where the buyer picks a payment method.
No AmEx, no IPS, no DinaCard Secure in this set — OTP does not ask for them
and "unchanged form" means we do not add marks the bank did not supply.

Layout rules (identical to AltaPay's): program marks grouped separately from
acceptance marks; one program group per page, a logo must not repeat on a
page; acceptance marks 37×23 … 180×113 px; program marks 60 … 155 px wide;
all marks in a group the same size; gap between the groups at least four
program-mark widths. Marks may be shown monochrome or in colour.

The bank's own grouping examples are `source/Primeri brendiranja vodoravno.jpg`
(one row) and `source/Primeri brendiranja uspravno.jpg` (stacked). The audit
checklist at the end of the instruction has two lines for this set:
*Ispravno prikazani logotipi kartica (2.1)* and *Ispravni linkovi logoa
sigurnosnih programa i banke (2.1)*.

## Files

`svg/` is what the SDK loads. `otpbanka-on-light.svg` is vectorised from the
bank's `OPT logo za dokumenta PRINT COLOR.pdf` (pure vector, two fills:
`#006c40` and `#4fb848`) and reframed onto the 50-unit canvas, glyph between
y=7 and y=43, 10 units of side air, viewBox `0 0 208 50`.
`otpbanka-on-dark.svg` keeps the light-green glyphs and turns the dark-green
ones white — the bank supplied no reverse variant and allows monochrome, so
this is the same treatment Banca Intesa's mark gets on dark footers. If the
bank objects at audit, drop the dark file and point the SDK at the colour
one (`t: 'light'` in the SDK's icon definition).

The scheme marks (Visa, Mastercard, Maestro, DinaCard, Visa Secure, ID Check)
are the same reframed files as in `acquirers/altapay/`; OTP's `Logo.zip`
ships the same official artwork, see `source/`.
