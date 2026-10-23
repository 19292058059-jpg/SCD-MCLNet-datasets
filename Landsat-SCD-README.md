# Landsat-SCD training data

Prepared: 2026-10-23

This package contains the existing Landsat-SCD training-ready data layout used in the accompanying research. The imagery, paired semantic masks and split-list files are packaged byte for byte from the supplied input. No pixel values, filenames, label encodings or split-list bytes were changed during preparation of this release. This release is a repackaged training layout, and is not claimed to be a byte-identical mirror of the original Figshare archive.

## Contents

```text
Landsat-SCD/
  A/                       2,385 earlier-date RGB PNG images
  B/                       2,385 later-date RGB PNG images
  labelA/                  2,385 earlier-date grayscale semantic PNG masks
  labelB/                  2,385 later-date grayscale semantic PNG masks
  train_list.txt           1,431 image filenames
  val_list.txt               477 image filenames
  test_list.txt              477 image filenames
  README.md
  SOURCES.md
  PROVENANCE.json
  LICENSE-CC-BY-4.0.txt
  MANIFEST-SHA256.txt
```

All images and masks are 416 x 416 pixels. Files with the same basename in the four data directories form one paired sample. The three split lists are mutually exclusive, contain no duplicates, and cover all 2,385 samples. Each line is a PNG basename, including the `.png` extension. The split-list files retain their original bytes and line endings.

## Label values

The masks use integer values, not the RGB visualization palette:

| Value | Meaning |
| --- | --- |
| 0 | No change |
| 1 | Farmland |
| 2 | Desert |
| 3 | Building |
| 4 | Water |

For a changed location, `labelA` and `labelB` describe the land-cover category at the earlier and later date, respectively. Value 0 denotes no change, rather than a separate land-cover category. The original Figshare description discusses 10 from-to change types; this pre-existing paired-mask layout expresses temporal semantic categories using the values above. This packaging process did not create or regenerate the masks.

The optional `labelA_rgb` and `labelB_rgb` visualization directories from the supplied input are omitted. They are visualization copies, not the grayscale training labels. A corrupt optional visualization file, `labelB_rgb/From1992To1998_01.png` (33 bytes), was observed in the supplied input. It was not repaired or redistributed. The four core data directories are complete; no core image or grayscale mask was removed on this basis.

## Source, attribution and license

Original dataset: Yuan Panli (Figshare depositor display name), *Landsat-SCD_dataset.zip*, version 1, Figshare. https://doi.org/10.6084/m9.figshare.19946135.v1

The original Figshare record licenses the dataset under Creative Commons Attribution 4.0 International (CC BY 4.0). Retain original attribution and citation when reusing or redistributing the data. The license text is included in `LICENSE-CC-BY-4.0.txt`; the license also contains the disclaimer of warranties and limitation of liability. https://creativecommons.org/licenses/by/4.0/

The original dataset authors request citation of:

Panli Yuan, Qingzhan Zhao, Xingbiao Zhao, Xuewen Wang, Xuefeng Long and Yuchen Zheng (2022). A transformer-based Siamese network and an open optical dataset for semantic change detection of remote sensing images. International Journal of Digital Earth, 15(1), 1506-1525. https://doi.org/10.1080/17538947.2022.2111470

Original dataset authorship belongs to the credited source authors. Packaging this release does not imply their endorsement. The package contains data and documentation; model and training source code are not included. Further provenance and packaging changes are recorded in `SOURCES.md` and `PROVENANCE.json`.

## Integrity

`MANIFEST-SHA256.txt` lists a SHA-256 checksum for every other file inside the package, using paths relative to the `Landsat-SCD` directory. The manifest excludes itself to avoid a circular checksum dependency. To verify after extraction with a standard checksum utility, run from that directory:

```sh
sha256sum -c MANIFEST-SHA256.txt
```

Original split-list SHA-256 checksums:

| File | SHA-256 |
| --- | --- |
| train_list.txt | `acb9f345547175d1f2493159eb693558721148b5e17b2cf0a6986f139c47252e` |
| val_list.txt | `b59582718e0b7fb032fed1dda08649bec1ad67477fec28ebb2d2d75c922017c9` |
| test_list.txt | `3a7355d8cf7cdb0e6997e613cc8e954773760aa7852d1de3613e6df274b2bfd0` |

The release archive was checked using a full ZIP CRC test and by recomputing every manifest checksum from the archive contents. Source-file checksums and source-tree metadata were checked again after packaging.
