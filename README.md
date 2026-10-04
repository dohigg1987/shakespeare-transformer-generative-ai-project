# Character-Level Transformer Text Generation (Tiny Shakespeare)

A small decoder-only Transformer, implemented from scratch in PyTorch, is trained to generate Shakespeare-style dialogue one character at a time. The project evaluates the generated text (valid-word rate, repetition, verbatim copying, qualitative failure cases) and discusses bias, misuse and creative ownership.

## Contents

- `generative_model.ipynb`: the complete, executed notebook (data inspection, preprocessing, model, training, generation, evaluation, failure analysis, summary)
- `Generative_AI_Analysis_Report.pdf`: the Generative AI Analysis and Ethics Report with citations and references
- `requirements.txt`: environment captured with `pip freeze`
- `data/README.md`: dataset access instructions (the notebook downloads the text and verifies its checksum)
- `figures/`: figures written by the notebook when it runs (also embedded in the notebook outputs and included in the zip version)

## Reproduce

```
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute generative_model.ipynb
```

Training uses the CPU and takes about 4 minutes; the full notebook runs in about 10 minutes.

## Headline result

Validation loss fell from 4.3 to 1.66 (perplexity 5.25). The output reproduces the layout of a play script with real speaker names but has no coherent meaning. At temperature 1.3 about a third of generated words are not in the training text.

## Data source

Karpathy, A. (2015). char-rnn [Computer software and data set]. GitHub. https://github.com/karpathy/char-rnn
