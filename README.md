accesslog2csv
=============

Utility script converting Apache/Tomcat log files to CSV format files

Introduction
------------

Recently, I had to analyze the Apache / Tomcat access log files, and so I needed to convert the log files into CSV in order to have a chance to use other tools such as spreadsheet.

The conversion shouldn't be hard. I found some scripts (in PHP, AWK, Perl or Ruby) on the internet, but those didn't fit my needs quite well. I didn't want to lose any data such as http method, byte size sent in response, etc. Also, the CSV should contain spreadsheet friendly data format. For example, "2012-07-10 22:30:03" instead of "10/Jul/2012:22:30:03".

So, I ended up writing yet another one by myself. Why not? ;-)

How to run
----------

```
$ perl accesslog2csv.pl access_log_file > csv_output_file.csv
```

Or, you can redirect STDIN like the following examples:

```
$ perl accesslog2csv.pl < access_log_file > csv_output_file.csv
```

```
$ cat access_log_file | perl accesslog2csv.pl > csv_output_file.csv
```

Also, you can check invalid log lines by redirecting STDERR, too:

```
$ perl accesslog2csv.pl < access_log_file > csv_output_file.csv 2> invalid_log_lines.txt
```

Hope it helps somewhere! :-)
