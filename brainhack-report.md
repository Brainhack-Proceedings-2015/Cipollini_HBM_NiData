---
event: '2015 OHBM Hackathon (HI)'

title:  'Advancing Open Science through NiData'

author:

- initials: BC
  surname: Cipollini
  firstname: Ben
  email: bcipolli@ucsd.edu
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
  street: 9500 Gilman Dr
  postcode: 92093
  city: La Jolla
  state: California
  country: USA
- id: aff2
  orgname: 'University of Washington'
  street: 3910 15th Ave NE
  postcode: 98195
  city: Seattle
  state: Washington
  country: USA

url: http://github.com/nidata/nidata

coi: None

acknow: The authors would like to thank the organizers and attendees of the 2015 OHBM Hackathon.

contrib: BC and AR wrote the software and the report.

bibliography: brainhack-report

gigascience-ref: \href{http://gigadb.org/dataset/100217}{doi:10.5524/100217}
...

#Introduction
The goal of this project is to improve accessibility of open datasets by curating them. “NiData” aims to provide a common interface for documentation, downloads, and examples to all open neuroimaging datasets, making data usable for experts and non-experts alike.

#Approach
Open datasets promise to allow more thorough analysis of hard-to-collect data and re-analysis using state- of-the-art analysis methods. However, open datasets are not truly open unless they are easy to find, simple to access, and have sufficient documentation for use. Currently, publicly available data in neuroscience are scattered across a number of websites and databases, without a common data format, no common method for data access, and varying levels of documentation. Datasets are being uploaded to public databases through a number of initiatives, including OpenFMRI \cite{Poldrack2013} and NITRC \cite{Buccigrossi2008}. In addition, there are funded efforts for collecting data explicitly for the purpose of public sharing – most visibly in the Human Connectome Project (HCP) \cite{VanEssen2013} - but also in the Pediatric Imaging, Neurocognition and Genetics (PING) study \cite{Jernigan2016}. There are a number of funded efforts to collect old data and re-release as public databases, notably the INDI \cite{Mennes2013} efforts (which include the popular ABIDE \cite{DiMartino2014} and functional connectomes 1000 datasets \cite{Biswal2010}. The BRAIN initiative \cite{Insel2013} aims to collect data that will be a challenge to store, let alone analyze. There are even online journals focused on publishing datasets (e.g. Nature Scientific Data), or with options to release data (e.g. F1000 “Data Notes”).

NiData is a Python package that provides a single interface accessing data from a variety of open data sources. The software framework makes it easy to add new data sources, simple to define and to provide access to multiple datasets from a single data source. Software dependencies are managed on a per-dataset basis, allowing downloads and examples to use any public packages without requiring installation of packages required by unused datasets. The interface also allows selective download of data (by subject or type) and caches files locally, allowing easy management of big datasets.

#Results
We focused on exposing new methods for downloading data from the HCP, supporting access via Amazon S3 and HTTP/XNAT \cite{Marcus2007} . We were able to provide a downloader that accepts login credentials and downloads files locally. We created an example that interacts with DIPY \cite{Garyfallidis2014} to produce diffusion imaging results on a single subject from the HCP. We also worked at collecting common data sources, as well as individual datasets stored at each data source, into NiData’s “data sources” wiki page. We incorporated downloads, documentation, and examples from the nilearn package and began discussion of making a more extensible object model.

Since the hackathon, we have created such an object model and migrated all code to use it, and a Sphinx- based website is under development. The current object model makes it easier to write general-purpose fetchers (e.g. HTTP, XNAT, Amazon S3) that can be extended to access specific databases (e.g. COINS \cite{Scott2011}, LORIS \cite{Das2011}, ADNI \cite{Jack2008}).

# Conclusions
Projects like NiData improve curated data access and increases the effectivity of big data projects with open source data.
