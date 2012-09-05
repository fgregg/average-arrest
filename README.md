![Average face of people arrested by the Cook County Sherrif on September 3, 2012, N=144](https://github.com/fgregg/average-arrest/raw/master/wow.jpg "Average face of people arrested by the Cook County Sherrif on September 3, 2012, N=144")

The Average Arrest
==============

Concept
-------
Display the average face of people arrested in Cook County for every day of the year and by charge.

Technical
---------
1. Download mugshots and arrestee details from Cook County Sherrif's website, i.e.
  * http://www2.cookcountysheriff.org/search2/details.asp?jailnumber=2012-0903186
  * The first eight digits of the jail number are the year, month, and day. The last three correspond to 
    how many people have been processed that day
  * An arrestee's information is only accesible while he or she is in custody. If she is bailed out or transfered,
    a search for her jail number will return a 404
    * May want some adaptive querying to make sure we have full coverage and not an biased sample that does not
      contain people with money and lawyers.
2. Average the faces together.
  * Ideally, we would use [jpsychomorph](http://users.aber.ac.uk/bpt/jpsychomorph/). It's what we used to create
    the above image (N=144). However, we need to figure out how to use it non-interactively. 
    1. Ask Bernie Tiddeman for code
    2. Create wrapper for jpsychomorph, http://users.aber.ac.uk/bpt/jpsychomorph/version4/javadoc/
    3. Recreate the functionality
      1. Alignment
        * http://docs.opencv.org/trunk/modules/contrib/doc/facerec/facerec_tutorial.html#aligning-face-images
        * http://vis-www.cs.umass.edu/code/congealingcomplex/
        * https://github.com/roblourens/facealign
        * http://sourceforge.net/apps/mediawiki/pyvision/index.php?title=FaceL:_Facile_Face_Labeling
        * http://code.google.com/p/aam-opencv/
      2. Texture blending
3. Display
