# Adaptive Cross-modal Embeddings for Image-Text Alignment (ADAPT)

This code implements a novel approach for training image-text alignment models, namely ADAPT.

<p align="center">
    <img src="assets/adapt.png" width="700"/>
</p>
<!-- future link: https://github.com/jwehrmann/retrieval.pytorch/assets/adapt.png -->

ADAPT is designed to adjust an intermediate representation of instances from a modality _a_ using an embedding vector of an instance from modality _b_. Such an adaptation is designed to filter and enhance important information across internal features, allowing for guided vector representations – which resembles the working of attention modules, though far more computationally efficient. For further information, please read our [AAAI 2020 paper](https://www.researchgate.net/publication/337636199_Adaptive_Cross-modal_Embeddings_for_Image-Text_Alignment).


## Installation

### 1. Python 3 & Anaconda

We don't provide support for python 2. We advise you to install python 3 with [Anaconda](https://docs.anaconda.com/anaconda/install/) and then create an environment.

### 2. As standalone project

```
conda create --name adapt python=3
conda activate adapt
git clone https://github.com/jwehrmann/retrieval.pytorch
cd retrieval.pytorch
pip install -r requirements.txt
```

### 3. Download datasets

```
wget https://scanproject.blob.core.windows.net/scan-data/data.zip
```

## Quick start

### Setup

* Option 1:

```
conda activate adapt
export DATA_PATH=/path/to/dataset
```

* Option 2:

You can also create a shell alias (shortcut to reference a command). For example, add this command to your shell profile:
```
alias adapt='source activate adapt && export DATA_PATH=/path/to/dataset' 
```

And then only run the declared name of the alias to have everything configured:
```
$ adapt
```

### Training Models

#### ADAPT-T2I

You can reproduce our main results using the following scripts.

* Training on Flickr30k:
```
python run.py options/adapt/f30k/adapt_t2i.yaml
python test.py options/adapt/f30k/adapt_t2i.yaml -data_split test
python run.py options/adapt/f30k/adapt_i2t.yaml
python test.py options/adapt/f30k/adapt_i2t.yaml -data_split test
```

* Training on MS COCO:
```
python run.py options/adapt/coco/adapt_t2i.yaml
python test.py options/adapt/coco/adapt_t2i.yaml -data_split test
python run.py options/adapt/coco/adapt_i2t.yaml
python test.py options/adapt/coco/adapt_i2t.yaml -data_split test
```

## Citation

If you find this research or code useful, please consider citing our paper:

```
@article{wehrmanna2020daptive,
  title={Adaptive Cross-modal Embeddings for Image-Text Alignment},
  author={Wehrmann, J{\^o}natas and Kolling, Camila and Barros, Rodrigo C},
  booktitle={The Thirty-Fourth AAAI Conference on Artificial Intelligence (AAAI 2020)},
  year={2020}
}
```


## Poster

<p align="center">
    <img src="assets/adapt_poster.png" width="300"/>
</p>
