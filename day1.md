# Day 1

## Static website generators

- Kaitlin Newson - @kaitlinnewson
- Digital Projects Librarian at Scholars Portal
- most popular static generator is [Jekyll](https://jekyllrb.com/) (built in Ruby)
- benefits - performance; fewer/less resources required on server; security; version control; simple hosting (e.g. GitHub pages, OLRC)
- drawbacks - no editing environment for non-technical content editors; learning template language; no dynamic elements
- Hugo - [gohugo.io](http://gohugo.io/) 
  - speed
  - fewer dependencies
  - built-in multilingual functionality
  - integrations (e.g. Google analytics)
  - contributed themes (many have example sites included with theme package)
  - built-in dev server
  - in Linux, can use snap package to install
  - config file (toml, yaml or json) for menus, etc.
  - content written in Markdown, with added HTML
  - uses Go's templating language
  - someone has to update nav in config if pages are added
- During Q and A, brief AsciiDoc vs Markdown discussion
  - GitLab uses Gollom which can use AD or MD - AD could assist with collaboration (i.e. multiple, simultaneous editors) piece


## Raspberry Pi project

- Cameron Metcalfe - UofO
- Model A+ provided to each member of systems team and tasked to create a project either alone or in collaboration
- Motivation 
  - team-building - improve communication on common ground; experiment and discover existing/new strengths
  - fight seasonal fatigue (i.e. timed after Christmas break)
  - reward factor, low risk, stand around the BBQ
  - try something different, but still associated with work
  - fun: show off your imagination
- project results: 
  - phone app debugger
  - digital signage
  - gaming platform (Quake 3 Arena)
  - video streaming
  - mapping library's quietest spaces (using leafletjs.com - "leaf me alone")
  - cookie jar alarm
  - repository of scripts and links
- findings:
  - need good power (phone adapters, extension cords); good micro SD cards (class 10); wifi dongle / cat5 network adapter; keyboard, mouse; probably need USB hub because only one USB port
  - be clutter-tolerant - it's not for the minimalist
  - a running, able-bodied computer
  - tweak the OS, applications for your device's specific task
  - technical spinoff rewards (e.g. learning about networking cat5)
  - appetite for more
  - use in headless state - no monitor; just ssh into it
- future
  - digital signage
  - coding dojo lab
  - robot - recent Pi kits have sensor for facial recognition
  - lendable tech
  - sensors - busiest library hotspots
- Pi has a config file in plain text required for using eduroam-style Wifi networking


## Don't take no for answer; using APIs to connect to OPAC

- Thomas Guignard
- union catalogue at OCLS - problem with hard-coded links and JS filtering in Sirsi-Dynex in enterprise edition
- search results from default Symphony setup would only show one college's results
- OCLS hacked it with custom widget to expose links for all colleges' results within search results
- some a11y issues due to JS required 


## Aba - Laravel app for collecting reference stats

- Mohammed Battou
- UofO have 12 locations - wanted to automate collection and reporting 
- Used [Laravel PHP framework](https://laravel.com)
- chose Laravel over Symfony 
  - good choice for small/medium sized project; based on Google trends was more popular
  - simple to install 
  - intuitive file structure
  - comes with dev server
  - MVC (model, view, controller)
  - database migration includes version control of database structure
  - database seeding included i.e. to insert test data
  - easy to write custom SQL queries
  - actively developed and maintained
  - uses [Blade templating engine](https://laravel.com/docs/5.4/blade)
- stack used: CentOS 6.5, nginx, postgresql, php 7, Laravel 5.4 and Composer (used to create Laravel project)
- there were 10 months of consultation before this was deployed
- https://github.com/mbattou/Reference-Statistics
- mbattou@uottawa.ca
- Discussion about head-counting apps
  - gvsu.edu has good head-counting app - contact Matt Reidsma
  - Queens has a head-counting app using cameras but running into problems with vehicle traffic obscuring results
  - Ryerson uses Slack bot to remind desk staff once an hour to do manual count and enter number in Google Sheet


## Canadiana.org

- Julienne Pascoe (metadata), Sascha Adler (developer), Russell McOrmond (systems)
- they are a trusted digital repository (TDR) - implement OAIS model
- goal of preserving and providing digital access to Canadian cultural heritage
- goal to implement LOD early on when building collections
- Linked. Open. Data.
- Digitization. Preservation. Access.
- working on the metadata workflows (aka "metadata bus")
- used Solr for indexing/search; used CouchDB for document store (because it has replication across the various data centres); used MySQL for database
- developing a digitization and preservation network across Canada
- moving from subversion to git ([their GitHub account](https://github.com/c7a))
- Canadiana and CHIN partnership - LOD/RDF project of art items with ~86K records
- demo of [iiif.io](http://iiif.io) (International Image Interoperability Framework - set of specs/APIs for getting images)
  - demo used two of the IIIF APIs: Image API and Presentation API
  - using [Cantaloupe](https://medusa-project.github.io/cantaloupe/) - open-source image server that implements the IIIF specification for serving up images and their derivatives
  - [universalviewer.io](http://universalviewer.io/) - takes an IIIF manifest and presents it
  - Bodleian library has a [IIIF manifest editor](https://github.com/bodleian/iiif-manifest-editor) - [source code](https://github.com/bodleian/iiif-manifest-editor)
- used [JHOVE](http://jhove.sourceforge.net/) for analysis and validation of files e.g. needed to know dimensions of images that were moving to the new system in CouchDB
  - they validated over 60M images - only about 1.6% of files were note well-formed (1.5%) or not valid (0.09%); JPGs were mostly correct, but TIFFs and PDFs had many issues
  - everything that [Poppler](https://poppler.freedesktop.org/) generated were not considered valid by JHOVE - they were recently-added items i.e. multipage PDFs that were created from single page PDFs 
  - see [blog post](http://mcormond.blogspot.ca/2017/05/jhove.html?spref=tw) for more details
- most people don't have tools to generate PDF/a format - but goal is to generate PDF/a from the new system
- IIIF uses tiling (aka Map Server) to handle zoom/pan
- using IIIF has allowed them to move from monolithic application to multiple smaller applications
- also benefiting from IIIF involvement and the various working groups (e.g. Newspaper-specific questions)


## Hackfest - Repository Usage Stats

- Anthony Petryk lead discussion, by first introducing [Dale Askey's talk at IR Managers meeting at CARL ](http://www.carl-abrc.ca/wp-content/uploads/2016/11/2016_reposforum_Askey_EN.pdf)
  - http://bit.ly/2qwzDYh - Anthony's Google Doc for discussion notes
- lots of stats noise (spiders, bots)
- Google Analytics misses a lot of stats because some downloads are through direct search and not through a click within DSpace
- [Piwik](https://piwik.org/) is free analytics software that can track downloads, as compared to GA, because it is on the same server; also can track lists of bots
- bottom line: accurate stats for real, human interaction is difficult
- [RAMP](http://www.arl.org/publications-resources/4215-ramp-repository-analytics-and-metrics-portal) - Repository Analytics and Metrics Portal
- we need standards for usage stats that products/vendors actually adhere too - there is currently too much varying interpretation of the implementation
- COUNTER is really a format for presenting spreadsheet
- JISC in UK compiles COUNTER reports from its members
- UofO creates DOIs for items with DataCite (for certain communities/collections e.g. etheses)
  - creates DOIs when object created, but only minted when decided

