# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a Russian text accentuation system that adds stress marks to Russian text. The system uses the spaCy NLP library with a Russian language model to tokenize and analyze Russian text, then applies stress marks based on dictionaries of lemmas and word forms.

## Architecture

The system works as follows:
1. Loads lemmas and word forms dictionaries from pickle files (`lemmas.dat` and `wordforms.dat`)
2. Reads input text from `in.txt`
3. Processes the text with a Russian spaCy model
4. Applies stress marks using dictionary lookups and linguistic rules
5. Writes the accentuated text to `out.txt` and prints it to console

## Commands

### Running the accentuation tool
```bash
# Process text in in.txt and output to out.txt
python stress.py
```

### Dependencies
The code requires:
- Python 3
- spaCy library
- Russian language model for spaCy (`ru_core_news_md`)

To install dependencies:
```bash
pip install spacy
python -m spacy download ru_core_news_md
```

## Data Files

- `lemmas.dat`: Binary pickle file containing Russian lemmas dictionary
- `wordforms.dat`: Binary pickle file containing Russian word forms dictionary
- `in.txt`: Input text file in Russian
- `out.txt`: Output text file with stress marks added