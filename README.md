# Multi-Sheet Performance Analyzer

A browser-based teacher analytics and result portal for analyzing student exam results from Excel workbooks.

## Features

- **Multi-sheet support** — load an `.xlsx` / `.xls` workbook and switch between class sheets via tabs
- **Student-wise analysis** — view each student's subject marks, grades, and pass/fail status on individual cards
- **Subject performance metrics** — see pass rate, fail count, and a visual progress bar for every subject
- **Smart filtering** — filter students by Full Pass, 1 Subject Fail, or Multiple Fails; live name/reg-no search
- **Subject count validation** — enter the expected total subjects to flag students with missing records
- **KPI summary cards** — at-a-glance totals for students, full passes, 1-subject fails, and pass percentage
- **PDF export** — export filtered student lists (All / Full Pass / 1 Subject Fail / Multiple Fails) or individual student reports as PDFs

## Usage

1. Open `result.html` in any modern browser (Chrome, Edge, Firefox).
2. Click **Upload Excel** and select your `.xlsx` or `.xls` result file.
3. Click a sheet tab to load that class.
4. *(Optional)* Enter the **Total Subjects** count to validate completeness.
5. Use the **Student-Wise Analysis** or **Subject Performance Metrics** tabs to explore data.
6. Use the **Export PDF** button to download filtered reports.

## Excel File Format

Each row in a sheet should represent one subject record for one student:

| Column | Index | Description |
|--------|-------|-------------|
| Reg No | 0 | Student registration number |
| Name | 1 | Student full name |
| Branch | 2 | Department / stream |
| Subject | 4 | Subject name |
| Marks | 8 | Marks obtained |
| Grade | 9 | Letter grade |
| Result | 10 | `P` for pass, `F` for fail |

Rows where column 0 is non-numeric or the row has fewer than 6 columns are skipped automatically.

## Absent / Missing Markers

The following values are treated as **absent** (not counted as fail):
`AB`, `WH`, `NA`, `N/A`, `--`, *(empty)*, `ABSENT`, `DNE`, `DNP`

## Dependencies (loaded via CDN)

- [Tailwind CSS v4](https://tailwindcss.com/)
- [SheetJS (xlsx)](https://sheetjs.com/) — Excel parsing
- [jsPDF](https://github.com/parallax/jsPDF) — PDF generation
- [jsPDF AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable) — table rendering in PDFs

No build step or server required — everything runs client-side.
