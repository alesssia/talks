<!-- Slide powered by MARP (https://github.com/yhatt/marp) -->

<!-- $theme: gaia -->

# YAMP: Yet Another Metagenomic Pipeline

##### <u>Alessia Visconti</u>, Tiphaine Martine, Mario Falchi
###### TwinsUK, King's College London

---

<!-- *template: invert -->

# Why?

---

# 1. Easy to use

---

# 2. Portable

---

# 3. Flexible

---

# 4. Reproducible

---

<!-- *template: invert -->

# How?

---

<img src="./img/nextflow.png" height="250px"/>

* Highly parallel
* Easily portable
* Very flexible and customisable

---

<img src="./img/docker.png" height="280px"/>

<br/>

* Lightweight, self-contained systems
* Software version management

---

<!-- *template: invert -->

# What?

---

<center>
<img src="./img/pipeline.png" height="680px"/>
</center>

---

<img src="./img/QC.png" height="690px" img style="float: left;"/>

#### Quality Control I

<br/>

* De-duplication: `clumpify`
* Trimming: `BBduk`
* Decontamination: `BBwrap`

---

<img src="./img/QC_assessment.png" height="690px" img style="float: left;"/>

#### Quality Control II

<br/>

* Assessment: `FastQC`

---

<img src="./img/CC.png" height="530px" img style="float: left;"/>

#### Community Characterisation

* Taxonomy binning & profiling: `metaphlan2`
* Functional annotation: `HUMAnN2`
* Assessment of diversity: `QIIME`

---

<!-- *template: invert -->

# Where?

---

<br/>

<center>
<img src="./img/github.png" height="150px"/> <br/>  
<a>https://github.com/alesssia/YAMP</a>
<a>https://github.com/alesssia/YAMP/wiki</a>
<br/>  <br/>  <br/>  
<img src="./img/dockerhub.png" height="90px"> <br/>  
<a>https://hub.docker.com/r/alesssia/yampdocker</a>
</center>

---

<!-- *template: invert -->

# Who?

---

### Acknowledgements

	TwinsUK

Mario Falchi
Tiphaine Martin

	The "community"

 Brian Bushnell
 Paolo Di Tommaso

<center>
<img src="./img/KCL.png" height="115px" img style="float: left;"/>  
<img src="./img/tuk.png" height="115px" img style="float: left;"/>
<a><img src="./img/twitterLogo.png" height="25px"/> @_alesssia</a><br/>
<a><img src="./img/mail.png" height="25px"/> alessia.visconti@kcl.ac.uk</a>
</center>
