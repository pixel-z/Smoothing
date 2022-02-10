# Smoothing
Implementation of smoothing methods `Kneser Ney` and `Witten Bell`.

A good read: [An Empirical Study of Smoothing Techniques for Language Modeling](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-10-98.pdf?from=https%3A%2F%2Fresearch.microsoft.com%2F%7Ejoshuago%2Ftr-10-98.pdf)
## Tokenizer
Tokenizer is made from scratch which handles following cases:
- **Word Tokenizer**
- **Punctuation**
- **URLs**: Replaced by \<URL>
- **Hashtags**: Replaced by \<HASHTAG>
- **Mentions**: Replaced by \<MENTION>
- ". . .. . ." Replaced by "." (similarly for other symbols)

Example:

![](https://imgur.com/zaPNrFZ.png)

It has been run on *twitter corpus* (set of 2000 tweets) and the output is stored in the file `2019111031_tokenize.txt`.

## Kneser-Ney Smoothing
Language model 1 & Language model 3 are smoothed with Kneser Ney smoothing.
- LM1: 
    - *Corpus*: Europarl corpus
    - *Avg. Train Perplexity*: 4.284909580178163
    - *Avg. Test Perplexity*: 13229.186428230216
- LM3: 
    - *Corpus*: Medical corpus
    - *Avg. Train Perplexity*: 3.4184223445091204
    - *Avg. Test Perplexity*: 20906.023541314356

## Witten-Bell Smoothing
Language model 2 & Language model 4 are smoothed with Witten-Bell Smoothing.
- LM2: 
    - *Corpus*: Europarl corpus
    - *Avg. Train Perplexity*: 2.754752175818304
    - *Avg. Test Perplexity*: 331.37547330408955
- LM4: 
    - *Corpus*: Medical corpus
    - *Avg. Train Perplexity*: 2.2151893632899857
    - *Avg. Test Perplexity*: 665.634549591011

## Instructions
- The Jupyter file uses data from my GDrive, the data can also be found in directory `data`.
- Other than that, the code is self-explanatory.
- At the end, the jupyter file also takes input from the user for the *type of smoothing* and *path of corpus* followed by an input sentence. 
- The output is the probability of that sentence using the two smoothing mechanisms.