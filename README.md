Download Link: https://assignmentchef.com/product/solved-solvedhomework-06
<br>
Write a program called “novella” to search and index text. Your programshould read a file specified as an argument on the command line.

novella myNoevel.txt

The program should allow the user to: **search** for a keyword to find wholeand partial sub-string matches within the text.

### Novel File Structure

1. The file format will be ASCII text [0-9][a-zA-Z] including punctuation.2. Lines should be parsed by newline character \n3. Pages should be counted every 20 lines. i.e. every 20 lines you read, you should increment the page number. You can assume this number to be fixed.4. Lines should be relative to page numbers. i.e. You should have Page 1, line 0, Page 2, line 0, Page N, line 0.

## Requirements

**Ignore common words** – Your program should ignore the top 100 most commonwords in the English language (see the end of the assignment for list). Youmay use an STL map to check each word before inserting into the Trie andSuffix Tree.

**Non-Alphanumeric Characters** – Your program should ignore non-alphanumericcharacters such as punctuation, hyphens, etc., such as “dog’s”, or “top-dog”.Only [0-9][a-zA-Z] must be considered when matching.

**Case sensitivity** – Your program should ignore case sensitivity. Searchingfor DoG should return DOG or dog. You may convert all text to upper or lowercase to make this assignment easier. Alternatively, no bonus points will begiven for maintaining case.

**PREFIX Search Command** – The program should have a search mode that looksfor prefixes of words. i.e. prefix dog would return the positions in the textwhere dog was listed. The positions should be given by page number, linenumber. You should also print the surrounding text where the keyword was foundwith the ellipsis as shown below:

prefix dog

dog found on:

Page 15, Line 7

…the big dog was here…

Page 16, Line 8

…gone away. Dog’s once ruled…

Page 16, Line 9

…there my Dog was spotted…

You should print two words before and after the keyword. In the Above examplethe keyword **dog** was found on three pages. Your program should not return“g-dog”, as it is prefixed by a **g**.

**Suffix Search Command** – The program should have a search mode that looksfor patterns in the text. This should list where in the text the pattern waslisted. The positions should be given by page number, line number. You shouldalso print the surrounding text where the keyword was found with the ellipsisas shown below:

suffix dog

dog found on:

Page 15, Line 7

…he was birddogged when he…

Page 16, Line 8,

…gone away. Dog’s once ruled…

Page 16, Line 9

…there my Dog was spotted…

You should print two words before and after the keyword. In the Above examplethe keyword dog was found on three pages. You don’t have to worry aboutshowing words on multiple lines.Although the program should now show:

Page 16, Line 16 &amp; 17…there mydog was sitting…

**Bonus**

5 bonus points if you print the keyword in colored text. Prefix and suffixcommands should only highlight the keyword searched (it’s ok if you includepunctuations, hyphens, etc., e.g. main-dog-s)

[http://en.wikipedia.org/wiki/ANSI_escape_code#graphics](http://en.wikipedia.org/wiki/ANSI_escape_code#graphics)

[http://stackoverflow.com/questions/2616906/how-do-i-output-coloured-text-to-a-linux-terminalGrading](http://stackoverflow.com/questions/2616906/how-do-i-output-coloured-text-to-a-linux-terminalGrading)

## Grading

**C** – (starting at 72/100)

Prefix finds the text and prints the pages and line numbersPrefix finds the text and prints the pages, line numbers, and surrounding text up to N charactersPrefix Finds the text and prints the pages, line numbers, and surrounding two words (left and right)

**B** – (starting at 82/100)

Suffix finds the pattern and prints the pages and line numbersSuffix finds the pattern and prints the pages, line numbers, and surrounding text, upto N characters

**A** – (starting at 92/100)

Suffix finds the pattern and prints the pages, line numbers, and surrounding two words (left and right)

**Bonus + 10**

1. Compare the space requirements for a trie to that of a standard array2. Compare the time it takes to search for a keyword pattern using the naïve approach discussed in class to using a suffix array3. If you don’t store the entire file for printing pre- and post-words after the pattern.

**Bonus + 5**

1. Colored text as mentioned above

**Max**

Max points = 110/100FailYou don’t use a trieYour code does not unzipYour code does not compileIf you only do the prefix command, you will receive half of the points for each section.Rank

—– —–Rank Word1 the2 be3 to4 of5 and6 a7 in8 that9 have10 I11 it12 for13 not14 on15 with16 he17 as18 you19 do20 at21 this22 but23 his24 by25 from26 they27 we28 say29 her30 she31 or32 an33 will34 my35 one36 all37 would38 there39 their40 what41 so42 up43 out44 if45 about46 who47 get48 which49 go50 me51 when52 make53 can54 like55 time56 no57 just58 him59 know60 take61 people62 into63 year64 your65 good66 some67 could68 them69 see70 other71 than72 then73 now74 look75 only76 come77 its78 over79 think80 also81 back82 after83 use84 two85 how86 our87 work88 first89 well90 way91 even92 new93 want94 because95 any96 these97 give98 day99 most100 us—– —–

## Guidance

This program is not as big as it may look. Consider what you have to do. Startfirst with pen and paper. Build the concept first BEFORE PROGRAMMING!!!!!!! Oryou are destined to do poorly.

### Data structures

1. Triea. compressed or standard trie2. Suffix Treea. This is a compressed trie3. Pattern4. Terminal Nodea. Store page #b. Store line #c. You could use two more pointers to reduce space requirements for your software.5. You could store each linea. Given Page ID, Line ID, return vector of words

### Building

1. Trie / Suffix Constructiona. Word Ignoreri. Given a word, should it be inserted in the trie?b. File Readingi. Parsing words, split on newline, split on space,ii. Page / Line Identifier Algorithmc. Word Trackeri. Given a line ID, return all words2. Algorithma. Get User Input Command and Patternb. Find all matches for patterni. Prefix or Suffix – think about it, is there much of a difference in what they return?c. For each matchi. Lookup the Lineii. Get the pre-words before patterniii. Get the post-words after patterniv. Print (pre-words, word, post-words)

### Define Your Tasks

1. Define your test cases2. Define your objects you will build3. Write each test and object and test each feature first.4. Then integrate the above.