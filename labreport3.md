# Lab Report 3
The command I explored was grep.
## Command 1: -v
Input:
```
grep -vlr "disease" technical/biomed > grep-results.txt 
```
Output:
```
technical/biomed/1468-6708-3-1.txt
technical/biomed/1468-6708-3-10.txt
technical/biomed/1468-6708-3-3.txt
technical/biomed/1468-6708-3-4.txt
technical/biomed/1468-6708-3-7.txt
technical/biomed/1471-2091-2-10.txt
technical/biomed/1471-2091-2-11.txt
technical/biomed/1471-2091-2-12.txt
technical/biomed/1471-2091-2-13.txt
technical/biomed/1471-2091-2-16.txt
technical/biomed/1471-2091-2-5.txt
technical/biomed/1471-2091-2-7.txt
// more paths produced
```
This command recursively searches all files in a given directory that does not contain the word 'disease"

Input: 
```
grep -v "," technical/biomed/1468-6708-3-1.txt 
 ```
Output: 
 ```
 Introduction
        even though there is little evidence that overweight is
        associated with increased mortality in those over age 65.
        Six large controlled population-based studies of
        non-smoking older adults have investigated the association
        for relevant covariates [ 1 2 3 4 5 6 ] . All studies found
        with moderately high BMI had little or no extra risk except
        in certain small subsets. A review of 13 studies of older
        adults drew similar conclusions [ 7 ] .
        Many healthy older adults report gradual weight gain
        throughout adult life. It may be that a small amount of
        gradual weight gain is normative and associated with the
        most robust health as we age. It has been suggested that
        weight standards be adjusted upwards for age [ 8 ] . Such
        because few studies have examined the relation of BMI to
        quality of life or years of healthy life (YHL) in the
        elderly [ 9 ] .
        trials of weight modification might be more successful if
        decreased mortality. Clinical trials powered to detect
        differences in YHL would often require fewer subjects than
        trials to detect survival differences or cardiovascular
        events [ 10 ] . In this paper we study whether BMI at
        well characterized. The goal is to determine whether
        analyses based on years of life (YOL) or on YHL would
        would yield more powerful evaluations of weight
        modification interventions in older adults.
        /* more text not included */
```
This command searches the provided file and returns all lines that do not contain the pattern, in this case a comma. 
In both cases, the -v command could be useful if you are searching for files in a directory and want to avoid a common phrase that might be used in them. 

## Command 2: -i
Input:
```
grep -ilr  "bomb" technical/government 
 ```
 Output:
 ```
technical/government/Alcohol_Problems/DraftRecom-PDF.txt
technical/government/Alcohol_Problems/Session3-PDF.txt
technical/government/Gen_Account_Office/ai9868.txt
technical/government/Gen_Account_Office/d02701.txt
technical/government/Gen_Account_Office/July11-2001_gg00172r.txt
technical/government/Gen_Account_Office/May1998_ai98068.txt
technical/government/Gen_Account_Office/pe1019.txt
technical/government/Gen_Account_Office/Testimony_cg00010t.txt
```
This command recursively performs a case-insensitive search in a directory and returns all the files that match the given pattern.

Input:

    grep -i "bomb"  technical/government/Gen_Account_Office/Testimony_cg00010t.txt
    
Output:

    The bombings in New York City in 1993 and in Oklahoma City in
  Here is one the files that the directory search produced and the command performs a case-insensitive search of the word "bomb." It prints out all lines that match the pattern.
 The -i command is useful if you want to search for files that contain a certain keyword but you do not care about capitalization. 
          
## Command 3: -A / -B
Input:

    grep -A 2 -B 1 "cell" technical/biomed/1471-213X-1-3.txt
Output:

        connective tissue covered by endothelial like trabecular
        cells and a Schlemm's canal (SC). The aqueous percolates
        through channels or intertrabecular spaces in the TM before
        entering SC. The fluid collected by SC drains into aqueous

        generally accepted as neural crest derived [ 8, 9]. Recent
        cell grafting and cell labeling studies of craniofacial
        morphogenesis in mouse embryos confirm a neural crest
        derivation of the mammalian periocular mesenchyme [ 10].
        // more lines redacted
  This command searches the provided .txt file for lines containing the pattern, "cell", and returns that line, along with one line before it and 2 lines after it. The -A command returns the specified amount of lines after the matching line, and the -B command returns the specified amount of lines before the matching line. 
  
