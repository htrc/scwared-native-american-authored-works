# Introduction to Native Authored Workset
The team at the University of Oklahoma (OU) was funded by the Andrew W.
Mellon Foundation through the SCWAReD project to create a workset by
Native authors in the HathiTrust digital library. This document serves
as an introduction to the workset, describing the workset building
process, the content of the workset, the context of the works, and some
example research questions that can be answered using this workset.

## Rationale for the Project

Native Americans represent a historically under-resourced textual
community. While there has been an ever-increasing number of Native
authors creating works since the 1960s, no corpus of Native-authored
works exists from which to draw insights about this particular
community, and give them the recognition equal to other similar
communities of practice (e.g. History of Black Writing<a id="ref01"/><span style="font-size:80%; vertical-align: super">[\[1\]](#note01)). In
collaboration with the HathiTrust Research Center (HTRC) team, we have
created a preliminary database of Native-authored works, of which a
subset has been identified in the HathiTrust digital library. This
workset is now available to all researchers with an interest in
Native-authored literature, and we hope that this workset will serve as
a basis for more qualitative and quantitative research that speaks to
the unique characteristics of this textual community.

## Building Process

### Team

The team at OU consists of Dr. Raina Heaton and Dr. Raymond Orr from the
Department of Native American Studies, and Dr. Kun Lu from the School of
Library and Information Studies. The team also supervises a student
mentee, Alyssa Vetter, a biology major with a minor in Native American
Studies. The OU team works closely with HTRC staff including Ryan
Dubnicek, Isabella Magni and a PhD student Nikolaus Parulian in HTRC.

Scope

There is a vast amount of extant literature on Native Americans and
Native-related topics, the vast majority of which is not authored by
Native people. As an illustration, a HathiTrust records search of
“American Indian” subject headings from the US, Canada, and Mexico
recovered 35,440 records, more than 17x the size of our dataset (see
below). There are also many long-standing issues related to establishing
both native ethnic and tribal affiliation, which we had to contend
with in assembling this database. Additionally, while there are Native
and Indigenous authors all over the world, we limited our search to
authors from and publishing in the continental US and Canada.
Additionally, since many works (particularly the scholarly works) are
co-authored by Native and non-Native people, or are instances where
Native writers have published in a compilation or edited volume, we have
included those volumes in our database rather than exclude them.

### Compiling lists of native authors and works

There is no mechanism in the metadata from the HathiTrust digital
library for identifying if an author is Native or non-Native. As such,
there is no easy way to collocate Native American authored works in the
HathiTrust digital library. To build the list of Native authors for the
workset, The OU team began compiling lists of Native authors and their
works from publicly available datasets, locally accessible resources,
and their personal knowledge.

One of the primary sources we used to compile our initial list of
authors was the Native American Authors collection provided by the
Internet Public Library
([<span class="underline">https://www.ipl.org/div/natam/</span>](https://www.ipl.org/div/natam/)).
The site contains information on Native North American authors and
bibliographies of their published works. Blakesley Lindsay (2003) wrote
a review of the IPL’s Native American Authors collection, claiming the
collection covers “a wealth of online resources dealing with Native
American writers,” and the author list includes “an extensive list of
Native American writers, including many lesser-known poets and authors,”
although the information available on each author varies (p. 41). At the
time of the review, the site listed over 1,200 titles. Apparently, it
has grown over years since our collection includes over 2,000 titles
from IPL. Dr. Lu wrote a Python script to scrape the author information
along with work titles and tribal affiliation. This resulted in 631
native authors and 2017 work titles where four works are listed without
author information, and therefore excluded. Additional information about
the works, such as publication date and author gender, was collected
manually by a student mentee.

Another source of information on Native-authored works came from the The
Native American Languages (NAL) collection at the Sam Noble Museum at
OU. The NAL collection is an archival repository for materials in and
pertaining to Indigenous languages, with a specialization in the
Indigenous languages of the central United States. The collection
includes audio and video recordings, manuscripts, books, journals,
ephemera and teaching curricula from more than 175 Native North American
languages. Materials have been donated to the collection from a variety
of individuals and groups, including tribal members and families,
linguists and anthropologists, community language projects, teachers and
students and other archives. As the curator for NAL, Dr. Heaton was able
to export a list of published works from the NAL databases, and then
manually screen them for Native authorship and other in-scope criteria.
The exported lists from NAL resulted in 122 work titles. Dr. Heaton also
contributed a list of native linguists and students maintained by LSA
(Linguistic Society of America) special interest group and went through
their CVs to identify relevant works, which includes 34 titles.

Dr. Orr compiled a list of Native American authors from two decades of
Native American Studies literature by looking at Native American Studies
journals since the year of 2000. These lists of native authors and works
were then searched in HathiTrust to identify the native authored
workset.

### Searching native authors and works in HathiTrust

The OU team converted the above lists of Native authors and works into a
searching format that is preferred by HTRC staff. The HTRC staff then
used the HathiTrust index to automatically search the authors and works
in HathiTrust. The search process relied on a tool built specifically
for identifying volumes available in the HT digital library based on a
provided list of titles/authors. The tool first executes a
pre-processing step to cleanup and normalize the title and author list,
and then it searches the published
[HathiFiles](https://www.hathitrust.org/hathifiles)
(an up-to-date listing of the entire HT holdings which includes title
and author information) for matches for each title/author combination
from the list provided. The searching is done via fuzzy-matching to
allow slight variations in spelling of both the title and author names.
While, in general, the fuzzy-matching process returns the correct
matches, there are situations where false positive matches are
identified, especially for works with very short titles (e.g. one-word
title) and a “common” author name. These were identified by HTRC staff
and the researchers at OU during the results review, and then removed.

The results from automated searches were then manually screened for
additional matches that were missed by automated searches due to
variations in author names or titles, and/or missing information. The
NAL collection, 37 out of 122 titles were found in HathiTrust,
accounting for a 30.33% coverage. For the IPL dataset, 900 titles out of
2013 were found, accounting for a 44.71% coverage. Table 1 summarizes
the coverage of native authored works in HathiTrust. The following
content will focus on the IPL and NAL datasets since they represent the
majority of the matches in HathiTrust.

Table 1: Coverage of native authored works in HathiTrust

| **Dataset**          | **\# of titles searched** | **\# of titles found in HT** | **Coverage** |
| -------------------- | ------------------------- | ---------------------------- | ------------ |
| IPL                  | 2013                      | 900                          | 44.71%       |
| NAL                  | 122                       | 37                           | 30.33%       |
| LSA native linguists | 34                        | 0                            | 0%           |

## Content of the Workset

### IPL workset

The IPL workset has 900 titles in HathiTrust by native authors. This
corresponds to 1,061 HathiTrust records, since one title may match
multiple records, in instances of different editions or multi-volume
works. And one record may also correspond to multiple duplicate volumes
in HathiTrust. This results in 1,304 unique items in HathiTrust. The
publication dates of these items range from 1826 to 2009. These works
are contributed by 358 distinct native authors. Figure 1 shows the
distribution of works over years.

![Number of works over years in the IPL workset](images/fig1.png)  
_Figure 1. Number of works over years in the IPL workset._

### NAL workset

The NAL workset includes 36 titles in HathiTrust by native authors. This
corresponds to 45 HathiTrust records and 56 HathiTrust items. The
publication dates range from 1900 to 2006. These works are contributed
by 15 native authors.

Naive authored workset summary

The following table summarizes the basic statistics of the worksets.

Table 2: A summary of statistics in the native authored worksets.

|                                | \# of titles | \# of Hathi records | \# of Hathi items | Publication date range | \# of native authors |
| ------------------------------ | ------------ | ------------------- | ----------------- | ---------------------- | -------------------- |
| IPL workset                    | 900          | 1061                | 1304              | 1826 to 2009           | 358                  |
| NAL workset                    | 36           | 45                  | 56                | 1900 to 2006           | 15                   |
| Total (after removing overlap) | 919          | 1083                | 1322              | 1826 to 2009           | 369                  |

There is overlap between the NAL and IPL worksets: Out of the 36 matched
titles, 45 matched records and 56 matched items in NAL, 17 titles, 23
records and 27 items are also matched in the IPL workset, respectively.
Four of the 15 NAL authors are also included in the IPL workset. The
total number of matches after removing overlap is listed in the last row
of Table 2.

## Gap Analysis

This section compares what is covered in HathiTrust versus what is not
covered in HathiTrust among the titles that have been searched in this
project.

### IPL dataset

#### Publication dates

Out of 2,013 titles in the IPL dataset that are searched in HathiTrust,
900 titles are found and 1,113 titles are not. The distribution of works
over years is shown below except for 33 titles that we do not have
publication date information:

![Comparison of publication dates on IPL dataset.](images/fig2.png)  
_Figure 2. Comparison of publication dates on IPL dataset._

The date range of the uncovered works is wider than that of the covered
works, ranging from 1768 to 2013, but the distributions for covered and
uncovered works look similar. Some older (before 1826) or newer (after
2009) are not found in HathiTrust. Both sets show gradual increase in
the number of works beginning in the mid-1960s, reach a peak ranging
from 1990 to 2000, and gradually decline after 2000. This trend could be
due to the coverage of the IPL dataset rather than that of the
HathiTrust. However, the number of titles covered in HathiTrust after
2000 is much smaller than that not covered in HathiTrust (66 v.s. 211).
*<span class="underline">This suggests that HathiTrust may have a lower
coverage on some more recent Native authored works in IPL.</span>*

It is important to add that there has been a continual increase in
publications by Native people since the early 2000s. Given that it is
now 2022, the fact that our data sources do not include many more
contemporary works is a limiting factor for analyses seeking to use this
dataset.

#### Tribal representation

Comparable level of tribal representation is observed in the covered and
uncovered works by HathiTrust, where 135 tribes are represented in works
covered by HathiTrust and 149 tribes represented in works not covered by
HathiTrust. There are 112 tribes represented in both sets, 23 tribes
only in works covered by HathiTrust, and 37 tribes represented only in
works not covered by HathiTrust.

#### Author gender representation

For those authors for whom we have gender information, the works covered
in HathiTrust are authored by 153 female authors and 198 male authors,
while the works not covered are authored by 184 female authors and 275
male authors. The percentage of female authors is 43.6% for works
covered in HathiTrust and 40.1% for works not in HathiTrust.

### NAL dataset

For the NAL dataset, 103 titles were searched and 36 were found in
HathiTrust. The coverage of HathiTrust on Native languages related
topics by Native authors is lower than that for IPL which is a more
general literature list. The following analysis compares the NAL works
that are covered by HathiTrust with those not covered. It should be
noted that the NAL collection size is much smaller with only 103 titles
searched.

#### Publication dates

The publication dates of the 36 titles found in HathiTrust range from
1900 to 2003, compared with 1928 to 2015 for those titles not covered by
HathiTrust. No clear trend is observed from this dataset due to the
small sample size. However, in terms of the coverage on more recent
works, only two titles after 2000 are covered by HathiTrust compared
with 23 titles not covered in the same period of time.
*<span class="underline">The coverage of some more recent titles is
lower in HathiTrust, which is consistent with what is observed in the
IPL dataset.</span>* Interestingly, HathiTrust covers some old titles
that were published before 1928.

![Comparison of publication dates on NAL dataset.](images/fig3.png)  
_Figure 3. Comparison of publication dates on NAL dataset._

#### Tribe representation

For the authors that we know their tribal affiliations, we analyzed the
tribal representation of the NAL works covered by HathiTrust versus not
covered by HathiTrust. Eleven tribes are represented in works found in
HathiTrust, compared with 25 tribes for works not found in HathiTrust.
There are two tribes only represented by the works in HathiTrust: Kiowa
and Gwich’in, and 16 tribes represented only by the works not in
HathiTrust. *<span class="underline">It appears that the tribal
representation is not as wide in HathiTrust for Native authored works on
and about Native languages.</span>*

#### Author gender representation

For the authors that we have gender information, we compared the gender
representation of works in HathiTrust versus works not in HathiTrust for
the NAL dataset. For the works in HathiTrust, there are six female
authors and eight male authors, compared with 34 female authors and 21
male authors of works not in HathiTrust. The percentage of female
authors is 42.86% for works covered in HathiTrust and 61.82% for works
not in HathiTrust. This result may not be conclusive due to the small
sample size of the NAL collection.

## Example Research Questions

1. What role do we see of nature and in what forms? Terms: nature,
   mountain, water (type of water), and maybe proximity to terms of
   respect or belonging.

2. What about the use of the collective versus individualistic terms
   (work by Greenfeld at UCLA found as the 20th century progressed,
   more “I”s than “we”s and greater use of entitlement compared to
   obligation)? Assumption is that authors might describe more
   collective rather than individual?

3. What types of works do we see?

4. What words for power or authority might be used? Sovereignty is a
   major topic in the field but how is it used? When talking about
   non-natives, what is the context? In the 70s / 80s you saw the
   term “white man,” what is the surrounding text? How about settler
   or colonist or invader?

5. An assumption is that literature might be dealing with or
   addressing loss and trauma. I wonder if we see terms that might
   indicate this in these works?

6. When an author of X tribe writes, does he/she talk about other
   tribes? Not sure this is helpful but how tribally specific or
   focused are authors. (how often do they use specific tribe against
   Native American / American Indian or more general terms).

7. Major places or events and how are they discussed? Wounded Knee,
   Alcatraz, Sand Creek. Also major figures such as Sitting Bull,
   Dennis Banks, Pocahontas but also non-Native peoples. (this one is
   a bit sloppy of a question, but would be curious).

8. What groups are more/less represented as authors? As topics? Is
   any region more represented than another?

9. Is there an asymmetry in male vs. female Native authors?

10. Graph the (presumed) increase in production of scholarship by
    Native authors over time.

11. What languages are more/less represented as language of the
    medium? As language of topic?

12. To what extent are Native languages used in English-language
    works? In what contexts?

13. Are there any examples of Native people publishing on Native
    languages that aren’t theirs?

14. Investigating discussions around “community”

15. Appearance of terms like “extinct”, “endangered”, “loss”,
    “obsolescence” vs. “dormant”, “awakening”, “revitalization”,
    “preservation”, “resilience”

16. Comparative lexical frequency analysis between our workset and the
    control. If we can do just general, that’s an option, or we can
    come up with relevant terms. Just trying to catch some things we
    may not have thought of.

Reference:

<div class="bibl" style="padding-left:2em; text-indent:-2em;">
Blakesley Lindsay, E. (2003). Native American Authors. *Reference
Reviews, 17*(5), 41-42.
</div>

<a id="note01"/>\[[1](#ref01)] <https://hbw.ku.edu/>
