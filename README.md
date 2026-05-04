# TOFU


## Installation
Run the following to create a conda environment with the necessary dependencies.
```bash
conda create -n tofu python=3.11
```
Next, after the activation of ```tofu``` environment, install required libraries.
```bash
pip install torch==2.8.0 torchvision==0.23.0 torchao==0.12.0 triton==3.4.0 --index-url https://download.pytorch.org/whl/cu128
pip install datasets==3.6.0
pip install einops
pip install transformers
pip install peft
pip install trl
pip install bitsandbytes
pip install sacrebleu
```

Next, after the activation of ```tofu``` environment, we recommend installing our code as a package. To do this, run the following.
```bash
pip install -e .
```


## Utilization

You can quantize a model using the following command:
```bash
python utils/quantize.py --model /path/to/model --output_dir /path/to/output/directory
```
After quantization, you can further train the model using:
```bash
python experiments/train_q_sft.py [options]
```
This supports training on datasets such as Alpaca and UltraFeedback, and allows selecting different methods, including CE, λ-PR, GEM, Focal Loss, and TOFU.
Inference and evaluation scripts are available in the ```inference``` and ```evaluation``` directories.