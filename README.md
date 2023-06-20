Exploratory Data Science Experiment with FAIR, RO-Crate, and Open Knowledge Networks
====================================================================================

Introduction
------------

This repository houses an exploratory data science experiment that aims to use the principles of Findable, Accessible, Interoperable, and Reusable (FAIR) data, combined with Research Object Crate (RO-Crate) and Open Knowledge Networks (OKN) to structure, organize, and make sense of scientific data. The experiment is framed within a real-world use case from the National High Magnetic Field Laboratory (MagLab).

### FAIR Principles

The FAIR Principles are guidelines that aim to ensure that data is Findable, Accessible, Interoperable, and Reusable. They were first published in 2016, and have since gained widespread acceptance in the scientific community. The goal of FAIR is to optimize the reuse of data by clearly articulating how to achieve this through the implementation of certain practices.

### RO-Crate

RO-Crate is a community effort to establish a lightweight approach to packaging research data with their metadata. It is based on the schema.org JSON-LD format, making it compatible with a broad range of applications. RO-Crate allows for the comprehensive description of resources and their relationships, making data self-describing and enhancing its interoperability and reusability.

### Open Knowledge Networks (OKN)

Open Knowledge Networks aim to create a web of knowledge that links data, people, and processes. They provide a way to map the relationships between different types of data, enabling better understanding, discovery, and use of data. OKN supports the FAIR principles by promoting the creation of a machine-readable and interoperable web of knowledge.

The MagLab User Story
---------------------

The National High Magnetic Field Laboratory (MagLab) is the largest and highest-powered magnet lab in the world. It conducts scientific experiments that generate a significant amount of data. As part of their effort to improve data management, the MagLab aims to use the principles of FAIR data, RO-Crate, and OKN to structure and organize their data. This repository serves as a proof of concept for this approach, using a representative dataset and experiment from the MagLab.

### Science on Schema.org

Science on Schema.org is an initiative to extend the schema.org vocabulary with terms for describing scientific datasets, variables, and observational studies. These terms provide a standardized way to describe scientific data in a machine-readable format.

### PIDINST

PIDINST is an identifier scheme for scientific instruments. It provides a standard, persistent way to reference instruments used in scientific experiments.

### RDA iAdopt

The Research Data Alliance (RDA) is a community-driven organization that aims to build the social and technical bridges to enable open sharing and re-use of data. The iAdopt model promotes the adoption of these principles in research data management.

### Wikidata

Wikidata is a free and open knowledge base that can be read and edited by both humans and machines. It can provide additional context for the instruments and experiments, further enhancing the understandability and reusability of the data.

The Experiment
--------------

This experiment involves creating a structured, machine-readable description of a MagLab scientific experiment using the RO-Crate metadata format. The resulting RO-Crate will be FAIR-compliant and will form part of an Open Knowledge Network. The structure of this metadata is designed to provide context to Large Language Models (LLMs) that can assist in the interpretation and reuse of the data.

Structure of the Repository
---------------------------

```tree
.
├── data
│   ├── raw
│   ├── processed
├── notebooks
│   ├── ro-crate-metadata.ipynb
├── scripts
├── docs
│   ├── project_overview.qmd
└── dvc
    ├── .dvc
    ├── .dvcignore
├── quarto
│   ├── _site
├── ro-crate-metadata.jsonld
├── .gitignore
├── README.md
└── LICENSE
```

This repository is organized following best practices for data science project structure, merged with the structure of an RO-Crate. It includes the following directories:

* `data`: Contains all the raw and processed experimental data
* `notebooks`: Contains the Jupyter notebooks used to generate the RO-Crate metadata
* `scripts`: Contains the scripts used to generate the RO-Crate metadata
* `docs`: Contains the Quarto document that describes the project

User Story
----------

The owner of the instrument is the NSF facility MagLab that has a ROR (https://ror.org/03s53g630). Josiah Carberry is the Facility user and has a ORCID (https://orcid.org/0000-0002-1825-0097) data acquisition info:

The experimental data (spectra) are acquired by a spectrometer (#1 HRS750, #2 IsoPlane, Teledyne Princeton Instruments). The spectrometers are (almost) fully automated and controlled via the LightField software (Teledyne Princeton Instruments). LightField automatically saves the acquired data and all experiment settings (spectrometer settings) in one file. https://www.princetoninstruments.com/products/software-family/lightfield

LightField saves files in *.SPE format (whatever it means).

MagLab uses a  file- / folder- name convention for data collection that follows the following pattern:

Folder name: PI name_Experiment ID_Magnet system-Instrument_Start date

For Example:
  Josiah_Carberry_P19401-E011-DC_SCM3-HRS750_02-12-2023
  Josiah_Carberry_none_B114-IsoPlane_02-12-2023

There is also a file name convention for the data files that follows the following pattern:
File name: Type of the experiment: PL, Ra(man), Re(flectance), Tr(ansmittance) Sample short name: **** Magnetic field: ***T (or from to ) Temperature: ***K Light source: SC, 532nm, 785nm, … - Power: ***mW or uW, or percentage Central frequency / wl/energy: ***cm-1, nm, eV Slit: value: *** um Acq.time: ***min or sec Objective NA: ***NA Other: gate voltage, pressure, …

For example:
PL_WSe2-MoSe2_00.0T_to_05.2T_ 10K_633nm-100uW_720nm_30um_2min_0.65NA.SPE
Ra_CsPr_30T_7.2K_532nm-2mW_550cm-1_30um_3x2min_0.82NA.SPE 
Re_InSe_0T_5K_SC-20%600meV_50um_5sec_0.65NA_Gate_Sweep_-10V_to_+20V.SPE
