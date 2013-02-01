latex-tifinagh
==============

An encoding + font + macro package for typesetting (Neo-)Tifinagh characters in LaTeX.


Overview
========

This package provides support for Tifinagh characters in LaTeX through a new encoding definition, ETIF, and a default font, IRCAM Unicode, as well as a couple other support files and macros for basic use.  While the project has been motivated by my linguistics work, (in particular, my


Encoding
--------

While it would be possible to combine the Latin and Tifinagh alphabets into one 256-glyph definition, upon evaluating the use cases, I decided that simplicity was more important, opting for a replacement of the Latin characters similar to the TIPA package (and the now-standard T3 encoding for IPA).

In general, I attempted to follow the common "Berber[**](#footnotes) Latin" transcription system, aligning phonetically-similar characters to the lowercase Latin alphabet.  This works for the majority of the standard, however due to the use of digraphs, diacritics, and foreign characters, some adjustments needed to be made:  

* **Emphatic consonants** are assigned to uppercase letters, paired with their non-emphatic form.  In all cases, these were phonetically sensible substitutions.
* **Yaɣ**, generally represented with a miniscule gamma (ɣ or γ), is assigned to lowercase 'v' and uppercase 'Y', for their visual similarity.  ('r' and 'R' being taken by the phonetically closer yar and emphatic yar)
* **yaɛ / yaʕ** is seen as a variety of characters -- epsilon (ɛ), ayn (ع), its IPA (ʕ), three (3), or accented a (â, ạ).  I opted for uppercase 'A', for its phonetic similarities.  It was also duplicated at 'o', in order to fill the lowercase alphabet with all the standard non-emphatic characters.
*  **yaḥ**, usually written as 'ḥ' and phonetically similar to the English 'h', is mapped to uppercase 'H'.  Like yaɛ, it was duplicated at 'p' to fill out the lowercase set.

Some of the "non-standard" characters (as labelled by IRCAM) have been assigned to the remaining uppercase letters when phonetically or orthographically appropriate, while the last set -- primarily Tuareg or other regional variants -- are only accessible through named macros.  I leave listing these equivalencies incomplete until I build a proper documentation file.  If you are in need, the macro name list can read rather simply out of ETIFenc.def.


Font
----

The font used is "Tifinagh IRCAM Unicode", freely available from IRCAM (*Institut Royal de la Culture AMazigh* - The  Royal Moroccan Institute for Amazigh Culture) on [their website](http://www.ircam.ma).  The package can be extended with other Unicode-compliant Tifinagh fonts, however each of these will need a matching font definition file before being used with LaTeX.

Note that I specify "Unicode-compliant" because I have encountered many Amazigh fonts that do not use the Tifinagh code block, instead simply replacing the Latin character set.  While this may have simplicity of use in many situations (and automatic "transliteration" - just switch to a different font!), for LaTeX's purposes, one must invoke a new font/encoding/style to accomplish either approach, so doing the "semantically-correct" one was the better option.  Plus, I believe it is precisely these sorts of technological shortcuts that end up eventually being a roadblock to the free exchange of information.


Installation
============

This package, while acceptable by LaTeX's core engine, has not yet been set up to work with common package installers (unless you have a magical one that requires no configuration whatsoever).  Thus there are several options, of which I will highlight two:

1. Copy the entirety of the package to your TeX working directory.  Simple, but cluttered and annoying to do repeatedly.

2. Manually move the files to their appropriate places in your *local* TeX folder.  (For my TeXLive distribution, that was C:\texlive\texmf-local, but I think the more standard location is in your user folder.)  Then the files should go into subdirectories as so, creating when necessary:
    * \\fonts\\map\\pdftex\\local\\tifinagh\\**ETIF.map**
    * \\fonts\\enc\\local\\tifinagh\\**ETIFgen.enc**
    * \\fonts\\tfm\\local\\tifinagh\\**Tifinaghe-IrcamUnicode--ETIF.tfm**
    * \\fonts\\tfm\\local\\tifinagh\\**Tifinaghe-IrcamUnicode--ETIF--base.tfm**
    * \\fonts\\vf\\local\\tifinagh\\**Tifinaghe-RcamUnicode--ETIF.vf**
    * \\tex\\latex\\local\\tifinagh\\ *for everything else*

Let me know if you have any troubles or questions.

<br><br><br>
<a id="footnotes"></a>

*note:* I do not personally advocate the label "Berber" or its associated terms, however I have nonetheless chosen to use it in certain fixed expressions where the alternatives would not be as useful of labels.
