# linux-cheat-sheets
Este repositório tem como objetivo armazenar comandos e dicas sobre linux de maneira resumida.

## Log parsing Cheat Sheet ##

GREP	GREP allows you to search patterns in files. ZGREP for GZIP files.
$grep <pattern> file.log

-n: Number of lines that matches.
-i: Case insensitive.
-v: Inver matches.
-E: Extended regex.
-c: Count number of matches.
-l: Find filenames that matches the pattern.
-R or -r: Find all ocurrences on recursive folders.

NGREP	NGREP is used for analyzing network packets.
$ngrep -I file.pcap

-d: Specify network interface
-i: Case insensitive.
-x: Print in alternate hexdump.
-t: Print timestamp.
-I: Read pcap file.

CUT		The CUT command is used to parte fields from delimited logs.
$cut -d ":" -f 2 file.log

-d: Use the field delimiter.
-f: The field numbers
-c: Specifies the char position.

SED	SED(Stream Editor) is used to replace string in a file.
$sed s/regex/replace/g

s: Search.
g: Replace.
d: Delete.
W: Append to file.
-e: Execute command.
-n: Suppress output.

SORT	SORTe is used to sort a file.
$sort foo.txt

-o: Output to file.
-r: Reverse order.
-n: Numerical sort.
-k: Sort by column.
-c: Check if ordered.
-u: Sort and remove.
-f: Ignore case.
-h> Human sort.

UNIQ	Unid is used to extract uniq occurrences.
$unid foo.txt

-c: Count the number of duplicates.
-d: Print duplicates.
-i: Case insensitive.

DIFF	DIFF is used to display differences in files by comparing line by line.
$diff foo.log bar.log

How to read output?
	a: Add		#: Line Numbers
	c: Change	<: File 1
	d: Delete	>: File 2

AWK	AWK is a programming language used to manipulate data.
$awk {print $2} foo.log

Print first column with separator ":"
$awk -F: '{print $1}' /etc/passwd

Extract unid value from two files:
$awk 'FNR==NR {a[$1]++;next} 1($0 in a)' f1.txt f2.txt
