---
layout: page
feature_image: "https://picsum.photos/1300/400?image=989"
feature_text: |
  # Covid19-PubAnnotation
  *Open, collaborative annotations to Covid-19 literature*
---

# Goal

To enable a *live* collaboration for annotation of Covid-19-related literature.

# Introduction

The outbreak of Covid-19 has motivated NLP researchers to explore ways to mine scientific literature, in order to potentially identify information that can be useful in fighting the virus. To this end, multiple Covid-19 datasets have been released, including LitCovid by NCBI and CORD-19 by Allen Institute for AI, and several research groups are producing and releasing annotations of these data that identify relevant entities mentioned within them. To avoid duplication of effort and, crucially, provide a communal collection of annotations over Covid-19-related literature, we have established Covid19-PubAnnotation, an open collaboration to collect annotations from researchers around the world in order to produce a set of integrated annotations that can be used for further research to fight the disease. 

PubAnnotation is an open repository of annotations of biomedical literature whose goal is to collect and integrate annotations contributed by the global NLP community. The PubAnnotation project has set up a collaborative annotation environment to enable a focused community effort and initiated a virtual bio-hackathon group involving annotators and annotation software developers from around the world. The Hackathon is taking place from April 5-11, after which a sizable set of richly annotated Covid-19 data will be released for public use. Contribution of annotation datasets, both during and after the hackathon, is open to anyone. All contributions will be integrated and made accessible via search, visualization, and fine-grained access from the PubAnnotation platform.

# Proof of concept example

### Individual vs. Aggregated annotations

The following example demonstrates the benefit of aggregating various annotations over Covid-19 literature:

