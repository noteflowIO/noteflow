# Welcome to NoteFlow

Simply document your inputs and outputs, and NoteFlow executes your Jupyter Notebook as a **serverless cloud-function**, which can be run manually, or via API (*coming soon*).

- [How Does It Work](#how-does-it-work)
  - [I/O Types](#io-types)
  - [Installing Packages](#installing-packages)
  - [Exporting Files](#exporting-files)
- [Uploading Notebooks]()
- [Running Notebooks]()
- [Reporting Bugs & Issues]()

## How Does It Work?

A notebook’s first code cell is used to document inputs and outputs. You can specify an input/output's type, as well as a friendly description.

For example:

> string_var = 'foo'				  #input  string    A string input  
> num_var = None					  #input  number    A numeric input     
> report_file = '/report.csv'		  #output filepath  The name of a file to export  

Currently, all documented inputs and outputs are required; there is no way to make an optional parameter.

### I/O Types

Input/Output supports the following types: string, number, and filepath

* `inputVar = None                 #input   [string, number, filepath]    Description`
* `outputVar = None                #output  [string, number, filepath]    Description`

### Installing Packages:

`Pip Install` not yet supported (coming soon) -- currently we support only the following libraries: `numpy, scipy, pandas, and matplotlib`

### Exporting Files

To export a file from a notebook, first document your output in the notebook's first cell block [see above](#how-does-it-work). Throughout the course of your notebook, simply save a file to the filepath specified in your I/O documentation and we will do the rest.

For example:

> \# first cell    
> chart_file = '/chart.png'				  #output filepath  The name of a file to export    
> \# ...later in the notebook           
> figure = my_dataframe.plot().get_figure()   
> figure.savefig(chart_file)     