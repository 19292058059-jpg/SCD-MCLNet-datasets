# Sources and packaging provenance

## Original data record

- Dataset title: *Landsat-SCD_dataset.zip*.
- Figshare depositor display name, preserved as listed by the source: Yuan Panli. The accompanying paper lists this author's name as Panli Yuan.
- Version: 1.
- Persistent identifier: https://doi.org/10.6084/m9.figshare.19946135.v1
- Official record: https://figshare.com/articles/figure/Landsat-SCD_dataset_zip/19946135/1
- Official version-specific metadata: https://api.figshare.com/v2/articles/19946135/versions/1
- Metadata checked: 2026-10-23.
- License as listed by Figshare: CC BY 4.0, https://creativecommons.org/licenses/by/4.0/.
- The official source archive is 4,400,617,661 bytes and has supplied/computed MD5 `c66a53c2c0ef12c8d232418200e4952a`. These are identifiers of the upstream Figshare archive, not checksums of this release.

## Requested scholarly citation

Panli Yuan, Qingzhan Zhao, Xingbiao Zhao, Xuewen Wang, Xuefeng Long and Yuchen Zheng (2022). A transformer-based Siamese network and an open optical dataset for semantic change detection of remote sensing images. International Journal of Digital Earth, 15(1), 1506-1525. https://doi.org/10.1080/17538947.2022.2111470

This citation is explicitly requested in the original Figshare record. The source record's depositor name and the paper author list are retained for attribution. Authors of any subsequent research using the data are not substituted as the original dataset creators.

## This package

- Includes all 2,385 paired samples in the supplied A/B/labelA/labelB training layout and all three supplied split lists.
- Preserves the exact bytes of those PNG files and split lists. Repackaging does not assert that historical processing before the supplied input was unchanged.
- Uses pre-existing paired grayscale semantic masks with 0 = no change, 1 = farmland, 2 = desert, 3 = building, and 4 = water. The class order was cross-checked against the existing LandsatSCD preprocessing class list `SCD_ClASSES`; no preprocessing implementation is redistributed.
- Omits both optional RGB label-visualization directories. A 33-byte corrupt PNG was observed at `labelB_rgb/From1992To1998_01.png` in the supplied input. No core PNG or grayscale mask was removed, repaired, recompressed or regenerated.
- Adds this documentation, sanitized source metadata, the official CC BY 4.0 legal text and a per-file SHA-256 manifest.
- Contains no model, training or preprocessing source code.
- Does not claim byte identity with the upstream Figshare ZIP, which has a different archive size and whose description discusses 10 from-to transition types.
- Does not claim sponsorship, endorsement or an official release by the original authors.

The original source data remain available at the persistent identifier above. The full legal text was obtained from https://creativecommons.org/licenses/by/4.0/legalcode.txt without editing its bytes.
