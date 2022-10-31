**```grep``` is the command i will talk about**
---


**grep -w:This command will allow the user to print the sentences that contains a certein keyword take as an argument.**

* In this example i just put a space in the argument so the command will print out the whole text from the file (pmed.0020055.txt). 
```
[cs15lfa22ou@ieng6-202]:plos:232$ grep -w " " pmed.0020055.txt
  
    
      
        
        “Publishing results in traditional paper based way in a journal hides too much
        information.” This is the verdict of Markus Ruschhaupt and colleagues who, in a paper in
        Statistical Applications in Genetics and Molecular Biology (3: article
        37), discuss a paradigm for the presentation of complex data—in this case, from microarray
        analyses. The title of the article, “A Compendium to Ensure Reproducibility in
        High-Dimensional Classification Tasks,” may not lend itself easily to a clinical audience,
        but the underlying message to clinicians could not be more important: that, currently,
        studies involving large datasets, especially ones that have a clinical outcome, are so
        poorly reported (or possibly so poorly done) that many are not reproducible. This problem
        was also the topic of a recent meeting in Heidelberg, “Best Practice in Microarray Studies”
        (http://www.biometrie.uni-heidelberg.de/workshops/bestpractice/index.htm).
        As microarrays have become mainstream research tools in biology and medicine, the large
        datasets and complex analyses from these studies have presented challenges: for authors in
        analyzing the data, for reviewers and editors in deciding on the suitability of papers for
        publication, for journals in determining how much data needs to be presented within the
        paper itself, for other researchers in reproducing the data, and, finally, for readers in
        deciding how to assess the data presented. The results from several high-profile papers
        have already proved difficult to reproduce, even by those with sufficient time and
        computing expertise.
        Where do such analyses leave the new science of molecular pathology? Ruschhaupt and
        colleagues comment that “the literature on the induction of prognostic profiles from
        microarray studies is a methodological wasteland.” Much the same could be said of other
        applications of molecular biology to clinical samples. A systematic review of molecular and
        biological tumor markers in neuroblastoma (Clin Cancer Res 10: 4–12) found that its
        conclusions were limited by “small sample sizes, poor statistical reporting, large
        heterogeneity across studies…and publication bias.” John Ioannidis and colleagues (Lancet
        362: 1439–1444) did a similar analysis of 30 microarray studies with major clinical
        outcomes in cancer. They showed that the studies were small—median sample size was 25
        patients, and validation was incomplete in most studies. They recommended that molecular
        prognostic studies be classified as phase 1 (early exploratory probing associations), phase
        2 (exploratory with extensive analyses), or phase 3 (large confirmatory studies with
        pre-stated hypotheses and precise quantification of the magnitude of the effect), and that
        only studies that had undergone phase 3 testing should be considered robust enough for use
        in clinical practice. Most current studies should be considered as phase 1 or, at best,
        phase 2.
        So, despite considerable hype, the published studies are far from the level of evidence
        that would be accepted for virtually any other medical test. In a review in 2003
        (Hematology [Am Soc Hematol Educ Program] 2003: 279–293), Rita Braziel and colleagues
        concluded, “rapid identification and neutralization of spurious results is essential to
        prevent them from becoming accepted facts.”
        But these problems are not new in medical research. In 1994 (BMJ 308: 283–284), Doug
        Altman, who was instrumental in developing the CONSORT guidelines for reporting of clinical
        trials, said that “huge sums of money are spent annually on research that is seriously
        flawed through the use of inappropriate designs, unrepresentative samples, small samples,
        incorrect methods of analysis, and faulty interpretation,” and “that quality control needs
        to be built in from the start rather than the failures being discarded.”
        So how can we ensure that the wealth of data pouring out of microarray and other
        molecular diagnostic studies is turned into meaningful knowledge? The Microarray Gene
        Expression Data Society has proposed a set of guidelines (MIAME) for the reporting of
        microarray data, and that all such data should be deposited in public databases. But as
        Ruschhaupt and others have shown, disclosure of results and data is not enough, since there
        is little consensus on the appropriate statistical analyses and many are developed on a
        data together with the textual documentation and conclusions.” One such compendium is
        illustrated in a paper by Robert Gentleman (Stat Appl Genet Mol Biol 4: article 2).
        PLoS Medicine is keen to work with authors towards making such reporting
        possible. But although the time might have gone when the two-dimensional journal article
        could suffice for complex papers, clinicians should nonetheless apply the same critical
        assessment that they would for any other clinical tool. If a result is too good to be true,
        it probably is.
```

