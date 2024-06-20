# TSR_model_comparison

This repository is dedicated to the comparison of models for Table Structure Recognition (TSR). Specifically, it evaluates and contrasts the performance of two advanced models: Table Transformers and Unitable.
Key Features:

- Models Compared: Table Transformers (TATR) vs Unitable
- Evaluation Metric: S-TEDS (Structural Tree Edit Distance Similarity)
- Dataset Used: SynthTabNet

This comparison is part of my degree project for the title of Masters in Data Science and Analytics from EAFIT University. It aims to provide insights into the strengths and weaknesses of each model when applied to the task of recognizing and interpreting table structures from various data sources.

## Cloning the Repository

To clone this repository along with its submodules, which are related to the models being compared, use the following commands:

```bash

# Clone the repository with submodules
git clone --recurse-submodules https://github.com/JmGarzon/TSR_model_comparison.git

# Navigate into the repository
cd TSR_model_comparison
```
If you have already cloned the repository and forgot to include the submodules, you can initialize and update them with:

```bash

# Initialize and update submodules
git submodule update --init --recursive
```

## Getting Started

1. Install Dependencies: Ensure you have all necessary dependencies installed for each project (`Unitable`/`table-transformer`).
Refer to the README files within each submodule for specific requirements.
    - TATR: https://github.com/JmGarzon/table-transformer?tab=readme-ov-file#code-installation
    - Unitable: https://github.com/JmGarzon/unitable?tab=readme-ov-file#quick-start

2. Download the pre-trained models to be evalated.
    - TATR: https://github.com/JmGarzon/table-transformer?tab=readme-ov-file#pre-trained-model-weights
        - This project used `TATR-v1.1-All-msft.pth`.
        - Place the downloaded weights into `TSR_model_comparison\table-transformer\pretrained_models`.
    - Unitable: https://huggingface.co/poloclub/UniTable/tree/main
        - This project used `unitable_large_structure.pt`.
        - Place the downloaded weights into `TSR_model_comparison\unitable\experiments\unitable_weights`

3. Prepare Data: Download and prepare the SynthTabNet dataset from https://github.com/IBM/SynthTabNet.
    - If you want to use the filtered subsample of SynthTabNet used in this project, please add [these `.jsonl` files](https://eafit-my.sharepoint.com/:f:/g/personal/jmgarzonv1_eafit_edu_co/Ep1_GLp3JK5OsVWu5sjPHicBRllbQ4wQnN9HycegwoyqLw?e=LDiUve) to each catgory in your SynthTabNet folder.

4. Update relevant paths in your local machine in the following files:
    - `TSR_model_comparison\table-transformer\src\test_model.py`
    - `TSR_model_comparison\table-transformer\src\tatr_runner.py`
    - `TSR_model_comparison\unitable\model_evaluation\test_model.py`
    - `TSR_model_comparison\unitable\model_evaluation\unitable_runner.py`

5. Run Experiments:
    - Run `unitable\model_evaluation\test_model.py` to generate CSV files that compiles the S-TEDS value of Unitable predictions against the ground truth for each of the SynthTabNet categories.
    - Run `table-transformer\src\test_model.py` to generate CSV files that compiles the S-TEDS value of TATR predictions against the ground truth for each of the SynthTabNet categories.

# Next Steps

    Change Model Configurations: Adjust the configurations of the models to better suit your specific needs or experiment with different settings.

    Evaluate Pre-trained Models: Test different pre-trained models to assess their performance on the SynthTabNet dataset (Or any other dataset with the same structure).

    Fine-tuning: Fine-tune the models on any other relevant dataset to potentially improve performance.

    Create Metrics and Compare Results: Use the same tools to generate the S-TEDS metrics and compare the results across different configurations or fine-tuned models.

# Contact

For any questions or issues, please open an issue in this repository or contact me at `jmgarzonv1@eafit.edu.co`.