<!-- $theme: gaia -->

## YAMP: a framework enabling reproducibility in metagenomics research

##### <br>Alessia Visconti
###### <a><img src="./img/twitterLogo.png" height="25px"/> @_alesssia</a><br/>

---
<!-- *template: invert -->

# Reproducibility

---

<span style="display:block; height:140px;"></span>
<div style="font-size: 150%", align="right">

# >50%    <span style="display:inline-block; width:25%"></span>       >70%
</div>

###  &nbsp;&nbsp;&nbsp;&nbsp; Repeatability <span style="display:inline-block; width:12%"></span> Reproducibility

<span style="display:block; height:100px;"></span>
<div style="font-size: 60%", align="right">

[Baker, Nature	(2016)](https://www.nature.com/news/1-500-scientists-lift-the-lid-on-reproducibility-1.19970)
</div>

---

<center>
<img src="./img/failures.png" height="550px"/>
</center>

<div style="font-size: 60%", align="right">

[Baker, Nature	(2016)](https://www.nature.com/news/1-500-scientists-lift-the-lid-on-reproducibility-1.19970)
</div>

---

<center>
<img src="./img/crisis.png" height="550px"/>
</center>

<div style="font-size: 60%", align="right">

[Baker, Nature	(2016)](https://www.nature.com/news/1-500-scientists-lift-the-lid-on-reproducibility-1.19970)
</div>

---

<span style="display:block; height:140px;"></span>
<div style="font-size: 190%", align="center">

# ~31%
</div>

## not-reproducible &rarr; non-trustable

<span style="display:block; height:80px;"></span>
<div style="font-size: 60%", align="right">

[Baker, Nature	(2016)](https://www.nature.com/news/1-500-scientists-lift-the-lid-on-reproducibility-1.19970)
</div>

---

<span style="display:block; height:150px;"></span>

<center>
<img src="./img/cost.png" height="200px", border="6"/>
</center>


---
<!-- *template: invert -->

# What cause<br>irreproducible research?

---

# 1. Unavailability of primary data

---

# Solution: data repository

<center>
<img src="./img/dataRepository.png" height="450px"/>
</center>

<div style="font-size: 60%", align="right">

[Data Sharing - Wikipedia](https://en.wikipedia.org/wiki/Data_sharing)
</div>

---

# 2. Unavailability of sufficient details on computational experimentation 

---

<span style="display:block; height:130px;"></span>

<center>
<img src="./img/drugome_rep.png" height="250px", border="6"/>
</center>

---


<span style="display:block; height:170px;"></span>

<center>
<div style="font-size: 180%">

# Provenance

</div>
<center>

---

### Solution: well-structured workflows

<span style="display:block; height:10px;"></span>


<center>
<img src="./img/genericworkflow.png" height="450px"/>
</center>

---

<span style="display:block; height:90px;"></span>

<center>
<img src="./img/workflows.png" height="300px", border="6"/>
</center>

---

<span style="display:block; height:160px;"></span>

<center>
<img src="./img/galaxy.png" height="200px"/>
</center>

---

<span style="display:block; height:160px;"></span>

<center>
<img src="./img/snakemake.png" height="200px"/>
</center>

---

<span style="display:block; height:170px;"></span>

<center>
<img src="./img/nextflow.png" height="200px"/>
</center>

---
<!-- *template: invert -->

# Data Sharing + 
# well-structured workflow

---

# 3. Variations across workstations and operating systems

---

#### Same data & pipeline, different OS and results

<span style="display:block; height:25px;"></span>


<center>
<img src="./img/transcriptionQuantification.png" height="350px"/>
</center>

<div style="font-size: 55%">
Kallisto and Sleuth pipelines, applied to find differentially expressed genes (q-value < 0.01) in an RNA-seq experiment, using data from human lung fibroblasts. 
</div>

<div style="font-size: 60%", align="right">

<span style="display:block; height:30px;"></span>

[Di Tommaso et. al, Nat. Biotechnol	(2017)](https://www.nature.com/articles/nbt.3820#f1)
</div>

--- 

# Solution: containers

<center>
<img src="./img/genericContainer.png" height="450px"/>
</center>

<div style="font-size: 60%", align="right">

[What is a container - Docker](https://www.docker.com/what-container)
</div>

<img src="./img/docker.png" height="300px" img style="float: right;"/>
<img src="./img/singularity.png" height="280px" img style="float: right;"/>

---
<!-- *template: invert -->

# Data sharing +
# well-structured containerised workflow

---

#### Same data, pipeline, container, and results

<span style="display:block; height:25px;"></span>


<center>
<img src="./img/transcriptionQuantification_fixed.png" height="350px"/>
</center>

<div style="font-size: 55%">
Kallisto and Sleuth pipelines, applied to find differentially expressed genes (q-value < 0.01) in an RNA-seq experiment, using data from human lung fibroblasts.
</div>

<div style="font-size: 60%", align="right">

<span style="display:block; height:30px;"></span>

[Di Tommaso et. al, Nat. Biotechnol	(2017)](https://www.nature.com/articles/nbt.3820#f1)
</div>


---
<!-- *template: invert -->

# Metagenomics

---

<br/>

<centre>
<img src="./img/bellybuttons.png" height="440px"/>
</centre>


<div style="font-size: 60%", align="right">

<span style="display:block; height:30px;"></span>

[Belly Button Microbiome &copy; Joana Ricou](http://microbialart.tumblr.com/)
</div>

---

> Metagenomics is the study of genetic material recovered directly from environmental samples.
<sub><sup>*[Metagenomics - Wikipedia](https://en.wikipedia.org/wiki/Metagenomics)*</sup></sub>

---

<br/>

<center>
<img src="./img/wordcloud.png" height="500px" border="0px"/>
</center>

---
<!-- *template: invert -->

# How to conduct metagenomics studies (simplified)

---

<center>
<img src="./img/complete_pipeline.png" height="680px" border="0px"/>
</center>

---
<!-- *template: invert -->

# YAMP: *Yet Another Metagenomics Pipeline*

---
<!-- *template: invert -->

## Why?

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

<center>
<img src="./img/nextflow.png" height="170px"/>
<img src="./img/docker.png" height="230px"/>
<img src="./img/singularity.png" height="230px"/>
</center>

---
<!-- *template: invert -->

# What?

---

<center>
<img src="./img/implemented_pipeline.png" height="680px" border="0px"/>
</center>


---

<center>
<img src="./img/QC_steps.png" height="450px"/>
</center>

---

<center>
<img src="./img/CC_steps.png" height="550px"/>
</center>

---

<img src="./img/extra_output.png" height="580px">

<div style="font-size: 60%", align="right">

Additional output: detailed log file &<br>statistics of memory usage and time of execution
</div>

---
<!-- *template: invert -->

# A case study

---

<span style="display:block; height:0px;"></span> 

<center>
<img src="./img/Table1.png" height="470px" border=6 />
</center>

<div style="font-size: 60%", align="right">

 <span style="display:block; height:30px;"></span> 

HMP Phase III, [PRJNA275349](http://www.ebi.ac.uk/ena/data/view/PRJNA275349)
</div>

---

<center>
<img src="./img/time.png" height="580px" border=4/>
</center>

<div style="font-size: 60%", align="right">

2.60GHz Intel<sup>&reg;</sup> Xeon<sup>&reg;</sup> processor with 32 GB of RAM
</div>

---

<center>
<img src="./img/phylum_bodysites.png" height="580px" border=4/>
</center>

<div style="font-size: 60%", align="right">


Phylum level relative abundances
</div>

---
<center>
<img src="./img/PCoA_bodysites.png" height="580px"/ border=4 >
</center>

<div style="font-size: 60%", align="right">


PCoA evaluated on the Bray-Curtis dissimilarity<br>among species relative abundances
</div>

---
<!-- *template: invert -->

# Conclusion

---

# 1. Easy to use

---

<span style="display:block; height:50px;"></span>

<div style="font-size: 77%", align="left">


Install YAMP (with preset default parameters):
	
    
	git clone https://github.com/alesssia/YAMP.git
   

Download the supporting data:
  
  	wget https://zenodo.org/record/1068229/files/YAMP_resources_20171128.tar.gz
    tar -xzf YAMP_resources_20171128.tar.gz
    

 
 Run your analysis:
 
    nextflow run YAMP.nf --reads1 R1.fq.gz --reads2 R2.fq.gz
    	--prefix mysample --outdir outdir --mode complete
            --with-singularity docker://alessia/yampdocker

</div>

---

# 2. Portable 

---

<span style="display:block; height:40px;"></span>

<div style="font-size: 90%" >

* SGE cluster


	executor = 'sge'


* PBS/Torque cluster


	executor = 'pbs'
	


* Your laptop


	// executor = 'sge'

</div>


---

# 3. Flexible

---

# 4. Reproducible 

---

# 5. Not only for metagenomics

---

# 6. Not only for reproducibility

---
<!-- *template: invert -->

# Where?

---

<div style="font-size: 85%", align="right">

<center>
<img src="./img/github.png" height="130px"/> <br/>  
<a>https://github.com/alesssia/YAMP</a>
<a>https://github.com/alesssia/YAMP/wiki</a>

<span style="display:block; height:1px;"></span> 

<img src="./img/dockerhub.png" height="80px"> 
<a>https://hub.docker.com/r/alesssia/yampdocker</a>

<span style="display:block; height:1px;"></span> 
 
<img src="./img/bioarxiv.png" height="100px"> 
<a>https://www.biorxiv.org/content/early/2017/11/21/223016</a>


</center>

</div>

---
<!-- *template: invert -->

# Who?

---
### <u>Acknowledgements </u>

Mario Falchi
Tiphaine Martin

Paolo Di Tommaso
Brian Bushnell 

Richard Davies

<span style="display:block; height:70px;"></span> 


<center>
<img src="./img/KCL.png" height="115px" img style="float: left;"/>  
<img src="./img/tuk.png" height="115px" img style="float: left;"/>
<a><img src="./img/twitterLogo.png" height="25px"/> @_alesssia</a><br/>
<a><img src="./img/mail.png" height="25px"/> alessia.visconti@kcl.ac.uk</a>
</center>
