---
layout: post
title:  "Stylo and the Stevensons"
date:   2016-07-13 16:24:09 +0100
categories: blog
---

Along with my PhD student Robyn Pritzker, I've been looking into the authorship of [*The Dynamiter*](https://babel.hathitrust.org/cgi/pt?id=uva.x000181310;view=1up;seq=9), a text by Robert Louis Stevenson and his wife Fanny van der Grift Stevenson. Although it's known that the pair collaborated on the writing, there's no certainty about which sections were written by which author, and how much of the book can be attributed to Fanny. (For more background on this, see [*Deciphering The Dynamiter*](http://thedynamiter.llc.ed.ac.uk/), which Robyn and [her MSc colleagues](http://thedynamiter.llc.ed.ac.uk/?page_id=17) put together for their major project in my DH for Literary Studies class in 2015. They did a huge amount of work preparing the corpora and getting to grips with both the historical context and the literature on stylometry, and I'm very proud of them.) Robyn and I are now at the point of having some results to share, which I am presenting at [DH2016](http://dh2016.adho.org/) in Krakow on behalf of us both.

Since *Deciphering The Dynamiter* went live in March 2015, a serendipitous thing happened: Maciej Eder released two new functions for the R library [Stylo](https://sites.google.com/site/computationalstylistics/stylo), rolling.classify and rolling.delta, which are designed specifically for the stylometric analysis of collaboratively written texts. These scripts work by slicing a text into overlapping chunks and performing analysis on each chunk using a 'moving window' approach, in order to discern the author whose most frequent words (MFW) in their reference texts most closely match the MFW of the test text. The available distance measures are nearest shrunken centroids, support vector machines and several flavours of Delta. Technical details [here](http://dx.doi.org/10.1093/llc/fqv010), or [try it yourself](https://sites.google.com/site/computationalstylistics/stylo/scripts/stylo_0.6.3.tar.gz?attredirects=0&d=1).

Using these rolling classification scripts, I generated some graphs that give a sense of where Fanny's authorial signal comes through the text most strongly, and which show how her signal varies as the number of MFW rises. To show how the signal varies with the number of MFW, the graphs below have been animated, and they run from 100 MFW to 1000 MFW in increments of 100.

#### The Dynamiter
 
*The Dynamiter, 100 to 1000 MFW, classic Delta distance, 4000w slices, 3500w overlap*
 
*The Dynamiter, 100 to 1000 MFW, NSC, 4000w slices, 3500w overlap*
 
*The Dynamiter, 100 to 1000 MFW, SVM, 4000w slices, 3500w overlap*

There are a few things to note about these graphs:

First, although the three distance measures are in rough agreement about the places where Fanny's authorial influence emerges in the text, these vary depending on the number of MFW chosen, especially when Delta is used.

Second, the three distance measures give quite different pictures of the *extent* of Fanny's contribution. Tomoji Tabata noted in [yesterday's Digital Literary Stylistics workshop](https://www.conftool.pro/dh2016/index.php?page=browseSessions&form_session=174&presentations=show) that in his tests of the three measures, SVM came out ahead at 0.975, followed by NSC at 0.9375 and Delta at 0.9025. When used on *The Dynamiter*, however, the SVM graph only allocates one tiny slice of the text to Fanny, and that very fleetingly (at 300MFW). The Delta graph identifies many different sections in which her style predominates, while the NSC graph is more consistent in the sections it assigns to her, but is often at odds with the Delta and SVM graphs.

Third, the collaboration seems not to have been governed by the sections of the book (shown by the dotted vertical lines, which represent the starting and ending points of the stories and stories-within-stories that constitute the book). Where the signal changes from one author to another, in other words, this does not necessarily align with any breaks between sections.
Seeking comparators to understand what these signals might tell us about Fanny and Louis's collaborative writing process, I ran the same analyses on three volumes that Louis co-authored with his stepson Lloyd Osbourne: *The Wrecker*, *The Ebb Tide* and *The Wrong Box*.

#### The Wrecker
 
*The Wrecker, 100 to 1000 MFW, classic Delta distance, 5000w slices, 4500w overlap*
 
*The Wrecker, 100 to 1000 MFW, NSC, 5000w slices, 4500w overlap*
 
*The Wrecker, 100 to 1000 MFW, SVM, 5000w slices, 4500w overlap*

#### The Ebb Tide
 
*The Ebb Tide, 100 to 1000 MFW, classic Delta distance, 5000w slices, 4500w overlap*
 
*The Ebb Tide, 100 to 1000 MFW, NSC, 5000w slices, 4500w overlap*
 
*The Ebb Tide, 100 to 1000 MFW, SVM, 5000w slices, 4500w overlap*

#### The Wrong Box
 
*The Wrong Box, 100 to 1000 MFW, classic Delta distance, 5000w slices, 4500w overlap*
 
*The Wrong Box, 100 to 1000 MFW, NSC, 5000w slices, 4500w overlap*
 
*The Wrong Box, 100 to 1000 MFW, SVM, 5000w slices, 4500w overlap*

Here again the signal is far from conclusive across the three distance measures, though it seems fairly safe to say that Louis appears to have heavily edited the texts he co-wrote with Lloyd. Taken together, the graphs suggest that Louis had something of a different mode of collaboration with Lloyd compared to the way he and Fanny worked together. For *The Wrong Box*, there is a relatively strong signal to suggest that Lloyd was the person who played the largest role in writing the ending of the book. For *The Ebb Tide*, there are well-delineated sections in the NSC graphs where Lloyd's signal is clearly present, so the question here is not whether he wrote those sections but to what extent his style emerges over Louis's generally more dominant voice. *The Wrecker* is the most confounding of all: the NSC graph suggests that Lloyd had influence only over a few very small slices of the text, while the Delta and SVM graphs tell a different story in suggesting that Lloyd's influence is present, even if not dominant, across much of the text. If we accept Tabata's idea that NSC is the most reliable distance measure, Lloyd's contributions to *The Wrecker* and *The Wrong Box* are very minimal, and his influence in *The Ebb Tide* more considerable. But the story told by the Delta and SVM graphs is more complicated, and suggest that Lloyd's input into the drafting process was more significant than the NSC graph allows. So, if NSC can be considered somewhat too black-and-white in the way it attributes authorship, then what these graphs suggest is that where the process of authoring has been an intricate and intermingled one – ie. where the authors have drafted and edited together, and/or edited and rewritten each others' materials, rather than each writing discrete sections – NSC may not be such a useful measure. Rather, the greater nuance of SVM and Delta may be better suited to observing the relative prominence of authorial signals.

Robyn will be working in Fanny's archives over the next few months and we hope she will turn up evidence there which will help to illuminate – and complicate – the information in the graphs above. For now, my tentative interpretation is that the presence of Fanny's signal at lower MFW and its tendency to disappear at higher MFW is an indication that she played an important role in the early conceptualising and drafting, while Louis contributed proportionally more in the later stages of redrafting and editing, which accords roughly with the (sparse) evidence we have in front of us now. Eder comes to [a similar conclusion](http://dx.doi.org/10.1093/llc/fqv010) for this pattern in Conrad and Ford's novel *The Inheritors*, and Mark Algee-Hewitt presented yesterday on some preliminary work on co-authored Stanford Lit Lab pamphlets which is particularly tantalising, as the authors of these co-written texts are still around and can be asked how the writing and editing actually occurred.

For more detail on the findings and how we have interpreted them – as well as why this kind of approach is exciting for feminist literary historians seeking to recuperate women's contributions to literary history – come along to our DH2016 paper (["All In the Family: Testing Burrows' Delta on Robert Louis Stevenson's Collaboratively Authored Volumes *The Dynamiter* and *The Wrecker*"](https://www.conftool.pro/dh2016/index.php?page=browseSessions&form_session=38&presentations=show)).


[![Creative Commons License](https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)
The material on this site is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/). Please also drop me a line at the address above to let me know what you've done with it. Thanks!
