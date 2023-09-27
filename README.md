# nanoGPT benchmark for l1_dim_pruner

A fork of nanoGPT to provide a benchmark for [l1_dim_pruner](https://github.com/nfergu/l1_dim_pruner)

## Usage

```
$ pip install torch numpy transformers datasets wandb tqdm
```

```
$ python data/openwebtext/prepare.py
```

```
$ python train.py eval_gpt2
```
