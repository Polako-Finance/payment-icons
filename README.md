# Payment Icons

This repository contains a collection of optimized and/or redrawn SVG icons and logos for widely used payment systems.

> [!IMPORTANT]\
> This project is not affiliated with or endorsed by any brand included in this repository. All logos are trademarks of their respective owners.

## Layout

One folder per acquirer. Each holds the complete set a merchant on that
acquirer must show, so an auditor (and the SDK) look in exactly one place:

```
acquirers/altapay/   AltaPay + Banca Intesa set   — README lists the source instruction, marks, links
acquirers/otp/       OTP banka set                — same, plus the bank-supplied pack under source/
polako/              Polako Finance attribution mark
svg/, png/           LEGACY flat layout — frozen, do not add to it
```

Within an acquirer folder, `svg/` is what the Polako SDK loads from the CDN
(`https://cdn.jsdelivr.net/gh/Polako-Finance/payment-icons@main/acquirers/<slug>/svg/<name>-<variant>.svg`),
`png/` holds brands whose official pack is raster only, `source/` the
artwork as the bank delivered it. Variant suffixes: `on-light`, `on-dark`,
`universal`.

Every SVG sits on a 50-unit-tall canvas with the glyph between y=7 and
y=43 (36 units) so a row of marks reads at one visual height. Four files
deliberately crop the viewBox to the glyph (`mc-idcheck`, `visa-secure`,
`dinacard-secure`, `amex-safekey`); the SDK compensates in CSS.

The flat `svg/` and `png/` directories are kept only until the payment-blank
SDK that reads `acquirers/` is on production; the SDK before that build
hard-codes those paths. Delete them in the same release that retires it.

## Licenses, Copyrights & Trademarks

Below is a summary of the logos included and their respective usage terms or trademark status. Use responsibly.

| Brand                          | Trademark Holder              | Notes                           | Official Guidelines/Website                                                  |
|--------------------------------|-------------------------------|---------------------------------|------------------------------------------------------------------------------|
| **Alta Group**                 | Alta Pay Group                | Reframed for layout consistency | [Link](https://altapay.rs/en/about-us)                                       |
| **American Express**           | American Express Company      | Reframed for layout consistency | [Link](https://www.americanexpress.com/en-us/business/merchant/supplies/)    |
| **DinaCard**                   | National Bank of Serbia       | Reframed for layout consistency | [Link](https://dinacard.nbs.rs/english)                                      |
| **Banca Intesa**               | Intesa Sanpaolo S.p.A.        | Reframed for layout consistency | [Link](https://group.intesasanpaolo.com/en/about-us/our-brand)               |
| **Maestro**®                   | Mastercard International Inc. | Reframed for layout consistency | [Link](https://www.mastercard.com/brandcenter/us/en/brand-requirements.html) |
| **Mastercard**®                | Mastercard International Inc. | Reframed for layout consistency | [Link](https://www.mastercard.com/brandcenter/us/en/brand-requirements.html) |
| **OTP banka**                  | OTP banka Srbija a.d.         | Reframed for layout consistency | [Link](https://www.otpbanka.rs/)                                             |
| Mastercard **Identity Check**™ | Mastercard International Inc. | Reframed for layout consistency | [Link](https://www.mastercard.com/brandcenter/us/en/brand-requirements.html) |
| **Polako Finance**             | Polako Finance                | Reframed for layout consistency | [Link](https://polako-finance.com)                                           |
| **Visa**                       | Visa Inc.                     | Reframed for layout consistency | [Link](https://www.merchantsignage.visa.com/brandguidelines)                 |
| **Visa Secure**                | Visa Inc.                     | Reframed for layout consistency | [Link](https://www.merchantsignage.visa.com/brandguidelines)                 |

> Always check the official link before using a logo commercially or publicly.

This repository's code and optimization scripts are licensed under Creative Commons CC0 1.0 Universal.
