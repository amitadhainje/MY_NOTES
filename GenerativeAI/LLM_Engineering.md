# LLM ENGINEERING 

1. We are using “UV” instead of conda environment. UV  is built using rust and it is much faster can conda.

2. Use the following version of OpenAI - 2.7.2

3. There are two types of prompt - 
* { ‘role’ : “system”, “content”:”system message goes here”}
* {‘role’ : “user”, “content”:”hi how are you?”}

4. Assignment - Scrape a website and summarise it using openAI

5. LLMs are also known as “Frontier Models”. Frontier models are closed source models and we need to pay to use them. Following are few of the Frontier models - GPT from OpenAI, Claude from Anthropic, Gemini from Google, Grok from X.ai

6. Open Source Models - Llama from Meta, Mixtral from Mistral, Qwen from Alibaba cloud, Gemma from Google, Phi from Microsoft, DeepSeek from DeepSeekAI, GPT-OSS from OpenAI

7. Three different ways to used the models -
* Chat interfaces like ChatGPT
* Cloud APIs ( LLM API, Frameworks like LangChain, Managed AI cloud services like AWS BedRock, Google Vertex, Azure ML )
* Direct Interface. Using HuggingFace & Transformers library with Ollama to run locally.
* There is a different model called “Groq”. This is different than Elon musk’s grok

8. Transformers - 2017, Google researchers wrote a paper named “Attention is all you need” proposing a new architecture called Transformers. 

9. Install Ollama on Mac. Ollama is free and you can use is on your local machine. ChatGPT OR Claude are good chatbots for getting online answers for your questions. 

10. Create the API Keys and do a sample code for the following - 
* OPENAI API Key
* Google Gemini Key
* Tavily API Key

11. Learn the following concepts in detail - 
* LangChain
* LangGraph
* Agno - https://youtube.com/watch?v=aKCgiq9z7JA
* Google ADK
* Agno + custom tool
* Agno + streamlit + Python Tools

12. AI code Editors - 
* Github Copilot
* Amazon Q
* Gemini Code Assist
* Cursor
* Replit
* Codex - Developed by OPENAI
* Claude Code - Developed by Anthropic
* Windsurf & Devin - Developed by Congnition

13. We are going to focus on Claude Code. It is paid application. AWS Claude. Claude Code extension is present in VS code. Probably it will be present in PyCharm also.

14. Key components of the AI Agents are environment, sensors, the model, decision making logic, actuators and feedback mechanisms. They are the building blocks for creating AI Agents. Different types of AI Agents have different environments. The self-driving car will have environments like roads, vehicles, weather conditions  etc… 

15. AI agent can operate in digital or physical environments. Sensors are the data collection tools for AI Agents. AI Agents receives loads of information from Sensors. In case of AI agents , Models are like brains for AI Agents. 
Models can be complex LLM to simple ML algorithms. Decision making logic helps the AI Agent to take proper decisions. Actions are performed by the AI agent as the end result of all the above components. Actuators help agents to take the actions. There are virtual actuators like APIs. 

16. The key features of AI Agents is to learn and adapt to the environments. 
AI Agents structures can be classified based on their complexity and functionality. Few of the AI Agent Structures are as follows - 
* Simple Reflex Agent
* Model-Based Reflex Agent
* Goal-Based Agent
* Utility-Based Agent
* Learning Agent	
    
19. Key Characteristics of a Sophisticated AI Agent are as follows-
* Profile and Persona - It decides how the agents must interact with the users. Agents background. They decide that how the agent should interact with users. Like a Tutor/Social Media Post Planning
* Memory - Added context provided to the agent. 
* Reasoning - Agents ability to draw conclusions and solve problems.
* Actions - Changes the environment with its actions
* Learning Capabilities

20. Not all agents types must have all the above five characteristics to qualify as agents. 

21. Simple Reflex Agent - fundamental tool that reacts on directly based immediate perception. It is not capable of learning	or adapting. It follows hard-coded rules. It is simply an agent . It is not an AI Agent.

22.  Model Based Reflex Agent - they perceive the environment. It is an AI agent. It does not necessarily learn or adapt. Does not improve its strategy based on experience. 

23. Goal Based Agent - A goal-based AI agent acts to achieve specific objectives by choosing actions that best lead to its desired goal. It uses goal information to make decisions dynamically rather than just following fixed rules.

24. Utility based Agent - decision logic is based on utility evaluation. Aims to evaluate actions based on potential returns.

25. Learning Agent - It has an extra component called the “Learning Agent” and it enhances the agent over time. It possesses the five components of the AI agent + the learning agent. It is capable of self-refining.

26. HITL ( Human In The Loop ) - emphasises the continuous involvement of humans in training monitoring and refinement of AI Agents. 

27. Frameworks for building AI Agents - ReWoo & ReAct
ReWOO - Reasoning without observations 
ReAct - Reasoning & Action

28. Read the following links -https://medium.com/@prashantgupta15/ai-evolution-predictive-ai-generative-ai-and-agentic-ai-7faa85f71b12

https://www.ibm.com/think/topics/agentic-ai-vs-generative-ai

https://wingedsheep.com/building-a-language-model/

https://medium.com/@sjasmeet135/transforming-text-generation-the-power-of-transformers-in-llms-703b236fa03b

29. Tokens - In early days neural networks were trained at the character level. Predict the next character in the sequence. Small vocab but expects too much from the network. Then the neural networks were trained off words, predict the next word in the sequence. It was easier than the previous approach but sometimes the rare words were omitted. The breakthrough was to work with the chunks of words "Tokens". A middle ground : manageable vocab , and elegantly handles the word stems. It is different from vectors. Visit the following website - https://platform.openai.com/tokenizer and you will get a slight hint of how GPT models generate the tokens. 

30. “Flavours of LLMs” is usually explained in **three broad categories**, based on how they are trained and used:

#### 1. Base (Foundation / Pretrained) LLMs

👉 *Raw language understanding models*

* Trained on massive general text data.
* Good at predicting next words, understanding grammar, context, and facts.
* Not aligned to follow instructions well.
* Example use: research, further fine-tuning.

**Examples:** GPT base models, LLaMA base, Falcon base.


#### 2. Instruction-Tuned LLMs

👉 *Models trained to follow human instructions*

* Fine-tuned on prompt–response datasets.
* Better at answering questions, summarizing, reasoning.
* More useful for applications directly.

**Examples:** ChatGPT-style models, LLaMA-Instruct, Mistral-Instruct.

#### 3. Chat / Aligned LLMs

👉 *Safety-aligned conversational models*

* Further trained with RLHF (human feedback).
* Optimized for helpfulness, safety, and conversational tone.
* Best for end-user interaction.

**Examples:** ChatGPT, Claude, Gemini chat models.

### Another popular “3-flavour” view (deployment perspective)

If you meant architecture instead, it can also be:

1. **Closed-source LLMs** (GPT-4/5, Claude, Gemini)
2. **Open-source LLMs** (LLaMA, Mistral, Falcon)
3. **Domain-specific LLMs** (medical, legal, finance fine-tuned models)












