
# DNA Sequence Analysis in R

## Introduction
This R program analyzes a DNA sequence by performing various tasks, including calculating nucleotide frequencies by kilobase, generating a reverse complement of the sequence, and analyzing the nucleotide distribution. This program is written in R and utilizes packages such as `seqinr` and `R.utils` to handle sequence data efficiently.

## Requirements
To run this program, you will need the following R packages:

- `seqinr`: For handling nucleotide sequences, reading FASTA files, and generating complementary sequences.
- `R.utils`: For handling compressed `.gz` files.

Install the required packages using the following commands:

```R
install.packages("seqinr")
install.packages("R.utils")
```

## Usage
The code in this program is structured in R Markdown and divided into several parts, each addressing a specific step in the DNA sequence analysis. Below is an outline of each part.

### Part 1: Loading the Sequence
This section loads and reads the DNA sequence file, which is in FASTA format and compressed as `.gz`. The program decompresses the file and reads the sequence for further processing.

### Part 2: Generating the Reverse Complement
This part generates the reverse complement of the DNA sequence. It reverses the sequence and replaces each nucleotide with its complementary base (A ↔ T, C ↔ G). The program also extracts specific letters from the reverse complement:
- **79th letter**: Prints the 79th letter in the reverse complement.
- **500th to 800th letters**: Prints the nucleotide sequence from positions 500 to 800 in the reverse complement.

### Part 3: Nucleotide Frequency by Kilobase
This section counts the occurrence of each nucleotide (A, T, C, G) in each 1000-base segment (kilobase) of the DNA sequence. The result is stored in a list where each element represents a kilobase with the nucleotide counts.

### Part 4: Data Frame and Analysis
The nucleotide frequency data is transformed into a data frame for easier analysis.

#### Part 4a
Creates a data frame with four columns representing the nucleotide counts (A, C, G, T) for the first 1000 base pairs.

#### Part 4b
Repeats the step from Part 4a for each kilobase in the sequence, storing the data in a single data frame where each row represents a kilobase.

#### Part 4c
Each row in the data frame is generated from individual list entries, representing each kilobase’s nucleotide counts.

#### Part 4d
Calculates the sum of nucleotide counts for each kilobase. The expected sum is 1000, as each kilobase should contain 1000 base pairs. 

#### Part 4e
Analyzes the data to identify any kilobases with sums that differ from the expected value. A discrepancy indicates that the final kilobase in the sequence is shorter than 1000 bases, as is often the case when a sequence length is not an exact multiple of 1000.

## Explanation and Expected Results

- **Expected Sum**: Each kilobase should contain 1000 bases, so the sum for each row is expected to be 1000.
- **Observed Discrepancies**: The final kilobase may have fewer than 1000 bases if the sequence length isn’t a perfect multiple of 1000. This discrepancy is natural and does not indicate an error.
- **General Explanation**: Any differences in expected vs. observed values for the sum indicate that the last segment of the DNA sequence is shorter than a full kilobase, which is typical in DNA analysis.
