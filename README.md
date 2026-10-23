# SCD-MCLNet dataset resources

Data access, experimental splits and integrity records for SECOND and Landsat-SCD used in SCD-MCLNet. Original dataset authorship is retained. No model or training source code is included.

## Downloads

Open the [v1.0.0 release](https://github.com/19292058059-jpg/SCD-MCLNet-datasets/releases/tag/v1.0.0) and choose the named assets. GitHub's automatically generated **Source code** archives contain repository files; use the explicitly named dataset assets below.

| Resource | Experimental partition | Download |
| --- | --- | --- |
| Landsat-SCD images and paired semantic masks | 1,431 training / 477 validation / 477 test pairs | [Landsat-SCD-training-data.zip](https://github.com/19292058059-jpg/SCD-MCLNet-datasets/releases/download/v1.0.0/Landsat-SCD-training-data.zip), 1,055,947,632 bytes |
| Landsat-SCD ZIP checksum | SHA-256 | [Checksum](https://github.com/19292058059-jpg/SCD-MCLNet-datasets/releases/download/v1.0.0/Landsat-SCD-training-data.zip.sha256) |
| SECOND experimental lists and local data checksums | 2,375 training / 593 test pairs | [SECOND-splits-and-checksums.zip](https://github.com/19292058059-jpg/SCD-MCLNet-datasets/releases/download/v1.0.0/SECOND-splits-and-checksums.zip), 509,367 bytes; metadata only |
| SECOND metadata ZIP checksum | SHA-256 | [Checksum](https://github.com/19292058059-jpg/SCD-MCLNet-datasets/releases/download/v1.0.0/SECOND-splits-and-checksums.zip.sha256) |
| SECOND original images and annotations | Original author distribution | [Official project](https://captain-whu.github.io/SCD/) / [Google Drive archive](https://drive.google.com/file/d/1mN8jzCKKK27p3ODGoDgepjiRYGQpB34u/view) |

## Landsat-SCD

The ZIP contains all 2,385 experimental samples in A/B/labelA/labelB, the three original split lists, documentation and a complete SHA-256 manifest. Images and masks are 416 x 416 pixels. Paired grayscale masks use 0 (unchanged), 1 (farmland), 2 (desert), 3 (building) and 4 (water). Included provenance explains this representation and its distinction from the original change-type labels.

This is a repackaged training layout, not a byte-identical copy of the original Figshare ZIP. Optional RGB visualization copies are omitted. All split-referenced images and grayscale masks are retained unchanged. No sample or split was regenerated during packaging.

The original deposit is by **Yuan Panli**, [Figshare v1, DOI 10.6084/m9.figshare.19946135.v1](https://doi.org/10.6084/m9.figshare.19946135.v1), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The original paper is by Panli Yuan, Qingzhan Zhao, Xingbiao Zhao, Xuewen Wang, Xuefeng Long and Yuchen Zheng, [DOI 10.1080/17538947.2022.2111470](https://doi.org/10.1080/17538947.2022.2111470). Attribution, license text, source links and packaging changes are inside the ZIP.

## SECOND

Download the original archive above and use SECOND_train_set.rar with the included lists. The research split is 2,375 training / 593 test pairs from the 2,968-pair official training pool. The separate 1,694-pair official test pool is distinct from our 593-pair test list.

Original list bytes and order are preserved. The lists have no duplicate IDs or intersection and cover all 2,968 training-pool IDs. In the documented layout, A/B correspond to original im1/im2; labels use label1/label2. The metadata ZIP includes SHA-256 hashes for 11,872 locally checked core PNGs. These identify the local research files; they do not claim a new full-pixel comparison against the upstream archive. Split-generation method and random seed are not inferred.

**SECOND images and labels are not mirrored here.** Explicit redistribution terms for the externally hosted archive could not be established. The official GitHub repository has an Apache-2.0 license, but reviewed sources do not establish that it covers the separate Google Drive imagery and annotations. This is an unresolved license-scope question, not a claim that redistribution is prohibited. Obtain data from the original authors and review their current terms. This repository does not grant or change rights to that data.

SECOND was introduced by Kunping Yang, Gui-Song Xia, Zicheng Liu, Bo Du, Wen Yang, Marcello Pelillo and Liangpei Zhang. See the [official project](https://captain-whu.github.io/SCD/) and [paper DOI 10.1109/TGRS.2021.3113912](https://doi.org/10.1109/TGRS.2021.3113912).

## Integrity

Download each ZIP and its matching .sha256 file into the same directory. Verify using sha256sum -c <checksum filename>, or compare PowerShell Get-FileHash -Algorithm SHA256 <ZIP filename> with:

```text
e81e718752318eeedd2880690c694666f46fdd7961e8a4f3fe1c4f0f3c898179  Landsat-SCD-training-data.zip
441123da6f63be368729588fd5a3406c4ce690584627142f4fb04b02dad39e2d  SECOND-splits-and-checksums.zip
```

Both local packages passed complete ZIP CRC and per-file SHA-256 checks before upload. Source files and split lists were unchanged. These checks establish integrity and split alignment; they do not establish spatial independence or reproduce model performance. Detailed per-file verification instructions are inside each package.

## Rights

Dataset-specific provenance and rights are documented separately. No blanket repository license is assigned to the underlying datasets. Retain original dataset citations. This resource does not imply endorsement by the original authors.
