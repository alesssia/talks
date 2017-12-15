<!-- $theme: gaia -->

# Simplifying shotgun metagenomics analysis with Nextflow
#### <u>Alessia Visconti</u>
###### *TwinsUK*, King's College London

---
<!-- *template: invert -->

# Metagenomics?!?

---

<br/>

<centre>
<img src="./img/bellybuttons.png" height="440px"/>
</centre>

<sub><sup>*[Belly Button Microbiome &copy; Joana Ricou](http://microbialart.tumblr.com/)*</sup></sub>

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

# Metagenomics<br/>@TwinsUK

---

# Pilot study 

<br/>

<centre>
<img src="./img/bgi.png" height="300px" img style="float: left;" border="4px"/>
</centre>

---

# Let's go big!

<br/>
  
* 1300 samples 
* 22M reads per sample 
* 1.6 Gb of data per sample 
* Novel in-house analysis workflow

---

<br/><br/>

<center>
<img src="./img/blank.png" height="400px" />
</center>

---
<!-- *template: invert -->

# Why has this<br/>happened?

---

<center>
<img src="./img/duckfamily.jpg" height="600px" border="4px"/>
</center>

---

# The analysis *'workflow'*

<center>
<img src="./img/script.png" height="400px" border="4px"/>
</center>

---

# The infrastructure

<br/><br/>


* Cluster1: `SGE`
* Cluster2: `PBS`
* Cluster3: `Slurm`

---

# A recipe for disaster

<br/><br/>

* Limited computational literacy
* Fast-moving field 
* Big(ger) data 

---
<!-- *template: invert -->

# Rewind

---


#### MAP, Metagenomics Analysis Pipeline

<br/>

<center>
<img src="./img/map.png" height="450px" border="4px"/>
</center>

<div style="text-align: right">
<sub><sup> <a>https://github.com/alesssia/MAP</a> </sup></sub>
</div>   


--- 

## This is not a solution

<small> &nbsp; </small>

* No step parallelisation 
* Limited portability 
* Resources not fully exploited
* Software management still problematic

---
<!-- *template: invert -->

# Rewind (again)

---

<br/> 

<img src="./img/nextflow.png" height="250px" img style="float: left;"/>
<img src="./img/docker.png" height="300px" img style="float: right;"/>

---
<!-- *template: invert -->

# Is this the<br/>solution?

---

## Parallelisation

<small> &nbsp; </small>

	process decontaminate {

	...
    
	output:
	file "${params.prefix}_clean.fq" into assessdecontaminated
	file "${params.prefix}_clean.fq" into toprofiletaxa
	file "${params.prefix}_clean.fq" into toprofilefunction
	
<br/>
<div style="text-align: right; font-size: 60%" >
<br/><u>Disclaimer:</u> I know I could use the 'into'<br/>operator to duplicate the channel output 
</div>

---

## Portability

<div style="font-size: 90%" >

* Cluster1


	executor = 'sge'


* Cluster2


	executor = 'pbs'
	queue = 'metagenome'


* My laptop


	// executor = 'sge'

</div>

---

## Resources fully exploited 

<div style="font-size: 90%">

    $trim 
    {
        time =  '1h'
        cpus = 4
        memory = '32 GB'
        jobName = "trim"	  
    }


    $qualityAssessmentTrimmed
    {
        time =  '15m'
        cpus = 4
        memory = '4 GB'
        jobName = "qualityAssessmentTrimmed"
    }
		
</div>

---

## Reproducibility

<div style="font-size: 90%" >

* All parameters in one place 

	
	qin=33
	kcontaminants = 23
	phred = 10 trimmed 
	minlength = 60 
    mink = 11 
	hdist = 1   

	...
	

* Docker Integration 


	nextflow run <script> -with-docker <docker>
   
</div>

---

## Flexibility

<div style="font-size: 80%" > A single parameter in the configuration file</div>

	dedup = true

<div style="font-size: 80%" > and a test in the main script </div>

    process dedup {
	
	...

	when:
	  params.dedup

<div style="font-size: 80%" > allow selecting whether dedup should be performed </div>

---

## A few more extra

<div style="font-size: 90%" >

* File management


	publishDir wdir, mode: 'copy', pattern: "*.{html,txt}"


* Profiling 

<center>
<img src="./img/timeline.png" height="300px" border="4px"/>
</center>

</div>

---

# A recipe for success

<br/>

* Simplicity
* Flexibility
* Portability
* Reproducibility

---
<!-- *template: invert -->

# All's well that<br/>ends well


---

#### YAMP, Yet Another Metagenomics Pipeline

<div style="font-size: 90%" >

<center>
<img src="./img/github.png" height="150px"/> <br/>  
<a>https://github.com/alesssia/YAMP</a>
<a>https://github.com/alesssia/YAMP/wiki</a>
<br/>  <br/>  <br/>  
<img src="./img/dockerhub.png" height="90px"> <br/>  
<a>https://hub.docker.com/r/alesssia/yampdocker</a>
</center>

</div> 

---
### <u>Acknowledgements </u>


Mario Falchi
Tiphaine Martin

Paolo Di Tommaso

<br/><br/><br/><br/>

<center>
<img src="./img/KCL.png" height="115px" img style="float: left;"/>  
<img src="./img/tuk.png" height="115px" img style="float: left;"/>
<a><img src="./img/twitterLogo.png" height="25px"/> @_alesssia</a><br/>
<a><img src="./img/mail.png" height="25px"/> alessia.visconti@kcl.ac.uk</a>
</center>





