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

The outbreak of Covid-19 calls an action of NLP researchers for a means to access the content of literature for potentially useful informtaion to deal with the disease, and multiple datasets have been released, notably, LitCovid by NCBI and CORD-19 by Allen Institute for AI. Now, many groups are producing and releasing annotations to the data set.
However, it would become much more useful if the datasets can be accessed in an integrated way.
Covid19-PubAnnotation is an open collaboration to collect those effort and produce an integrated annotation to the Covid-19-related literature datasets. PubAnnotation is an open repository of literature annotation which features functionalities to collect and integrate contributed annotations. A collaborative annotation environment for the two literature datasets are setup at PubAnnotation, and a number of groups area producing annotation for contribution. We are aiming at releasing a meaning amount of rich annotation data sets in the end of the virtual hackathon. Contribution with annotation datasets is completely open, and all the contributed annotation datasets will become immediately integrated and accessible, in various ways, including search, visualization, and fine-grained access.

# Proof of concept example

### Individual vs. Aggregated annotations

Following example demonstrates the benefit of aggregating various annotations, the more the better.

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

When there are annoations shown above, a search over them can be issued.
Below is an example which shows the result of a search for the sentences which mention SARS (severe acute respiratory syndrome) and anatomical locations:<br/>
[The result of search for the sentences which mention SARS and anatomical locations](http://pubannotation.org/projects/CORD-19-sample-paragraphs/search?query=PREFIX+pubann%3A%3Chttp%3A%2F%2Fpubannotation.org%2Fontology%2F%3E%0D%0ASELECT+DISTINCT+%3Fsentence%0D%0AWHERE+%7B%0D%0A%09%3Fo1+tao%3Adenoted_by+%3Fsars_mention+%3B%0D%0A%09%09a+%3Chttp%3A%2F%2Fpurl.obolibrary.org%2Fobo%2FMONDO_0005091%3E+.%0D%0A%09%3Fo2+tao%3Adenoted_by+%3Flocation_mention+%3B%0D%0A%09%09a+%3Fc2+.%0D%0A%09FILTER+strstarts%28str%28%3Fc2%29%2C+%22http%3A%2F%2Fpurl.obolibrary.org%2Fobo%2FUBERON_%22%29%0D%0A%0D%0A%09%3Fo3+tao%3Adenoted_by+%3Fsentence+%3B%0D%0A%09%09a+pubann%3ASentence+.%0D%0A%09%3Fsentence+tao%3Acontains+%3Fsars_mention+.%0D%0A%09%3Fsentence+tao%3Acontains+%3Flocation_mention+.%0D%0A%7D%0D%0A&template_select=23&show_mode=textae&project_name=&projects=CORD-19-sample-MONDO%2CCORD-19-sample-UBERON)

# Repository

An environment to collect annotations to Covid-19 literature is set up at [PubAnnotation](http://pubannotation.org), which
* is a public repository of text annotation for which anyone can contribute with his/her annotation data
* all the contributed annotations are automatically aligned to the canonical texts in PubAnnotation.
* search is enabled over contributed anntoations.

# Literature data sets

* LitCovid (NCBI) : [Home](https://www.ncbi.nlm.nih.gov/research/coronavirus/) \| [PubAnnotation](http://pubannotation.org/collections/LitCovid)
* CORD-19 (Allen research institute of AI) : [Home](https://pages.semanticscholar.org/coronavirus-research) \| [PubAnnotation](http://pubannotation.org/collections/CORD-19)

# Plan

* The literature collections @ PubAnnotation will be kept updated as the collections themselves are growing (under development).
* Anyone can contribute with their annotation datasets, of any kind of annotation to the literature collection.

# Participants, so far

Names | Annotations
------|------------
Mariana Neves ([BfR](https://www.bfr.bund.de/))| Cell line annotation
Nico Colic ([UZH](https://www.uzh.ch/)), Fabio Rinaldi ([IDSIA](http://www.idsia.ch/)) | OGER annotation
Simon Suster | PICO categories
Zhiyong Lu ([NCBI](https://www.ncbi.nlm.nih.gov/)) | PubTator
Mayla Boguslav, William Baumgartner, Larry Hunter ([UColorado](http://www.ucdenver.edu/)) | Epistemic statements
Keith Suderman, Nancy Ide ([Vassar College](https://www.vassar.edu/)) | TimeML annotation
JanChristoph Klie, Richard Eckart de Castilho ([TUDarmsdadt](https://www.informatik.tu-darmstadt.de/ukp)) | INCEpTION
Wang Yuxing, Jingbo Xia ([HZAU](http://www.hzau.edu.cn/)) | Gene variation and GOF/LOF annotation

<br/>

## Annotator

Aiko Hiraki ([DBCLS](http://dbcls.rois.ac.jp/))


## Coordinator

Jin-Dong Kim ([DBCLS](http://dbcls.rois.ac.jp/))

