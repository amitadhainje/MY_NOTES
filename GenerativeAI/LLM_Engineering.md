# LLM Engineering 
---

# What is an LLM 

An LLM (Large Language Model) is a type of AI model trained on massive amounts of text data to understand and generate human-like language. It is based on deep learning architectures like transformers (e.g., GPT). It learns patterns, grammar, context, and meaning from billions of words. It can perform tasks like answering questions, writing content, coding, summarizing, and translating. Examples include models from OpenAI, Google, and Meta.
It doesn’t “think” like humans—it predicts the most likely next word based on context.

# Why LLM

LLMs emerged due to limitations in earlier NLP systems and advancements in compute and data:
- Traditional NLP was rule-based → brittle, hard to scale, domain-specific.
- Machine learning models needed feature engineering → time-consuming and less flexible.
- Explosion of internet data enabled large-scale training.
- Breakthrough of the Transformer architecture (2017) made it possible to process long context efficiently.
- Availability of high GPU/TPU compute power enabled training huge models.
- Need for general-purpose AI assistants across domains.
- LLMs came to make language understanding general, scalable, and context-aware.

# Uses of LLMs

LLMs are used to build the following applications - 
- Chatbots and Virtual Assistants
- Content Generation
- Code Generation
- Data Analysis and Summarization 
- Translation and Language Tasks
- Domain Specific applications
- Agentic AI Systems

# Few more details regarding LLMs 

- Closed Source Models OR Frontier Models - GPT from OpenAI, Claude from Anthropic, Gemini from Google, Grok from X.ai
- Open Source LLM Models - Llama from Meta, Mixtral from Mistral, Qwen from Alibaba Cloud, Gemma from Google, Phi from Microsoft, DeepSeek from DeepSeekAI, GPT-OSS from OpenAI. There are three different ways of using the models - Chat Interfaces like ChatGPT, CloudAPIs & LLM APIs , Frameworks like LangChain, AI Cloud Services like Amazon BedRock, Google Vertex , Azure ML. We can also use the models using the direct inference with huggingFace and Transformers library. 
- OpenAI - Python Package Library.
- There are 3 different flavours of LLMs
  - Base Models - Take the sequence of input words and predicts the next word. We had to give Q&A as input. 
  - Chat/Instruct Model - Something similar to the chatgpt. We give the user prompt and system prompt as the input.
  - Reasoning/Thinking Model - The models which does a thought process first. 
  - Hybrid - Combination of Chat/Instruct & Reasoning/thinking models
- GPT - Generative Pre-Trained Transformer
- **Tokenization in GPT models** is the process of converting raw text into smaller units called tokens, which the model can understand and process numerically. Instead of reading full sentences as humans do, GPT breaks text into pieces that may be whole words, subwords, punctuation, or even spaces. This is done using a method based on Byte Pair Encoding (BPE), specifically a byte-level variant. The algorithm starts with individual characters (or bytes) and repeatedly merges the most frequent combinations to form commonly used subwords. As a result, frequent words may become single tokens, while rare or complex words are split into multiple tokens. This approach ensures efficiency, reduces vocabulary size, and allows the model to handle any language or symbol without running into unknown words. Tokenization also directly impacts how much text the model can process (context length), as well as performance and cost, since everything is measured in tokens rather than words.
- Important Points
  - GPT does not process raw text; it works on tokens (text chunks).
  - Tokens can be words, subwords, punctuation, or spaces.
  - Uses Byte Pair Encoding (BPE) to learn common text patterns. 
  - Based on byte-level tokenization, so it supports all languages and symbols.
  - Frequent words → fewer tokens, rare words → split into multiple tokens. 
  - Spaces are often included with tokens (e.g., " hello").
  - Same word can tokenize differently depending on context.
  - Token count determines context limits and API cost.
  - Roughly 1 token ≈ 0.75 English words (varies by text type).
  - You can check the how GPT does tokenization by using the following URL - https://platform.openai.com/tokenizer
- Three roles used in GPT-Style Prompting - 
  - **System Role** - The system role sets the overall behavior and rules for the model. It acts like a high-level instruction layer that defines tone, constraints, and boundaries (e.g., “be concise” or “act as a tutor”). These instructions persist throughout the conversation and guide how the assistant responds. It has the strongest influence among all roles.
  - **User Role** - The user role represents the actual input or query given by the person interacting with the model. It contains the questions, instructions, or tasks the user wants the model to perform. The assistant primarily responds to this role while still respecting system-level rules. It can vary turn by turn in a conversation.
 - **Assistant Role** - The assistant role contains the model’s responses to the user. It reflects how the model interprets and answers the user’s query based on both system instructions and prior conversation context. Previous assistant messages also help maintain continuity and context in multi-turn conversations.