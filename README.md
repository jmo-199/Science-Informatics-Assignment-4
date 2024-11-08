# DNA Sequence Analysis in R

## Identifying Information
  - **Programmer**: Jason Moore
  - **Language**: R (R Markdown format)
  - **Version**: 1.0
  - **Date Submitted**: 11/10/2024
  - **Description**: This R program analyzes a DNA sequence by performing various tasks including calculating nucleotide frequencies by kilobase, generating a reverse complement of the sequence, and analyzing the nucleotide distribution. It handles sequence data stored in a compressed FASTA format and generates outputs to facilitate further biological analysis.

## Required Files
- **DNA Sequence File**: This program requires a DNA sequence in FASTA format, compressed as a `.gz` file (e.g., `chr1_GL383518v1_alt.fa.gz`).

## Required Libraries/Packages/Software
- **seqinr**: For handling nucleotide sequences, reading FASTA files, and generating complementary sequences.
- **R.utils**: For handling compressed `.gz` files.
  
Install these packages in R with the following commands:
```R
install.packages("seqinr")
install.packages("R.utils")
```

## Instructions for Running the Script
1. **Download the Sequence File**: Place the compressed DNA sequence file in the appropriate directory.
2. **Open the R Markdown File**: Load the R Markdown file containing this program.
3. **Run Each Code Block**: Execute each code block in sequence within R or RStudio to complete the analysis.
4. **Verify Output**: Review the outputs displayed in the console and data frames generated in each part for nucleotide counts, sums, and sequence information.

## Files Created During Script Execution
- **Data Frames**: Multiple data frames are created to store nucleotide counts and reverse complements. These can be reviewed within the R environment for detailed analysis.
- **Reverse Complement Output**: The reverse complement of the sequence is generated and specific positions are extracted.
- **Kilobase Nucleotide Counts**: Counts of each nucleotide are calculated per kilobase, stored in a structured format for further review.

## Program Output and Analysis

1. **Reverse Complement Generation**: The reverse complement of the sequence is calculated. Specific letters are extracted to validate the sequence:
   - 79th letter
   - 500th to 800th letters

2. **Nucleotide Frequency by Kilobase**: Nucleotide counts for each kilobase (1000-base segment) are stored in a list, which is converted into a data frame. Each row represents one kilobase with counts for A, C, G, and T.

3. **Data Summation and Analysis**:
   - The program calculates the sum of each kilobase’s nucleotide counts, with an expected sum of 1000.
   - Any discrepancies in row sums are flagged and explained as sequences that do not reach a full 1000 bases, typically occurring in the last kilobase if the sequence length is not a multiple of 1000.
