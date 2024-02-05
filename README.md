# 2023 PainMonit Database (PMDB)

## Description
This repository summarises the code made public available for the PainMonit Database (PMDB) publication.

The database has two parts, the heat-based PainMonit Heat Database ([PMHDB][PMHDB_link]) and the physiotherapy based PainMonit Physiotherapy Database ([PMPDB][PMPDB_link]). The code for the former can be found under the directory [PMHDB/](PMHDB/), for the latter under directory [PMPDB/](PMPDB/).

A more detailed description of the database can be found in the paper '**The PainMonit Database: Experimental and Clinical Physiological Signal Data for Automated Pain Recognition**' published in *Scientific Data* can be found under following [link][paper_link].

## How to use this repository
- Clone the project
    ```bash 
    git clone https://github.com/gouverneurp/PMDB
    ```

- Install Python (tested under [Python 3.12](https://www.python.org/downloads/release/python-3120/)).

- Create a Python environment and activate it. 
    Windows:
    ```bash
    python -m venv venv
    .\venv\Scripts\activate
    ```
    Linux:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

- Install the requirements
    ```bash 
    pip install -r requirements.txt
    ```

## How to use the PMHDB
- Go to the subdirectory [PMHDB](PMHDB/)
    ```bash 
    cd PMHDB
    ```

- Place the PMHDB dataset (available under [link][PMHDB_link]) in the subdirectory [dataset](PMHDB/dataset/) following the description in the [README](PMHDB/dataset/README.md) file there.

- Run [create_np_files.py](PMHDB/create_np_files.py) to create a segmented dataset for machine learning. A numpy dataset composed of three files (_X.npy_, _y.npy_ and _subjects.npy_) will be generated.
    ```bash
    python create_np_files.py
    ```

- After creating the segmented dataset, a Machine Learning pipeline can be applied. An example of such can be found in the following paper '[Explainable Artificial Intelligence (XAI) in Pain Research: Understanding the Role of Electrodermal Activity for Automated Pain Recognition](https://www.mdpi.com/1424-8220/23/4/1959)'. The code is available on [GitHub](https://github.com/gouverneurp/XAIinPainResearch) as well.

- If you want to read in the original raw data files, you can do so in Python with the following code:
    ```python 
    pd.read_csv(filename, sep=";", decimal=",")
    ```
    where _filename_ is the path to the file of one subject.
    Functions on how to read in the data can be found in the [read_data.py](PMHDB/read_data.py) script.

- Functions on how the heater signal was cleaned can be found in the [heater.py](PMHDB/heater.py) script.

## How to use the PMPDB
- Go to the according subdirectory [PMPDB](PMPDB/)
    ```bash 
    cd PMPDB
    ```
- Place the PMPDB dataset (available under [link][PMPDB_link]) in the directories under [dataset](PMPDB/dataset/) following the description in the [README](PMPDB/dataset/README.md) file there.

- Run [create_np_files.py](PMPDB/create_np_files.py) to create a segmented dataset for machine learning. A Numpy dataset composed of three files (_X.npy_, _y\_heater.npy_, _y\_covas.npy_ and _subjects.npy_) will be generated.
    ```bash
    python create_np_files.py
    ```

- If you want to want to read in the original raw data files, you can do so by using the functions in the [read_data.py](PMPDB/read_data.py) script:
    ```python 
    python PMPDB/read_data.py
    ```

## Please cite our paper if you use the PMDB or our code
Bibtex entry:
```bibtex
TODO: add the Bibtex entry after publication
```

__TODO: update links to the to the paper and datasets, eventually__

[PMHDB_link]: https://github.com/gouverneurp/PMDB
[PMPDB_link]: https://github.com/gouverneurp/PMDB
[paper_link]: https://github.com/gouverneurp/PMDB
