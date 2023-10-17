# Notes for running a model with MPS device

This branch adds MPS support and allows specifying the number of generated samples via a `--n_samples` argument for the `eval_sample.py` script.

Use `--no-mps` to disable MPS and run on the CPU instead.

First, [Download pretrained models](https://drive.google.com/drive/folders/1EQ9koVx-GA98kaKBS8MZ_jJ8g4YhdKsL?usp=sharing) and save to `./PretrainedModels`.

Then, run the following:
```shell
$ mkdir outputs
$ mv PretrainedModels/qm9_latent2 outputs
$ pip install -r requirements_simplified.txt
$ python eval_sample.py --model_path outputs/qm9_latent2 --n_samples=1
```

Generated chains and molecules can be found in the `outputs/qm9_latent2/eval` directory.
E.g.,

```shell
$ open outputs/qm9_latent2/eval/chain_0/output.gif
```
