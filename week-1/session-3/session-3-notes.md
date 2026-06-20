# Session 3 - How AI Actually Works

**Date:** Saturday, 21 Jun 2026
**Module:** 1 - AI/ML and GenAI Foundations
**Whiteboard:** [session-3-canvas.png](./session-3-canvas.png)

---

## What We Covered

### 1. The AI Pyramid - AI, ML, DL, LLM

Four layers, each building on the one below:

| Layer | What It Means | Examples |
|-------|---------------|----------|
| AI | Any system that mimics human intelligence | Spam filters, thermostats, calculators |
| ML | AI that learns patterns from data instead of hand-written rules | Netflix recommendations, fraud detection |
| DL | ML using neural networks with many layers of pattern recognition | Face unlock, voice assistants, image recognition |
| LLM | Deep learning on text at massive scale (billions of parameters) | ChatGPT, Claude, Llama, Qwen |

As an LLM Engineer, you work at the top of this pyramid.

### 2. How LLMs Work

**Neural Networks (the foundation):**
- A neural network is layers of connected nodes that learn patterns from data
- Each connection has a "weight" that gets adjusted during training
- An LLM is a massive neural network trained on billions of words

**Tokens:**
- LLMs cannot read raw text. They read chunks called tokens
- "The cat sat on the mat" becomes 6 tokens
- "unhappiness" becomes 3 tokens: "un", "happi", "ness"
- Rule of thumb: 100 tokens is roughly 75 words
- Context window = how many tokens the model can see at once (GPT-4: 128K, smaller models: 4K-8K)

**Attention:**
- The model looks at all tokens and decides which ones matter most
- Like skimming a long email and jumping to deadlines and action items
- Self-attention = the model looking at ALL tokens simultaneously to understand relationships

**Next-Token Prediction:**
- An LLM does one thing: predicts the next token
- "The capital of France is ___" -> predicts "Paris"
- Then takes the full text and predicts the NEXT token, and the next, and the next
- This loop is called autoregressive generation

**The full pipeline:**

```
Text -> Tokens -> Attention -> Predict Next Token -> Output
                                    ^                   |
                                    |___________________|
                                         (loop)
```

### 3. Frontier (Closed) vs Open-Source LLMs

**Closed / Frontier models:**
- GPT-4o, o3 (OpenAI), Claude (Anthropic), Gemini (Google)
- You pay per token
- Your data goes to their servers
- You cannot customize the model

**Open-Source models:**
- Llama 3 (Meta), Mistral (Mistral AI), Qwen 3 (Alibaba), Phi (Microsoft), Gemma (Google), DeepSeek
- Free to download and run
- Data stays on your machine
- You can fine-tune for your domain

**Why open-source matters:**

| Reason | Details |
|--------|---------|
| Zero cost | No per-token billing. Run it 1000 times for free. |
| Data privacy | Banks, hospitals, government -- data never leaves your machine. |
| Customizable | Fine-tune any model to become a domain expert. |
| No vendor lock-in | You own the model. Nobody can change the terms. |

### 4. The GenAI Engineering Lifecycle

The 8 stages of building a GenAI product:

```
Data -> Model Selection -> Prompt Engineering -> RAG -> Fine-tuning -> Agents -> Deploy -> Evaluate
```

| Stage | What It Means | Real-World Example |
|-------|---------------|-------------------|
| Data | Collecting and preparing information | Zomato restaurant reviews |
| Model Selection | Picking the right LLM for the job | Swiggy using small models for autocomplete |
| Prompt Engineering | Writing instructions the model follows | ChatGPT's system prompt making it polite |
| RAG | Giving the model access to your data before answering | Bank chatbot retrieving your account balance |
| Fine-tuning | Training the model on your specific domain | Hospital model trained on medical terminology |
| Agents | Models that can take actions and use tools | Cursor reading, writing, and running code |
| Deploy | Making it available to real users via API | ChatGPT's web interface |
| Evaluate | Measuring if the AI actually works well | Testing accuracy, hallucination rate |

### 5. Live Demo Recap

What we saw in the Jupyter notebook:

- **Tokenization:** Used tiktoken to break text into tokens. Hindi text uses more tokens than English.
- **LLM API call:** Called a local Qwen model from Python using the Ollama API.
- **System prompts:** Same question with different system prompts gave completely different responses (helpful assistant vs pirate vs professor).
- **Temperature:** Temperature 0.0 = same answer every time. Temperature 1.0 = different answer every time. Low = safe. High = creative.
- **Streaming:** Watched tokens appear one by one, just like ChatGPT's typing effect.

### 6. HuggingFace

- HuggingFace (huggingface.co) is the GitHub of AI
- Over 500,000 models available for free
- Model cards show size, license, benchmarks, and usage instructions
- We will use it throughout the course

---

## Key Takeaways

1. **AI, ML, DL, LLM** form a pyramid. Each builds on the one below. You work at the top.
2. **LLMs predict the next token**, one at a time. That is the entire mechanism.
3. **Open-source models are free**, private, and customizable. Closed models are powerful but come with cost and data trade-offs.
4. **The GenAI lifecycle** has 8 stages from data to evaluation. Each stage is a career path. This course covers all of them.
5. **You can run AI on your own laptop** with Ollama. No internet, no API cost.

---

## Homework

See [setup-guide.md](./setup-guide.md) for full installation instructions.

**Required for Session 4 (tomorrow):**
- Install Python 3.10+
- Install Ollama and pull qwen3:0.6b
- Install VS Code (or any editor) with the Jupyter extension

**Mini-challenge (optional):**
Pick one product you use daily (Swiggy, YouTube, PhonePe, etc). Write down which stages of the GenAI lifecycle you think it uses. We will discuss a few at the start of Session 4.

---

## What is Next

**Session 4 (Sunday) - Python for AI Engineering**

Not a generic Python class. Every example uses LLMs. You will:
- Learn Python data structures through the lens of AI (ChatML message format)
- Call an LLM from Python and build a simple chatbot
- Use Pydantic to validate LLM outputs
- Write async Python to make parallel LLM calls
- Set up a proper project structure

Come with Python and Ollama installed.
