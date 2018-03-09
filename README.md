This is a file data transformation script to convert from waves height and direction MetOffice format to SWAN format.


Usage
---
Just:

```Shell
metoffice2swan -d decimal_separator -s csv_delimiter [targetFolder]
```

where "targetFolder" is the folder containing the CSV files to transform, and the options:

- -d decimal_separator: determines the decimal separator (, or ., defaults to ,)
- -s csv_separator: determines the CSV separator (defaults to ;)

for example:

```Shell
metoffice2swan -d . -s | .
```

will look for |-delimited, decimal point numbers CSV in the current folder (.). To transform CSV in the current folder with default options, just:

```Shell
metoffice2swan .
```

The script will search for all .csv files in the target folder and try the conversion, leaving at the end an "out-swan" folder with .csv.txt files, compatible with SWAN, with the same names as the original source files.


Excel Format
---
Column order and total number of them is irrelevant, so long the following column name conventions are followed:

- year: year
- month: month
- day: day
- hour: hour
- wave height: Hs
- wave period: T
- wind azimuth: wind direction

Please note that column names are case-sensitive. Modify the Excel column names to match the aforementioned ones.

After exporting to CSV, a clean text file with a header akin to the following format should be obtained:

```Shell
hour;day;month;year;Hs;T;wind direction
0;1;7;2003;0,6;3,7;62
3;1;7;2003;0,9;4;34
```

Remember that column order is irrelevant, as well as any extra columns. So long the critical columns are named correctly, the script should work.
