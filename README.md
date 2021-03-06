# DISAE
## A Deep Learning Framework for Elucidating Chemical Interaction Space of Orphan Proteins




This is the repository to replicate experiments for the fine-tuning of classifier with pretrained ALBERT.
## ----------- INSTRUCTION -----------
### 1. Install Prerequisites
- python 3.7
- Pytorch 
- rdkit
- Transformers ([Huggingface](https://huggingface.co/transformers/). The author installed the package in Jan 2020. The newest version might have slight changes)

### 2. Clone this repository

### 3. Download Data
All data could be download [here](https://drive.google.com/file/d/1o12gyV_YY8E2lWFaqm73xsT5wfpGBsk8/view?usp=sharing) and put it under this repository, i.e. in the same directory as the finetuning_train.py.

There will be four subdirectories in the data folder.

![image](https://user-images.githubusercontent.com/33879882/88445795-246b9a00-cdf3-11ea-9757-1afabd87dc39.png)

- activity: gives you the  train/dev/test set split based on protein similarity at threshold of bitscore 0.035
- albertdata: gives you pretrained ALBERT model. The ALBERT is pretraind on distilled triplets of whole Pfam
- Intergrated: gives collected chemicals from several database
- protein: gives you mapping from uniprot ID to triplets form

### 4. Run Finetuning
To run ALBERT model (default: ALBERRT frozen transformer):
```
python finetuning_train.py --protein_embedding_type="albert"
```
To try other freezing options, change "frozen_list" to choose modules to be frozen.


To run LSTM model:
```
python finetuning_train.py --protein_embedding_type="lstm"
```


![distilled-and-architecture](https://user-images.githubusercontent.com/33879882/91499613-b9006680-e88f-11ea-8374-fe7ce529666a.png)

