# Oxford Nanopore Long-Read Bacterial Genome Assembly & Analysis Workflow

A reproducible **Galaxy workflow** for bacterial whole-genome assembly and downstream analysis using **Oxford Nanopore Technologies (ONT)** long-read sequencing data.

This workflow integrates quality assessment, read preprocessing, genome assembly, polishing, annotation, taxonomic classification, and assembly quality evaluation into a single, reproducible pipeline.

---

## Overview

This repository provides a Galaxy workflow developed for bacterial genome analysis from Oxford Nanopore long-read sequencing data. It is intended for researchers, students, and bioinformaticians seeking an end-to-end workflow for microbial genome assembly and annotation.

The workflow emphasizes reproducibility and leverages widely adopted open-source bioinformatics tools.

---

## Workflow

```text
Raw ONT Reads
      │
      ▼
 NanoPlot
      │
      ▼
 Porechop
      │
      ▼
 BBduk
      │
      ▼
 Filtlong
      │
      ▼
 Flye
      │
      ▼
 Medaka
      ├──────────────┬──────────────┐
      ▼              ▼              ▼
   BUSCO         GTDB-Tk        Prokka
      │
      ▼
    QUAST
```

---

## Pipeline Components

| Step | Tool     | Purpose                                   |
| ---- | -------- | ----------------------------------------- |
| 1    | NanoPlot | Long-read quality assessment              |
| 2    | Porechop | Adapter trimming                          |
| 3    | BBduk    | Quality filtering and contaminant removal |
| 4    | Filtlong | Long-read filtering                       |
| 5    | Flye     | De novo genome assembly                   |
| 6    | Medaka   | Assembly polishing                        |
| 7    | BUSCO    | Genome completeness assessment            |
| 8    | GTDB-Tk  | Genome-based taxonomic classification     |
| 9    | Prokka   | Genome annotation                         |
| 10   | QUAST    | Assembly quality evaluation               |

---

## Repository Structure

```text
.
├── workflow/
│   └── Galaxy-Workflow-*.ga
├── docs/
│   └── workflow.png
├── LICENSE
├── README.md
└── CITATION.cff
```

---

## Requirements

* Galaxy Platform (local or public instance)
* Oxford Nanopore long-read sequencing data
* Installed Galaxy tools corresponding to the workflow

---

## Input

* Oxford Nanopore long-read FASTQ files

---

## Output

Depending on the selected workflow steps, outputs may include:

* Quality assessment reports
* Filtered sequencing reads
* Genome assembly
* Polished assembly
* Genome annotation
* Taxonomic classification
* Assembly quality statistics
* Genome completeness assessment

---

## Installation

1. Clone this repository.

```bash
git clone https://github.com/Sivasan/ont-bacterial-genome-assembly-galaxy.git
```

2. Import the `.ga` workflow into a Galaxy instance.

3. Upload your ONT sequencing reads.

4. Execute the workflow.

---

## Reproducibility

The workflow is distributed in Galaxy's native `.ga` format, allowing straightforward import into compatible Galaxy installations for reproducible analyses.

---

## Data Availability

This repository contains **only the computational workflow**.

The sequencing datasets, genome assemblies, annotations, and analysis outputs used during research are **not included**, as they are associated with ongoing or unpublished studies. These materials will be released in accordance with publication, institutional, and data-sharing policies where applicable.

---

## Citation

If you use this workflow in your research, please cite the relevant software tools included in the pipeline.

A formal citation for this workflow will be added in a future release.

---

## License

This project is distributed under the **MIT License**.

See the `LICENSE` file for details.

---

## Acknowledgements

This workflow relies on several outstanding open-source bioinformatics projects, including NanoPlot, Porechop, BBduk, Filtlong, Flye, Medaka, BUSCO, GTDB-Tk, Prokka, QUAST, and the Galaxy Project. The developers of these tools are gratefully acknowledged.

---

## Author

**Sivasankar Palaniappan**

Scientist | Marine Microbiology | Environmental Biotechnology | Microbial Genomics | Bioinformatics

GitHub: https://github.com/Sivasan
