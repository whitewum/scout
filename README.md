# SCOUT: A Single-Round, Fixed-Budget Probe for Continuous Reconciliation in Heterogeneous Replication

This repository contains the LaTeX source and compiled PDFs of the SCOUT manuscript.

- [`scout.pdf`](scout.pdf): main paper
- [`scout-supplement.pdf`](scout-supplement.pdf): supplemental material

SCOUT is a diagnostic probe for continuous reconciliation over black-box replicas. Both sides insert keys into a signed count table; from a single sketch exchange, a centered (drift-removed) energy statistic computed on the count differences is used to estimate the discrepancy size, to decide whether narrow verification is likely to pay off, and to locate the data segments that merit follow-up verification.

## Building

```sh
mkdir -p build
pdflatex -output-directory=build -jobname=fast-en main.tex
pdflatex -output-directory=build supplement.tex
(cd build && BIBINPUTS=..: bibtex fast-en && BIBINPUTS=..: bibtex supplement)
# run both pdflatex commands two or three more times to resolve cross-document references
```

The main paper and the supplement reference each other through `xr-hyper`, so both must be compiled in the same `build/` directory.

## Author

Min Wu, Hangzhou Dianzi University (wumin@hdu.edu.cn, [@whitewum](https://github.com/whitewum))

## License

The LaTeX sources and figures are released under the MIT License (see [`LICENSE`](LICENSE)). The template files `usenix2019_v3.sty`, `usenix.sty` and `acm.bst` belong to their respective owners.
