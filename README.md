# Lucene-Project
- Lucene is a high-performance, full-featured text search engine library writtena entirely in Java.
- Use Lucene index to search the words “Conversational Agent”, “Chatbot”, “Personal Assistant”, “Smart Speaker”

## How Lucene Work
![image](https://user-images.githubusercontent.com/79159894/197627996-852740bc-03c9-45fa-bca2-09ecaad7f6f0.png)

- 1. Pass the Document object to the IndexWriter.
- 2. Uses the Analyzer to generate Terms from the plain text obtained by the Reader.
- 3. Writes everything that is necessary to update the index to the Directory.

## Download the lucene library

Download lucene library from here
- https://archive.apache.org/dist/lucene/java/
- ![image](https://user-images.githubusercontent.com/79159894/197449150-73f5d9b0-dfb7-4d1f-85a1-7f22ac312c61.png)
- Download the lucene-9.4.0.tgz and use 7-zip to extract the file.
- Then you can find all jar in module file
- ![image](https://user-images.githubusercontent.com/79159894/197449265-1352cec7-8055-4a09-b43f-541bef07f243.png)



## Do not Download jar from these websites because module are not complete!
- Download lucene-core-6.6.0.jar file
- Download lucene-queryparser-6.6.0.jar file
- Reference:
- http://www.java2s.com/example/jar/l/download-lucenecore660jar-file.html#google_vignette
- http://www.java2s.com/example/jar/l/download-lucenequeryparser660jar-file.html


## Covert gz to xml
- Install wsl in Window 10
- use Administrator permissions to open cmd, and type down this command
```
wsl.exe --install
```

and after reboot the computer then
```
gunzip xxx.xml.gz
```

Or
just download the `7-zip file manager` to extract the xml from gz
- Reference:
- https://www.youtube.com/watch?v=egqnJ9YsUJ8
- https://www.omgubuntu.co.uk/how-to-install-wsl2-on-windows-10
- https://www.7-zip.org/


## Code Review


## Output
```
Total Number of Files that found Conversational Agent: 4
Conversational Agent 3 times
Path  : inputFiles\dblp004.xml
Conversational Agent 2 times
Path  : inputFiles\dblp003.xml
Conversational Agent 1 times
Path  : inputFiles\dblp002.xml
Conversational Agent 0 times
Path  : inputFiles\dblp001.xml

Total Number of Files that found Chatbot: 0

Total Number of Files that found Personal Assistant: 4
Personal Assistant 2 times
Path  : inputFiles\dblp003.xml
Personal Assistant 1 times
Path  : inputFiles\dblp002.xml
Personal Assistant 3 times
Path  : inputFiles\dblp004.xml
Personal Assistant 0 times
Path  : inputFiles\dblp001.xml

Total Number of Files that found Smart Speaker: 4
Smart Speaker 0 times
Path  : inputFiles\dblp001.xml
Smart Speaker 2 times
Path  : inputFiles\dblp003.xml
Smart Speaker 3 times
Path  : inputFiles\dblp004.xml
Smart Speaker 1 times
Path  : inputFiles\dblp002.xml
```
## Issues
## 1. Lucene Library Applied
- First problems I met is the library can not be apply for the program.
- I tried lots of way, finally TA help me to found out, library need to add under the class path not under the module path.
- ![image](https://user-images.githubusercontent.com/79159894/197464655-b93a9b47-58dc-469e-a1d4-de7b76963a5b.png)
- ![image](https://user-images.githubusercontent.com/79159894/197464768-a748dff6-0eea-42ce-b055-88531c12ae73.png)
And at Order and Export, we need to seclet all jar files and apply.
- ![image](https://user-images.githubusercontent.com/79159894/197464824-6349c04f-b99a-4ebb-8403-81888fafca2f.png)
- Reference:
- https://stackoverflow.com/a/24644256/19462556

## 2. XML File Location
- So I ran into this issue `IndexNotFoundException: no segments* file found`, TA try lots of way to help me.
- like use `indewriter.commit()` before `indexwriter.close()`, but it not help.
- Finally, TA found the problem is in my xml file, so I tried to open my xml file in my java project, but it can not show the data.
- So I try to extrat my gz file again and set the extracted location directly to my java project, and that work!!
![image](https://user-images.githubusercontent.com/79159894/197467996-4d6f3710-3221-48e8-abac-7e265a92de3f.png)
- Reference
- https://stackoverflow.com/a/68717768/19462556

## GitHub
```
> git push -u origin main
Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

- Solution
```
git remote set-url origin https_link_to_repository

git push -u origin master
```
- https://stackoverflow.com/a/53277459/19462556



## Reference
- https://www.javacodegeeks.com/2015/09/apache-lucene-fundamentals.html
- https://www.lucenetutorial.com/lucene-in-5-minutes.html
- https://howtodoinjava.com/lucene/lucene-index-and-search-text-files/
- https://stackoverflow.com/questions/5158138/what-does-lucenes-scoredoc-score-mean
- https://lucene.apache.org/core/3_0_3/scoring.html
