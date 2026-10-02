# Building a Text Statistics Analyzer using Python Fundamentals

A comprehensive text analysis project built using Python fundamentals and core data analysis libraries. The project analyzes the BBC News Dataset to extract statistical insights, recurring text patterns, word and character frequencies, sentence-level statistics, and visualizations.

---

## Project Overview

This project was developed as part of Assignment 1: Python Fundamentals for NLP.

The objective is to build a text analysis tool using core Python libraries such as Regex, NumPy, Pandas, and Matplotlib, without relying on specialized NLP libraries.

The project performs:

- Text data loading and exploration
- Text statistics calculation
- Regular expression-based pattern extraction
- Word frequency analysis
- Character-level analysis
- Sentence-level analysis
- Data visualization
- Pandas-based word analysis
- Export of processed results
- Exploratory analysis of the BBC News dataset

The assignment specifically focuses on implementing text processing, pattern extraction, statistical analysis, and visualization using Python fundamentals.

---

## Dataset

### BBC News Dataset

The project uses the BBC News Dataset, containing 2,225 news articles across five categories:

- Business
- Entertainment
- Politics
- Sport
- Technology

The dataset contains BBC news stories from 2004–2005.

### Dataset Structure

```text
bbc/
├── business/
├── entertainment/
├── politics/
├── sport/
└── tech/
```

Each category contains multiple .txt files representing individual news articles.

---

## Technologies Used

| Technology | Purpose |
| ---------- | ------- |
| Python | Core programming and text processing |
| Regular Expressions (`re`) | Pattern extraction |
| NumPy | Numerical and statistical analysis |
| Pandas | Data manipulation and analysis |
| Matplotlib | Data visualization |
| pathlib | File and directory handling |
| json | Exporting extracted patterns |
| collections | Frequency analysis |

No specialized NLP libraries such as NLTK, spaCy, or TextBlob were used.

---

## Project Workflow

```text
BBC News Dataset
       ↓
Load Text Files
       ↓
Text Cleaning & Preprocessing
       ↓
Basic Text Statistics
       ↓
Regex Pattern Extraction
       ↓
Word & Character Analysis
       ↓
Sentence Analysis
       ↓
Statistical Analysis with NumPy
       ↓
Data Analysis with Pandas
       ↓
Matplotlib Visualizations
       ↓
Export Results
       ↓
Analysis Report
```

---

## Project Components

### 1. Data Loading and Exploration

The first stage loads all BBC news articles using Python file I/O.

The following statistics were calculated for the complete dataset:

- Total number of documents
- Total characters
- Total words
- Total sentences
- Average word length
- Average sentence length
- Word count per document
- Character count per document

A Pandas DataFrame was also created to store document-level statistics.

### Dataset Statistics

| Metric | Value |
| ------ | -----: |
| Documents | 2,225 |
| Characters | 5,039,982 |
| Words | 855,598 |
| Sentences | 44,468 |
| Average Word Length | 4.66 |
| Average Sentence Length | 19.24 |

The document-level statistics were exported to:

```text
document_statistics.csv
```

---

### 2. Regular Expression Pattern Extraction

Regular expressions were used to identify different patterns in the complete dataset.

The following patterns were analyzed:

- Email addresses
- Phone numbers
- Hashtags
- Mentions
- URLs
- Domains
- Dates
- Currency values

### Extracted Pattern Summary

| Pattern | Occurrences | Unique |
| ------- | ----------: | -----: |
| Emails | 0 | 0 |
| Phone Numbers | 0 | 0 |
| Hashtags | 30 | 6 |
| Mentions | 0 | 0 |
| URLs | 3 | 2 |
| Dates | 2 | 1 |
| Currencies | 1,543 | 550 |

The extracted results were exported to:

```text
extracted_patterns.json
```

### Example URL Domains

```text
dec.org.uk
arsenal.com
```

The absence of emails, phone numbers, and mentions is expected because the dataset consists of news articles rather than social-media-oriented text.

---

### 3. Text Statistics

#### Word Frequency Analysis

A frequency dictionary was created for the words present in the complete dataset.

The most frequently occurring words include:

| Word | Frequency |
| ---- | --------: |
| the | 52,636 |
| to | 25,113 |
| of | 20,008 |
| and | 18,611 |
| a | 18,323 |
| in | 17,725 |
| s | 9,070 |
| for | 8,945 |
| is | 8,555 |
| that | 8,257 |

The frequency values were converted into NumPy arrays for statistical analysis.

Statistical measures such as mean, median, standard deviation, 25th percentile, 50th percentile, and 75th percentile were calculated for word frequencies.

#### Character-Level Analysis

Character frequency distribution was calculated across the complete dataset.

The most frequently occurring alphabetic characters included:

```text
e
t
a
o
i
n
s
r
```

