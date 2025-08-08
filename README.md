# 'Anarchists', 'terrorists', 'freedom fighters' – how do the media talk about social movements? The potential of historical press analysis.

Words are powerful and shifts in discourse are politically relevant. We see this today not only in the context of migration or gender. It makes a big difference, for example, whether the media speak of ‘climate activists’, ‘Klimakleber’ or ‘climate terrorists’. This is why media discourse, and especially the press, is also a central source for historical research. However, this presents several challenges: although many European newspapers from the 19th and 20th centuries have been digitised in various formats, they are often not systematically searchable as full texts. Where a full-text search is possible, it is not clear how well it works. Finally, there is the question of how best to analyse this mass data and how data science tools can help, for example by recognising typical word combinations. 

## Below is a brief guide to the key folders:

historical_press_analysis/          # root of the project
├── french_newspapers_analysis/
│   ├── context_analysis/                 # csv file per newspaper contains words count
│   ├── harvest_data_from_gallica.ipynb   # Gallica scraper notebook
│   └── words_frequency_context_analysis.ipynb   # term-frequency & context study
└── OCR_comparison_french_and_german/         # OCR quality benchmark
    ├── ddb_ocr/                              # raw OCR export from DDB
    ├── gallica_ocr.txt                       # raw OCR export from Gallica
    ├── models/                               # OCR-correction / language-model checkpoints
    ├── samples_from_ddb/                     # manually verified German snippets
    ├── samples_from_selected_list_of_french_newspapers/ # manually verified French snippets
    ├── OCR_comparison_french.ipynb           # WER/CER analysis – French set
    └── OCR_comparison_german.ipynb           # WER/CER analysis – German set

## Installation

Use **one** of the methods below.

---

### 1 · conda enironment (recommended)
```bash
# create the environment from the YAML file
conda env create -f environment.yml

# activate the new environment
conda activate historical-press
```

### 2 · pip + virtualenv
```bash
# create an isolated virtual environment in the .venv folder
python -m venv .venv

# activate it (Linux / macOS)
source .venv/bin/activate
# Windows equivalent:
# .venv\Scripts\activate

# install all required Python packages
pip install -r requirements.txt
```

> **GPU users**  
> Replace the default CPU-only PyTorch wheel if you need CUDA support:
> ```bash
> # PyTorch 2.3.0 for CUDA 12.1 (adjust as needed)
> pip install torch==2.3.0+cu121 -f https://download.pytorch.org/whl/torch_stable.html
> ```

## Data sources
- French newspapers: Downloaded from [Gallica](https://gallica.bnf.fr)
- German newspapers: Downloaded from [Deutsche Digitale Bibliothek](https://www.deutsche-digitale-bibliothek.de)