* In this example i put the word "review" in the argument so the command will print out the sentences that contain that word from the file (pmed.0020055.txt). 


```
[cs15lfa22ou@ieng6-202]:plos:234$ grep -w "review" pmed.0020055.txt
        applications of molecular biology to clinical samples. A systematic review of molecular and
        that would be accepted for virtually any other medical test. In a review in 2003        
```
* In this example i put the word "illustrate" in the argument so the command will print out the sentences that contain that word from the all the files in the directory (*.txt). 

```
[cs15lfa22ou@ieng6-202]:plos:238$ grep -w "illustrate" *.txt
journal.pbio.0020010.txt:        considered. Not a detail of world-shattering significance, but it does illustrate the fact
journal.pbio.0020071.txt:        that the authors draw on a range of carefully chosen human traits to illustrate their
journal.pbio.0020113.txt:        examples illustrate how susceptible fisheries are to environmental fluctuations. When the
journal.pbio.0020127.txt:        Xenopus to illustrate the process, it is because it accompanies
journal.pbio.0020147.txt:        conclusions are sparse. We guess the aim of the chapter is to illustrate that environmental
journal.pbio.0020164.txt:        Taken as a pair, the von Dassow and Ingolia papers illustrate the value of complementary
journal.pbio.0020350.txt:        illustrate how birds might interact with bees at different-coloured flowers.
journal.pbio.0020400.txt:        The examples mentioned here illustrate the versatile potential of thiol modifications.
journal.pbio.0030021.txt:        These celebrated discoveries illustrate ways that very different organisms are, at a
pmed.0010013.txt:        illustrate their surgical method and skills. In many instances, case series also serve as
pmed.0020065.txt:        In their article, Kulldorff and colleagues illustrate the utility of the new method by
pmed.0020182.txt:        shown in Figure 5B and 5C, respectively. These images illustrate the dynamic range of the
pmed.0020208.txt:        The Washington whistleblowers' stories illustrate these issues. Psychiatrist Stefan
```


**grep -l:This command will allow the user to print the name of the files that contains a certein keyword take as an argument.**

* In this example i put the word "cell" in the argument so the command will print out the name of the files that contain that word from the all the files in the directory (*.txt). 

