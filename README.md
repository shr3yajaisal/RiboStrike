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

6. Steps to setup the present the data in structured manner -
- Environment setup -
  - Install prerequisites - Python , deepchem, sci - kit learn, tensor flow gpu installed (conda environment is recommended)
  - Clone the RiboStrike repository.
 
- 