* Annotation using [MONDO](https://mondo.monarchinitiative.org/)
<div class="textae-editor" style="font-size:x-small" config="http://textae-configs.pubannotation.org/configs/COVID19-annotation.json"
target="http://pubannotation.org/docs/sourcedb/CORD-19/sourceid/f820e5c342b0e3ce1af0905b69ebea927865a809/spans/2850-3461/annotations.json?projects=CORD-19-sample-MONDO"></div>

* Annotation using [MONDO](https://mondo.monarchinitiative.org/) + [HP](https://hpo.jax.org/)
<div class="textae-editor" style="font-size:x-small" config="http://textae-configs.pubannotation.org/configs/COVID19-annotation.json"
target="http://pubannotation.org/docs/sourcedb/CORD-19/sourceid/f820e5c342b0e3ce1af0905b69ebea927865a809/spans/2850-3461/annotations.json?projects=CORD-19-sample-MONDO,CORD-19-sample-HP"></div>

* Annotation using [MONDO](https://mondo.monarchinitiative.org/) + [HP](https://hpo.jax.org/) + [UBERON](http://uberon.org/) + [FMA](http://si.washington.edu/projects/fma)
<div class="textae-editor" style="font-size:x-small" config="http://textae-configs.pubannotation.org/configs/COVID19-annotation.json"
target="http://pubannotation.org/docs/sourcedb/CORD-19/sourceid/f820e5c342b0e3ce1af0905b69ebea927865a809/spans/2850-3461/annotations.json?projects=CORD-19-sample-MONDO,CORD-19-sample-HP,CORD-19-sample-UBERON,CORD-19-sample-FMA"></div>

* Annotation using [MONDO](https://mondo.monarchinitiative.org/) + [HP](https://hpo.jax.org/) + [UBERON](http://uberon.org/) + [FMA](http://si.washington.edu/projects/fma) + [CHEBI](https://www.ebi.ac.uk/chebi/)
<div class="textae-editor" style="font-size:x-small" config="http://textae-configs.pubannotation.org/configs/COVID19-annotation.json"
target="http://pubannotation.org/docs/sourcedb/CORD-19/sourceid/f820e5c342b0e3ce1af0905b69ebea927865a809/spans/2850-3461/annotations.json?projects=CORD-19-sample-MONDO,CORD-19-sample-HP,CORD-19-sample-UBERON,CORD-19-sample-FMA,CORD-19-sample-CHEBI"></div>

* Annotation using [MONDO](https://mondo.monarchinitiative.org/) + [HP](https://hpo.jax.org/) + [UBERON](http://uberon.org/) + [FMA](http://si.washington.edu/projects/fma) + [CHEBI](https://www.ebi.ac.uk/chebi/) + [IDO](http://infectiousdiseaseontology.org/)
<div class="textae-editor" style="font-size:x-small" config="http://textae-configs.pubannotation.org/configs/COVID19-annotation.json"
target="http://pubannotation.org/docs/sourcedb/CORD-19/sourceid/f820e5c342b0e3ce1af0905b69ebea927865a809/spans/2850-3461/annotations.json?projects=CORD-19-sample-MONDO,CORD-19-sample-HP,CORD-19-sample-UBERON,CORD-19-sample-FMA,CORD-19-sample-CHEBI,CORD-19-sample-IDO"></div>


### Search over aggregated annotations

Once integrated into PubAnnotation, annotations such as those shown above can be searched for individual entities as well as groups of entities. The example below shows the result of a search for sentences mentioning SARS (severe acute respiratory syndrome) and anatomical locations::<br/>
[Search results for sentences mentioning SARS and anatomical locations](http://pubannotation.org/projects/CORD-19-sample-paragraphs/search?query=PREFIX+pubann%3A%3Chttp%3A%2F%2Fpubannotation.org%2Fontology%2F%3E%0D%0ASELECT+DISTINCT+%3Fsentence%0D%0AWHERE+%7B%0D%0A%09%3Fo1+tao%3Adenoted_by+%3Fsars_mention+%3B%0D%0A%09%09a+%3Chttp%3A%2F%2Fpurl.obolibrary.org%2Fobo%2FMONDO_0005091%3E+.%0D%0A%09%3Fo2+tao%3Adenoted_by+%3Flocation_mention+%3B%0D%0A%09%09a+%3Fc2+.%0D%0A%09FILTER+strstarts%28str%28%3Fc2%29%2C+%22http%3A%2F%2Fpurl.obolibrary.org%2Fobo%2FUBERON_%22%29%0D%0A%0D%0A%09%3Fo3+tao%3Adenoted_by+%3Fsentence+%3B%0D%0A%09%09a+pubann%3ASentence+.%0D%0A%09%3Fsentence+tao%3Acontains+%3Fsars_mention+.%0D%0A%09%3Fsentence+tao%3Acontains+%3Flocation_mention+.%0D%0A%7D%0D%0A&template_select=23&show_mode=textae&project_name=&projects=CORD-19-sample-MONDO%2CCORD-19-sample-UBERON)

# Repository

[PubAnnotation](http://pubannotation.org) has set up a public repository of Covid-19 literature annotations to which anyone can contribute. All contributed annotations are automatically aligned to the canonical texts in PubAnnotation. Search facilities are enabled over contributed annotations.

# Literature data sets

* LitCovid (NCBI) : [Home](https://www.ncbi.nlm.nih.gov/research/coronavirus/) \| [PubAnnotation](http://pubannotation.org/collections/LitCovid)
* CORD-19 (Allen research institute of AI) : [Home](https://pages.semanticscholar.org/coronavirus-research) \| [PubAnnotation](http://pubannotation.org/collections/CORD-19)

More will be added.

# Plan

* The literature collections @ PubAnnotation will be kept updated as the collections themselves are growing (under development).
* Anyone can contribute with their annotation datasets, of any kind of annotation to the literature collection.

# Participants, contribution, prograss, so far

Names | Annotations | Status
------|--------------------- 
Mariana Neves ([BfR](https://www.bfr.bund.de/))| Cell line annotation | Initial version added for LitCovid
Nico Colic ([UZH](https://www.uzh.ch/)), Fabio Rinaldi ([IDSIA](http://www.idsia.ch/)) | OGER annotation | V.2 added for LitCovid
Simon Suster | PICO categories |
Zhiyong Lu ([NCBI](https://www.ncbi.nlm.nih.gov/)) | PubTator | Annotation ready for addition
Mayla Boguslav, William Baumgartner, Larry Hunter ([UColorado](http://www.ucdenver.edu/)) | Epistemic statements | V.1 ready to be added for CORD-19
Keith Suderman, Nancy Ide ([Vassar College](https://www.vassar.edu/)) | LAPPS Grid biomedical analysis software | Under development for performance improvement
JanChristoph Klie, Richard Eckart de Castilho ([TUDarmsdadt](https://www.informatik.tu-darmstadt.de/ukp)) | INCEpTION annotation platform | Ready to be integrated
Wang Yuxing, Jingbo Xia ([HZAU](http://www.hzau.edu.cn/)) | Gene variation and GOF/LOF annotation | annotation is under development

<br/>

## Annotator

Aiko Hiraki ([DBCLS](http://dbcls.rois.ac.jp/))


## Coordinator

Jin-Dong Kim ([DBCLS](http://dbcls.rois.ac.jp/))

