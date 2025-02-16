---
publish: true
Date Created: 01-26-2025 8:18
Last Modified: 02-09-2025 18:55
---
# Other
[[Options Trading]]

# Nvidia
## [Jensen Huang Inteview](https://www.youtube.com/watch?v=7ARBJQn6QkM)
GPUS are time travelling
- simulation of futures, enable lifetimes worth of work in one lifetime  
- gaming first step: huge market, huge potential of separating parallelize (GPU) vs sequential (CPU) gaming  
- notice it easily beats supercomputer CPUS at other industries/tasks, but have to trick CPU to use GPU  
  - CUDA born: make common programming languages very accessible for GPU execution  
  - ![[efa32dadc0c6c4f1a8be675317687571_MD5.png]]  
  - physical dynamics need in gaming so more needs for cuda, great chance of huge market give everyone huge computing power  
- revolutionize image classification \- ALEXNET trained huge image dataset on Nvidia GPUs GTX 580  
	- reasoned hope that this would reach researchers esp in CV x CUDA → solved by Alexnet others  
	- take Alexnet to next level? what needed architecture for that? DGX reinvent entire tech stack from IBM  
	- one by one, solve suddenly long time unsolved problems of intelligence 2012  
- why took 10 years? if no success for long time, may course correct  
	- unwavering core belief in NVIDIA based on fundamental reasoned beliefs  
	- belief in inherent scalability of DNNs \+ parallel/sequential GPU/CPU design  
	- unless physical, architectural, or mathematical limit, then focus on what to learn from any data modality (human experience)  
		- words to human robot action?  
		- proteins to what the proteins do? universal problems that may be solved  
		- last 10 years is AI science, next 10 years is application of AI  
- applied AI \-\> omniverse sim robots way faster (cosmos real life shaders)  
	- **generative AI:** OpenAI, hallucinates not grounded by truth  
	- **ground truth:** NotebookLM, search web, grounde by truth  
	- just like chatgpt, same with physical ai. object permanence, inertial, cause/effect, etc.  
	    - encoded into sim to build world common sense  
	    - ground truth? physical simulation, laws we understood for long time  
- next 10 years, "fun", "accessible"  
	- friend AI follows you in car, smart phone, physical robot, smartphone, etc. for entire life a certainty  
	- in 8 years since 2016 OpenAI delivery, 10k times more energy efficient now  
		- what about other things? light bulbs? etc.   
	- transformers: each word ←\> each other word in context, so put limits (impossible to process all so "forget", flash attention, hierarchical attention, wave attention to fit the transformer model)  
	- fundamentally believe new revolution beyond transformers in designing hardware bets  
	- hire experts at semiconductive physics (know limits) not rely on just manufacturers TSMC  
		- constantly optimizing everything (aerodynamics of cooling fans, liquid cooling, etc.)  
		- domain expertise to push limits of such design  
	- new bet: cosmos x omniverse simulate world  
	- sim biology language too just like physics, predict/gen/etc.   
	- climate science weather prediction very regional   
- affect our future?   
	- i.e. highways everywhere, 1 week work becomes instantaneous, new industries, living/etc.  
	- Jensen as CEO, empowers to tackle more ambitious things rather than feel useless by superintelligence, same with AI  
	- constant back-and-forth between Geforce and AI (gaming → physics → CUDA→ alexnet → geforce → DLSS → gaming) RTX 50 series  
	- AI from researchers to everybody, students, so smaller DGX $3k for schools  
	- being incredibly good at asking questions → prompt engineering → for everybod\!\!\!, where to use AI?   
	- **![[99bdcbcd7953d7ae246ff03c7875103c_MD5.png]]**
	- cuda; 


# Job Market as ML Researcher
## [The Harsh Reality of Being an ML Researcher](https://www.youtube.com/watch?v=Me8klpxNaeg)

