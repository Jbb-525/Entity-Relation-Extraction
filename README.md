# Entity Relation Extraction

Course Project of **Text Analysis and Practice** (Score: 96)

### The aim of this project is to construct models with diverse architectures and explore the efficiency of different model structures in ntity Relation Extraction.
**Conclusion of the project:**
  1. The effectiveness of **segmented pooling**
  2. The effectiveness of integrating **positional information**
  3. The effectiveness of **earlier** integrating entities information with **more granular features** of the sequence

## ① PCNN model fusing location features
  _Focus on extracting interaction features between entities and **individual words**, along with **position features** of words relative to the two entities._
  
  * **Concatenated** the word vectors of the two entities with each word in the sentence
  - Incorporated the relative **position** of each word to the two entities to form the final word vector matrix
  * Conducted **segmented convolution**, dividing it into before, middle, and after based on the positions of the two entities

  ![image](https://github.com/Jbb-525/Entity-Relation-Extraction/assets/88278422/29982f27-e0fa-4222-af29-e006c9af6372)

## ② BiGRU-1
  _Focus on extracting interaction features between the two entities and the **entire sentence.**_

  * Concatenated the word vectors of the two entity with the output of each hidden layer of the BiGRU
  -  Employed attention mechanism to learn the relationship between each word and the two entities

  ![image](https://github.com/Jbb-525/Entity-Relation-Extraction/assets/88278422/1d025ed9-32f1-4e73-b6da-c1097e81acd1)

## ③ BiGRU-2
  _Focus on extracting feature interactions between entities and the before, middle, and after **segments of the sequence** that dividied by the positions of the two entities._

  * Applyed segmented pooling to the hidden layer features of each word extracted by BiGRU
  * Concatenated the last hidden layer state of BiGRU and the word vectors of the two entities with the results obtained from segmented pooling

  
## Model Evaluation

### PCNN model fusing location features is the **BEST ONE**



    

