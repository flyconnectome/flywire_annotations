# Supplemental data for Schlegel et al. (2023)
This paper _A consensus cell type atlas from multiple connectomes reveals principles of circuit stereotypy and variation_
reports the systematic annotation of the FAFB-FlyWire adult female fly brain connectome including over 3000 consensus cell types validated across two brains and three brain hemispheres. The raw annotation data will be available here for download and have also been contributed to the https://codex.flywire.ai portal.

## Annotations

To aid a number of analyses, hemibrain meshes were mapped into FlyWire (FAFB14.1) space. These can be co-visualised within neuroglancer for example by following this link: https://tinyurl.com/flywirehb. This also enables direct querying of both our flywire annotations and hemibrain annotations from within neuroglancer to efficiently find and compare cell types.

## Skeletons & NBLAST scores
Skeletons and NBLAST scores are too large to be deposited on Github. Instead they are available for download via Zenodo: https://doi.org/10.5281/zenodo.8077335

## Software tools 
All the software developed for working with FlyWire data and used in this paper is open-source and available through Github. 

### Python 

| Name             | Description |
| ---------------- | ----------- |
| [navis](https://github.com/navis-org/navis)            | Analysis and visualisation of neurons. Used e.g. for NBLAST.  |
| [navis-flybrains](https://github.com/navis-org/navis-flybrains)  | Used to transform data between template spaces (e.g. from hemibrain to FlyWire. |
| [fafbseg](https://github.com/flyconnectome/fafbseg-py)          | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations. |
| [neuprint-python](https://github.com/connectome-neuprint/neuprint-python)  | Query neuPrint instances (e.g. for the hemibrain). Developed by FlyEM (Janelia Research Campus). |

### R

| Name             | Description |
| ---------------- | ----------- |
| [natverse](https://natverse.org)          | Analysis suite with a focus on neuroanatomical data.  |
| [fafbseg](https://github.com/naverse/fafbseg)          | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations. |
| [coconat](https://github.com/natverse/coconat) | Analysis suite for comparative connectomics in R. See also [coconatfly](https://github.com/natverse/coconatfly) |
| [neuprintr](https://github.com/natverse/neuprintr) | Query neuPrint instances (e.g. for the hemibrain) |

Please open an issue in the respective repository if you have questions or run into problems.

## CATMAID-spaces
Skeletons, connectivity and annotations for FlyWire neurons have been imported into a CATMAID instance publicly available at https://fafb-flywire.catmaid.org/. This allows the interactive exploration and analysis of the data.

## Found a broken link?
Please open an [issue](https://github.com/flyconnectome/flywire_annotations/issues).
