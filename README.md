# Gene Prediction Tool

The Gene Prediction Tool is a Python program designed to predict gene locations in a given genomic sequence in FASTA format. It identifies potential start and stop codons, evaluates the presence of Shine-Dalgarno motifs, and generates both a list of predicted gene positions and a FASTA file containing the corresponding gene sequences.

## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)
- [Contact](#contact)

## Features

- Reads genomic sequences in FASTA format.
- Predicts genes based on user-defined parameters.
- Identifies Shine-Dalgarno motifs upstream of start codons.
- Outputs gene positions and sequences in both tabular and FASTA formats.

## Requirements
- Python 3.9
- Required Python packages:
  - `argparse`
  - `textwrap`
  - `re`
  - `os`
  - `pathlib`
  
### Create a virtual environment
It is recommended to create a virtual environment to install the required packages. You can create a virtual environment using `conda`:
```bash
conda create -n gpred python
conda activate gpred
```

## Installation
1. Clone the repository:
```bash
git clone git@github.com:SanaGUEDOUAR/geneprediction-tp.git
cd geneprediction-tp
```

2. Install any additional dependencies if needed.

## Usage
```bash
python gpred/gpred.py -i <genome_file.fasta> [-g <min_gene_len>] [-s <max_shine_dalgarno_distance>] [-d <min_gap>] [-p <predicted_genes_file>] [-o <fasta_file>]
```
### Arguments
- -i or --genome_file: (required) Path to the input genome file in FASTA format.
- -g or --min_gene_len: (optional) Minimum gene length to consider. Default is 50.
- -s or --max_shine_dalgarno_distance: (optional) Maximum distance from the start codon to search for a Shine-Dalgarno motif. Default is 16.
- -d or --min_gap: (optional) Minimum gap between two genes (Shine-Dalgarno motif not included). Default is 40.
- -p or --predicted_genes_file: (optional) Output file for the predicted gene positions in CSV format. Default is predict_genes.csv.
- -o or --fasta_file: (optional) Output FASTA file for the sequences of predicted genes. Default is genes.fna.

### Example
```bash
python gpred/gpred.py -i genome.fasta -g 100 -s 20 -d 50 -p predicted_genes.csv -o genes.fna
```

## Output
## Output

The program generates two types of output files based on the predicted genes in the genome:

1. **Predicted Genes File (`predict_genes.csv`)**:
   - This file contains a tabular representation of the predicted gene positions in the genome.
   - Each row includes:
     - **Start**: The start position of the predicted gene.
     - **Stop**: The stop position of the predicted gene.

   Example content of `predict_genes.csv`:
   Start, Stop
    1, 100
    200, 300
    400, 500

2. **Fasta File (`genes.fna`)**:
- This file provides the sequences of the predicted genes in FASTA format.
- Each gene sequence is preceded by a header line that identifies the gene.

Example content of `genes.fna`:
>gene_1
GTGCAATCAATTGAAGACATCTGGCAGGAAACACTGC
>gene_2
ATGAAATTTGTTATTGAGCGTGATCGTCTTGTCCAAG


## License
This project is licensed under the GNU General Public License v3.0. See the [LICENSE](https://www.gnu.org/licenses/gpl-3.0.html) file for more details.

## Contact
For questions or feedback, please contact:

Author: Sana Guedouar
Email: [sana.guedouar@etu.u-paris.fr](mailto:sana.guedouar@etu.u-paris.fr)
University: Université Paris Cité