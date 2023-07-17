# EvalRS-KDD-2023
Official Repository for EvalRS @ KDD 2023, the Second Edition of the workshop on
well-rounding the evaluation of recommender systems.

[//]: # (TODO: add links here)

<a href="https://colab.research.google.com/drive/1QeXglfCUEcscHB6L0Gch2qDKDDlfwLlq?usp=sharing">  <img src="https://colab.research.google.com/assets/colab-badge.svg"> </a>


[//]: # (TODO: choose image - do we want to change it?)
![https://reclist.io/kdd2023-cup/](images/back_evalrs.png)


## Overview

This is the official repository for [EvalRS @ KDD 2023](https://reclist.io/kdd2023-cup/): _a Well-Rounded Evaluation of Recommender Systems_.

During KDD 2023 we will host a pizza hackathon night, where participants will pursue innovative projects for the rounded evaluation of recommender systems. The aim of the hackathon is to evaluate recommender systems across a set of important dimensions (accuracy being _one_ of them) through a principled and re-usable sets of abstractions, as provided by [RecList](https://github.com/jacopotagliabue/reclist) 🚀. 

Organizers will provide in advance an open dataset and tools to help the teams, and award monetary prizes for the best projects. Everything will go back to the community as open source contributions!

Please refer to the appropriate sections below to know how to get the dataset and run the evaluation loop properly.


### Important dates

Check the [EvalRS website](https://reclist.io/kdd2023-cup/) for the official timeline, including start date, paper submission and workshop day.

### Quick links

* 🛖 [EvalRS website](https://reclist.io/kdd2023-cup/)
* 📚 [EvalRS paper](https://arxiv.org/abs/2304.07145)
* 📖 [RecList website](https://reclist.io/)


## Dataset and target scenario

This Data Challenge is based on the [LFM-1b Dataset, Corpus of Music Listening Events for Music Recommendation](http://www.cp.jku.at/datasets/LFM-1b/). The use case is a typical user-item recommendation scenario: at _prediction time_, we have a set of target users to which we need to recommend a set of songs to listen to. To achieve that, we have historical anonymous data on previous music consumptions from users in the same setting.

Among all possible datasets, we picked LFM as it suits the spirit and the goal of this Challenge: in particular, thanks to [rich meta-data on users](http://www.cp.jku.at/people/schedl/Research/Publications/pdf/schedl_ijmir_2017.pdf), the dataset allows us to test recommender systems among many non-obvious dimensions, on top of standard Information Retrieval Metrics (for the philosophy behind behavioral testing, please refer to the original [RecList paper](https://arxiv.org/abs/2111.09963)).

To provide richer [meta-data on items](https://arxiv.org/abs/1912.02477), we have extended the LFM-1b dataset with content-based features and user-provided labels from the [WASABI dataset](https://github.com/micbuffa/WasabiDataset) (see more details below).

### Data overview

When you run the evaluation loop below, the code will automatically download _a chosen subset of the LFM dataset_, ready to be used (the code will download it only the first time you run it). There are three main objects available from the provided evaluation class:

_Users_: a collection of users and available meta-data, including patterns of consumption, demographics etc.. In the Data Challenge scenario, the user Id is the query item for the model, which is asked to recommend songs to the user.

![http://www.cp.jku.at/datasets/LFM-1b/](images/users.png)

_Tracks_: a collection of tracks and available meta-data. In the Data Challenge scenario, tracks are the target items for the model, i.e. the collection to chose from when the model needs to provide recommendations.

![http://www.cp.jku.at/datasets/LFM-1b/](images/tracks.png)

[//]: # (TODO: add one more picture on the extra fields and their coverage)

_Historical Interactions_: a collection of interactions between users and tracks, that is, listening events, which should be used by your model to build the recommender system for the Data Challenge.

![http://www.cp.jku.at/datasets/LFM-1b/](images/training.png)

For in-depth explanations on the code and the template scripts, see the instructions below and check the provided examples and tutorials in `notebooks`.

For information on how the original dataset was built and what meta-data are available, please refer to [this paper](http://www.cp.jku.at/people/schedl/Research/Publications/pdf/schedl_ijmir_2017.pdf).

[//]: # (TODO: add a reference to the notebook used to merge the two datasets)


## Hack with us

### 1. Try things out

#### Locally

If you just want to run our code on your local computer, download the repo and setup a virtual environment. _NOTE_: the code has been developed and tested with Python 3.8: please use the same version for reproducibility.

```bash
git clone https://github.com/RecList/evalRS-CIKM-2022
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

#### Via Codespaces

Otherwise, you can just launch the project by using Github Codespaces. Click on the green "code" button on the top of the Github page, select "Codespaces" and click on "Create codespaces on main".
Be aware, Github Codespaces is still in beta, if you don't have already applied for it, you can do it from here: [Sign up for the Codespaces beta](https://github.com/features/codespaces/signup)

### 2. Run evaluation on pretrained models

### 3. Train models for evaluation

### 4. Expand RecList with your own tests


## Hackathon Structure and Rules

### How the Hackathon runs

- can people work on it before the event? 
- What do we expect as a final submission (a repo? A video? A demo? Slides?) 


### Rules and Prizes

_The rules_

_The prizes_

Thanks to our generous sponsors, the following prizes will be awarded (at the sole discretion of the committee):

* a ... prize, xxxx USD, for ...;


## FAQ

* any questions we might expect

## Organizers

This Data Challenge focuses on building in the open, and adding lasting artifacts to the community. _EvalRS @ KDD 2023_ is a collaboration between practitioners from industry and academia, who joined forces to make it happen:

* Federico Bianchi, Stanford
* Patrick John Chia, Coveo
* Jacopo Tagliabue, NYU / Bauplan
* Claudio Pomo, Politecnico di Bari
* Gabriel de Souza P. Moreira, NVIDIA
* Ciro Greco, Bauplan
* Davide Eynard, mozilla.ai
* Fahd Husain, mozilla.ai

## Sponsors

This Data Challenge is open and possible thanks to the generous support of these awesome folks. Make sure to add a star to [our library](https://github.com/jacopotagliabue/reclist) and check them out!


<a href="https://mozilla.ai/" target="_blank">
    <img src="images/mozai.svg" width="200"/>
</a>

<a href="https://snap.com/en-US" target="_blank">
    <img src="images/snap.png" width="200"/>
</a>

<a href="https://www.bauplanlabs.com/" target="_blank">
    <img src="images/bauplan.png" width="200"/>
</a>



## How to Cite

If you find our code, datasets, tests useful in your work, please cite the original WebConf contribution as well as the EvalRS paper.

_RecList_

[//]: # (TODO: do we want to add other papers?)

```
@inproceedings{10.1145/3487553.3524215,
    author = {Chia, Patrick John and Tagliabue, Jacopo and Bianchi, Federico and He, Chloe and Ko, Brian},
    title = {Beyond NDCG: Behavioral Testing of Recommender Systems with RecList},
    year = {2022},
    isbn = {9781450391306},
    publisher = {Association for Computing Machinery},
    address = {New York, NY, USA},
    url = {https://doi.org/10.1145/3487553.3524215},
    doi = {10.1145/3487553.3524215},
    pages = {99–104},
    numpages = {6},
    keywords = {recommender systems, open source, behavioral testing},
    location = {Virtual Event, Lyon, France},
    series = {WWW '22 Companion}
}
```

_EvalRS_

```
@misc{https://doi.org/10.48550/arXiv.2304.07145,
  doi = {10.48550/ARXIV.2304.07145},
  url = {https://arxiv.org/abs/2304.07145},
  author = {Federico Bianchi and Patrick John Chia and Ciro Greco and Claudio Pomo and Gabriel Moreira and Davide Eynard and Fahd Husain and Jacopo Tagliabue},
  title = {EvalRS 2023. Well-Rounded Recommender Systems For Real-World Deployments},
  publisher = {arXiv},
  year = {2023},
  copyright = {Creative Commons Attribution 4.0 International}
}
```
