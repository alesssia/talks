<!-- $theme: gaia -->

###### &nbsp;
## Reproducible shotgun metagenomic analysis with Nextflow and containers

###### &nbsp;

#### Alessia Visconti
###### TwinsUK, King's College London

##### <a><img src="./img/twitterlogo.png" height="25px"/> @_alesssia</a><br/>

---
<!-- *template: invert -->

# Metagenomics?!?

---
<span style="display:block; height:40px;"></span>


<centre>
<img src="./img/bellybuttons.png" height="440px"/>
</centre>

<div style="font-size: 100%", align="right">

<sub><sup>*[Belly Button Microbiome &copy; Joana Ricou](http://microbialart.tumblr.com/)*</sup></sub>

</div>

---

> Metagenomics is the study of genetic material recovered directly from environmental samples.
<sub><sup>*[Metagenomics - Wikipedia](https://en.wikipedia.org/wiki/Metagenomics)*</sup></sub>

---
<!-- *template: invert -->

# Metagenomics<br/>@TwinsUK

---

<span style="display:block; height:130px;"></span>

<centre>
<img src="./img/bgi.png" height="300px" img style="float: left;" border="4px"/>
</centre>

---

<span style="display:block; height:150px;"></span>

<centre>
<img src="./img/hli.png" height="250px" img style="float: left;" border="4px"/>
</centre>

---

<center>
<img src="./img/pipeline.png" height="650px"/>
</center>

---
<!-- *template: invert -->

# With great power comes great responsibility 
# (and great trouble)

---

# 1. Reproducible 

---

# 2. Portable 

---

# 3. Flexible 

---

# 4. Efficient

---

# 5. Easy to use 

---
<!-- *template: invert -->

# Reinventing the wheel?

---
#### Well-structured workflows

<span style="display:block; height:0px;"></span>

<center>
<img src="./img/genericworkflow.png" height="420px"/>
</center>

<span style="display:block; height:px;"></span>

<img src="./img/nextflow.png" height="80px" img style="float: right;"/>

---
<!-- *template: invert -->

# Are we there yet?

---
#### Same data & pipeline, different OS and results

<span style="display:block; height:10px;"></span>

<center>
<img src="./img/transcriptionQuantification.png" height="350px"/>
</center>

<div style="font-size: 55%">
Kallisto and Sleuth pipelines, applied to find differentially expressed genes (q-value < 0.01) in an RNA-seq experiment, using data from human lung fibroblasts. 
</div>

<div style="font-size: 60%", align="right">

[Di Tommaso et. al, Nat. Biotechnol	(2017)](https://www.nature.com/articles/nbt.3820#f1)
</div>

--- 
## Containers

<center>
<img src="./img/genericContainer.png" height="350px"/>
</center>

<span style="display:block; height:1px;"></span>

<img src="./img/singularity.png" height="150px" img style="float: right;"/> 

<img src="./img/docker.png" height="150px" img style="float: right;"/>

---
#### Same data, pipeline, container, and results

<span style="display:block; height:10px;"></span>

<center>
<img src="./img/transcriptionQuantification_fixed.png" height="350px"/>
</center>

<div style="font-size: 55%">
Kallisto and Sleuth pipelines, applied to find differentially expressed genes (q-value < 0.01) in an RNA-seq experiment, using data from human lung fibroblasts.
</div>

<div style="font-size: 60%", align="right">

[Di Tommaso et. al, Nat. Biotechnol	(2017)](https://www.nature.com/articles/nbt.3820#f1)
</div>

---
<!-- *template: invert -->

# YAMP: *Yet Another Metagenomics Pipeline*

---
# 1. Reproducible 

<div style="font-size: 80%" >

* Parameters all in the same place 
	
		qin=33
		kcontaminants = 23
		phred = 10 trimmed 
		minlength = 60 
   		mink = 11 
		hdist = 1   
		...
	
* Container Integration 

		nextflow run <script> -with-docker <docker>
        nextflow run <script> -with-singularity <docker>
        
* Detailed logs
   
</div>

---
# 2. Portable 

<div style="font-size: 90%" >

* Cluster1

		executor 'sge'

* Cluster2

		executor 'pbs'


* Personal laptop

		// executor 'sge'

* The *Cloud* 

</div>
		
---
# 3. Flexible 

<span style="display:block; height:1px;"></span>

<div style="font-size: 75%">

	process dedup {
	
		input:
		set file(in1), file(in2) from todedup

		output:
		file("${params.prefix}_dedupe*.fq") into totrim
		file("${params.prefix}_dedupe*.fq") into topublishdedupe

		when:
		(params.mode == "QC" || params.mode == "complete") && params.dedup
        
            script:
	        """
                ...
        
            """
    }

</div>

---
# 4. Efficient

* User-transparent parallelisation
		
* Resources fully exploited 

	<div style="font-size: 75%">

	    $trim 
	    {
	        time '1h'
	        cpus 4
	        memory '32 GB'	  
	    }

	    $qualityAssessmentTrimmed
	    {
	        time '15m'
	        cpus 4
	        memory '4 GB'
	    }
		
	</div>

---
# 5. Easy to use 

<div style="font-size: 77%", align="left">

Install YAMP (with preset default parameters)
    
	git clone https://github.com/alesssia/YAMP.git
 
Download the supporting data
  
	wget https://zenodo.org/record/1068229/files/YAMP_resources_20171128.tar.gz
	tar -xzf YAMP_resources_20171128.tar.gz
    
Run the analysis
 
	nextflow run YAMP.nf --reads1 R1.fq.gz --reads2 R2.fq.gz
		--prefix mysample --outdir outdir --mode complete
	        --with-singularity docker://alessia/yampdocker

</div>

---

# 6. Not only for reproducibility

---

<span style="display:block; height:160px;"></span>

<center>
  
# 7. Not only for metagenomics

<span style="display:block; height:20px;"></span>

<div style="font-size: 70%">

<img src="./img/nf-core-logo.png" height="100px"/>   &nbsp;
<a>https://nf-co.re</a>
</div>

</centre>

---
<!-- *template: invert -->

# Nextflow + containers = :tada:

---

<div style="font-size: 85%", align="right">

<center>
<img src="./img/gigascience.png" height="220px" border=4> 

<img src="./img/github.png" height="140px"/>   
<a>https://github.com/alesssia/YAMP</a>

<span style="display:block; height:1px;"></span> 

<img src="./img/dockerhub.png" height="80px"> 
<a>https://hub.docker.com/r/alesssia/yampdocker</a>

<span style="display:block; height:1px;"></span> 

</center>

</div>

---
### <u>Acknowledgements </u>

Mario Falchi
Tiphaine Martin

Paolo Di Tommaso
Richard Davies

<span style="display:block; height:150px;"></span> 

<center>
<img src="./img/twinsUK.jpg" height="115px" img style="float: left;"/>
<a><img src="./img/twitterLogo.png" height="25px"/> @_alesssia</a><br/>
<a><img src="./img/mail.png" height="25px"/> alessia.visconti@kcl.ac.uk</a>
</center>
