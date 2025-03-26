## BASICS
1. **Micro RNAs -** Micro RNAs or miRNAs are the molecules present in our body that help to regulate the gene expression. They control important processes like cell growth, development or damage repair.
When some miRNAs start working abnormally, they can contribute to diseases like cancer. For example - miR - 21 is an miRNA that is often overactive in cancer which silences the tumour suppressor genes and allows cancer cells to grow uncontrollably.

2. **RiboStrike -** RiboStrike is an AI - powered tool that helps scientists find small molecules capable of inhibiting harmful miRNAs, which are linked to diseases like cancer.

3. **How does RiboStrike work?**
- Scientists first choose a target miRNA they want to inhibit.
- Instead of manually testing every compound in the lab, RiboStrike uses AI to screen a massive database of small molecules.
- The goal is to find the molecule which will help to bind or block the target miRNA.
- RiboStrike applies deep learning to analyze how molecules interact with miRNA.
- It uses graph - based AI , which treats molecules like a network of nodes (atoms) and edges (bonds), to predict which molecules will work best as inhibitors.
- After screening down millions of molecules, RiboStrike narrows down the top potential miRNA inhibitors that have the highest chance of working.
- The selected molecules are then tested in the lab.

4. **PCBA (PubChem BiaAssay) -** PubChem BioAssay contains small-molecule and RNAi screening data along with associated annotation information from contributing organizations.

5. **BioAssay -** BioAssay contains a collection of bioactivity and toxicity data that has greatly supported research in fields such as medicinal chemistry, drug discovery, pharmaceutical genomics and informatics research.
Each bioassay (e.g., PCBA-1030, PCBA-1379) represents an experiment testing how different chemical compounds interact with a specific biological target.

6. **Steps to setup the present the data in structured manner -**
- **Environment setup -**
  - Install prerequisites - Python , deepchem, sci - kit learn, tensor flow gpu installed (conda environment is recommended)
  - Clone the RiboStrike repository.
 
- **Data collection -**
  - PCBA dataset
  - Zinc database
  - Asinex database

- **Pre - processing (Clean and format the dataset) -**
  - Canonicalize smiles
  - Remove duplicates and missing data
  - Classify active and inactive datatest (1 - active and 0 - inactive)
  - Desalt and remove inorganic molecules (if applicable)
  - **Splitting -** split the data into train, test and validation sets. (do scaffold - based splitting to ensure that the data used for training and testing does not overlap in terms of molecular structure)

- **Hyper - parameter optimization -**
  - Task selection
  - Featurization
  - Hyper - parametre tuning
  - Validation
  - (tools : Randomized Search CV from Sci - kit learn or custom code for hyper - parameter optimization)
    
- **Model training -** 
  - Choosing an operation mode
  - Featured data
  - Build the model (Deepchem’s GNN or CNN models for training)
  - Train on data (use the training data to train the model and tune the data based on the validation set)
  - Result
    
- **Evaluation -**
  - use the test set to evaluate the trained model performance
  - If the model is a multitasking model you may need to evaluate each sub model individually.

- **Inference -**
  - Load pre - trained model.
  - If you are using a pre - trained model then set transfer = True
  - Load inference dataset like zinc or Asinex for prediction and then run inference

- **Task recommendation -**
  - After training evaluate the performance of each sub - model on a validation set.
  - Choose the sub - models that align most closely with the target task and use them for 0 short predictions.

- **Molecule selection -**
  - After the identification of the molecules that have the highest potential we will select them based on clustering and predicting uncertainty.
  - Extract model fingerprints.
  - Cluster molecules - use k means clustering and u map to cluster similar molecules.
  - Select molecules. Choose the top predictions from zinc and FDA dataset with low uncertainty.
  - Final evaluation. Evaluate these molecules for toxicity and their ability to interact with DICER (to ensure that they are specific to miR - 21)


