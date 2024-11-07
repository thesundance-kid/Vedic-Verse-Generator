# Vedic-Verse-Generator

## N-gram Text Generator using the Mahabharata as its source 

This project implements increasingly sophisticated n-gram models to generate text in the style of the Mahabharata, one of the major Sanskrit epics of ancient India. The models learn patterns from an English translation of the Mahabharata to generate new, stylistically similar text. AKA, can we generate new bits of ancient vedic wisdom through computation? 

## Overview

The project was inspired by Karpathy's lecture on makemore that started with using a bigram model to generate new names (https://www.youtube.com/watch?v=PaCmpygFfXo&t=3777s). As an exercise he suggests implementing a trigram model. I wanted to create a generalizable function that could do the same with quadgrams and higher and as input decided to replace a list of names with the ancient epic of the Mahabharata.

The project demonstrates the implementation of:
- Character-level n-gram models (trigrams through hexagrams)
- Text preprocessing and cleaning
- Model evaluation using negative log likelihood
- Handling of computational limitations in large n-gram spaces
- Text generation with context-aware sampling

## Key Features

- **PDF Text Extraction**: Extracts and cleans text from a PDF version of the Mahabharata
- **N-gram Implementation**: Creates n-dimensional tensors to store n-gram frequencies and probabilities
- **Flexible Architecture**: Supports variable n-gram sizes through generalized functions
- **Smart Sampling**: Implements efficient sampling strategies to handle large n-gram spaces
- **Model Evaluation**: Compares model performance using negative log likelihood

## Results

The project shows clear improvements in model performance with increasing n-gram sizes:
- Trigram model: ~1.86 NLL
- Quadgram model: ~1.40 NLL
- Pentagram model: ~1.13 NLL
- Hexagram model: ~0.99 NLL

Sample generated text becomes increasingly coherent with larger n-grams, though with interesting computational challenges at higher orders. At the size of heptagrams and above, my kernel dies. But as we know; death is certain for one who has been born, and rebirth is inevitable for one who has died. Therefore, you should not lament over the inevitable.

Some personal favorites of the computer generated vedic pearls:
- "Ia furthened or purities with many sight as mighty vabhru thou sees his shalya upraise of bhishma on himself and thou seeks to a hundreds of all crowned for that has and then those two portion xlvi sanatsujata p by the require pourer of all religious brahma." : from the hexagram model. Im sure deep within this sentence exists much wisdom. Ponder away.
- "Hymn." : short and sweet. Deeply instructive. 

## Technical Implementation

- **Framework**: PyTorch for tensor operations
- **Key Libraries**: 
  - PyPDF2 for PDF processing
  - NLTK for sentence tokenization
  - torch for tensor operations and sampling

## Challenges and Solutions

- Handled the torch.multinomial limitation (max 2^24 categories) by implementing progressive sampling for higher-order n-grams (updated function for this created with the help of Claude)
- Balanced memory usage with model complexity
- Implemented proper probability normalization and handling of zero-frequency cases

## Usage

1. Clone the repository
2. Install required packages:
```bash
pip install PyPDF2 nltk torch
```
3. Place your Mahabharata PDF in the project directory
4. Run the Jupyter notebook

## Future Improvements

Potential areas for enhancement:
- Implementation of smoothing techniques
- Parallel processing for larger n-gram sizes
- Word-level n-grams instead of character-level
- Comparison with modern neural approaches
- Including other ancient sanskrit texts as "training" input

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.


## Acknowledgments

- Source text: [The Mahabharata translated into English by Kisari Mohan Ganguli]
- Inspired by classical NLP techniques, Karpathy, and the ancient literature of India
