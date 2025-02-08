# aganitha_python_assignment

# PubMed Research Paper Fetcher

This Python program fetches research papers from PubMed based on a user-specified query, identifies papers with at least one author affiliated with a pharmaceutical or biotech company, and returns the results in a CSV file format.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
  - [Command-line Options](#command-line-options)
- [Code Organization](#code-organization)
- [External Tools and Libraries](#external-tools-and-libraries)
- [How to Contribute](#how-to-contribute)
- [License](#license)

## Overview

The program interacts with PubMed's API to fetch research papers based on the provided search query. It then filters papers to identify those with at least one non-academic author or one author affiliated with a pharmaceutical or biotech company. The results are saved in a CSV file, which can be specified by the user.

### Features

- Fetches research papers from PubMed using its full query syntax.
- Filters papers based on non-academic authors or authors affiliated with pharmaceutical/biotech companies.
- Returns results in CSV format with the following columns:
  - `PubmedID`: Unique identifier for the paper.
  - `Title`: Title of the paper.
  - `Publication Date`: Date the paper was published.
  - `Non-academic Author(s)`: Names of authors affiliated with non-academic institutions.
  - `Company Affiliation(s)`: Names of pharmaceutical/biotech companies.
  - `Corresponding Author Email(s)`: Corresponding author's email address.

## Installation

To install the required dependencies and set up the project, follow these steps:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/pubmed-fetcher.git
   cd pubmed-fetcher

2. **Install Poetry**

    If you don't have Poetry installed, you can follow the installation guide [here](https://python-poetry.org/).
    
    To install Poetry, run:
    
    ```bash
    curl -sSL [https://install.python-poetry.org](https://install.python-poetry.org) | python3 -
    ````

3. **Install dependencies using Poetry**

    Inside the project directory, run:
    
    ```bash
    poetry install
    ```

This will set up all the required dependencies specified in `pyproject.toml`.

## Usage

### Command-line Options

The program supports the following command-line options:

  * `-h` or `--help`: Display usage instructions.
  * `-d` or `--debug`: Enable debug mode, printing additional information about the execution process.
  * `-f` or `--file`: Specify the filename where the results should be saved. If this option is not provided, the output will be printed to the console.

### Example Usage

1. Fetch papers based on a query and print the results to the console:

```bash
poetry run get-papers-list "machine learning"
```

2. Fetch papers and save the results to a CSV file:

```bash
poetry run get-papers-list "machine learning" -f results.csv
```

3. Enable debug mode to print additional information:

```bash
poetry run get-papers-list "machine learning" -d
```

### Example Output

When the program runs, it will either save the results to a CSV file or print the following structure to the console:

```
Retrieved Paper Details['PubMed ID', 'Title', 'Publication Date', 'Non-academic Author(s)', 'Company Affiliation(s)', 'Corresponding Author Email(s)']
['12345678', 'Machine Learning in Healthcare', '2025-02-01', 'Dr. John Doe', 'XYZ Biotech', 'john.doe@xyz.com']
...
```

## Code Organization

The code is organized into the following components:

1.  **`PubMedFetcher` Class:** Responsible for fetching PubMed IDs based on a search query and retrieving the corresponding paper details in batches.
2.  **`PubMedParser` Class:** Responsible for parsing the retrieved XML data, extracting relevant paper metadata (such as authors, publication date, and company affiliations).
3.  **`CSVWriter` Class:** Responsible for saving the parsed paper metadata into a CSV file.
4.  **Main Script:** The script that handles command-line arguments and ties everything together.

## External Tools and Libraries

  * **Requests:** Used for making HTTP requests to the PubMed API. [Requests Documentation](https://www.google.com/url?sa=E&source=gmail&q=https://docs.python-requests.org/en/latest/)
  * **ElementTree (`xml.etree.ElementTree`):** Used for parsing XML data returned by the PubMed API.
  * **Poetry:** Used for dependency management and packaging. [Poetry Documentation](https://python-poetry.org/)
  * **CSV Module:** Used to write the results to a CSV file.

## How to Contribute

Contributions to this project are welcome\! To contribute:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes.
4.  Open a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
```

