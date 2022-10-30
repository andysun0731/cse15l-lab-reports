# Lab Report 4

## `grep` command with option `-l`
* We can use this option to find the file names which its content contains the pattern we are looking at. This option is useful because we can easily locate the files we are looking at.
* Example 1:
```
andysun@AndydeAir biomed % grep -l "apple" *  
1468-6708-3-10.txt
1471-2105-3-12.txt
1471-2202-2-5.txt
1471-2458-3-11.txt
1472-6882-1-10.txt
gb-2002-3-10-research0053.txt
gb-2002-3-12-research0077.txt
gb-2003-4-8-r51.txt
```

* Example 2:
```
andysun@AndydeAir 911report % grep -l "United States" *
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-13.4.txt
chapter-13.5.txt
chapter-2.txt
chapter-3.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt
preface.txt
```

* Example 3:
```
andysun@AndydeAir plos % grep -l "crisis" *       
journal.pbio.0020052.txt
journal.pbio.0020430.txt
journal.pbio.0030127.txt
pmed.0010039.txt
pmed.0020075.txt
```

## `grep` command with option `-c`
* This command can print number of lines in a file that matches the pattern. We can use the option to find how mny lines in the file are the ones we want.
* Example 1:
```
andysun@AndydeAir biomed % grep -c "biology" rr74.txt
0
```

* Example 2:
```
andysun@AndydeAir 911report % grep -c "America" chapter-3.txt 
34
```

* Example 3:
```
andysun@AndydeAir 911report % grep -c "law" chapter-7.txt
7
```

## `grep` command with option `-o`
* This option can print only the matching part of a matching line. We can use this option to detect the matching parts of everyline in a file and also count how many times the pattern appears.
* Example 1:
```
andysun@AndydeAir 911report % grep -o "law" chapter-7.txt
law
law
law
law
law
law
law
```

* Example 2:
```
andysun@AndydeAir biomed % grep -o "mutations" rr167.txt    
mutations
```

* Example 3:
```
andysun@AndydeAir biomed % grep -o "output" rr74.txt    
output
```
