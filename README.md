# usageinfo-gnuplot

Convert time-dependent tabular 2D data to executable gnuplot scripts.

## Installation

Clone the remote repository and change into the local repository:

```bash
$ git clone https://github.com/mboljen/usageinfo-gnuplot
$ cd usageinfo-gnuplot
```

Use the following command to install this software:

```bash
$ make
$ make install
```

The default `PREFIX` is set to `/usr/local`.  In order to successfully complete the installation, you need to have write permissions for the installation location.

## Requires

+ [Math::Derivative - Numeric 1st and 2nd order differentiation](https://metacpan.org/pod/Math::Derivative)
+ [Math::Spline - Cubic Spline Interpolation of data](https://metacpan.org/pod/Math::Spline)
+ [Spreadsheet::Read::Simple - Simple parsing of spreadsheets](https://github.com/mboljen/spreadsheet-read-simple-perl)
+ [Time::Piece - Object Oriented time objects](https://metacpan.org/pod/Time::Piece)
+ [Time::Seconds - API to convert seconds to other data values](https://metacpan.org/pod/Time::Seconds)

## Usage

### Synopsis

```console
$ usageinfo [OPTION]... INFILE
```

### Options

- **--man**
  
  Prints the manual page and exits.

- **--help**
  
  Prints a brief help message and exits.

#### Reading data

Customize how data is read in.

- **--sep**=_value_
  
  Sets separation character for plain text files.

- **--sheet**=_value_
  
  Sets sheet number for spreadsheet files (default: `1`).

- **--column**=_abscol_ _ordcol_
  
  Sets numbers of abcissa column (default: `1`) and ordinate column (default: `2`).

- **--dtfmt**=_datespec_
  
  Sets date specifier accordint to **strftime**.

#### Writing data

Customize how data is output.

- **-t**, **--title**=_string_
  
  Uses specific Gnuplot title.

- **--ylabel**=_value_
  
  Uses specific Gnuplot label for ordinate axis (default: `undef`).

- **--yformat**=_value_
  
  Uses specific Gnuplot label for ordinate tics (default: `undef`).

- **--yrange**=_value_
  
  Uses specific Gnuplot range for ordinate axis (default: `undef`).

- **-c**, **--color**=_colorspec_
  
  Uses specific Gnuplot color.

- **-r**, **--rate**=_ratespec_
  
  Show first derivative of ordinate values with respect to _ratespec_. Available options are: `year`, `month`, `week`, `day`, `hour`, `min`, `sec`.  Alternatively, a custom period can be specified in seconds.

- **-s**, **-scale**=_num_
  
  Scales ordinate values by factor _num_ (default: `1`).

#### Splitting data

Customize how data is split.

* **-p**, **--period**=_string_
  
  Splits data with respect to periods into datasets. Avaliable options are `year`, `month`, `week`, `day`, `hour` (default: `year`).

* **-m**, **--max**=_num_
  
  Limits output to latest `num` datasets.  Set to zero to include all available datasets (default: `0`).

* **--reset**
  
  Resets ordinate values to zero at the start of each dataset.

## See also

Full documentation and sources at: <https://github.com/mboljen/usageinfo-gnuplot>

## Contributing

Pull requests are welcome.  For major changes, please open an issue first to discuss what you would like to change.

Submit bug reports online at: <https://github.com/mboljen/usageinfo-gnuplot/issues>

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
