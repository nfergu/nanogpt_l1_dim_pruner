# nanoGPT benchmark for l1_dim_pruner

A fork of [nanoGPT](https://github.com/karpathy/nanoGPT) to provide a benchmark for [l1_dim_pruner](https://github.com/nfergu/l1_dim_pruner)

## Usage

Using Python 3.10 or later:

```
pip install torch numpy transformers datasets wandb tqdm
```

```
python data/openwebtext/prepare.py
```

On GPU:

```
python train.py config/eval_gpt2.py
```

On CPU:

```
python train.py config/eval_gpt2.py --device=cpu compile=False
```

On CPU this will take while to run.
