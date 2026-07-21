# FlyWire neuron annotations

> [!IMPORTANT]
> Annotations in this repository have been updated since the initial FlyWire preprint.
> Please see the [tagged release](https://github.com/flyconnectome/flywire_annotations/releases)
> for versions matching specific publications. See the [changelog](#Changelog) for details.

This repository contains systematic neuron annotations and other data products for the `783` public release of
the FlyWire female adult fly brain (FAFB) connectome.

The initial set of annotations was reported in Schlegel _et al._ ["Whole-brain annotation and multi-connectome cell typing of Drosophila", Nature (2024)](https://doi-org.ezp.lib.cam.ac.uk/10.1038/s41586-024-07686-5).
We have since integrated the optic lobe annotations from Matsliah _et al._ ["Neuronal parts list and wiring diagram for a visual system", Nature (2024)](https://www.nature.com/articles/s41586-024-07981-1)].
With [Berg _et al._, bioRxiv (2025)](https://www.biorxiv.org/content/10.1101/2025.10.09.680999v1) we added/extended a lot of annotations based
on cross-validation with the Janelia MaleCNS connectome.

Annotations collated here are used by the [fafbseg-py](https://fafbseg-py.readthedocs.io/) Python and
the [fafbseg](https://natverse.org/fafbseg/) R package to enable programmatic analysis of the FlyWire dataset.

> [!IMPORTANT]
> Some but not all of the annotations deposited here are also available on [Codex](https://codex.flywire.ai/). Importantly,
> Codex presents a mix of annotations from different sources which likely diverge from the systematic and cross-checked annotations
> presented here.

We're generally happy to consider contributions from the community to update/improve existing or add entirely new annotations.
Please see the ["How to contribute"](#How-to-contribute?) section for details.

## Annotations dumps

- [`/supplemental_files/Supplemental_file1_neuron_annotations.tsv`](supplemental_files/Supplemental_file1_neuron_annotations.tsv) contains neuron annotations for flow, superclass, cell class, nerve, lineage, side, morphology groups, neurotransmitter and VirtualFlyBrain IDs; this file is the basis for annotations in `fafbseg-py`
- [`/supplemental_files/Supplemental_file2_non_neuron_annotations.tsv`](supplemental_files/Supplemental_file2_non_neuron_annotations.tsv) contains annotations for non-neuronal objects such as trachae and glia
- [`/supplemental_files/Supplemental_file3_hemilineages_clustering.csv`](supplemental_files/Supplemental_file3_hemilineages_clustering.csv) contains details on the NBLAST clustering of hemilineages that generated the morphology groups
- [`/supplemental_files/Supplemental_file4_summary_with_ngl_links.csv`](supplemental_files/Supplemental_file4_summary_with_ngl_links.csv) contains a summary for each hemilineage including neuroglancer links to view them
- [`/supplemental_files/Supplemental_file5_hemibrain_meta.csv`](supplemental_files/Supplemental_file5_hemibrain_meta.csv) contains meta data for hemibrain (v1.2.1) pulled from neuPrint with some additional columns (e.g. `side`) used in our analyses

_See [here](supplemental_files/README.md) for detailed explanations for each column in these spreadsheets._

- [`/code/annotation_counts.ipynb`](/code/annotation_counts.ipynb) contains examples of
reading the annotation data and extracting numbers/counts used in the paper

To aid a number of analyses, hemibrain meshes were mapped into FlyWire (FAFB14.1) space. These can be co-visualised within neuroglancer for example by following this link: https://tinyurl.com/flywire783. This also enables direct querying of both our flywire annotations and hemibrain annotations from within neuroglancer to efficiently find and compare cell types.

## Videos
High-resolution supplemental videos have been uploaded to YouTube:

[![IMAGE ALT TEXT](http://img.youtube.com/vi/kNYUhzunuKg/0.jpg)](http://www.youtube.com/watch?v=kNYUhzunuKg "Supplemental Video")

_Supplemental Video 1: Rendering of all FlyWire neurons._

[![IMAGE ALT TEXT](http://img.youtube.com/vi/9TYPM83_8lU/0.jpg)](https://www.youtube.com/watch?v=9TYPM83_8lU "Supplemental Video")

_Supplemental Video 2: Rendering of neurons by superclass._

[![IMAGE ALT TEXT](http://img.youtube.com/vi/m6ZJZfnWEe0/0.jpg)](https://www.youtube.com/watch?v=m6ZJZfnWEe0 "Supplemental Video")

_Supplemental Video 3: Hemilineage slides show._

[![IMAGE ALT TEXT](http://img.youtube.com/vi/tTrU4XerwCg/0.jpg)](https://www.youtube.com/watch?v=tTrU4XerwCg "Supplemental Video")

_Supplemental Video 4: FlyWire hemibrain cell type matches._

## Skeletons & NBLAST scores
Skeletons and NBLAST scores are too large to be deposited on Github. Instead they are available for download via Zenodo: https://doi.org/10.5281/zenodo.10877326

## Connectivity
Synapses table and edge list can be downloaded from https://zenodo.org/records/10676866 (provided by Sven Dorkenwald & FlyWire.ai).

## Software tools
All software used in this paper is open-source and available through Github. Some of it was specifically developed for working with FlyWire data. Please open an issue in the respective repository if you have questions or run into problems.

### Python

| Name             | Description |
| ---------------- | ----------- |
| [navis](https://github.com/navis-org/navis)            		   | Analysis and visualisation of neurons. Used e.g. for NBLAST.  |
| [navis-flybrains](https://github.com/navis-org/navis-flybrains)  | Used to transform data between template spaces (e.g. from hemibrain to FlyWire). |
| [fafbseg-py](https://github.com/flyconnectome/fafbseg-py)           | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations). |
| [cocoa](https://github.com/flyconnectome/cocoa) | Analysis suite for comparative connectomics. Enables e.g. hemibrain-FlyWire connectivity clustering. |
| [neuprint-python](https://github.com/connectome-neuprint/neuprint-python)  | Query neuPrint instances (e.g. for the hemibrain). Developed by FlyEM (Janelia Research Campus). |

The recommended entry point for Python is [fafbseg-py](https://github.com/flyconnectome/fafbseg-py).

### R

| Name             | Description |
| ---------------- | ----------- |
| [natverse](https://natverse.org)        		   | Analysis suite with a focus on neuroanatomical data.  |
| [fafbseg](https://natverse.org/fafbseg)          | Query and analyse FlyWire data (segmentation, meshes, skeletons, annotations). |
| [coconatfly](https://natverse.org/coconatfly)    | Analysis suite for Drosophila comparative connectomics. Enables hemibrain-FlyWire connectivity clustering. See also [coconat](https://github.com/natverse/coconat). |
| [neuprintr](https://natverse.org/neuprintr)      | Query neuPrint instances (e.g. for the hemibrain) |

The recommended entry point for R is [coconatfly](https://natverse.org/coconatfly).

## CATMAID-spaces
Skeletons, connectivity and annotations for FlyWire neurons have been imported into a CATMAID instance publicly available at https://fafb-flywire.catmaid.org/. This allows the interactive exploration and analysis of the data.

## How to cite?

Version `>=3.0.0`:

Please cite Berg _et al._ (2025), Schlegel _et al._ (2024), Matsliah _et al._ (2024) and Dorkenwald _et al._ (2024) when using annotations from this repository.

Pre `3.0.0`:

Please cite Schlegel _et al._ (2024) and Dorkenwald _et al._ (2024) when using annotations from this repository.

<details>
<summary>BibTex entries for publications</summary>

```bibtex
@article{Berg2025,
  author = {Berg,  Stuart and Beckett,  Isabella R and Costa,  Marta and Schlegel,  Philipp and Januszewski,  Michal and Marin,  Elizabeth C and Nern,  Aljoscha and Preibisch,  Stephan and Qiu,  Wei and Takemura,  Shin-ya and Fragniere,  Alexandra M C and Champion,  Andrew S and Adjavon,  Diane-Yayra and Cook,  Michael and Gkantia,  Marina and Hayworth,  Kenneth J and Huang,  Gary B and Kampf,  Florian and Katz,  William T and Lu,  Zhiyuan and Ordish,  Christopher and Paterson,  Tyler and Stuerner,  Tomke and Trautman,  Eric T and Whittle,  Catherine R and Burnett,  Laura E and Hoeller,  Judith and Li,  Feng and Loesche,  Frank and Morris,  Billy J and Pietzsch,  Tobias and Pleijzier,  Markus W and Silva,  Valeria and Yin,  Yijie and Ali,  Iris and Badalamente,  Griffin and Bates,  Alexander Shakeel and Bogovic,  John and Brooks,  Paul and Cachero,  Sebastian and Canino,  Brandon S and Chaisrisawatsuk,  Bhumpanya and Clements,  Jody and Crowe,  Arthur and de Haan Vicente,  Ines and Dempsey,  Georgia and Dona,  Erika and dos Santos,  Marcia and Dreher,  Marisa and Dunne,  Christopher R and Eichler,  Katharina and Finley-May,  Samantha and Flynn,  Miriam A and Hameed,  Imran and Hopkins,  Gary Patrick and Hubbard,  Philip M and Kiassat,  Ladann and Kovalyak,  Julie and Lauchie,  Shirley A and Leonard,  Meghan and Lohff,  Alanna and Longden,  Kit D and Maldonado,  Charli A and Mitletton,  Myrto and Moitra,  Ilina and Moon,  Sung Soo and Mooney,  Caroline and Munnelly,  Eva J and Okeoma,  Nneoma and Olbris,  Donald J and Pai,  Anika and Patel,  Birava and Phillips,  Emily M and Plaza,  Stephen M and Richards,  Alana and Rivas Salinas,  Jennifer and Roberts,  Ruairi J V and Rogers,  Edward M and Scott,  Ashley L and Scuderi,  Louis A and Seenivasan,  Pavithraa and Serratosa Capdevila,  Laia and Smith,  Claire and Svirskas,  Rob and Takemura,  Satoko and Tastekin,  Ibrahim and Thomson,  Alexander and Umayam,  Lowell and Walsh,  John J and Whittome,  Holly and Xu,  C Shan and Yakal,  Emily A and Yang,  Tansy and Zhao,  Arthur and George,  Reed and Jain,  Viren and Jayaraman,  Vivek and Korff,  Wyatt and Meissner,  Geoffrey W and Romani,  Sandro and Funke,  Jan and Knecht,  Christopher and Saalfeld,  Stephan and Scheffer,  Louis K and Waddell,  Scott and Card,  Gwyneth M and Ribeiro,  Carlos and Reiser,  Michael B and Hess,  Harald F and Rubin,  Gerald M and Jefferis,  Gregory S X E},
  title = {Sexual dimorphism in the complete connectome of the Drosophila male central nervous system},
  DOI = {10.1101/2025.10.09.680999},
  publisher = {Cold Spring Harbor Laboratory},
  year = {2025},
}
@article{Matsliah2024,
  publisher = {Springer Science and Business Media LLC},
  author = {Matsliah,  Arie and Yu,  Szi-chieh and Kruk,  Krzysztof and Bland,  Doug and Burke,  Austin T. and Gager,  Jay and Hebditch,  James and Silverman,  Ben and Willie,  Kyle Patrick and Willie,  Ryan and Sorek,  Marissa and Sterling,  Amy R. and Kind,  Emil and Garner,  Dustin and Sancer,  Gizem and Wernet,  Mathias F. and Kim,  Sung Soo and Murthy,  Mala and Seung,  H. Sebastian and David,  Celia and Joroff,  Jenna and Kristiansen,  Anne and Stocks,  Thomas and Braun,  Amalia and Silies,  Marion and Skelton,  Jaime and Aiken,  Travis R. and Ioannidou,  Maria and Collie,  Matt and Linneweber,  Gerit A. and Molina-Obando,  Sebastian and Dorkenwald,  Sven and Panes,  Nelsie and Gogo,  Allien Mae and Rastgarmoghaddam,  Dorfam and Pilapil,  Cathy and Candilada,  Rey Adrian and Serafetinidis,  Nikitas and Lee,  Wei-Chung and Borst,  Alexander and Wilson,  Rachel I. and Schlegel,  Philipp and Jefferis,  Gregory S. X. E.},
  title = {Neuronal parts list and wiring diagram for a visual system},
  year = {2024},
  DOI = {10.1038/s41586-024-07981-1},
  publisher = {Springer Nature},
  journal = {Nature},
}
@article {Schlegel2024,
	author = {Philipp Schlegel and Yijie Yin and Alexander Shakeel Bates and Sven Dorkenwald and Katharina Eichler and Paul Brooks and Daniel S Han and Marina Gkantia and Marcia dos Santos and Eva J Munnelly and Griffin Badalamente and Laia Serratosa Capdevila and Varun Aniruddha Sane and Alexandra M F Fragniere and Ladann Kiassat and Markus William Pleijzier and Imaan F M Tamimi and Christopher R Dunne and Irene Salgarella and Alexandre Javier and Siqi Fang and Eric Perlman and Tom Kazimiers and Sridhar R Jagannathan and Arie Matsliah and Amy R Sterling and Szi-chieh Yu and Claire E McKellar and FlyWire Consortium and Marta Costa and H. Sebastian Seung and Mala Murthy and Volker Hartenstein and Davi D Bock and Gregory S X E Jefferis},
	title = {Whole-brain annotation and multi-connectome cell typing of Drosophila},
	year = {2024},
	doi = {10.1038/s41586-024-07686-5},
	publisher = {Springer Nature},
	journal = {Nature}
}
@article{Dorkenwald2024,
  author = {Dorkenwald,  Sven and Matsliah,  Arie and Sterling,  Amy R. and Schlegel,  Philipp and Yu,  Szi-chieh and McKellar,  Claire E. and Lin,  Albert and Costa,  Marta and Eichler,  Katharina and Yin,  Yijie and Silversmith,  Will and Schneider-Mizell,  Casey and Jordan,  Chris S. and Brittain,  Derrick and Halageri,  Akhilesh and Kuehner,  Kai and Ogedengbe,  Oluwaseun and Morey,  Ryan and Gager,  Jay and Kruk,  Krzysztof and Perlman,  Eric and Yang,  Runzhe and Deutsch,  David and Bland,  Doug and Sorek,  Marissa and Lu,  Ran and Macrina,  Thomas and Lee,  Kisuk and Bae,  J. Alexander and Mu,  Shang and Nehoran,  Barak and Mitchell,  Eric and Popovych,  Sergiy and Wu,  Jingpeng and Jia,  Zhen and Castro,  Manuel A. and Kemnitz,  Nico and Ih,  Dodam and Bates,  Alexander Shakeel and Eckstein,  Nils and Funke,  Jan and Collman,  Forrest and Bock,  Davi D. and Jefferis,  Gregory S. X. E. and Seung,  H. Sebastian and Murthy,  Mala and The FlyWire Consortium},
  title = {Neuronal wiring diagram of an adult brain},
  year = {2024},
  doi = {10.1038/s41586-024-07558-y},
  publisher = {Springer Nature},
  journal = {Nature},
}
```
</details>

## Changelog
Because annotations are still evolving we will occasionally update them. Thanks to Github's versioning you can always go back to the state at a
given time (e.g. at initial publication) using the tags!

- [`3.1.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v3.1.0): Minor update based on the peer-reviewed version of [Berg _et al._ (2026, under rev.)]():
  - complete retyping of Johnston's Organ (JO) sensory neurons
  - updated `fru_dsx` annotations
  - small changes to other columns (`cell_type`, `hemibrain_type`, etc)
- [`3.0.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v3.0.0): First update from [Berg _et al._, bioRxiv (2025)](https://www.biorxiv.org/content/10.1101/2025.10.09.680999v1). Principally based on comparison between FlyWire (materialization `783`) and the Janelia MaleCNS connectome (version `0.9`):
  - Updated and new cell type annotations based on cross-validation with MaleCNS
  - dimorphism (isomorphic, dimorphic, sex-specific) annotations (`dimorphism` and `matching_notes` columns)
  - synonyms for cell types to cross-link with past literature (`synonyms` column)
  - _fruitless_ and _doublesex_ expression annotations (`fru_dsx` column)
  - `morphology_group` column has been removed
  - new `supertype` column which matches the corresponding entry in neuPrint for the MaleCNS
  - minor updates to hemilineage annotations for Flywire and hemibrain
- [`2.1.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v2.1.0): Still based on the `783` materialization but with substantial updates and revisions to cell types and other annotations. This is the version reported on in the Schlegel *et al.*, Nature (2024) and Dorkenwald *et al.*, Nature (2024).
- [`2.0.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v2.0.0): First major revision of annotations. With this release annotations are now based principally on the updated FlyWire segmentation version `783`. It includes new cell types and cell classes for the majority of neurons in both central brain and optic lobes.
- [`1.1.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v1.1.0): Second release for the updated Schlegel *et al*. (2023) bioRxiv version. Principally based on FlyWire segmentation version `630`.
- [`1.0.0`](https://github.com/flyconnectome/flywire_annotations/releases/tag/v1.0.0): First release matching the Schlegel *et al*. bioRxiv paper. Principally based on FlyWire segmentation version `630`.

## How to contribute?
We welcome all kinds of contributions. For example:

- reports of incorrect annotations (e.g. cell types), broken links, etc.
- suggestions for new/updated cell type information (e.g. from more recent publications)

If you already know what needs doing, feel free to fork & PR
right away. When in doubt please open an [issue](https://github.com/flyconnectome/flywire_annotations/issues) so we can discuss the best way to address the issue.
