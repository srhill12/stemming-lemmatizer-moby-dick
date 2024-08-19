
# Text Processing with NLTK: Moby Dick Analysis

This project demonstrates how to preprocess a text corpus using Natural Language Processing (NLP) techniques provided by the Natural Language Toolkit (NLTK). Specifically, the project focuses on processing the text of Herman Melville's *Moby Dick*, extracted from the Gutenberg corpus. The main tasks include tokenizing, lemmatizing, and stemming the text, as well as extracting specific portions of the text using regular expressions.

## Project Structure

- **Main Script**: The script imports necessary libraries, reads the text of *Moby Dick*, processes the text, and outputs the results.
- **Text Processing Techniques**:
  - **Lemmatization**: Reducing words to their base or root form using the WordNet Lemmatizer.
  - **Stemming**: Reducing words to their root form using the Snowball Stemmer.
  - **Tokenization**: Breaking the text into individual words.
  - **Text Extraction**: Using regular expressions to extract specific sections of the text.

## Requirements

- **Python 3.x**
- **NLTK**: The Natural Language Toolkit is required for text processing. Install it using pip:
  ```bash
  pip install nltk
  ```

## Setup

Before running the script, ensure that you have the required NLTK data packages. The script will download them if they are not already installed:

```python
import nltk
nltk.download('punkt')
nltk.download('wordnet')
```

## Usage

1. **Lemmatization**:
   - The `WordNetLemmatizer` is used to reduce words to their base or root form.
   - Example:
     ```python
     lemmatizer = WordNetLemmatizer()
     ```

2. **Stemming**:
   - The `SnowballStemmer` is used to reduce words to their root form.
   - Example:
     ```python
     s_stemmer = SnowballStemmer(language='english')
     ```

3. **Reading the Text**:
   - The text of *Moby Dick* is loaded from the Gutenberg corpus.
   - Example:
     ```python
     book = gutenberg.raw(fileids=('melville-moby_dick.txt'))
     ```

4. **Text Extraction**:
   - A regular expression is used to extract all the text starting from "CHAPTER 1" in the novel.
   - Example:
     ```python
     match = re.search(r'CHAPTER 1.*', book, re.DOTALL)
     if match:
         moby_dick = match.group(0)
     print(moby_dick)
     ```

## Example

The following snippet demonstrates how the script processes the text:

```python
# Instantiate the lemmatizer
lemmatizer = WordNetLemmatizer()

# Instantiate the Snowball Stemmer and pass in the "english" language parameter.
s_stemmer = SnowballStemmer(language='english')

# Read in the entire novel
book = gutenberg.raw(fileids=('melville-moby_dick.txt'))

# Use regular expression to get all the text after "CHAPTER 1".
match = re.search(r'CHAPTER 1.*', book, re.DOTALL)
if match:
    moby_dick = match.group(0)
print(moby_dick)
```

## Conclusion

This project provides a foundation for working with text data in Python using NLTK. By using lemmatization, stemming, and tokenization, it becomes easier to process and analyze large corpora of text. The project also highlights the use of regular expressions for extracting specific content from a text.

```
