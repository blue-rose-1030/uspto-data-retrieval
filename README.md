# Access USPTO data in Rectangular Format

## Overview

This package allows easy access to USPTO (United States Patent and Trademark Office) bulk patent data in rectangular format. By downloading, converting, and storing patent data directly from the USPTO website, patentpy minimizes the work needed to acquire usable data, allowing users to focus on analyzing the data.

## Installation

Note: This package utilizes pybind11 to wrap a custom txt parser written in C++ code, lxml to parse xml files, and pandas for the option of presenting uspto bulk data as a dataframe.

## Sample code

Bulk patent data in TXT or XML format (1976+) can be downloaded using the year and week (within each year) as follows:

```python
# import get_bulk_patent_data functionality
from patentpy.acquire import get_bulk_patent_data


# download patents from the first week of 2024 and get data frame
patent_data = get_bulk_patent_data(year = 2020, week = 1)

# download patents from the last 5 weeks of 1980
# and store in a CSV file named "patent-data.csv"
# Note: uspto patent data is reported on Tuesdays and 1980
# has 53 Tuesdays, hence, 53 weeks worth of data
get_bulk_patent_data(year = [2020] * 5, week = [i for i in range(49,54)], output_file = "patent-data.csv")
```

## Functionality

### Data collected for each patent

* unique identifier (patent number - WKU)
* application date
* patent issue date
* patent title
* inventor name(s)
* assignee name(s)
* ICL classification (IPC or Locarno)
* referenced patent numbers
* claims

## Contribute

To contribute to patentpy, you can create issues for any bugs/suggestions on the [issues page](https://github.com/JYProjs/patentpy/issues).
You can also fork the patentpy repository and create pull requests to add features you think will be useful for users.