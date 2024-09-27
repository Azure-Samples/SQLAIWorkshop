## Vector Search and RAG Patterns

## Vector search
Vector search is a method that helps you find similar items based on their data characteristics rather than by exact matches on a property field. This technique is useful in applications such as searching for similar text, finding related images, making recommendations, or even detecting anomalies. It works by taking the vector representations (lists of numbers) of your data that you created by using a machine learning model by using an embeddings API, such as **[Azure OpenAI Embeddings] https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/embeddings** or **[Hugging Face on Azure] https://azure.microsoft.com/solutions/hugging-face-on-azure**. It then measures the distance between the data vectors and your query vector. The data vectors that are closest to your query vector are the ones that are found to be most similar semantically. Using a native vector search feature offers an efficient way to store, index, and search high-dimensional vector data directly alongside other application data. This approach removes the necessity of migrating your data to costlier alternative vector databases and provides a seamless integration of your AI-driven applications. 

## Embeddings
An embedding is a special format of data representation that machine learning models and algorithms can easily use. The embedding is an information dense representation of the semantic meaning of a piece of text. Each embedding is a vector of floating-point numbers, such that the distance between two embeddings in the vector space is correlated with semantic similarity between two inputs in the original format. For example, if two texts are similar, then their vector representations should also be similar. A vector database capability that allows you to store your embeddings with your original data ensures data consistency, scale, and performance. 


## Retrieval-Augmented Generation (RAG)
Retrieval-augmentated generation (RAG) is an architecture that augments the capabilities of LLMs like ChatGPT, GPT-3.5, or GPT-4 by adding an information retrieval system like vector search that provides grounding data, such as those stored in a vector database. This approach allows your LLM to generate contextually relevant and accurate responses based on your custom data sourced from vectorized documents, images, audio, video, etc.

A simple RAG pattern using Azure SQL DB could be:

- Enroll in the Azure SQL DB Vector preview
- Setup a database
- Insert data into an Azure SQL DB 
- Create embeddings from external REST endpoitn Invocation using Azure OpenAI Embeddings
- Use a vector function to perform vector similarity search based on a user prompt
- Perform question answering over the data using an Azure OpenAI Completions model
- The RAG pattern, with prompt engineering, serves the purpose of enhancing response quality by offering more contextual information to the model. RAG enables the model to apply a broader knowledge base by incorporating relevant external sources into the generation process, resulting in more comprehensive and informed responses. For more information on "grounding" LLMs, see **[grounding LLMs] https://techcommunity.microsoft.com/t5/fasttrack-for-azure/grounding-llms/ba-p/3843857**