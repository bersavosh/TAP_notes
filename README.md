# TAP notes
Notes and examples for using TAP and ADQL

## Definitions:
- [What is TAP](http://www.ivoa.net/documents/TAP/)
- [What is ADQL](http://www.ivoa.net/documents/ADQL/)

## Ingredients:
You need a few components to be able to send a TAP query:

1- **Server address** - e.g., TAP on Vizier: 

[`http://tapvizier.u-strasbg.fr/TAPVizieR/tap/`](http://tapvizier.u-strasbg.fr/TAPVizieR/tap/)

2- **Table designation** - e.g., The main table in [This catalog](http://vizier.u-strasbg.fr/viz-bin/VizieR?-source=V/106&-to=3) on Vizier has the following designation:

`V/106/lmxbcat`

3- **Query configuartions** - e.g., to set query type (synchronous vs. asynchronous), output format:

`sync?REQUEST=doQuery&LANG=ADQL&FORMAT=CSV`

4- **ADQL query** - e.g., asking for the first 5 entries in the table: 

`QUERY=SELECT top 5 * FROM "V/106/lmxbcat"`

## How can I send a TAP/ADQL query to a TAP-enabled server:
There are numerous ways, here are a few basic examples:

1- Putting it in a web browser address bar:

```
http://tapvizier.u-strasbg.fr/TAPVizieR/tap/sync?REQUEST=doQuery&LANG=ADQL&FORMAT=CSV&QUERY=SELECT top 5 * FROM "V/106/lmxbcat"
```

2- Curl or wget:

```
$ wget 'http://tapvizier.u-strasbg.fr/TAPVizieR/tap/sync?REQUEST=doQuery&LANG=ADQL&FORMAT=CSV&QUERY=SELECT top 5 * FROM "V/106/lmxbcat"'
```

You can also write a bash script to send the query. A nice example for that is provided in the CADC page linked below.

3- Topcat (and probably a few other GUI-based softwares): Topcat has a built-in support for TAP and ADQL. The interface helps you search for the table you're looking for across a variety of recognized databases and allows you to put your query together from many common examples (e.g., crossmatch, cone search).

4- Packages in various programing languages: there are packages developed for understanding TAP and ADQL in languages like Python, Java, Ruby, C++.

## Examples, cookbooks, recipes, tutorials:
- [A short course on ADQL by Markus Demleitner](http://docs.g-vo.org/adql/html/index.html)
- [ADQL Cookbook](https://www.gaia.ac.uk/data/gaia-data-release-1/adql-cookbook)
- [ADQL Cheatsheet](http://docs.g-vo.org/adqlref/adqlref.pdf)
- [Examples of ADQL queries from CADC](http://www.cadc-ccda.hia-iha.nrc-cnrc.gc.ca/en/doc/tap/)
- [Example of using TAP for Gaia in Astropy](https://gea.esac.esa.int/archive-help/tutorials/python_cluster/index.html)
- [A fantastic tutorial for TAP in python by Morgan Fouesneau](https://github.com/mfouesneau/tap/blob/master/examples/TAP_tutorial.ipynb)

## Some TAP/ADQL-Aware clients and packages:
- [TAP in Topcat](http://www.star.bris.ac.uk/~mbt/topcat/sun253/TapTableLoadDialog.html)
- [TAP in Astroquery](http://astroquery.readthedocs.io/en/latest/utils/tap.html) (part of Astropy)
- [TAP in PyVO](https://pyvo.readthedocs.io/en/latest/#data-access)
- [A python script by Morgan Fouesneau](https://github.com/mfouesneau/tap)
- [ADQL Library](http://cdsportal.u-strasbg.fr/adqltuto/) (Java)
- [Gaia-on-tap](https://github.com/andycasey/gaia-on-tap/) (specifically for Gaia)

## Some notable astronomy databases accessible via TAP:
- [Visier](http://tapvizier.u-strasbg.fr/adql/)
- [NOAO](https://datalab.noao.edu/decals/dataAccess.php) (part of NOAO datalab)
- [SIMBAD](http://simbad.u-strasbg.fr/simbad/sim-tap)
- [HEASARC](https://heasarc.gsfc.nasa.gov/docs/archive/vo/)

and many many more. 
