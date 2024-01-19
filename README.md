## LLM-annotation
## Background
Biomedical phenomena are diverse, with various granularities from molecules, cells, and organisms. Handling the complexity of biomedical knowledge with consistency requires ontology development with high-quality annotations. 
However, there are several issues with manual annotation.
* Time and Cost for:
  Identify entities (molecules, processes, diseases) in articles
  Identifies relations between entities in articles
  Find terms in existing ontologies
* Scalability issues
* Update difficulties:
  Difficulties in keeping up-to-date article annotation
* Dependent on annotatorch ’s ability
LLM is an attractive techinique for annotation. 


## Aim
In this study, using large-scale language models (LLMs), we investigate a preliminary investigation of the possibility of utilizing annotations from figures of review aticles for ontology development. 


## Methods
### 1. Preprocessing: 
In this study, we focus on cellular senescence and aging.

 #### 1-1. PubMed search using the following search formula:
(PubMed PMC open access[filter]) AND (((cellular senescence[MeSH Major Topic]) AND (aging[MeSH Major Topic])) AND (humans[MeSH Terms]) AND (review[Filter])) 
Condition:
    Articles and Figure: open access.
    Figures: Download free
    Theme: Cellular senescence and aging
    Species: Human
    Article Type: Review articles

 #### 1-2. Prepare a set of correct answers for verification by manual annotation 
From the 409 articles, we selected nine figures from 4 articles to compare manual annotation and LLM annotation.
Annotation: Identify nodes (process, molecules/genes, chemical compounds, cell, disease) and relationships between them (promote/suppress)
Ontology list for mapping: GO, Protein Ontology, chEBI, Cell Ontology, Disease Ontology (DOID),  HoIP ontology

### 2.  Download figures

### 3. Prepare promts

### 4. LLM annotation using GPT-4 with Vision
GPT-4 with Vision, sometimes referred to as GPT-4V or gpt-4-vision-preview in the API, allows the model to take in images and answer questions about them


### 5. Ontology mapping

### 6. Evaluation

## Outcome
1.	Human annotation: 240 relations
2.	We conducted preliminary investigstion for prompt enginerring.
* Preliminary prompt:
    "Extract information about molecular biological pathways from the input figure, where the type of Node is process, protein, chemical_compound, biological_structure, or disease, and the relation type is either promote or suppress."
* Result:
LLM could indentify molecules, processes, and diseases.
LLM could annotate interactions(Promote/Suppress)  between nodes interpreted and generated each type of edge (Promote/Suppress) based on the context of each figure.
* Issue of LLM annotation:
 Hallucination: Some relationships were output even between nodes with no relationship.
 Direct/indirect relationships need to be investigated in detail in the future. We need to identify whether annotations are derived from image annotations or interpreted from general knowledge.

## Next steps
### 1. LLM annotation
#### Step 1: Extract node label from figures 
#### Step 2: Determine node type(process, molecues/genes, chemical compounds, cell, disease).
#### Step3: Determine source, target of edge
#### Step4: Determine edge type (promote/suppress)   
### 2. Obtology mapping by LLM
### 3. Evaluation of the performance of LLM: Metrics of Precision, Recall, and F1 Score. 
 Furthermore, mapping results will be  evaluated from the both 
lexical accuracy and emantic similarity perspectives.



## Acknowledgements
We would like to thank the participants at BLAH8 for their collaboration and constructive advice. We are grateful to the organizers for providing this opportunity.

## References
* GPT-4 with Vision: https://platform.openai.com/docs/guides/vision
* Yuki Yamagata, Tsubasa Fukuyama, Shuichi Onami, Hiroshi Masuya
Ontology for Cellular Senescence Mechanisms
bioRxiv 2023.03.09.531883
DOI: https://doi.org/10.1101/2023.03.09.531883
