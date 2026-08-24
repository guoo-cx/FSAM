# Mitigating Multimodal Hallucinations via Adaptive Layer Selection and Frequency-Sensitive Head Modulation

This repository contains the implementation for mitigating hallucinations in Multimodal Large Language Models (MLLMs).
The code is built on top of **LLaVA** and follows the default LLaVA environment setup.

  
## Environment Setup

This project follows the default LLaVA environment setup.

First, enter the LLaVA directory:

```bash
cd FreqDAM
```

Create and activate the conda environment:

```bash
conda create -n FreqDAM python=3.10 -y
conda activate FreqDAM
cd LLaVA
pip install -e .
```
Please make sure that the original LLaVA inference can run correctly before using FreqDAM.
### Evaluation

- `eval/eval_pope.py`  
  Evaluation script for POPE. It computes Accuracy, Precision, Recall, and F1 Score.

### Backbone

- `LLaVA`  
  The LLaVA codebase used as the backbone MLLM.
## Evaluation

After inference, evaluate the generated results using:

```bash
cd infer
python infer_pope.py \
  --annotation-file /path/to/pope/questions.json \
  --question-file /path/to/pope/questions.json \
  --result-file /path/to/output/answers.jsonl
```


## Example Workflow

```bash
# Activate environment
conda activate FreqDAM

# Run FreqDAM inference and evaluate POPE results
cd infer
bash infer_pope.sh

---


## License

This project is released under the license provided in the `LICENSE` file.
