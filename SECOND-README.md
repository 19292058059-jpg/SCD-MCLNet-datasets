# SECOND research split lists and checksums

Prepared: 2026-10-23

This metadata package publishes the existing research partition of the official SECOND training pool: 2,375 training samples and 593 held-out samples. The original SECOND training pool contains 2,968 paired samples. The official dataset also has a separate 1,694-sample test set. The file named `list/test.txt` here refers to the 593-sample research split of the training pool; it is not the official SECOND test set.

The two supplied split-list files are distributed with their original bytes and ordering. No split was regenerated when preparing this package. Each line contains a five-digit sample ID without a file extension. The lists contain no duplicate IDs, have no intersection, and together cover all 2,968 IDs in the official training-pool directory records. The split-generation algorithm and random seed are not inferred from the existing lists.

## Package contents

```text
SECOND/
  list/train.txt                 2,375 sample IDs; original bytes
  list/test.txt                    593 sample IDs; original bytes
  DATA-MANIFEST-SHA256.txt       11,872 locally checked PNG checksums
  README.md
  SOURCES.md
  PROVENANCE.json
```

No image, label, model, training or preprocessing source files are included. The manifest describes 2,968 samples in each of `A`, `B`, `label1` and `label2`; it does not contain image or label pixels. Auxiliary local heatmap and overlay PNGs are outside the split and manifest scope.

## Obtain the original images and labels

Download SECOND from the original authors' project page: https://captain-whu.github.io/SCD/

Official Google Drive archive linked by that page: https://drive.google.com/file/d/1mN8jzCKKK27p3ODGoDgepjiRYGQpB34u/view?usp=sharing

The official archive contains `SECOND_train_set.rar` and a separate `SECOND_total_test.zip`. Use the 2,968-sample training pool with the lists in this package. In the local layout documented by the manifest, the official `im1` and `im2` directory roles correspond to `A` and `B`; labels use `label1` and `label2`. Matching sample IDs identify the four files for a pair. Each referenced local PNG is 512 x 512 and RGB, including the color-coded label PNGs.

The hashes record the exact local file bytes checked for the accompanying research. They identify those bytes and do not assert that this package has re-downloaded and verified every pixel file against the upstream archive. A checksum difference indicates different file bytes, even if an image looks the same. Preserve original files when preparing a matching data layout.

## Data access and license scope

The underlying SECOND imagery and annotations are not mirrored in this package because an explicit redistribution license for the externally hosted dataset has not been confirmed. The official GitHub repository contains an Apache-2.0 license, but the reviewed materials do not establish that it covers the separate Google Drive image and label archive. This is an unresolved scope question, not a claim that the authors prohibit redistribution. Obtain the data from the official source and review the original authors' current terms. This metadata package does not grant or change a license for the underlying data.

## Integrity and local checks

`DATA-MANIFEST-SHA256.txt` contains a SHA-256 checksum for each of 11,872 locally supplied core PNG files. Paths are relative to the data root, for example `A/00003.png`. After obtaining and arranging the data in that layout, place the manifest at the data root and run:

```sh
sha256sum -c DATA-MANIFEST-SHA256.txt
```

Original split-list SHA-256 values:

| File | SHA-256 |
| --- | --- |
| list/train.txt | `4dcec4f189da07f270b6ce6c56d943cead1e719332890729b1bf966c23aca676` |
| list/test.txt | `c2b4bac7fe93aee1f971b85409f72a81da5f7a39dbd412f32bdde04312e52a8e` |

The source split files and the 11,872 data-file checksums were checked without modifying the source data. The same-day local PNG audit verified PNG integrity and fully decoded all 11,876 stored PNGs, including four auxiliary visualization files; no decode errors were found. All 11,872 split-referenced PNGs are covered by this manifest. The audit metadata still matched the source files when this package was prepared. `PROVENANCE.json` records the validation scope and results.

## Original dataset attribution

SECOND was introduced by Kunping Yang, Gui-Song Xia, Zicheng Liu, Bo Du, Wen Yang, Marcello Pelillo and Liangpei Zhang. Original project and paper information are linked in `SOURCES.md`. Original dataset authorship is retained; the research split lists do not imply endorsement by the source authors.
