# nanoGPT benchmark for l1_dim_pruner

A fork of [nanoGPT](https://github.com/karpathy/nanoGPT) to provide a benchmark for [l1_dim_pruner](https://github.com/nfergu/l1_dim_pruner).

This prunes 50% of the weights in the fully-connected layers of a GPT-2 model, along dimension 1 (the second dimension). 

## Installation

Using Python 3.10 or later:

```
pip install torch numpy transformers datasets tiktoken wandb tqdm
```

```
python data/openwebtext/prepare.py
```

## Benchmark

To prune a GPT-2 model using the [l1_dim_pruner](https://github.com/nfergu/l1_dim_pruner) and report the validation loss:

```
python train.py config/eval_gpt2_l1_dim_pruning.py --compile=False
```

When this finishes you should see a validation loss of **~3.5**.

If you do not a have GPU append `--device=cpu` to the arguments, but this will take a long time to run (multiple hours probably).

## Comparison

### Standard L1-norm

To compare to standard L1-norm pruning ([torch.nn.utils.prune.l1_unstructured](https://pytorch.org/docs/stable/generated/torch.nn.utils.prune.l1_unstructured.html#torch-nn-utils-prune-l1-unstructured)):

```
python train.py config/eval_gpt2_l1_pruning.py --compile=False
```

When this finishes you should see a validation loss of **~4.3**.


### Unpruned

To compare to the unpruned version:

```
python train.py config/eval_gpt2.py --compile=False
```

When this finishes you should see a validation loss of **~3.1**.