The analysis also calculated:

- Most common character
- Least common character
- Vowel count
- Consonant count
- Vowel-to-consonant ratio

The most common character in the dataset was:

```text
e
```

#### Sentence-Level Analysis

Regular expressions were used to split the text into sentences.

Sentence lengths were then analyzed to determine:

- Average sentence length
- Median sentence length
- Sentence length distribution
- Longest sentence
- Shortest sentence
- Outliers

A box plot was used to visualize the sentence length distribution and identify unusually long sentences.

---

## Data Visualizations

The project contains more than the required minimum of seven visualizations.

All plots are stored inside the `plots/` directory.

### Visualizations Created

#### 1. Top 20 Most Frequent Words

A horizontal bar chart showing the 20 most frequently occurring words.

```text
plots/top_20_words.png
```

#### 2. Word Length Distribution

A histogram showing the distribution of word lengths along with a normal distribution curve.

```text
plots/word_length_distribution.png
```

#### 3. Top 15 Characters

A bar chart showing the most frequently occurring characters while excluding spaces.

```text
plots/top_15_characters.png
```

#### 4. Letter Frequency

A visualization showing the frequency distribution of alphabetic characters.

```text
plots/letter_frequency.png
```

#### 5. Punctuation Frequency

A visualization showing the frequency of punctuation characters.

```text
plots/punctuation_frequency.png
```

#### 6. Sentence Length Box Plot

A box plot showing sentence-length distribution and potential outliers.

```text
plots/sentence_length_boxplot.png
```

#### 7. 2×2 Analysis Dashboard

A combined dashboard containing multiple key text statistics.

```text
plots/text_analysis_dashboard.png
```

#### 8. Category-Wise Average Document Length

A custom visualization comparing average document length across BBC news categories.

Average words per document:

| Category | Average Words |
| -------- | ------------: |
| Technology | 504 |
| Politics | 455 |
| Sport | 333 |
| Entertainment | 332 |
| Business | 324 |

This visualization provides a category-level comparison of article length.

---

## Pandas Data Analysis

A word-level DataFrame was created with each unique word as the index.

### DataFrame Structure

| Column | Description |
| ------ | ----------- |
| `frequency` | Number of times the word occurs |
| `length` | Number of characters in the word |
| `first_char` | First character of the word |
| `vowel_count` | Number of vowels in the word |

Example structure:

```text
              frequency  length  first_char  vowel_count
word
the              52636       3       t           1
to               25113       2       t           1
of               20008       2       o           1
and              18611       3       a           1
```

The following Pandas operations were performed:

- Grouping by word length
- Grouping by first character
- Sorting by frequency
- Extracting the top 50 words
- Filtering words longer than 10 characters
- Pivot tables
- Cross-tabulations

---

## Output Files

The project generates the following output files:

```text
document_statistics.csv
extracted_patterns.json
cleaned_text.txt
final_analysis_summary.csv
```

### `document_statistics.csv`

Contains document-level statistics such as:

- Document ID
- Filename
- Category
- Word count
- Character count

### `extracted_patterns.json`

Contains extracted:

- Emails
- Phone numbers
- Hashtags
- Mentions
- URLs
- Domains
- Dates
- Currency values

### `cleaned_text.txt`

Contains the processed text generated during the analysis.

### `final_analysis_summary.csv`

Contains consolidated analysis results and summary information.

---

## Project Structure

```text
text-statistics-analyzer/
│
├── data/
│   └── bbc/
│       ├── business/
│       ├── entertainment/
│       ├── politics/
│       ├── sport/
│       └── tech/
│
├── plots/
│   ├── top_20_words.png
│   ├── word_length_distribution.png
│   ├── top_15_characters.png
│   ├── letter_frequency.png
│   ├── punctuation_frequency.png
│   ├── sentence_length_boxplot.png
│   ├── text_analysis_dashboard.png
│   └── category_average_document_length.png
│
├── document_statistics.csv
├── extracted_patterns.json
├── cleaned_text.txt
├── final_analysis_summary.csv
│
├── text_statistics_analyzer.ipynb
├── README.md
└── analysis_report.pdf
```

> The exact filenames may vary depending on the final notebook/output naming.

---

## Key Findings

### Word Usage

Common English function words such as `the`, `to`, `of`, `and`, `a`, and `in` dominate the frequency distribution.

This is expected in a large collection of English news articles because function words occur frequently across different topics.

### Character Usage

The character `e` was the most frequently occurring alphabetic character.

The character-level distribution shows that common English letter-frequency patterns are reflected in the BBC news corpus.

### Article Length

The average article length differs between categories.

The Technology and Politics categories contain longer articles on average, while Business and Entertainment articles are shorter in comparison.

### Pattern Extraction

