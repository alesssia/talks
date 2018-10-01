<!-- Slide powered by MARP (https://github.com/yhatt/marp) -->

<!-- $theme: gaia -->

#### DeepDiff: DEEP-learning for predicting DIFFerential gene expression from histone modifications
###### &nbsp;
###### *A. Sekhon, R. Singh, and  Y. Qi,  Bioinformatics 34 (17)*

###### &nbsp;
###### &nbsp;
###### UnConference 2018 

###### *[@_alesssia](https://twitter.com/_alesssia)* - *[@AIClubGenderMinority](https://twitter.com/AIClubGenderMin)* - *[@H2Oai](https://twitter.com/h2oai)*


---
<!-- *template: invert -->

# What? Why?

---

<centre>
<span style="display:inline-block; width:25%"></span>  <img src="./img/celltypes.png" height="600px"/>
</centre>

---

<centre>
<img src="./img/dna-chromatin-histone.png" height="600px"/>
</centre>

---

<centre>
<img src="./img/transcription_sm.png" height="600px"/>
</centre>

---

## Differential gene expression: cell differentiation and <u>diseases</u>

---
<!-- *template: invert -->

# Challenges

---

#### 1. Genome-wide histone modification (HM) signals are spatially structured and may have long-range dependency

---

#### 2. We want to  understand what the relevant HM factors are, and how they work together 

---

#### 3. We want to understand how HMs affect gene regulation, therefore we require a model with a degree of interpretability 

---

#### 4. We are dealing with multiple cells 

---
<!-- *template: invert -->

# How?

---
### Recurrent Neural Networks (RNNs)

<span style="display:block; height: 80px;"></span>

<centre>
<img src="./img/RNN-unrolled.png" height="250px"/>
</centre>

<span style="display:block; height: 10px;"></span>
<div style="font-size: 70%", align="right">

[Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
</div>

---
### Recurrent Neural Networks (RNNs)

<span style="display:block; height: 50px;"></span>

<centre>
<img src="./img/RNN-longtermdependencies.png" height="290px"/>
</centre>

<span style="display:block; height: 10px;"></span>
<div style="font-size: 70%", align="right">

[Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
</div>

---
#### Long Short Term Memory networks (LSTMs)

<span style="display:block; height: 50px;"></span>

<centre>
<img src="./img/LSTM3-chain.png" height="320px"/>
</centre>

<span style="display:block; height: 10px;"></span>
<div style="font-size: 70%", align="right">

[Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
</div>

---
#### Attention-based deep-learning methods

<span style="display:block; height: 10px;"></span>

<centre>
<img src="./img/Example-of-image-captioning-with-attention.png" height="400px"/>
</centre>

<span style="display:block; height: px;"></span>
<div style="font-size: 50%", align="right">

[How to Automatically Generate Textual Descriptions for Photographs with Deep Learning](https://machinelearningmastery.com/how-to-caption-photos-with-deep-learning/)
</div>

---
<!-- *template: invert -->

# DeepDiff

---
## Input generation

<span style="display:block; height: 0px;"></span>

<centre>
<span style="display:inline-block; width:10%"></span> <img src="./img/Fig1.png" height="400px"/>
</centre>

----
## DeepDiff network architecture

<span style="display:block; height: 1px;"></span>

<centre>
<span style="display:inline-block; width:10%"></span> <img src="./img/Fig2.png" height="300px"/>
</centre>


---
###  Multitasking with auxiliary tasks

<span style="display:block; height: 80px;"></span>

1. Cell-type specific  prediction
2. Siamese architecture formulation

---
<!-- *template: invert -->

# Results

---
## Dataset

<span style="display:block; height: 20px;"></span>

<div style="font-size: 90%">

* 10 cell lines from the RoadMap project  (18,460 genes)

	* 10,000 genes used for training
	* 2,360 genes used for validation (and tuning)
	* 1,100 genes used for testing

* Performances as PCC between DeepDiff variants and *baselines* (aka, alternative approaches)

</div>

---
## Performances

<centre>
<img src="./img/Results.png" height="550px", border=6/>
</centre>

---
## Interpretation via Attention

<span style="display:block; height: 1px;"></span>

<centre>
<span style="display:inline-block; width:8%"></span><img src="./img/attentionResults.png" height="430px", border=6/>
</centre>



---
<!-- *template: invert -->

# Discussion

---

### Points for discussion

<span style="display:block; height: 50px;"></span>

<div style="font-size: 90%">

1. Any thoughts on DeepDiff architecture?
2. Will the DeepDiff generalise with new cell lines?
3. Is this the best way to evaluate DeepDiff?
4. Is attention helpful?

</div>

---

<!-- *template: invert -->

<span style="display:block; height: 100px;"></span>


# Thanks for surviving until the end of the last session :sunglasses:
# You deserve :pizza:

<centre>
  <span style="display:inline-block; width:78%"></span><img src="./img/h2o_logo.svg" height="150px", border=2/>
</centre>

<div style="font-size: 78%", align="right">
  #H2OAIWorld London &nbsp;&nbsp;&nbsp;&nbsp;
</div>