Input:

    grep -A 2 "cell" technical/biomed/1471-213X-1-3.txt
Output:
   
        cells and a Schlemm's canal (SC). The aqueous percolates
        through channels or intertrabecular spaces in the TM before
        entering SC. The fluid collected by SC drains into aqueous

        cell grafting and cell labeling studies of craniofacial
        morphogenesis in mouse embryos confirm a neural crest
        derivation of the mammalian periocular mesenchyme [ 10].
        // more lines redacted
  If I just wanted to see the two lines after the lines matching the pattern, I could leave the -B command out. This command could be useful if context is important when you are searchinga file.
  This command could be especially in a scenario where you not only needed to find lines in a file matching a pattern but if the surrounding lines around the matching lines are also important.
  
## Command 4: --exclude
Input:
  
    grep -r "apple" --exclude-dir=biomed technical
Output:
  
    technical/911report/chapter-8.txt:                grappled with reports alleging plots in Yemen and Italy, as well as a report about a
    technical/government/About_LSC/commission_report.txt:apples (4,428), vegetable harvesting (4,822), and fruit harvesting
    technical/government/About_LSC/commission_report.txt:the October apple harvest, and then return to Mexico until the work
    technical/government/About_LSC/commission_report.txt:apple harvest. See April Comments at 101 (comment of Garry G.
    technical/government/Gen_Account_Office/Oct15-2001_d0224.txt:incidents has proven to be challenging as organizations grapple
    technical/government/Gen_Account_Office/Testimony_cg00010t.txt:Clearly, much has already changed as GAO has grappled with this
    technical/government/Gen_Account_Office/Testimony_cg00010t.txt:grapples with increasingly complex and contentious issues requiring  
    technical/government/Media/Law_Schools.txt:government post. Here is how to grapple "in the service of
    technical/plos/pmed.0010013.txt:        easier to grapple with a difficult, but ultimately soluble, basic science question than to
  This command recursively searches the technical directory for lines in files containing the pattern "apple." The exclude command caused grep not to search the provided directory, in this case the biomed directory. 
 
Input:
  
  
    grep -wr "dog" --exclude=a --exclude-dir=biomed technical
 
Output:
 ```
   technical/911report/chapter-13.3.txt:                testimony, Mar. 23, 2004. When "wag the dog" allegations were again raised during
   technical/911report/chapter-3.txt:            The failure of the strikes, the "wag the dog" slur, the intense partisanship of the   
   technical/government/Media/Abuse_penalties.txt:Fines the same for beating a dog in county
   technical/government/Media/Abuse_penalties.txt:If you beat a dog in Schuylkill County, you'll probably get a
   technical/government/Media/Attorney_gives_his_time.txt:"Someone's cat was bit by a dog, as I recall," he said.
   technical/plos/journal.pbio.0020297.txt:              dog embraced so many unlike specimens of differing sizes and different forms; he was
   technical/plos/journal.pbio.0020297.txt:              disturbed by the fact that a dog at three-fourteen (seen in profile) should have the
   technical/plos/journal.pbio.0020297.txt:              same name as the dog at three-fifteen (seen from the front).…Without effort, he had
   technical/plos/pmed.0020034.txt:        cat, and also to birch and dog. However, in the United States and New Zealand, the presence
```
The exclude command can also be used to exclude path files that matched a certain pattern. In this input, paths leading to a file that had the character a in it were excluded, as well as the biomed directory when performing the search. The command searched the technical directory, excluding the mentioned conditions, and returned all file lines that contained the whole word "dog," which is what the -w command does. 
The --exclude command is useful if you are searching a directory that contains many others directories or files that are unrelated or irrelevant to the ones you need to find. 

## Sources 
- [ChatGPT](https://chat.openai.com/)

    Prompts Used: "what are some ways to use grep in command line" and "what are some more ways to use the grep command"
 
