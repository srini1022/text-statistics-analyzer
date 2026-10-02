# Final Analysis Report

## 1. Introduction

This project developed a Text Statistics Analyzer using Python fundamentals and core libraries including Regular Expressions, NumPy, Pandas, and Matplotlib. The BBC News dataset was used for the analysis, containing news articles from five categories: business, entertainment, politics, sport, and technology.

The analysis was performed on the complete dataset rather than on a sample. The project covers text loading and exploration, regular expression pattern extraction, statistical analysis, visualization, and word-level analysis.

## 2. Dataset and Summary Statistics

A total of 2,225 BBC News documents were analyzed. The dataset contains approximately 5.04 million characters, 855,598 words, and 44,468 sentences.

The average word length was approximately 4.66 characters, while the average sentence length was approximately 19.24 words. These statistics provide an overall view of the structure and complexity of the news articles.

The document-level statistics were stored in a Pandas DataFrame and exported to `document_statistics.csv`.

## 3. Pattern Extraction Findings

Regular expressions were used to identify emails, phone numbers, hashtags, mentions, URLs, dates, and currency values.

The dataset contained no email addresses, phone numbers, or mentions. A small number of hashtag-like patterns were detected. URL extraction identified URLs such as `www.arsenal.com` and `www.dec.org.uk`.

Date extraction identified occurrences of dates such as `May 19, 2006`. Currency extraction produced the largest number of matches, with 1,543 occurrences and 550 unique currency values.

These results show that financial values occur frequently in the BBC articles, particularly because several articles discuss business and economic topics.

## 4. Word Frequency Analysis

The word-frequency analysis showed that common English function words dominate the highest-frequency positions. The most frequent word in the dataset was `the`, followed by `to`, `of`, `and`, and `a`.

These words are grammatically important but generally carry limited topic-specific information. Their high frequency is expected in English text because they are used to construct sentences rather than describe particular subjects.

The word-frequency distribution is highly uneven: a small number of words occur very frequently while a large number of words occur relatively rarely. This pattern is consistent with the general behavior expected from natural language and can be further examined using Zipf's law.

## 5. Character-Level Analysis

The character-level analysis showed that alphabetic characters dominate the text. Among the most frequent letters, `e`, `t`, and `a` appeared prominently.

The vowel-to-consonant analysis also demonstrated that consonants occur more frequently than vowels in the complete dataset. Character-level analysis is useful because it provides a basic understanding of the linguistic structure of the corpus without requiring specialized NLP libraries.

The character-frequency visualization clearly showed the difference between highly frequent letters and less frequent characters.

## 6. Word-Length and Sentence-Length Analysis

The word-length histogram showed that shorter words occur much more frequently than long words. Most words were concentrated in the lower word-length range, while very long words occurred less frequently.

The normal distribution curve was added for comparison. The actual word-length distribution is not perfectly normal and has a noticeable right-skew because a smaller number of long words extend the distribution.

Sentence-length analysis showed that most sentences fall within a relatively compact range, while a number of longer sentences appeared as statistical outliers. The box plot clearly identified these observations.

These outliers do not necessarily represent errors. They can result from long news sentences containing multiple clauses, quotations, or detailed descriptions.

## 7. Category-Level Analysis

The category-level visualization showed differences in average document length across the five BBC categories.

The average word counts obtained from the analysis were approximately:

- Technology: 504 words per document
- Politics: 455 words per document
- Sport: 333 words per document
- Entertainment: 332 words per document
- Business: 324 words per document

This indicates that article length varies across topics in the dataset.

## 8. Vocabulary Analysis

The Pandas word-level DataFrame contained each unique word along with its frequency, length, first character, and vowel count.

Grouping by word length made it possible to examine how frequency changes as words become longer. Grouping by first character showed how the vocabulary is distributed according to starting letters.

The analysis also identified the top 50 words and words longer than 10 characters. Pivot tables and cross-tabulations were used to examine the relationship between word length and first character.

## 9. Interesting Patterns and Anomalies

Several patterns were observed during the analysis.

First, a small number of common words account for a large portion of total word usage. Second, shorter words are considerably more common than longer words. Third, sentence lengths contain several outliers, including some exceptionally long sentences.

The category analysis also showed that the average article length differs between BBC news categories.

The extracted currency values were particularly numerous compared with other custom patterns. This reflects the presence of financial amounts throughout the news corpus.

## 10. Challenges and Solutions

One challenge was handling a large number of text files consistently. This was addressed by using Python's `pathlib` and file I/O operations to process the complete BBC dataset.

Another challenge was handling different text encodings. UTF-8 was used as the primary encoding with appropriate handling when reading the files.

Regular expression extraction also required careful pattern design because different types of information have different formats. Separate patterns were used for emails, phone numbers, URLs, dates, hashtags, mentions, and currency values.

Sentence splitting was another challenge because punctuation can occur in different contexts. A regular-expression-based approach was therefore used to identify sentence boundaries.

Finally, visualization of a large corpus required aggregation of the raw text into meaningful statistics such as word frequency, character frequency, sentence length, and category-level averages.

## 11. Conclusion

The Text Statistics Analyzer successfully processed the complete BBC News dataset using Python fundamentals. The project demonstrated how Regular Expressions, NumPy, Pandas, and Matplotlib can be combined to perform meaningful text analysis without relying on specialized NLP libraries.

The analysis provided insights into word usage, character distributions, sentence structure, document length, vocabulary characteristics, and recurring text patterns. The generated CSV, JSON, cleaned text file, statistical tables, and visualizations provide reusable outputs for further NLP analysis.