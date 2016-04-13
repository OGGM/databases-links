Special data structure for GlaThiDa multiple links
===================================================

We have started to also link single GlaThiDa 2014 entries to multiple RGI5.0 polygons.
Results can be found in the file `Manual_links_GlaThiDa_to_RGI_WORLD_20160412_multiple_included.csv`
This has implications on the data structure as now the RGI equivalents are given as lists.

The separator has changed from comma to semicolon and it's a bit tricky to read the files now as there are problems with the interpretation of the list entries. For this reason, it is also not displayable in the "beautiful and searchable" GitHub way. Reading in Python can be done the following:

|

.. code:: python

   import pandas as pd
   import ast 

   data = pd.read_csv(foopath, sep=';')
   data.RGI_ID = [ast.literal_eval(string) for string in data.RGI_ID]

|

In the remark column of the data, sometimes literature can be found on which the RGI polygon selection is based.
The list of references is given in bibtex file "GlaThiDa_world_literature.bib"

|

If you don't like to encounter the difficulties of linking a single GlaThiDa entry to multiple RGI polygons, you can refer to the file `Manual_links_GlaThiDa_to_RGI_WORLD_20160412.csv` , which has the data structure that all other files use.
