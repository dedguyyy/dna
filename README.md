# DNA Sequence Analyzer

This project is a command-line Python application that identifies individuals based on their DNA sequence. It compares a given DNA sequence against a database of individuals and their Short Tandem Repeat (STR) counts to find a matching profile.

## Features

- Reads a DNA database (CSV format) containing names and STR counts for each individual.
- Reads a DNA sequence file (text format).
- Calculates the longest run of each STR in the DNA sequence.
- Compares the STR counts from the sequence to each profile in the database.
- Prints the name of the matching individual, or "No match" if there is no match.

## How It Works

1. **Input**
    - The program expects two command-line arguments:
        1. The path to the DNA database CSV file.
        2. The path to the DNA sequence text file.

2. **Processing**
    - The database is read into a list of dictionaries.
    - The DNA sequence is read as a string.
    - For each STR in the database, the program computes the longest consecutive run in the DNA sequence.
    - The computed STR counts are compared to each individual's profile in the database.

3. **Output**
    - If a profile matches all STR counts exactly, the individual's name is printed.
    - If no profile matches, "No match" is printed.

## Usage

```sh
python dna.py database.csv sequence.txt
```

- `database.csv`: CSV file with a header row (name, STR1, STR2, ...) and rows for each individual.
- `sequence.txt`: Text file containing the DNA sequence to analyze.

## Example

**database.csv**
```
name,AGAT,AATG,TATC
Alice,2,8,3
Bob,4,1,5
Charlie,3,2,5
```

**sequence.txt**
```
AAGGTAAGTTTAGATAGATAGATAATGAATGTATCTATCTATC
```

**Command**
```sh
python dna.py database.csv sequence.txt
```

**Output**
```
Alice
```

## File Structure

- `dna.py` — Main Python script for DNA analysis.

## Requirements

- Python 3.x

## Notes

- The program assumes the database and sequence files are properly formatted.
- STRs and their counts must match exactly for a profile to