```
[cs15lfa22ou@ieng6-202]:plos:243$ grep -l "cell" *.txt   
journal.pbio.0020001.txt
journal.pbio.0020012.txt
journal.pbio.0020013.txt
journal.pbio.0020019.txt
journal.pbio.0020028.txt
journal.pbio.0020035.txt
journal.pbio.0020040.txt
journal.pbio.0020042.txt
journal.pbio.0020043.txt
journal.pbio.0020053.txt
journal.pbio.0020063.txt
journal.pbio.0020064.txt
journal.pbio.0020068.txt
journal.pbio.0020071.txt
journal.pbio.0020073.txt
journal.pbio.0020100.txt
journal.pbio.0020116.txt
journal.pbio.0020125.txt
journal.pbio.0020127.txt
journal.pbio.0020133.txt
journal.pbio.0020145.txt
journal.pbio.0020146.txt
journal.pbio.0020147.txt
journal.pbio.0020148.txt
journal.pbio.0020161.txt
journal.pbio.0020164.txt
journal.pbio.0020169.txt
journal.pbio.0020172.txt
journal.pbio.0020183.txt
journal.pbio.0020187.txt
journal.pbio.0020190.txt
journal.pbio.0020206.txt
journal.pbio.0020213.txt
journal.pbio.0020215.txt
journal.pbio.0020216.txt
journal.pbio.0020224.txt
journal.pbio.0020232.txt
journal.pbio.0020241.txt
journal.pbio.0020262.txt
journal.pbio.0020263.txt
journal.pbio.0020276.txt
journal.pbio.0020306.txt
journal.pbio.0020307.txt
journal.pbio.0020311.txt
journal.pbio.0020337.txt
journal.pbio.0020348.txt
journal.pbio.0020350.txt
journal.pbio.0020394.txt
journal.pbio.0020400.txt
journal.pbio.0020401.txt
journal.pbio.0020404.txt
journal.pbio.0020419.txt
journal.pbio.0020431.txt
journal.pbio.0020439.txt
journal.pbio.0020440.txt
journal.pbio.0030021.txt
journal.pbio.0030024.txt
journal.pbio.0030050.txt
journal.pbio.0030062.txt
journal.pbio.0030065.txt
journal.pbio.0030076.txt
journal.pbio.0030094.txt
journal.pbio.0030102.txt
journal.pbio.0030131.txt
journal.pbio.0030136.txt
journal.pbio.0030137.txt
pmed.0010008.txt
pmed.0010013.txt
pmed.0010021.txt
pmed.0010023.txt
pmed.0010024.txt
pmed.0010025.txt
pmed.0010026.txt
pmed.0010028.txt
pmed.0010036.txt
pmed.0010041.txt
pmed.0010045.txt
pmed.0010047.txt
pmed.0010048.txt
pmed.0010049.txt
pmed.0010050.txt
pmed.0010051.txt
pmed.0010058.txt
pmed.0010061.txt
pmed.0010064.txt
pmed.0010066.txt
pmed.0010070.txt
pmed.0010071.txt
pmed.0020002.txt
pmed.0020015.txt
pmed.0020017.txt
pmed.0020018.txt
pmed.0020021.txt
pmed.0020022.txt
pmed.0020027.txt
pmed.0020033.txt
pmed.0020034.txt
pmed.0020036.txt
pmed.0020040.txt
pmed.0020045.txt
pmed.0020050.txt
pmed.0020059.txt
pmed.0020060.txt
pmed.0020062.txt
pmed.0020068.txt
pmed.0020073.txt
pmed.0020074.txt
pmed.0020075.txt
pmed.0020085.txt
pmed.0020091.txt
pmed.0020094.txt
pmed.0020098.txt
pmed.0020103.txt
pmed.0020115.txt
pmed.0020118.txt
pmed.0020140.txt
pmed.0020150.txt
pmed.0020160.txt
pmed.0020161.txt
pmed.0020162.txt
pmed.0020182.txt
pmed.0020191.txt
pmed.0020196.txt
pmed.0020198.txt
pmed.0020201.txt
pmed.0020206.txt
pmed.0020209.txt
pmed.0020210.txt
pmed.0020212.txt
pmed.0020231.txt
pmed.0020232.txt
pmed.0020237.txt
pmed.0020238.txt
pmed.0020242.txt
pmed.0020249.txt
pmed.0020273.txt
```


* In this example i put the word "illustrate" in the argument so the command will print out the name of the files that contain that word from the the files that have "journal" in their name (journal*). 

```
[cs15lfa22ou@ieng6-202]:plos:244$ grep -l "illustrate" journal.*   
journal.pbio.0020010.txt
journal.pbio.0020042.txt
journal.pbio.0020071.txt
journal.pbio.0020113.txt
journal.pbio.0020127.txt
journal.pbio.0020133.txt
journal.pbio.0020147.txt
journal.pbio.0020161.txt
journal.pbio.0020164.txt
journal.pbio.0020187.txt
journal.pbio.0020262.txt
journal.pbio.0020307.txt
journal.pbio.0020350.txt
journal.pbio.0020400.txt
journal.pbio.0020420.txt
journal.pbio.0020431.txt
journal.pbio.0020439.txt
journal.pbio.0030021.txt
journal.pbio.0030136.txt
```


* In this example i put the empty "" in the argument so the command will print out all the files we have in directory (*.txt). 

