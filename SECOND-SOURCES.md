# SECOND sources and provenance

Source checks were reviewed on 2026-10-23.

## Original sources

- Official SECOND project page: https://captain-whu.github.io/SCD/
- Original data download linked directly by that page: https://drive.google.com/file/d/1mN8jzCKKK27p3ODGoDgepjiRYGQpB34u/view?usp=sharing
- Official project repository: https://github.com/CAPTAIN-WHU/SCD
- Official repository license: https://github.com/CAPTAIN-WHU/SCD/blob/main/LICENSE
- Original authors' paper page: https://arxiv.org/abs/2010.05687
- Published paper DOI: https://doi.org/10.1109/TGRS.2021.3113912

Original authors: Kunping Yang, Gui-Song Xia, Zicheng Liu, Bo Du, Wen Yang, Marcello Pelillo and Liangpei Zhang. The arXiv/project title is *Semantic Change Detection with Asymmetric Siamese Networks*. The published paper title is *Asymmetric Siamese Networks for Semantic Change Detection in Aerial Images*.

## Dataset partition provenance

The original project describes 4,662 paired samples in total. The directory metadata of the official download were inspected read-only: `SECOND_train_set.rar` contains 2,968 paired samples across `im1`, `im2`, `label1` and `label2`; the separate `SECOND_total_test.zip` contains 1,694 paired samples. The supplied `list/train.txt` (2,375 IDs) and `list/test.txt` (593 IDs) form a repartition of the 2,968-sample training pool. Their union was checked against every official training-pool ID in all four directory records and matched exactly. The 593-sample list is not the official 1,694-sample test set.

The local data checksum manifest covers exactly those 2,968 sample IDs in each of `A`, `B`, `label1` and `label2`. The local directory roles `A`/`B` correspond to official `im1`/`im2`. The manifest records the local bytes used for the research, with no claim of a new full-pixel comparison against the downloaded official archive. No sampling seed or generation history is reconstructed from the lists.

## Redistribution scope

The official project repository has an Apache-2.0 license. The image and annotation archive is hosted externally on Google Drive. The reviewed project page, repository materials, paper text and complete archive directory records did not establish an explicit redistribution license for that external data archive. No LICENSE, README or NOTICE file was found in the inspected data archive directories. Absence of such a file is not proof that redistribution is forbidden. Until the external data license scope is clarified, this package provides the existing split lists, checksums and source links without mirroring the images or labels and without assigning a new data license.

No private contact details, absolute local paths or algorithm source files are included. No source image, annotation or split list was modified during this packaging operation. The downloaded data and any associated terms remain attributable to their original authors.
