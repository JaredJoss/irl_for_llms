# Inverse Reinforcement Learning for Large Language Models

This repository implements **Inverse Reinforcement Learning (IRL)** for extracting reward models from **Reinforcement Learning from Human Feedback (RLHF)**-fine-tuned Large Language Models (LLMs). The project includes scripts for fine-tuning LLMs, applying Max-Margin IRL, and evaluating reward models.

## Environment Setup

To replicate the environment used for training, follow the steps below:

### Step 1: Create and activate a conda environment
```bash
conda create --name IRLforLLM python=3.11.7
conda activate IRLforLLM
```

### Step 2: Clone this repository
```bash
git clone git@github.com:JaredJoss/irl_for_llms.git
cd irl_for_llms
```

### Step 3: Install dependencies
```bash
pip install -r requirements.txt
```

To fine-tune LLMs using RLHF, you'll need the trlx library. Follow the instructions on the official TRLx GitHub page to install it:

[https://github.com/CarperAI/trlx](https://github.com/CarperAI/trlx)


## Usage

### Fine-Tuning an LLM using RLHF
To fine-tune a large language model using RLHF, use the following command:
```bash
python src/train_rlhf.py
```

### Generate IRL Demonstrations
Before running the IRL algorithm, you need to generate demonstrations using the original and RLHF-trained model. Run the following script to create the necessary dataset for IRL:

```bash
python src/create_dataset_irl.py
```

### Extract Reward Model using Max-Margin IRL
After generating the demonstrations, you can implement Max-Margin IRL and extract the reward function from the RLHF-trained LLM:

```bash
python irl.py
```
