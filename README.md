# Supplemental data for Schlegel et al. (2023)
This paper "_A consensus cell type atlas from multiple connectomes reveals principles of circuit stereotypy and variation_"
reports the systematic annotation of the FAFB-FlyWire adult female fly brain connectome including over 3000 consensus cell types validated across two brains and three brain hemispheres. The raw annotation data will be available here for download and have also been contributed to the https://codex.flywire.ai portal and [FAFB-FlyWire CATMAID spaces](https://fafb-flywire.catmaid.org/).

## Annotations

- [`/supplemental_files/Supplemental_file1_annotations.tsv`](supplemental_files/Supplemental_file1_annotations.tsv') contains annotations for flow, superclass, cell class, nerve, lineage, side, morphology groups, neurotransmitter and VirtualFlyBrain IDs (see [here](/supplemental_files/Supplemental_file1_columns.md) for detailed explanations for each column)
- [`/supplemental_files/Supplemental_file2_hemilineages_clustering.csv`](supplemental_files/Supplemental_file2_hemilineages_clustering.csv') contains details on the NBLAST clustering of hemilineages that generated the morphology groups
- [`/supplemental_files/Supplemental_file3_summary_with_ngl_links.csv`](supplemental_files/Supplemental_file3_summary_with_ngl_links.csv') contains a summary for each hemilineage including neuroglancer links to view them

To aid a number of analyses, hemibrain meshes were mapped into FlyWire (FAFB14.1) space. These can be co-visualised within neuroglancer for example by following this link: https://tinyurl.com/flywirehb. This also enables direct querying of both our flywire annotations and hemibrain annotations from within neuroglancer to efficiently find and compare cell types.

## Videos 
[![IMAGE ALT TEXT](http://img.youtube.com/vi/1kctjRyJYno/0.jpg)](http://www.youtube.com/watch?v=1kctjRyJYno "Supplemental Video")

_Supplemental Video 1: Rendering of all FlyWire neurons._

[![IMAGE ALT TEXT](http://img.youtube.com/vi/V-af_NQYGx0/0.jpg)](http://www.youtube.com/watch?v=V-af_NQYGx0 "Supplemental Video")

_Supplemental Video 2: Rendering of neurons by superclass._


## Skeletons & NBLAST scores
Skeletons and NBLAST scores are too large to be deposited on Github. Instead they are available for download via Zenodo: https://doi.org/10.5281/zenodo.8077335

## Software tools 
All software used in this paper is open-source and available through Github. Some of it was specifically developed for working with FlyWire data.

### Python 

| Name             | Description |
| ---------------- | ----------- |
| [navis](https://github.com/navis-org/navis)            | Analysis and visualisation of neurons. Used e.g. for NBLAST.  |
| [navis-flybrains](https://github.com/navis-org/navis-flybrains)  | Used to transform data between template spaces (e.g. from hemibrain to FlyWire). |
| [fafbseg](https://github.com/flyconnectome/fafbseg-py)          | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations). |
| [neuprint-python](https://github.com/connectome-neuprint/neuprint-python)  | Query neuPrint instances (e.g. for the hemibrain). Developed by FlyEM (Janelia Research Campus). |

### R

| Name             | Description |
| ---------------- | ----------- |
| [natverse](https://natverse.org)          | Analysis suite with a focus on neuroanatomical data.  |
| [fafbseg](https://github.com/naverse/fafbseg)          | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations). |
| [coconat](https://github.com/natverse/coconat) | Analysis suite for comparative connectomics in R. See also [coconatfly](https://github.com/natverse/coconatfly). |
| [neuprintr](https://github.com/natverse/neuprintr) | Query neuPrint instances (e.g. for the hemibrain) |

Please open an issue in the respective repository if you have questions or run into problems.

## CATMAID-spaces
Skeletons, connectivity and annotations for FlyWire neurons have been imported into a CATMAID instance publicly available at https://fafb-flywire.catmaid.org/. This allows the interactive exploration and analysis of the data.

## How to cite?
```bibtex
@article{schlegel2023,
  author = {Schlegel, Philipp and Yin, Yijie and Bates, Alexander S. and Dorkenwald, Sven and Eichler, Katharina and Brooks, Paul and Han, Daniel S. and Gkantia, Marina and dos Santos, Marcia and Munnelly, Eva J. and Badalamente, Griffin and Capdevila, Laia Serratosa and Sane, Varun and Pleijzier, Markus W. and Tamimi, Imaan F.M. and Dunne, Christopher R. and Salgarella, Irene and Fang, Siqi and Perlman, Eric and Kazimiers, Tom and Jagannathan, Sridhar R. and Matsliah, Arie and Sterling, Amy R and Yu, Szi-chieh and McKellar, Claire E. and Consortium, FlyWire and Costa, Marta and Seung, H. Sebastian and Murthy, Mala and Hartenstein, Volker and Bock, Davi D. and Jefferis, Gregory S.X.E.},
  journal = {bioRxiv},
  title = {A consensus cell type atlas from multiple connectomes reveals principles of circuit stereotypy and variation},
  year = {2023}}
```

## Found a broken link?
Please open an [issue](https://github.com/flyconnectome/flywire_annotations/issues).
