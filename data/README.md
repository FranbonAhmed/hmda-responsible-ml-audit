# Data Setup

Raw HMDA data are intentionally excluded from GitHub because the source file is large.

The source notebooks use the **2024 HMDA Loan Application Register (LAR)** and reference the CFPB / FFIEC 2024 dynamic national loan-level dataset page in code comments.

The portfolio notebooks look for an extracted `.txt` file in:

```text
data/raw/
```

If none is present, they use the same shared Google Drive file ID configured in the original team notebooks and extract the archive into `data/raw/`.

Expected source format: pipe-delimited HMDA LAR text file.

The source modeling workflow ultimately retains 3,962,464 cleaned applications for the saved analysis.
