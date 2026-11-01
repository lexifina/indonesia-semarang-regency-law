# How this repository was made (Semarang Regency (Indonesia))

This file is written by the build on 2026-11-01, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| JDIH Kabupaten Semarang (Bagian Hukum Sekretariat Daerah Kabupaten Semarang): Peraturan Daerah, each the published copy (salinan) as a PDF with a text layer | <https://jdih.semarangkab.go.id> | 2026-11-01 | Peraturan Daerah of Kabupaten Semarang as published (salinan) on https://jdih.semarangkab.go.id. Undang-Undang Nomor 28 Tahun 2014 tentang Hak Cipta, Pasal 42: "Tidak ada Hak Cipta atas hasil karya berupa: a. hasil rapat terbuka lembaga negara; b. peraturan perundang-undangan; c. pidato kenegaraan atau pidato pejabat Pemerintah; d. putusan pengadilan atau penetapan hakim; dan e. kitab suci atau simbol keagamaan." (There is no copyright in ... b. laws and regulations.) A Peraturan Daerah Kabupaten/Kota is one of the peraturan perundang-undangan listed in Pasal 7(1) huruf g of Undang-Undang Nomor 12 Tahun 2011. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `perda-2025-001-pengelolaan-tempat-pemakaman` | PERATURAN DAERAH KABUPATEN SEMARANG NOMOR 1 TAHUN 2025 TENTANG PENGELOLAAN TEMPAT PEMAKAMAN | 1 | 2025-02-12 to 2025-02-12 |
| `perda-2025-007-pencabutan-peraturan-daerah-nomor-26-tahun-2016-tentang-pengelolaan` | PERATURAN DAERAH KABUPATEN SEMARANG NOMOR 7 TAHUN 2025 TENTANG PENCABUTAN PERATURAN DAERAH NOMOR 26 TAHUN 2016 TENTANG PENGELOLAAN LIMBAH BAHAN BERBAHAYA DAN BERACUN | 1 | 2025-09-01 to 2025-09-01 |
| `perda-2025-008-pencabutan-peraturan-daerah-nomor-5-tahun-2016-tentang-izin` | PERATURAN DAERAH KABUPATEN SEMARANG NOMOR 8 TAHUN 2025 TENTANG PENCABUTAN PERATURAN DAERAH NOMOR 5 TAHUN 2016 TENTANG IZIN PEMBUANGAN AIR LIMBAH DAN IZIN PEMANFAATAN AIR LIMBAH | 1 | 2025-09-01 to 2025-09-01 |

The build made 3 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-01.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 3 tags.

## Dates

Each commit is dated at noon (Asia/Jakarta) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: A Peraturan Daerah takes effect on the day its last Pasal names; almost always "mulai berlaku pada tanggal diundangkan", the day it is promulgated in the Lembaran Daerah. https://jdih.semarangkab.go.id

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `d95916e2298f582e69504b872c8a3bf9f72c4ce3331c79c128d9b603e0e11d29` (62106 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `35388bee5aa05369f7da68f5a8fa015ea8d442b8`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

3 versions of 3 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Oldest version available: each Peraturan Daerah is one version, its text as enacted (the published copy, salinan), credited to the JDIH publisher (first_law null), not to an amending law. An amending Perda is recorded as an act of its own; its changes are not replayed into the Perda it amends, and a repeal is not applied.
- Dated by the day the Perda takes effect under its own last Pasal: the promulgation day (diundangkan, printed in the closing) when it says "mulai berlaku pada tanggal diundangkan", or the calendar day it names. A Perda whose commencement is a period or another event is left out for now.
- Parts are added oldest first, so each part only adds history after the last one.
- Units: a-pembukaan (heading, preamble, enacting words), one file per Pasal (chapter, part and paragraph headings printed between two Pasal stay at the end of the earlier one, in printed order), z1-penutup (promulgation order, signatures, Lembaran Daerah number, certification), z2-penjelasan (the elucidation) and z3-lampiran (the annex) where printed. One paragraph per line.
- Left out of the text: page numbers and the "SALINAN" stamp line. Text-layer PDFs only (no OCR): scans are left out.
- Every Perda is checked by a second PDF reader (pdftotext): each paragraph of the record, letters and digits only, must be one unbroken stretch of the PDF, and together they must cover the whole PDF with nothing left over except page numbers and the stamp. A Perda that fails is left out.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the PDFs published on JDIH.
