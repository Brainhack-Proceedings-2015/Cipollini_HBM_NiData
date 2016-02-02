---
event: '2015 OHBM Hackathon (HI)'

title:  'Advancing Open Science through NiData'

author:

- initials: BC
  surname: Cipollini
  firstname: B
  email: bcipollini@ucsd.edu
  affiliation: aff1
  corref: aff1
- initials: AR
  surname: Rokem
  firstname: A.
  email: arokem@uw.edu
  affiliation: aff2

affiliations: 

- id: aff1
  orgname: 'University of California, San Diego'
  street: 1 Embarcardo St
  postcode: 90270
  city: San Diego
  state: California
  country: USA
- id: aff2
  orgname: 'University of Washington'
  street: 1 Pike's Place
  postcode: 87777
  city: Seattle
  state: Washington
  country: USA

url: http://github.com/nidata/hackathon

coi: None

acknow: The authors would like to thank the organizers and attendees of the 2015 OHBM Hackathon.

contrib: BC and AR wrote the software and the report.
  
bibliography: brainhack-report

gigascience-ref: REFXXX
...

#Introduction
The goal of this project is to improve accessibility of open datasets by curating them. [“NiData"](http://github.com/nidata/nidata) aims to provide a common interface for documentation, downloads, and examples to all open neuroimaging datasets, making data usable for experts and non-experts alike.

#Approach
Open datasets promise to allow more thorough analysis of hard-to-collect data and re-analysis using state-of-the-art analysis methods. However, open datasets are not truly open unless they are easy to find, simple to access, and have sufficient documentation for use. Currently, publicly available data in neuroscience are scattered across a number of websites and databases, without a common data format no common method for data access, and varying levels of documentation. Datasets are being uploaded to public databases through a number of initiatives, including [OpenFMRI](http://www.openfmri.org/) and [NITRC](http://www.nitrc.org). In addition, there are funded efforts for collecting data explicitly for the purpose of public sharing – most visibly in the [Human Connectome Project (HCP)](http://www.humanconnectome.org/) - but also in the [Pediatric Imaging, Neurocognition and Genetics (PING)](http://pingstudy.ucsd.edu/) study. There are a number of funded efforts to collect old data and re-release as public  databases,  notably the [INDI](http://fcon_1000.projects.nitrc.org/indi/IndiRetro.html)\cite{Mennes2013} efforts (which include the popular  ABIDE and F1000 datasets). The [BRAIN initiative](http://braininitiative.nih.gov/) aims to collect data that will be a [challenge to store, let alone analyze](http://www.brainupdate.nih.gov/calling-all-statisticians/). There are even online journals focused on publishing datasets (e.g. [Nature Scientific Data](http://www.nature.com/sdata/)), or with options to release data (e.g. [F1000 “Data Notes”](http://f1000research.com/articles?tab=ALL&articleTypes=DATA_NOTE&subjectArea=396)).

Nidata is a Python package that provides a single interface accessing data from a variety of open data sources. The software framework makes it easy to add new data sources, simple to define and to provide access to multiple datasets from a single data source. Software dependencies are managed on a per-dataset basis, allowing downloads and examples to use any public packages without requiring installation of packages required by unused datasets. The interface also allows selective download of data (by subject or type) and caches files locally, allowing easy management of big datasets.

#Results
We focused on exposing new methods for downloading data from the HCP. We were able to provide a downloader that accepts login credentials and downloads files locally. We created [an example](https://github.com/arokem/nidata/blob/bcipolli-ohbm2015-ipynb/ipynb/hcp-fetcher-dwi.ipynb) that interacts with [dipy](https://github.com/nipy/dipy) to produce diffusion imaging results on a single subject from the HCP. We also worked at collecting common data sources, as well as individual datasets stored at each data source, into [nidata’s “data sources” wiki page](https://github.com/nidata/nidata/wiki/Data-sources). We incorporated downloads, documentation, and examples from the [nilearn](http://github.com/nilearn/nilearn) package and began discussion of making a more extensible object model.

Since the hackathon, we have created such an object model and migrated all code to use it.


# Conclusions
Projects like nidata improve curated data access and increases the effectivity of big data projects with open source data.