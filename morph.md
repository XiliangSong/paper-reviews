Morphology (Word Segmentation & PoS Tagging)
============================================

PoS Tagging
-----------

* Dipanjan Das and Slav Petrov. Unsupervised Part-of-Speech Tagging with Bilingual Graph-Based Projections http://static.googleusercontent.com/media/research.google.com/en/us/pubs/archive/37071.pdf
    - Build a PoS tagger (on universal PoS tag set) for resource scarce languages (using parallel data and English supervised PoS tagger)
    - Projection and label propagation on a bilingual graph of trigrams (in foreign language) and word types (in English), using similarity statistics and word alignment
    - PoS tagger was trained on feature-based HMM (Berg-Kirkpatrick et al. 2010) using tag distributions as features
    - Experiment: used 8 Indo-European languages from Europarl and ODS UN dataset
    - Full model achieved 10.4 point increase from the state-of-the art and 16.7% from vanilla HMM

Multi-Word Expressions
----------------------

* Katerina Frantz, et al. Automatic Recognition of Multi-Word Terms: the C-value/NC-value Method, International Journal on Digital Libraries, 2000. http://personalpages.manchester.ac.uk/staff/sophia.ananiadou/ijodl2000.pdf
    - C-value: "termhood" - nested multi-word terms. row freq minus (normalized) freqs of words which contain the term, weighted by length.
    - NC-value incorporates context information (term context words which appear in the vicinity of terms), weighted by importance (relative freq. of appearance with terms)
    - From 810K-word eye-pathology medical record, extracted terms with 75% precision (top 40) using NC-value (5 point increase over C-value)

* Youngja Park, et al. Automatic Glossary Extraction: Beyond Terminology Identification. COLING 2002. https://aclweb.org/anthology/C/C02/C02-1142.pdf
    - Extraction of glossary items (e.g., words/phrases to include published glossaries)
    - Recognize phrases by PoS tag sequences, finite state transducers
    - Calculate domain specificity and association of pre-modifiers and remove generic ones
    - Variant aggregation: symbolic variants, compounding variants, inflectional variants, misspelling variants, abbreviations
    - Ranking based on term domain-specificity and term cohesion
    - Many domain specific terms in Top300 and less in Bottom300, compared to LLR and MI
