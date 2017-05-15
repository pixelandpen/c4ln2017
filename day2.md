# Day 2

## Roles for the library in infrastructure breakdown

- John Fink
- amateur radio demographics - old, white males
- can now buy radio transceiver (transmitter, receiver) for $35 - hopefully will encourage broader demographic involvement
- backup power is another issue in time of emergency
- mesh networking uses wifi equipment to talk to each other instead of central node
- ISCSI - SCSI over internet
- Raspberry Pi 3 can boot from firmware, and has bluetooth and wifi which can be used in mesh network; can also be powered over ethernet


## I didn't become a worse librarian when I became a grad student

- Tim Ribaric
- librarian, code, researcher (rock, paper, scissors - each has strength and weakness)
- had to circumvent barriers due to Brock's limitations on research resources 
- empathy is created through shared experiences


## mermaid.js

- Ruth Collings
- Mermaid - [docs](https://knsv.github.io/mermaid/#mermaid) and [live editor](https://knsv.github.io/mermaid/live_editor)
- [Demo page](http://ruthcollings.ca/mermaid.html) - do a 'view source'
- creates SVG of the graph in question


## What do you do with 2457 theses?

- John Dingle
- have IR with all etheses at Brock, available with API
- goal: cited references from theses in machine-readable format, starting with PDFs and ending with XML/JSON with DOIs
- found 3 possible open-source solutions
  - [ParsCit](https://github.com/knmnyn/ParsCit)
  - [Cermine](https://github.com/CeON/CERMINE)
  - [Grobid](https://github.com/kermitt2/grobid) - worked the best of the three
- Grobid is in Java - run as .jar and accessed via RESTful API; extracts 55 elements from scholarly documents (e.g. citation, image); does call to CrossRef to extract more metadata
  - accuracy varied by discipline - Grobid says they get 80% accuracy


## Putting maps on the map

- Sarah Simpkin         
- digitizing 1000+ maps of Ontario topographical maps
- important for researchers tracking changes over time
- crowd sourced a listing of maps across schools
- scanned at high res using best scanners within groups of schools part of this project
- GCP = ground control points - need about 8 per map to make sure digital map is accurate compared to real-world; use things like rail lines, intersections (things that haven't changed) for GCPs
- loaded in SPortal GeoPortal
- [Project website](http://ocul.on.ca/topomaps/)


## Security

- David Fiander
- need to use two factor authentication (2FA)
- FIDO Alliance - 2FA that is web-based - works with Chrome, and Firefox soon
- Yubico sells FIDO key along with fancier models
- recommend having two keys - one as a backup


## Things learned when mushing together data from other people

- Catie Sahadath
- Canadian RDM Survey Consortium - http://bit.ly/c4ln1 - from Portage
- 14 participating universities
- IASSIST 2017 presentation - bit.ly/c4ln3
- never assume mutual understanding in data formatting across participants
- [codebooks](http://www.icpsr.umich.edu/icpsrweb/NAHDAP/support/faqs/2006/01/what-is-codebook) for data were required/created using [SPSS](https://en.wikipedia.org/wiki/SPSS) and Google Sheets
- [Stata](http://www.stata.com/) used for recoding values with controlled vocabulary
- mapping values to correct disciplines was difficult
- unlabelled values and variables also an issue
- inconsistent data collection e.g. some schools surveyed grad students and librarians while others did
- for next time:
  - one-on-one work with those collecting data
  - do some sample extractions before hand i.e. beta testing
  - have others label their own variables
  - keep everything in non-proprietary formats for as long as possible - e.g. R as format
  - amend the controlled vocabs
  - teach someone else how to do the things


## Afternoon discussions / hackfests

- [Docker](https://www.docker.com) use cases
  - Note: need to update Docker settings when using Eduroam and other networks - see [Gist from John Fink](https://gist.github.com/jbfink/e4eea501f10d1b745e811d95bcf9584e)
- Possible [Library Carpentry](https://librarycarpentry.github.io/) workshop in Ontario this year?
- mermaid.js
