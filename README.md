## Sequence Labeling for NLP (Assignment 3)

This repository implements a sequence labeling model for NLP (e.g., NER/POS) using recurrent neural networks and optional pre-trained word embeddings.

### Objectives
- **Encode text and labels numerically** for neural network input/output
- **Build, train, and run** a recurrent model for sequence labeling
- **Initialize embeddings** with pre-trained GloVe vectors (optional)

---

### Project Structure
```
.
├── data/                     # Train/eval/trial TSV datasets
├── sequencelabeling.ipynb    # Main notebook (end-to-end workflow)
├── test.py                   # Automated checks (pytest)
├── test_utils/               # Test fixtures & pretrained artifacts
├── requirements.txt          # Python dependencies
└── README.md                 # You are here
```

---

### Quickstart
1) Create a virtual environment (recommended) and install dependencies:
```
pip install -r requirements.txt
```

2) (Optional) Download GloVe embeddings to enable pre-trained initialization:
- Linux/macOS:
```
wget http://nlp.stanford.edu/data/glove.6B.zip
unzip -d glove glove.6B.zip
```
- Windows (PowerShell):
```
curl -L -o glove.6B.zip http://nlp.stanford.edu/data/glove.6B.zip
tar -xf glove.6B.zip -C ./glove
```
Alternatively, download manually from `http://nlp.stanford.edu/data/glove.6B.zip` and unzip into a `glove/` folder at repo root.

3) Open the notebook and run cells:
- `sequencelabeling.ipynb`

---

### Datasets
- `data/train.tsv`: Training set
- `data/eval.tsv`: Evaluation/validation set
- `data/trial.tsv`: Small sample for quick runs

All files are in TSV format; the notebook includes cells to load and preprocess them.

---

### Running Tests
This project includes tests to validate your implementation and guide development.
```
python -m pytest -q
```
Artifacts under `test_utils/` (e.g., vocab, labels, sample models) are provided to speed up testing.

---

### Notebook Outline (what you'll find in `sequencelabeling.ipynb`)
- Data loading and formatting into token/label sequences
- Building a vocabulary and label mapping
- Model definition (RNN-based sequence labeler; with/without pre-trained embeddings)
- Training loop and metrics
- Inference/prediction on evaluation data

---

### Using Pre-trained Embeddings
If `glove/` is present with GloVe files (e.g., `glove.6B.100d.txt`), the notebook can build an embedding index and initialize the model embedding layer. Ensure the embedding dimension matches the chosen GloVe file.

---

### Requirements
Install with:
```
pip install -r requirements.txt
```
Python 3.9+ is recommended.

---

### Reproducibility Tips
- Fix random seeds where possible
- Log package versions (`pip freeze > versions.txt`)
- Keep `test_utils/` unchanged to ensure tests run consistently

---

### License
Academic/educational use.

---

### Acknowledgements
- GloVe embeddings from Stanford NLP
- Course scaffolding and test artifacts provided as part of the assignment