Currency values were the most frequently detected special pattern, with 1,543 occurrences.

URLs, dates, and hashtags were detected in relatively small numbers.

Emails, phone numbers, and mentions were not found in the dataset.

### Vocabulary

The dataset contains a large number of unique words, indicating substantial vocabulary variation across the five news categories.

Word frequency analysis also demonstrates a typical long-tail distribution where a small number of words occur very frequently while many words occur relatively rarely.

### Zipf's Law

The word-frequency distribution shows the expected general behavior of natural language: a small number of words have very high frequencies, while a large number of words have relatively low frequencies.

This is consistent with the general pattern described by Zipf's law.

---

## Challenges Faced

### 1. Handling Multiple Text Files

The dataset contains thousands of individual .txt files.

Solution: Python file I/O and pathlib were used to systematically traverse the category folders and process all documents.

### 2. Sentence Splitting

Sentence boundaries are more complex than simply splitting on periods because punctuation can appear in abbreviations and other contexts.

Solution: Regular expressions were used to perform sentence splitting instead of relying only on a simple `.` delimiter.

### 3. Regex Pattern Variations

Different patterns such as URLs, dates, currencies, and hashtags can appear in different formats.

Solution: Custom regular expressions were designed for each required pattern and applied across the complete corpus.

### 4. Large Frequency Distributions

The dataset contains hundreds of thousands of word occurrences and millions of characters.

Solution: Python dictionaries, collections, NumPy arrays, and Pandas DataFrames were used to efficiently organize and analyze the frequency data.

---

## Project Type

This project can be classified as:

**Text/NLP Exploratory Data Analysis (EDA)**

It combines:

- Text data exploration
- Statistical analysis
- Pattern extraction
- Feature analysis
- Data visualization
- Document-level analysis
- Word-level analysis

The project is primarily an EDA project for textual data, while also serving as a foundation for further NLP tasks.

---

## Future Improvements

Possible extensions to this project include:

- Zipf's law visualization
- N-gram extraction
- Bigram and trigram analysis
- Sentiment keyword analysis
- Interactive dashboard
- Topic-based comparison
- TF-IDF analysis
- Text classification
- Word embeddings
- Advanced NLP preprocessing

These extensions can be added as future NLP projects building on this text-analysis foundation.

---

## Assignment Deliverables

The project fulfills the major assignment components:

- [x] Text data loading
- [x] File I/O
- [x] Text statistics
- [x] Document-level Pandas DataFrame
- [x] CSV export
- [x] Email extraction
- [x] Phone number extraction
- [x] Hashtag extraction
- [x] Mention extraction
- [x] URL extraction
- [x] Domain categorization
- [x] Date extraction
- [x] Currency extraction
- [x] Word frequency analysis
- [x] NumPy statistical analysis
- [x] Character-level analysis
- [x] Sentence analysis
- [x] Word-frequency visualization
- [x] Word-length histogram
- [x] Character visualizations
- [x] Sentence-length box plot
- [x] 2×2 dashboard
- [x] Custom visualization
- [x] Pandas groupby analysis
- [x] Top 50 word analysis
- [x] Long-word filtering
- [x] Pivot tables
- [x] Cross-tabulations
- [x] CSV output
- [x] JSON output
- [x] Cleaned text output
- [x] Analysis report

---

## Reference

### Dataset

BBC News Dataset containing 2,225 documents across five categories:

- Business
- Entertainment
- Politics
- Sport
- Technology

Dataset period: 2004–2005

### Assignment

**Assignment 1: Python Fundamentals for NLP**

**Title:** Building a Text Statistics Analyzer using Python Fundamentals

The assignment requires text processing, regex-based pattern extraction, NumPy statistical analysis, Matplotlib visualizations, Pandas analysis, and an analysis report.

---

## Author

**Srinidhi M D**

B.Tech – Computer Science and Engineering

---

## Project Summary

> Building a Text Statistics Analyzer using Python Fundamentals is a text-based exploratory data analysis project that analyzes 2,225 BBC News articles using Python, Regular Expressions, NumPy, Pandas, and Matplotlib. The project extracts textual patterns, calculates word, character, and sentence statistics, performs document and word-level analysis, and presents the findings through multiple visualizations and exported analytical results.

---

## GitHub Details

**Repository name:**
```text
text-statistics-analyzer
```

**Short description:**
```text
Python-based text statistics analyzer for BBC News articles using Regex, NumPy, Pandas, and Matplotlib.
```

**Topics/tags you can add on GitHub:**
```text
nlp
text-analysis
eda
exploratory-data-analysis
bbc-news
numpy
pandas
matplotlib
regex
data-analysis
natural-language-processing
```

The README structure follows the assignment's actual title, required components, outputs, visualization requirements, and analysis-report requirements.
