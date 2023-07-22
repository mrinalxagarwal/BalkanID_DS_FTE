# Research Paper Analysis and Impact Evaluation

## Task 1: Building a Research Paper Dataset

### Introduction

The main goal for Task-1 was to create a knowledge graph that helps in visualising the relationship between different research papers and the various entities.

### Findings

On pre-processing the data, we found the following features about the data present:

Unique Keys in the JSONL file:
{'paper_id', '_pdf_hash', 'bib_entries', 'ref_entries', '_source_name', 'body_text', '_source_hash', 'discipline', 'metadata', 'abstract'}
 
Unique Keys within 'metadata':
{'comments', 'license', 'categories', 'journal-ref', 'versions', 'authors', 'report-no', 'authors_parsed', 'id', 'submitter', 'title', 'doi', 'update_date', 'abstract'}

Unique Keys within 'abstract')
{'section', 'cite_spans', 'ref_spans', 'text'}

Unique Keys within 'body_text)
{'section', 'content_type', 'cite_spans', 'sec_type', 'sec_number', 'ref_spans', 'text'}

### Note
I tried to complete the task, but was unable to successfully present a demo of the graph and execute SPARQL queries. However, I was able to acheive a RDF file and a TTL file that contains the graphs and have further visualised in an HTML format.

## Task 2: Building a Research Paper Recommendation System

### Introduction

In Task 2, we developed a research paper recommendation system to suggest similar and important papers to researchers based on the content and citation relationships.

### Approach

1. **Text Vectorization (TF-IDF):** We utilized the TF-IDF (Term Frequency-Inverse Document Frequency) vectorization technique to convert abstracts of existing papers into numerical vectors. The TF-IDF score reflects the importance of each word in the abstract relative to the entire dataset, helping us capture the essence of each paper.

2. **Cosine Similarity:** We calculated the cosine similarity between the abstracts of new research papers and existing papers. The cosine similarity measures the cosine of the angle between two vectors, representing the degree of similarity between the two abstracts.

3. **Citation Network:** We constructed a directed graph, referred to as the citation network, where each node represented a research paper. The edges in the graph indicated citation relationships, with an edge from paper A to paper B implying that paper B is cited by paper A.

4. **PageRank Algorithm:** The PageRank algorithm was applied to the citation network to rank papers based on their importance. Papers with high PageRank scores are considered influential within the citation network.

### Findings

The research paper recommendation system generates top recommendations for each new research paper by considering both content similarity and citation importance. The recommended papers are likely to be relevant and impactful within the research domain.

### Usage

To use the research paper recommendation system:

1. Ensure you have a DataFrame named `citation_data` with columns 'citing_paper_id' and 'paper_id'. Replace this example data with your actual citation data.

2. Call the function `recommend_similar_important_papers(new_research_papers, existing_papers)` by passing two DataFrames:
   - `new_research_papers`: DataFrame containing new research papers to find recommendations for.
   - `existing_papers`: DataFrame containing the existing research papers in the system.

3. The function will return a dictionary of recommended papers for each new research paper.

### Visualization

The recommendation system does not directly involve visualizations. However, you can visualize the citation network using graph visualization libraries like NetworkX or Gephi to gain insights into the citation patterns and paper influence.

## Conclusion

The research paper recommendation system serves as a valuable tool for researchers seeking related and impactful papers. By employing text vectorization, cosine similarity, and PageRank, the system provides personalized suggestions, helping researchers explore relevant literature and expand their understanding of the research landscape.


## Task 3: Unveiling the Trailblazers

### Introduction

In Task 3, we focused on impact analysis to identify the research works that have made the most significant impact on their peers.

### Impact Analysis Methods

1. **Citation Count:** The citation count measures the number of times a paper is cited by other research papers. Higher citation counts indicate greater recognition and influence of the paper within the academic community.

2. **H-index:** The H-index considers both the number of citations a paper receives and the number of papers with an equal or higher number of citations. It provides a more comprehensive evaluation of a researcher's overall impact.

### Approach

We implemented the impact analysis using Python and RDFLib. The RDF knowledge graph includes entities for papers, authors, and citations, along with relevant properties representing relationships between entities. We utilized SPARQL queries to calculate the citation count and H-index for research papers.

### Findings

The impact analysis allowed us to rank research papers based on their citation counts and H-index. The top-ranked papers are considered the trailblazers in their respective fields, making the most significant impact on the scholarly community.

### Visualization Tool

We developed a visualization tool to explore the interconnectedness of research papers, their authors, citations, and other relevant metadata. Researchers can use the tool to gain insights into the citation patterns and impact of specific papers and authors.

## Conclusion

The research paper analysis and impact evaluation tasks provided valuable insights into the influence and significance of research papers. By leveraging various methodologies, we gained a comprehensive understanding of scholarly contributions and identified trailblazing works within the academic domain. The dataset, citation network, and impact analysis results offer researchers a powerful resource for further exploration and research in their respective fields.

---
*Note: The code implementation details and visualization tool can be found in the respective code files provided in the repository.*