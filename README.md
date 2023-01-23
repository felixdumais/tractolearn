# tractolearn

[![test, package](https://github.com/scil-vital/tractolearn/actions/workflows/test_package.yml/badge.svg?branch=main)](https://github.com/scil-vital/tractolearn/actions/workflows/test_package.yml?query=branch%3Amain)

Tractography learning.

- Documentation: https://tractolearn.readthedocs.io/en/latest/
- [Contributing](.github/CONTRIBUTING.rst)


## Installation

To use tractolearn, it is recommended to create a virtual environment using
python 3.8 that will host the necessary dependencies. Torch tested with an
NVIDIA RTX 3090 with:

```sh
   virtualenv tractolearn_env --python=python3.8
   source tractolearn_env/bin/activate
```

`tractolearn` can be installed from its sources by executing, at its root:

```sh
   pip install -e .
```

In order to execute experiments reporting
to [Comet](https://www.comet.ml/site/), an `api_key` needs to be set as an
environment variable named `COMETML`. You can write this command in
you `.bashrc`

```sh
   export COMETML="api_key"
```

## Training models

To train deep learning models, you need to launch the
script [ae_train.py](scripts/ae_train.py). This script takes a config file with
all training parameters such as epochs, datasets path, etc. The most up-to-date
config file is [config.yaml](configs/train_config.yaml). You can launch the
training pipeline with the following command:

```sh
   ae_train.py train_config.yaml -vv
```

## How to cite

If you use this toolkit in a scientific publication or if you want to cite
our previous works, we would appreciate if you considered the following aspects:
- If you use `tractolearn`, please add a link to the appropriate code, data or
  related resource hosting service (e.g., repository, PyPI) from where you
  obtained `tractolearn`. You may want to include the specific version or commit
  hash information for the sake of reproducibility.
- Please, cite the appropriate scientific works:
  - If you use `tractolearn` to filter implausible streamlines or you want to
    cite our work in tractography filtering, cite [FINTA] and [FIESTA].
  - If you want to cite our work in tractography bundling, cite [CINTA] and
    [FIESTA].
    - If you use `tractolearn` to bundle streamlines using a k-nearest neighbor
      label approach, cite [CINTA].
    - If you use `tractolearn` to bundle streamlines using a thresholding
      approach, cite [FINTA] and [FIESTA].
  - If you use `tractolearn` for generative purposes or you want to cite our
    work in generative models for tractography, cite [GESTA] and [FIESTA].
  - If you use parts of `tractolearn` for other purposes, please generally cite
    [FINTA] and [FIESTA].

The corresponding `BibTeX` files are contained in the above links.

Please reach out to us if you have related questions.

## Patent

J. H. Legarreta, M. Descoteaux, and P.-M. Jodoin. “PROCESSING OF TRACTOGRAPHY
RESULTS USING AN AUTOENCODER”. Filed 03 2021. Imeka Solutions Inc. United States
Patent #17/337,413. Pending.

## License

This software is distributed under a particular license. Please see the
[*LICENSE*](LICENSE) file for details.


[FINTA]: ./doc/bibtex/Legarreta21_-_MIA_-_FINTA.bib "Filtering in tractography using autoencoders (FINTA)"
[CINTA]: ./doc/bibtex/Legarreta22_-_MICCAI-CDMRI_-_CINTA.bib "Clustering in Tractography Using Autoencoders (CINTA)"
[GESTA]: ./doc/bibtex/Legarreta22_-_arXiv_-_GESTA.bib "Generative sampling in tractography using autoencoders (GESTA)"
[FIESTA]: ./doc/bibtex/Dumais22_-_arXiv_-_FIESTA.bib "FIESTA: Autoencoders for accurate fiber segmentation in tractography"
