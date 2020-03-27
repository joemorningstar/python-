python csv 模块
=======

**csv- CSV File Reading and Writing**

See python's guide about [csv module](https://docs.python.org/3/library/csv.html#csv.DictReader)

Other great tutorials: [Reading and Writing a CSV file](https://www.guru99.com/python-csv.html)

<br>
**What is CSV**

A CSV file is a type of plain text file that uses specific structuring to arrange tabular data. CSV is a common format for data interchange as it's compact, simple and general. Many online services allow its users to export tabular data from the website into a CSV file. Files of CSV will open into Excel, and nearly all databases have a tool to allow import 	from CSV file. The standard format is defined by rows and columns data. Moreover, each row is terminated by a newline to begin the next row. 	Also within the row, each column is separated by a comma.


The csv module’s *reader* and *writer* objects read and write sequences. Programmers can also read and write data in dictionary form using the `DictReader` and `DictWriter` classes.

**How to read a CSV file**

To read data from CSV files, you must use the reader function to generate a reader object.

The reader function is developed to take each row of the file and make a list of all columns. Then, you have to choose the column you want the variable data for.

examples:
```
import csv
with open('/Users/IMAC/Desktop/python-testing-files/demo.csv','rt') as file:
	data=csv.reader(file)
	for row in data:
		print(row)
```

open in a dictionary:

	import csv
	with open('/Users/IMAC/Desktop/python-testing-files/demo.csv',newline='') 	as file:
    	reader=csv.DictReader(file)
    	for row in reader:
    	    print(row['name'])


**How to write a csv file**

	import csc
	with open('X:\writeData.csv', mode='w') as file:
   	 writer = csv.writer(file, delimiter=',', quotechar='"', 	quoting=csv.QUOTE_MINIMAL)
	
    #way to write to csv file
    writer.writerow(['Programming language', 'Designed by', 'Appeared', 'Extension'])
    writer.writerow(['Python', 'Guido van Rossum', '1991', '.py'])
    writer.writerow(['Java', 'James Gosling', '1995', '.java'])
    writer.writerow(['C++', 'Bjarne Stroustrup', '1985', '.cpp'])
    
`delimiter` is the character used to separate each field.(the default is the 	comma , ) `quotechar `is the character used to surround fields that contaim the 	delimiter character,( default is a double quote)


**Better ways to read and write a csv file (using pandas)**

read:

	#import necessary modules
	import pandas
	result = pandas.read_csv('demo.csv')
	print(result)
	
write:

	from pandas import DataFrame
	C = {'Programming language': ['Python','Java', 'C++'],
        'Designed by': ['Guido van Rossum', 'James Gosling', 'Bjarne Stroustrup'],
        'Appeared': ['1991', '1995', '1985'],
        'Extension': ['.py', '.java', '.cpp'],
    }
	df = DataFrame(C, columns= ['Programming language', 'Designed by', 'Appeared', 'Extension'])
	export_csv = df.to_csv (r'X:\pandaresult.csv', index = None, header=True) # 	here you have to write path, where result file will be stored
	print (df)
	







