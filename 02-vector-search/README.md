# Vector Search

## Semantic Search ( Dense Vector Search)

Semantic search is a type of information retrieval that uses semantic similarity to find documents that are similar to a given query. It is a type of vector search that uses a dense vector to represent the query and the documents.

## Keyword Search with TF-IDF ( Sparse Vector Search)

Keyword search is a type of information retrieval that uses keywords to find documents that are similar to a given query. It is a type of vector search that uses a sparse vector to represent the query and the documents.

## Hybrid Search ( Dense + Sparse Vector Search)

Hybrid search is a type of information retrieval that uses both semantic and keyword search to find documents that are similar to a given query. It is a type of vector search that uses a dense vector to represent the query and the documents and rerank the results using a sparse vector.

## Fusion

### Reciprocal Rank Fusion (RRF)

- RRF combines rankings from multiple retrieval systems (e.g., dense and sparse searches).
- Documents are scored based on their ranks in each system.

### Distribution-Based Score Fusion (DBSF)

- DBSF combines the results from multiple retrieval systems (e.g., dense and sparse searches).
- DBSF uses the statistical properties (distribution) of each system’s scores to normalize and combine them.
