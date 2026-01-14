Your university runs IT services, a teaching hospital, and a renewable microgrid. Answer the following question using RAG: “What are the minimum governance, monitoring, and documentation controls required to deploy a RAG assistant safely in production across IT, healthcare, and energy operations.”

Inputs (drag&drop into colab or download directly):
- NIST AI Risk Management Framework: https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf
- WHO ethics and governance of AI for health: https://iris.who.int/server/api/core/bitstreams/f780d926-4ae3-42ce-a6d6-e898a5562621/content
- EU AI Act official regulation text: https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202401689

Implementation steps:
- Use the existing coding environment and use the created api_key.txt file to mask your key
- Fetch the 3 pages, extract clean text with BeautifulSoup, cache locally
- Chunk into about 200-word passages and assign chunk IDs
- Implement a BM25 style retriever in pure Python
- Retrieve the top 6 chunks for the target question
- Call the Gemini API using only the retrieved chunks as context
- The generated response includes
- Requirements grounded by the ingested documents
- Chunk citations like [C3] after each bullet