
# nanoGPT


## install

```
pip install torch numpy transformers datasets tiktoken wandb tqdm
```

Dependencies:

- [pytorch](https://pytorch.org) <3
- [numpy](https://numpy.org/install/) <3
-  `transformers` for huggingface transformers <3 (to load GPT-2 checkpoints)
-  `datasets` for huggingface datasets <3 
-  `tiktoken` for OpenAI's fast BPE code <3
-  `wandb` for optional logging <3
-  `tqdm` for progress bars <3

## dataset prepare
```sh
python data/daily/prepare.py
```

## train

```sh
python train.py config/train_daily.py
```

## text generate

```sh
python sample.py --out_dir=out-daily
```

To allow sentences to end naturally, a punctuation_ids set is defined for punctuation filtering: punctuation_ids = {stoi['.'], stoi['?']}, and punctuation_ids is passed during text generation

The generated text is written to the file out-daily/gen_daily.txt