```
[cs15lfa22ou@ieng6-202]:plos:245$ grep -l "" *.txt   
journal.pbio.0020001.txt
journal.pbio.0020010.txt
journal.pbio.0020012.txt
journal.pbio.0020013.txt
journal.pbio.0020019.txt
journal.pbio.0020028.txt
journal.pbio.0020035.txt
journal.pbio.0020040.txt
journal.pbio.0020042.txt
journal.pbio.0020043.txt
journal.pbio.0020046.txt
journal.pbio.0020047.txt
journal.pbio.0020052.txt
journal.pbio.0020053.txt
journal.pbio.0020054.txt
journal.pbio.0020063.txt
journal.pbio.0020064.txt
journal.pbio.0020067.txt
journal.pbio.0020068.txt
journal.pbio.0020071.txt
journal.pbio.0020073.txt
journal.pbio.0020100.txt
journal.pbio.0020101.txt
journal.pbio.0020105.txt
journal.pbio.0020112.txt
journal.pbio.0020113.txt
journal.pbio.0020116.txt
journal.pbio.0020121.txt
journal.pbio.0020125.txt
journal.pbio.0020127.txt
journal.pbio.0020133.txt
journal.pbio.0020140.txt
journal.pbio.0020145.txt
journal.pbio.0020146.txt
journal.pbio.0020147.txt
journal.pbio.0020148.txt
journal.pbio.0020150.txt
journal.pbio.0020156.txt
journal.pbio.0020161.txt
journal.pbio.0020164.txt
journal.pbio.0020169.txt
journal.pbio.0020172.txt
journal.pbio.0020183.txt
journal.pbio.0020187.txt
journal.pbio.0020190.txt
journal.pbio.0020206.txt
journal.pbio.0020213.txt
journal.pbio.0020214.txt
journal.pbio.0020215.txt
journal.pbio.0020216.txt
journal.pbio.0020223.txt
journal.pbio.0020224.txt
journal.pbio.0020228.txt
journal.pbio.0020232.txt
journal.pbio.0020241.txt
journal.pbio.0020262.txt
journal.pbio.0020263.txt
journal.pbio.0020267.txt
journal.pbio.0020272.txt
journal.pbio.0020276.txt
journal.pbio.0020297.txt
journal.pbio.0020302.txt
journal.pbio.0020306.txt
journal.pbio.0020307.txt
journal.pbio.0020310.txt
journal.pbio.0020311.txt
journal.pbio.0020337.txt
journal.pbio.0020346.txt
journal.pbio.0020347.txt
journal.pbio.0020348.txt
journal.pbio.0020350.txt
journal.pbio.0020353.txt
journal.pbio.0020354.txt
journal.pbio.0020394.txt
journal.pbio.0020400.txt
journal.pbio.0020401.txt
journal.pbio.0020404.txt
journal.pbio.0020406.txt
journal.pbio.0020419.txt
journal.pbio.0020420.txt
journal.pbio.0020430.txt
journal.pbio.0020431.txt
journal.pbio.0020439.txt
journal.pbio.0020440.txt
journal.pbio.0030021.txt
journal.pbio.0030024.txt
journal.pbio.0030032.txt
journal.pbio.0030050.txt
journal.pbio.0030051.txt
journal.pbio.0030056.txt
journal.pbio.0030062.txt
journal.pbio.0030065.txt
journal.pbio.0030076.txt
journal.pbio.0030094.txt
journal.pbio.0030097.txt
journal.pbio.0030102.txt
journal.pbio.0030105.txt
journal.pbio.0030127.txt
journal.pbio.0030129.txt
journal.pbio.0030131.txt
journal.pbio.0030136.txt
journal.pbio.0030137.txt
pmed.0010008.txt
pmed.0010010.txt
pmed.0010013.txt
pmed.0010021.txt
pmed.0010022.txt
pmed.0010023.txt
pmed.0010024.txt
pmed.0010025.txt
pmed.0010026.txt
pmed.0010028.txt
pmed.0010029.txt
pmed.0010030.txt
pmed.0010034.txt
pmed.0010036.txt
pmed.0010039.txt
pmed.0010041.txt
pmed.0010042.txt
pmed.0010045.txt
pmed.0010046.txt
pmed.0010047.txt
pmed.0010048.txt
pmed.0010049.txt
pmed.0010050.txt
pmed.0010051.txt
pmed.0010052.txt
pmed.0010056.txt
pmed.0010058.txt
pmed.0010060.txt
pmed.0010061.txt
pmed.0010062.txt
pmed.0010064.txt
pmed.0010066.txt
pmed.0010067.txt
pmed.0010068.txt
pmed.0010069.txt
pmed.0010070.txt
pmed.0010071.txt
pmed.0020002.txt
pmed.0020005.txt
pmed.0020007.txt
pmed.0020009.txt
pmed.0020015.txt
pmed.0020016.txt
pmed.0020017.txt
pmed.0020018.txt
pmed.0020019.txt
pmed.0020020.txt
pmed.0020021.txt
pmed.0020022.txt
pmed.0020023.txt
pmed.0020024.txt
pmed.0020027.txt
pmed.0020028.txt
pmed.0020033.txt
pmed.0020034.txt
pmed.0020035.txt
pmed.0020036.txt
pmed.0020039.txt
pmed.0020040.txt
pmed.0020045.txt
pmed.0020047.txt
pmed.0020048.txt
pmed.0020050.txt
pmed.0020055.txt
pmed.0020059.txt
pmed.0020060.txt
pmed.0020061.txt
pmed.0020062.txt
pmed.0020065.txt
pmed.0020067.txt
pmed.0020068.txt
pmed.0020071.txt
pmed.0020073.txt
pmed.0020074.txt
pmed.0020075.txt
pmed.0020082.txt
pmed.0020085.txt
pmed.0020086.txt
pmed.0020088.txt
pmed.0020090.txt
pmed.0020091.txt
pmed.0020094.txt
pmed.0020098.txt
pmed.0020099.txt
pmed.0020102.txt
pmed.0020103.txt
pmed.0020104.txt
pmed.0020113.txt
pmed.0020114.txt
pmed.0020115.txt
pmed.0020116.txt
pmed.0020117.txt
pmed.0020118.txt
pmed.0020120.txt
pmed.0020123.txt
pmed.0020140.txt
pmed.0020144.txt
pmed.0020145.txt
pmed.0020146.txt
pmed.0020148.txt
pmed.0020149.txt
pmed.0020150.txt
pmed.0020155.txt
pmed.0020157.txt
pmed.0020158.txt
pmed.0020160.txt
pmed.0020161.txt
pmed.0020162.txt
pmed.0020180.txt
pmed.0020181.txt
pmed.0020182.txt
pmed.0020187.txt
pmed.0020189.txt
pmed.0020191.txt
pmed.0020192.txt
pmed.0020194.txt
pmed.0020195.txt
pmed.0020196.txt
pmed.0020197.txt
pmed.0020198.txt
pmed.0020200.txt
pmed.0020201.txt
pmed.0020203.txt
pmed.0020206.txt
pmed.0020208.txt
pmed.0020209.txt
pmed.0020210.txt
pmed.0020212.txt
pmed.0020216.txt
pmed.0020226.txt
pmed.0020231.txt
pmed.0020232.txt
pmed.0020235.txt
pmed.0020236.txt
pmed.0020237.txt
pmed.0020238.txt
pmed.0020239.txt
pmed.0020242.txt
pmed.0020246.txt
pmed.0020247.txt
pmed.0020249.txt
pmed.0020257.txt
pmed.0020258.txt
pmed.0020268.txt
pmed.0020272.txt
pmed.0020273.txt
pmed.0020274.txt
pmed.0020275.txt
pmed.0020278.txt
pmed.0020281.txt
```


