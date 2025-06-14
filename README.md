# SemiKong Chip Design LLM

An open-source AI/ML project to optimize semiconductor chip design using CoreML. Predicts defects with tabular data and analyzes design notes to generate optimization recommendations, deployable on iOS/macOS.

## Features
- **Defect Prediction**: Classifies chips as defective using features like process node, transistor count.
- **Text Analysis**: Classifies design notes for optimization potential with TF-IDF features.
- **Synthetic Datasets**: 10,000 samples each for tabular and text data.
- **CoreML Ready**: Train tabular classifiers in CreateML.
- **Community-Driven**: Contribute anonymized data, models, or Swift code.

## Project Structure
```
semikong-chip-design-llm/
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
├── CONTRIBUTING.md
├── src/
│   ├── generate_chip_data.py
│   ├── generate_text_data.py
│   └── preprocess_text.py
└── data/
    ├── tabular/
    │   └── chip_design_data.csv
    └── text_notes/
        └── design_text_data.csv
```

## Getting Started
### Prerequisites
- Python 3.8+
- Xcode 13+ with CreateML
- macOS

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/egkhor/semikong-chip-design-llm.git
   cd semikong-chip-design-llm
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Generate datasets:
   ```bash
   python src/generate_chip_data.py
   python src/generate_text_data.py
   python src/preprocess_text.py
   ```

### Using with CoreML
1. Open Xcode > CreateML > Tabular Classifier.
2. Import `data/tabular/chip_design_data.csv` or `data/text_notes/processed_design_text_data.csv`.
3. Set `has_defect` or `has_optimization` as the target.
4. Train and export as a `.mlmodel`.

## Notes
- **Synthetic Data**: For prototyping; use real design data for production.
- **Scalability**: Adjust `N_SAMPLES` in scripts.
- **Future Work**: Integrate true LLMs (e.g., fine-tuned Llama) or EDA tools.

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md).

## License
MIT License. See [LICENSE](LICENSE).

## Contact
Connect via GitHub Issues or www.egkhor.com.my
