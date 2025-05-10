# Russian Text Accentuation

This tool automatically adds stress marks (accents) to Russian text using natural language processing and specialized dictionaries.

## Overview

The system uses the spaCy NLP library with a Russian language model to tokenize and analyze Russian text, then applies stress marks based on dictionaries of lemmas and word forms.

## Features

- Analyzes Russian text using spaCy's linguistic models
- Applies stress marks based on comprehensive dictionaries
- Handles grammatical cases, tenses, and number correctly
- Preserves original capitalization and formatting

## Installation

1. Clone this repository
2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install spacy
   python -m spacy download ru_core_news_md
   ```

## Usage

1. Place your Russian text in the `in.txt` file
2. Run the script using one of these methods:
   ```bash
   # Option 1: Direct execution with Python
   python stress.py

   # Option 2: Using the virtual environment's Python
   venv/bin/python stress.py

   # Option 3: After activating the virtual environment (bash/zsh)
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   python stress.py

   # Option 4: After activating the virtual environment (fish shell)
   source venv/bin/activate.fish
   python stress.py
   ```
3. The accentuated text will be:
   - Written to `out.txt` with accent marks (е.g., "опу́шке")
   - Written to `out_pluses.txt` with plus signs before stressed vowels (e.g., "оп+ушке")
   - Printed to the console

## How It Works

1. The system loads dictionaries of Russian lemmas and word forms from binary files
2. It uses spaCy to break the input text into tokens and analyze their grammatical properties
3. For each word, it tries to determine the correct accentuation by:
   - Checking if all interpretations agree on accent placement
   - Filtering interpretations by grammatical compatibility
   - Using lemma-matching as a fallback
4. The system preserves capitalization, punctuation, and spacing

## Files

- `stress.py`: Main script for text accentuation
- `in.txt`: Input text file in Russian
- `out.txt`: Output text file with stress marks added (е.g., "опу́шке")
- `out_pluses.txt`: Output text file with plus signs before stressed vowels (e.g., "оп+ушке")
- `lemmas.dat`: Binary pickle file containing Russian lemmas dictionary
- `wordforms.dat`: Binary pickle file containing Russian word forms dictionary

## Requirements

- Python 3
- spaCy library
- Russian language model for spaCy (`ru_core_news_md`)