**grep -h:This command will allow the user to print the line that contains a certein keyword take as an argument. This command option can help us finding the line the word is in so we can find our about the word and where it was mentioned in the file.**


* In this example i put the word "literate" in the argument so the command will print out all the lines that contains that word from directory (*.txt). 

```
[cs15lfa22ou@ieng6-202]:plos:252$ grep -h "literate" *.txt
        Like academia, industry needs scientifically literate personnel; unlike academia,

```

* In this example i put the word "academia" in the argument so the command will print out all the lines that contains that word from directory (*.txt). 


```
[cs15lfa22ou@ieng6-202]:plos:256$ grep -h "academia" *.txt
        existing structures in academia or through funding R&D arms of existing companies to
        Like academia, industry needs scientifically literate personnel; unlike academia,
        official stamp of academia to his science of expression, documenting in the language of
        Finally, similar to the pressures faced by their colleagues elsewhere in academia,
```

* In this example i put the word "Therapeutic" in the argument so the command will print out all the lines that contains that word from the files that their name starts with "1471". 


```
[cs15lfa22ou@ieng6-202]:biomed:269$ grep -h "Therapeutic" 1471*
          flavopiridol (Developmental Therapeutics Program,
        (Table 2). Therapeutic ratios, calculated as CC
        antigen-presenting cell or Langerhans cell. Therapeutic
```