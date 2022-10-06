# LIBSsa2 - Laser Induced Breakdown Spectroscopy spectra analyzer

### Current stable version: _2.0.94_

## About the software

**LIBSsa 2** is a free software, licenced under the **GNU Affero General Public License
version 3**, and written in **Python 3.x** for analyzing **LIBS spectra**.
It can read multiple formats of data inside raw/text files, import the spectra, and
perform multiple analysis in the data. The environment (spectra, peaks and results)
may be saved into an encapsulated **lb2e** file.
Finally, users can also export result of analysis in many common files (**csv** and **xlsx**).

## Features

1. **Importing Spectra**: users can import data into LIBSsa 2 from any kind of raw/text
data, including **txt**, **csv**, **esf** and **ols**. There are also many options in how data can be loaded:
   1. **Load methods**: how files are read by the program
      1. **Multi**: one folder per sample, several files per sample
      2. **Single**: one file per sample, multiple columns in each file
   2. **Delimiters**: TAB ("**\t**"), SPACE ('**\s+**'), comma ("**.**") and semicolon ("**;**")
   3. **Header**: number of rows to skip
   4. **Wavelength and Counts**: in which columns are the wavelength and counts data
   5. **Decimals**: if user wants to round loaded signal (for improved performance)
   6. **FSN** (Full Spectrum Normalization): can use signal information during the loading for normalization
2. **Outliers removal**: there are 2 algorithms for outliers removal in LIBSsa 2:
   1. **SAM** (Spectral Angle Mapper): removes outliers based on how different a sample is from the average
   2. **MAD** (Median Absolute Deviation): remove outliers based on a per wavelength criteria
3. **Correlation Spectrum**: if reference is provided, calculates Pearson-R as function of wavelength
4. **Peak isolation**: can isolate multiple peaks at once
5. **Peak fitting**: can perform peak fitting to obtain areas and heights for multiple functions/curves: 
   1. Lorentzian
   2. Gaussian
   3. Voigt
   4. Trapezoidal*
6. **Linear Regression**: can use one or two peaks for obtaining linear models
7. **PLS Regression**: can create models and predict blind samples  
8. **PCA** (Principal Components Analysis): can run PCA on dataset, using RAW data or fitted data
9. **Plasma parameters**: by using the Saha-Boltzmann equation, can obtain plasma temperature (**T [K]**)
and electrons density (**Ne [cm-3]**)
10. **Save environment**: if the user wants to keep all analysis into a single file, it is possible
to save a _LIBSsa 2 environment file_ (**lb2e**). The file is a lzma-compressed pickle containing all
data loaded and processed, with about **40%** of the size of original/text spectra.  
11. **Export data**: it is also possible to export analysed data into **csv** and **xlsx** files

## Installing Python

You will need to install Python 3.x (tested on 3.5+) in order to use the program.
Python can be obtained from the official website: [https://www.python.org/](https://www.python.org/).

### 1. Linux users

If you use **Linux**, you probably already have it, as most of the distributions comes with
Python pre-installed. However, if for some reason Python 3 is not installed, you'll have to
install it (either from website) or from your distribution repositories. As an example,
for Debian-based distribution, you can use **apt** (_Advanced package tool_):

```bash
sudo apt install python3-minimal python3-pip python3-setuptools python3-wheel build-essential
```

In case of any problems, check the official documentation about [installing Python on
Unix platforms](https://docs.python.org/3/using/unix.html).

### 2. Windows users

**Windows** users may obtain Python either from [Microsoft Store](https://apps.microsoft.com/store/detail/python-39/9P7QFQMJRFP7)
(if you use Windows 8+) or downloading it from the [official website](https://www.python.org).
Also, one should not forget to mark during the installation to *ADD PYTHON TO PATH* and
to _REMOVE MAX PATH 260 LENGTH LIMIT_.

I also recommend checking the official documentation about [installing Python on
Windows platforms](https://docs.python.org/3/using/windows.html).

## External Libraries

To properly works, this program uses the following external libraries:

1. [NumPy](https://numpy.org/) (~=1.22.3)
2. [SciPy](https://scipy.org/) (~=1.8.0)
3. [Pandas](https://pandas.pydata.org/) (~=1.4.1)
4. [Scikit-Learn](https://scikit-learn.org/stable/) (~=1.1.2)
5. [PySide6](https://wiki.qt.io/Qt_for_Python) (~=6.2.3)
6. [PyQtGraph](https://pyqtgraph.readthedocs.io/en/latest/index.html) (~=0.12.4)
7. [OpenPyXL](https://openpyxl.readthedocs.io/en/stable/) (~=3.0.5)
8. [Psutil](https://github.com/giampaolo/psutil) (~=5.9.1)
9. [Markdown](https://python-markdown.github.io/) (~3.4.1)

And, besides those libraries, its dependencies as well.

### Installing external libraries

External libraries may be installed using the [PIP](https://docs.python.org/3/installing/index.html)
tool and the file _**requirements.txt**_. Just open a **terminal** or **Windows PowerShell**
and type:

```powershell
pip install -r requirements.txt --user
```

With the command above, you'll install all needed libraries in a compatible (_tested_)
version of the program. You may also install them directly, but be aware that this may lead
to **unstable behaviour**:

```powershell
pip install numpy scipy pandas scikit-learn PySide6 pyqtgraph openpyxl psutil markdown --user
```

You may also use `python -m pip install [COMMAND]` for installing libraries. Finally,
advanced users are encouraged to use [venv](https://docs.python.org/3/library/venv.html)
(Virtual Environment).

## Warranty

LIBSsa 2 is an open-source project. It is distributed in the hope that it will be
useful, but *WITHOUT ANY WARRANTY*; without even the implied warranty of *MERCHANTABILITY*
or *FITNESS FOR A PARTICULAR PURPOSE*. See the GNU Affero General Public License
version 3 attached for more details.

## Historical background

The **LIBSsa 1** was a software created in the middle of 2017 for my personal use
in a LIBS class during my doctorate. Eventually, many colleagues from the
_Optics and Photonics Laboratory_ at [Embrapa Instrumentation](https://www.embrapa.br/en/instrumentacao)
(Sao Carlos, SP, Brazil) enjoyed the application, and I continued developing it until late 2019.

Eventually, the _LIBSsa_ software became an important part of my doctorate/thesis,
so I've decided to restructure it into a new - _better_ - version. Finally, in the middle
of 2020, the development of the **LIBSsa 2** started.

---

Developed by: [Kleydson Stenio](mailto:kleydson.stenio@gmail.com?Subject=LIBSsa_2_QUESTIONS) @ 2022
