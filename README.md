# Construct New Company-Level Database of Meaningful Patent Transfers with Company Permnos via Textual Analysis and NLP

<details>
<summary><strong><em>Table of Contents</em></strong></summary>

- [Overview](#overview)
  - [Parse XML Format of USPTO Patent Transfers](#parse-xml-format-of-uspto-patent-transfers)
  - [Determine Not Meaningful Patent Transfers](#determine-not-meaningful-patent-transfers)
  - [Preprocess Company Names](#preprocess-company-names)
  - [Texutal Analysis to Improve the Accuracy of Fuzzy Matching Company Names](#texutal-analysis-to-improve-the-accuracy-of-fuzzy-matching-company-names)
  - [Develop Parallelizations to Speed Up Codes](#develop-parallelizations-to-speed-up-codes)
- [Acknowledgement](#acknowledgement)

</details>

# Overview

## Parse XML Format of USPTO Patent Transfers
The XML format of raw USPTO patent transfers data at the patent property level is parsed into the CSV format of patent transfers at the patent transfer level. 

Note that multiple patent transfers of one patent property may be updated at the same date. Thus, the date + patent id cannot uniquely identify each patent transfer. 

## Determine Not Meaningful Patent Transfers 
Textual Analysis and Regular Expressions are developed in Python to determine not meaningful patent transfers.

Not Meaningful Patent Transfers:
* Transfers from inventors to their companies: Develop Textual analysis and regular expressions to identify whether the name is a company name or a person name
* Transfers across subsidiaries of companies: Compare similarities of addresses between patent assignors and assignees to identify this internal transfer

## Preprocess Company Names
Company names are preprocessed and standardized to improve the number of exact matching company names.
* Remove meaningless symbols in company names and trailing spaces
* Convert abbreviations to full names for standardization
* Drop company attributes and stop words

## Textual Analysis to Improve the Accuracy of Fuzzy Matching Company Names
* Extract unique company identifiers out of company names 
* Develop special algorithm for fuzzy matching short company names 

## Develop Parallelizations to Speed Up Codes
All codes are speeded up by parallelizing operations of Pandas DataFrame and Numpy Arrays.

# Acknowledgement
USPTO Patents Assignments Database https://www.google.com/googlebooks/uspto-patents-assignments.html
