[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2540718.svg)](https://doi.org/10.5281/zenodo.2540718)

# CNN Soil Texture Classification

1-dimensional convolutional neural networks (CNN) for the classification of soil texture based on hyperspectral data.

## Description

We present 1-dimensional (1D) convolutional neural networks (CNN) for the classification of soil texture based on hyperspectral data. The following CNN models are included:

* `LucasCNN`
* `LucasResNet`
* `LucasCoordConv`
* `HuEtAl`: 1D CNN by Hu et al. (2015), DOI: [10.1155/2015/258619](http://dx.doi.org/10.1155/2015/258619)
* `LiuEtAl`: 1D CNN by Liu et al. (2018), DOI: [10.3390/s18093169](https://dx.doi.org/10.3390%2Fs18093169)

These 1D CNNs are optimized for the soil texture classification based on the hyperspectral data of the *Land Use/Cover Area Frame Survey* (LUCAS) topsoil dataset. It is available [here](https://esdac.jrc.ec.europa.eu/projects/lucas). For more information have a look in our publication (see below).

**Introducing paper:** [arXiv:1901.04846](https://arxiv.org/abs/1901.04846)

**Licence:** [MIT](LICENSE)

**Authors:**

* [Felix M. Riese](mailto:felix.riese@kit.edu)
* [Sina Keller](mailto:sina.keller@kit.edu)

**Citation of the code and the paper:** see [below](#citation) and in the [bibtex](bibliography.bib) file

## Requirements

* see [Dockerfile](Dockerfile)
* download `coord.py` from [titu1994/keras-koordconv](https://github.com/titu1994/keras-coordconv) based on [arXiv:1807.03247](https://arxiv.org/abs/1807.03247)

## Setup

```bash
git clone https://github.com/felixriese/CNN-SoilTextureClassification.git

cd CNN-SoilTextureClassification/

wget https://raw.githubusercontent.com/titu1994/keras-coordconv/c045e3f1ff7dabd4060f515e4b900263eddf1723/coord.py .
```

## Usage

You can import the Keras models like that:

```python
import cnn_models as cnn

model = cnn.getKerasModel("LucasCNN")
model.compile(...)

```

Example code is given in the `lucas_classification.py`. You can use it like that:

```python
from lucas_classification import lucas_classification

score = lucas_classification(
    data=[X_train, X_val, y_train, y_val],
    model_name="LucasCNN",
    batch_size=32,
    epochs=200,
    random_state=42)

print(score)
```

## Citation

The bibtex file including both references is available [here](bibliography.bib).

### Paper

F. M. Riese and S. Keller, "Soil Texture Classification with 1D Convolutional Neural Networks based on Hyperspectral Data", 2019, [arXiv:1901.04846](https://arxiv.org/abs/1901.04846), Accepted at ISPRS Geospatial Week 2019 in Enschede (NL).

```tex
@article{riese2019soil,
    author = {Riese, Felix~M. and Keller, Sina},
    title = {Soil Texture Classification with 1D Convolutional Neural Networks based on Hyperspectral Data},
    year = {2019},
    note = {Accepted at ISPRS Geospatial Week 2019 in Enschede (NL)},
    archivePrefix = {arXiv},
    eprint = {1901.04846},
    primaryClass = {cs.CV},
    url = {https://arxiv.org/abs/1901.04846}
}
```

### Code

F. M. Riese, "CNN Soil Texture Classification", [doi.org/10.5281/zenodo.2540718](https://doi.org/10.5281/zenodo.2540718), 2019.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2540718.svg)](https://doi.org/10.5281/zenodo.2540718)

```tex
@misc{riese2019cnn,
    author       = {Riese, Felix~M.},
    title        = {{CNN Soil Texture Classification}},
    year         = {2019},
    publisher    = {Zenodo},
    DOI          = {10.5281/zenodo.2540718},
    howpublished = {\href{https://doi.org/10.5281/zenodo.2540718}{doi.org/10.5281/zenodo.2540718}}
}
```
