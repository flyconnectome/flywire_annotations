# FlyWire neuron annotations

This repository is principally based on Schlegel _et al._ ["_Whole-brain annotation and multi-connectome cell typing quantifies circuit stereotypy in Drosophila_"](https://www.biorxiv.org/content/10.1101/2023.06.27.546055v2)
which reports the systematic annotation of the FlyWire female adult fly brain
connectome. The annotation data will be available here for download and have
also been contributed to the https://codex.flywire.ai portal and
[FAFB-FlyWire CATMAID spaces](https://fafb-flywire.catmaid.org/).

The annotations collated here are used by e.g.
[fafbseg-py](https://fafbseg-py.readthedocs.io/) to programmatically work
with the FlyWire dataset.

We're generally happy to consider contributions from the community to update/improve existing or add entirely new annotations.
Please see the ["How to contribute"](#How-to-contribute?) section for details.


## Annotations dumps

- [`/supplemental_files/Supplemental_file1_neuron_annotations.tsv`](supplemental_files/Supplemental_file1_neuron_annotations.tsv) contains neuron annotations for flow, superclass, cell class, nerve, lineage, side, morphology groups, neurotransmitter and VirtualFlyBrain IDs; this file is the basis for annotations in `fafbseg-py`
- [`/supplemental_files/Supplemental_file2_non_neuron_annotations.tsv`](supplemental_files/Supplemental_file2_non_neuron_annotations.tsv) contains annotations for non-neuronal objects such as trachae and glia
- [`/supplemental_files/Supplemental_file3_hemilineages_clustering.csv`](supplemental_files/Supplemental_file3_hemilineages_clustering.csv) contains details on the NBLAST clustering of hemilineages that generated the morphology groups
- [`/supplemental_files/Supplemental_file4_summary_with_ngl_links.csv`](supplemental_files/Supplemental_file4_summary_with_ngl_links.csv) contains a summary for each hemilineage including neuroglancer links to view them
- [`/supplemental_files/Supplemental_file5_hemibrain_meta.csv`](supplemental_files/Supplemental_file5_hemibrain_meta.csv) contains meta data for hemibrain (v1.2.1) pulled from neuPrint with some additional columns (e.g. `side`) used in our analyses

_See [here](supplemental_files/Supplemental_files_columns.md) for detailed explanations for each column in these spreadsheets._

- [`/code/annotation_counts.ipynb`](/code/annotation_counts.ipynb) contains examples of
reading the annotation data and extracting numbers/counts used in the paper

To aid a number of analyses, hemibrain meshes were mapped into FlyWire (FAFB14.1) space. These can be co-visualised within neuroglancer for example by following this link: https://tinyurl.com/flywire783. This also enables direct querying of both our flywire annotations and hemibrain annotations from within neuroglancer to efficiently find and compare cell types.

## Videos
[![IMAGE ALT TEXT](http://img.youtube.com/vi/a7YejmMU8CI/0.jpg)](http://www.youtube.com/watch?v=a7YejmMU8CI "Supplemental Video")

_Supplemental Video 1: Rendering of all FlyWire neurons._

[![IMAGE ALT TEXT](http://img.youtube.com/vi/3obmOmQB0ak/0.jpg)](https://www.youtube.com/watch?v=3obmOmQB0ak "Supplemental Video")

_Supplemental Video 2: Rendering of neurons by superclass._

[![IMAGE ALT TEXT](http://img.youtube.com/vi/wX8z8zG6U6s/0.jpg)](https://www.youtube.com/watch?v=wX8z8zG6U6s "Supplemental Video")

_Supplemental Video 4: FlyWire hemibrain cell type matches._


## Skeletons & NBLAST scores
Skeletons and NBLAST scores are too large to be deposited on Github. Instead they are available for download via Zenodo: https://doi.org/10.5281/zenodo.8077335


## Software tools
All software used in this paper is open-source and available through Github. Some of it was specifically developed for working with FlyWire data.

### Python

| Name             | Description |
| ---------------- | ----------- |
| [navis](https://github.com/navis-org/navis)            		   | Analysis and visualisation of neurons. Used e.g. for NBLAST.  |
| [navis-flybrains](https://github.com/navis-org/navis-flybrains)  | Used to transform data between template spaces (e.g. from hemibrain to FlyWire). |
| [fafbseg-py](https://github.com/flyconnectome/fafbseg-py)           | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations). |
| [neuprint-python](https://github.com/connectome-neuprint/neuprint-python)  | Query neuPrint instances (e.g. for the hemibrain). Developed by FlyEM (Janelia Research Campus). |

### R

| Name             | Description |
| ---------------- | ----------- |
| [natverse](https://natverse.org)        		   | Analysis suite with a focus on neuroanatomical data.  |
| [fafbseg](https://natverse.org/fafbseg)          | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations). |
| [coconatfly](https://natverse.org/coconatfly)    | Analysis suite for Drosophila comparative connectomics. Enables hemibrain-flywire connectivity clustering. See also [coconat](https://github.com/natverse/coconat). |
| [neuprintr](https://natverse.org/neuprintr)      | Query neuPrint instances (e.g. for the hemibrain) |

Please open an issue in the respective repository if you have questions or run into problems.

## CATMAID-spaces
Skeletons, connectivity and annotations for FlyWire neurons have been imported into a CATMAID instance publicly available at https://fafb-flywire.catmaid.org/. This allows the interactive exploration and analysis of the data.

## How to cite?
```bibtex
@article {Schlegel2023,
	author = {Philipp Schlegel and Yijie Yin and Alexander Shakeel Bates and Sven Dorkenwald and Katharina Eichler and Paul Brooks and Daniel S Han and Marina Gkantia and Marcia dos Santos and Eva J Munnelly and Griffin Badalamente and Laia Serratosa Capdevila and Varun Aniruddha Sane and Markus William Pleijzier and Imaan F M Tamimi and Christopher R Dunne and Irene Salgarella and Alexandre Javier and Siqi Fang and Eric Perlman and Tom Kazimiers and Sridhar R Jagannathan and Arie Matsliah and Amy R Sterling and Szi-chieh Yu and Claire E McKellar and FlyWire Consortium and Marta Costa and H. Sebastian Seung and Mala Murthy and Volker Hartenstein and Davi D Bock and Gregory S X E Jefferis},
	title = {Whole-brain annotation and multi-connectome cell typing quantifies circuit stereotypy in Drosophila},
	elocation-id = {2023.06.27.546055},
	year = {2023},
	doi = {10.1101/2023.06.27.546055},
	publisher = {Cold Spring Harbor Laboratory},
	URL = {https://www.biorxiv.org/content/early/2023/07/15/2023.06.27.546055},
	eprint = {https://www.biorxiv.org/content/early/2023/07/15/2023.06.27.546055.full.pdf},
	journal = {bioRxiv}
}
```

## Changelog
Because annotations are still evolving we will occasionally update them. Thanks to Github's versioning you can always go back to the state at a
given time (e.g. at initial publication) using the tags!

- [`2.0.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v2.0.0): First major revision of annotations. With this release annotations are now based principally on the updated FlyWire segmentation version `783`. It includes new cell types and cell classes for the majority of neurons in both central brain and optic lobes.
- [`1.1.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v1.1.0): Second release for the updated Schlegel *et al*. bioRxiv version. Principally based on FlyWire segmentation version `630`.
- [`1.0.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v1.0.0): First release matching the Schlegel *et al*. bioRxiv paper. Principally based on FlyWire segmentation version `630`.

## How to contribute?
We welcome all kinds of contributions. For example:
- reports of incorrect annotations (e.g. cell types), broken links, etc.
- suggestions for new/updated cell type information (e.g. from more recent publications)

If you already know what needs doing, feel free to open a pull request
right away. When in doubt please open an [issue](https://github.com/flyconnectome/flywire_annotations/issues) so we can discuss the best way to the issue.
