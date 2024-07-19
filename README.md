# `scnn`: Scalable Convex Neural Networks in Tensorflow

A library for global optimization of shallow neural networks.
API documentation at [ReadTheDocs](https://scnn.readthedocs.io/en/latest/).

### Requirements

Python 3.8 or newer. Development dependencies are listed in `dev_requirements.txt`. 

### Setup

Install using `pip`:

```
python -m pip install pyscnn
```

Or, clone the repository and manually install: 

```
git clone https://github.com/pilancilab/scnn.git
python -m pip install ./scnn
```

### Contributions

Coming soon!

### Citation

Please cite our paper if you use this package.

```
@article{DBLP:journals/corr/abs-2202-01331,
  author    = {Aaron Mishkin and
               Arda Sahiner and
               Mert Pilanci},
  title     = {Fast Convex Optimization for Two-Layer ReLU Networks: Equivalent Model
               Classes and Cone Decompositions},
  journal   = {CoRR},
  volume    = {abs/2202.01331},
  year      = {2022},
  url       = {https://arxiv.org/abs/2202.01331},
}
```

Looking for the code to replicate our experiments?
See [scnn_experiments](https://github.com/aaronpmishkin/scnn_experiments).

**The following information pertains to the translation of our project from Python & PyTorch to TensorFlow:**

This project aims to translate an existing **Python & PyTorch** codebase into **TensorFlow** for the SCNN library. The translation encompasses several interconnected files located in various directories within the src/scnn directory. Below is a list of all the files, along with their specific directories, that we translated from Python and PyTorch to TensorFlow:

•	src/scnn/optimize.py

•	src/scnn/models.py

•	src/scnn/private/methods/termination_criteria.py

•	src/scnn/private/interface/models.py

•	src/scnn/private/methods/optimizers/fista.py

•	src/scnn/private/methods/core/proximal_gradient.py

•	src/scnn/private/prox/proximal_ops.py

•	src/scnn/private/methods/optimizers/proximal_optimizer.py

•	src/scnn/private/methods/optimizers/optimizer.py

•	src/scnn/private/models/model.py

•	src/scnn/private/models/regularizers/regularizer.py

•	src/scnn/private/methods/line_search/conditions.py

•	src/scnn/private/methods/line_search/backtrack.py

•	src/scnn/private/methods/line_search/step_size_updates.py

The motivation behind this translation is found in the notebook file named **convex-vs-nonconvex.ipynb**, which imports the optimize module. In this notebook, we aim to analyze the behavior of the **FISTA** optimizer. Therefore, the first step is to translate the relevant parts of optimize.py.
During this process, it became evident that optimize.py relies on other files that also needed translation. Consequently, we provided all necessary files with their directories. We have commented out the original Python and PyTorch code to facilitate comparison with the new TensorFlow code.

For example, the translation process began with optimizer.py. Within this file, certain models such as **ConvexGatedReLU** and **GatedReLU** required translation. These models are defined in another file called models.py. This process continued until all relevant files were identified and translated. In total, we translated 14 files.
You can navigate to each file's directory to identify the specific parts that have been translated.
Additionally, the lab library is crucial for this project, as its absence may cause random errors in parts of the code unrelated to the specific model and optimizer translations. To install this library, you can use the following repository, which includes a setup.py file with the lab module and version tag:

[Repo's Link](https://github.com/pilancilab/scnn_experiments.git)