- phD greatly helps getting into FAANG, otherwise need equivalent exp  
- very domain-specific (esp in companies like NVIDIA) expertise so years of working on 1 problem  
- if PhD, need successful committee-accepted papers  
- big companies split roles into research scientist vs ml engineer  
- research \= applying your cutting edge idea \= no guarantee it will work/be accepted  
- nowadays research highly advanced to be cutting edge \= lots of equipment needed (see physics)  
- [https://borismeinardus.substack.com/p/a-list-of-different-ml-domains](https://borismeinardus.substack.com/p/a-list-of-different-ml-domains)  
	- RL  
	- NLP  
	- CV  
	- audio processing  
	- multimodal learning  
	- GNNs  
	- applied ai  
	- evolutionary learning  
	- meta learning

## [ML Engineering is Not What You Think - ML jobs Explained](https://www.youtube.com/watch?v=SizM-sau8F0)  
**data engineer:** 
- find data sources, build/maintain infrastructure to collect data pipeline, preprocess extracted info in desired format  
- easily access massive data organized (i.e. PostgreSQL)  
- preprocess clean data (missing vals/mistakes) to handle for actual analysis/training


**data scientist**
- extract business insight from data (sometimes manually) for trends/patterns for decisions  
- exploratory data analysis to predict  
- use rudimentary ML models not beyond jupyter notebook to auto train and see which perform best  
- work with stakeholders closely


**applied scientist**
- not normal tabular dataset (no simple AutoML tool, complex data?)  
- read papers, build on existing research, apply theoretical knowledge to real world (new hypothesis, ideas)  
- cross-disciplinary expertise i.e. healthcare x ML, close to production systems large-scale


**generic ml engineer**
- generic, turn data into product (better engineer than data scientist, may not use ML)  
	- i.e. not use ML: ML infrastructure engineer, ML accelerator/hardware engineer  
- subfield of software engineering, LC  
- i.e. endpoint to handle requests to ML request, develop distrib. computing infrastructure for training  
- better to hire brilliant software engineers that not necessarily know ML


**research (needs PhD)**
- develop actual models like transformers, attention is all you need, LLMs  
- real research? solid knowledge of ML and DL details, domains of ML commits to one (i.e. CV)  
- read papers to keep up and how they can be improved (hypothesis) and design/test  
- lots of uncertainty in results, publish paper and attend conferences


**research engineer (very rare)**
- come up with idea for ml engineer to do, usually combined as one role,


## [AI/ML Engineer path - The Harsh Truth](https://www.youtube.com/watch?v=HR91Wrr8KH8)
- job opening lingo?  
- "senior" \= 5-10 years exp, 5% phd  
- "junior" \= 50% BS 50% MS, 3% phd, 8% mention qualification of MS/PhD  
- "AI/ML" \= 60% ms, 11% phd,  30% mention qualification of MS/PHD  
- 2019, 19% of AI data scientists held PHD, 2021 28%, AI index report 45% increase in AI PhDs  
- start anywhere any engineer  
	- first look at exp, then skill demo, then degree  
	- go for less competitive roles not necessarily follow passion in tough job market  
	- in current nonAI roles: initiate automate manual task, propose real solutions, observe ppl's challenges  
	- side projects for real customers

## [The Sad Reality of AI Job Market w/ ML Engineer](https://www.youtube.com/watch?v=yrK2Fn0tQ7w)

- skill in **integrating** working AI models in existing complex software infrastructure  
- Stanford AI Index Report: study of AI job market for phds/10+ years exp. in 2022  
- want true ml engineer not whip up Pytorch easy. need nitty gritty data pipeline, monitor perf/retrain  
- used to be only academia, now 35-70% growth for industry research for the money
	- traditional education not at all prep for this shift to industry research

## [How To Get into AI (Realistically) w/ ML Engineer](https://youtu.be/nMbm8ib3b0M?si=7VeNmy_F74_u-MbG)

- domain expertise very critical  
- data scientist (model dev, domain expertise esp important, intuition and needs, demo, POC) vs ml engineer  
- audio engineer, boss expert in audio not AI so knows nitty-gritty (domain expertise)  
- define clear end goal: skipping PhD is the exception for insanely smart ppl with quick side projects  
- R for academic circles, full tech stack (databases, pipelines, apache(airflow, kafka), models, then deployment (i.e. AWS, Google Cloud, Asure backend), tools to monitor/retrain existing models  
- ![[edb7dcf921f4ae6aa0c2d46a4e3d2240_MD5.png]]  
- aspirations?  
	- analyst at small company w/ basic ML/Python   
	- vs ML engineering at FAANG substantial multi-year journey of theory/practicality  
	- 