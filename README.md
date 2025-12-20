# AI Prompt Engineering Technique Samples

Welcome to the **AI Prompt Engineering Technique Samples** repository! This collection features advanced, self-contained Jupyter notebooks designed to demonstrate state-of-the-art reasoning patterns using the OpenAI API.

Each notebook serves as a hands-on tutorial, helping developers and prompt engineers master specific techniques to improve LLM reliability, reasoning, and creativity.

---

## Table of Contents

* [Core Techniques](#-core-techniques)
* [Advanced Reasoning & Logic](#-advanced-reasoning--logic)
* [Creativity & Content Generation](#-creativity--content-generation)
* [Optimization & Meta-Learning](#-optimization--meta-learning)
* [Agentic & Interactive Patterns](#-agentic--interactive-patterns)
* [Setup & Usage](#-setup--usage)
* [Resources](#-resources)

---

## Core Techniques

These foundational patterns are essential for getting consistent, high-quality results from LLMs.

### [Chain of Thought (CoT)](chain_of_thought.ipynb)
**Best for:** Math word problems, logical riddles, multi-step reasoning, debugging.
* **Description:** Encourages the model to "show its work" by breaking down problems into intermediate reasoning steps before providing a final answer.
* **When Not to Use:** Simple factual lookups or latency-critical applications.

### [Few-Shot Prompting](few_shot_prompting.ipynb)
**Best for:** Text classification, strict formatting (JSON), style imitation (e.g., "Pirate English").
* **Description:** "Teaching" the model a specific pattern by providing a small set of high-quality "Input → Output" examples in the prompt.
* **When Not to Use:** Zero-shot capable tasks or when context window space is extremely limited.

### [Persona Pattern](persona_pattern.ipynb)
**Best for:** Domain-specific advice, expert consultations, role-playing scenarios.
* **Description:** Assigns a specific expert identity (e.g., "Senior Software Architect") to activate relevant knowledge and communication styles.
* **When Not to Use:** Generic tasks where expertise framing adds no value.

### [Prompt Chaining](prompt_chaining.ipynb)
**Best for:** Complex multi-part tasks, content pipelines, code review workflows.
* **Description:** Breaks complex tasks into sequential prompts where each step's output feeds into the next, improving accuracy and debuggability.
* **When Not to Use:** Simple single-step tasks or when latency is critical.

---

## Advanced Reasoning & Logic

For complex problems where standard prompting fails, these techniques introduce structured thinking processes.

### [Tree of Thought (ToT)](tree_of_thought.ipynb)
**Best for:** Strategic decision-making, complex planning, open-ended problem solving.
* **Description:** Explores multiple "branches" of reasoning simultaneously. The model generates distinct possibilities, evaluates pros/cons, and selects the optimal path.
* **When Not to Use:** Linear tasks with a single clear path (adds unnecessary token cost).

### [Graph of Thought (GoT)](graph_of_thought.ipynb)
**Best for:** Complex synthesis, non-linear storytelling, multi-dimensional analysis.
* **Description:** Models reasoning as a network (DAG) where thoughts are nodes that can merge, split, loop, or transform.
* **When Not to Use:** Simple linear reasoning tasks.

### [Self-Consistency](self_consistency.ipynb)
**Best for:** Improving accuracy on math problems, symbolic logic, and reducing "hallucinations."
* **Description:** Generates multiple Chain of Thought paths (samples) and uses "majority voting" to select the most reliable answer.
* **When Not to Use:** Creative writing (where diversity is desired) or resource-constrained environments.

### [Reflexion](reflexion_prompting.ipynb)
**Best for:** Hard coding challenges, rigorous logic puzzles, tasks requiring high precision.
* **Description:** An iterative loop where the model critiques its own previous attempt ("What went wrong?") and retries with new insight.
* **When Not to Use:** Simple queries where the first answer is usually correct.

---

## Creativity & Content Generation

Techniques designed to structure long-form content or spark innovation.

### [Skeleton-of-Thought (SoT)](skeleton_of_thought.ipynb)
**Best for:** Writing long-form content (blogs, reports, guides) quickly and coherently.
* **Description:** Generates a concise outline first, then expands each point (potentially in parallel) to create a full document.
* **When Not to Use:** Short summaries or highly interdependent narratives.

### [Play Off Method](play_off_method.ipynb)
**Best for:** Ideation, brainstorming, marketing slogans, creative writing.
* **Description:** A creative technique where the AI generates variations by contrasting, combining, or "playing off" a base idea.
* **When Not to Use:** Factual retrieval or data extraction.

---

## Optimization & Meta-Learning

Techniques for improving and automating prompt engineering itself.

### [Automatic Prompt Engineer (APE)](automatic_prompt_engineer.ipynb)
**Best for:** Optimizing prompts for production pipelines, squeezing out maximum accuracy.
* **Description:** A meta-learning workflow where the AI writes, tests, and ranks its own system prompts to find the optimal instruction.
* **When Not to Use:** One-off tasks where optimization cost outweighs the benefit.

### [Meta-Prompting](meta_prompting.ipynb)
**Best for:** Prompt design assistance, exploring prompting strategies, rapid prototyping.
* **Description:** Uses the AI to help design, refine, and optimize prompts based on your goals and best practices.
* **When Not to Use:** When you already have a well-tested prompt that works.

---

## Agentic & Interactive Patterns

Patterns that define how the AI interacts with users or tools.

### [ReAct (Reason + Act)](react.ipynb)
**Best for:** Agents that need to use external tools (search, APIs) or multi-step verification.
* **Description:** Interleaves "Thought", "Action" (using tools), and "Observation". The model reasons about what to do, acts, and observes the result.
* **When Not to Use:** Purely conversational tasks relying solely on internal training data.

### [Interview Pattern](interview_pattern.ipynb)
**Best for:** Diagnostics, career coaching, personalized recommendations, complex intake forms.
* **Description:** The AI takes control, asking one question at a time to gather necessary information before providing a final recommendation.
* **When Not to Use:** When the user needs an immediate answer or a short interaction.

---

## Setup & Usage

### Prerequisites
- Python 3.8+
- OpenAI API key

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-repo/ai-prompt-engineering-technique-samples.git
   cd ai-prompt-engineering-technique-samples
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

   Or install manually:
   ```bash
   pip install openai python-dotenv networkx matplotlib
   ```

3. **Configure API Key:**
   Create a `.env` file in the root directory:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

4. **Run:** Open any notebook in Jupyter and run the cells to start the interactive tutorial:
   ```bash
   jupyter notebook
   ```

### Requirements

All notebooks use the **modern OpenAI Python SDK (v1.0+)** with the `OpenAI` client pattern:

```python
from openai import OpenAI
client = OpenAI(api_key=api_key)
response = client.chat.completions.create(...)
```

Each notebook includes:
- Error handling for API failures
- Input validation
- Clear explanations of temperature settings
- Interactive input/output loops

---

## Techniques Overview

| Technique | Category | Best For | Temperature |
|-----------|----------|----------|-------------|
| Chain of Thought | Core | Math, Logic, Debugging | 0.2 |
| Few-Shot | Core | Classification, Formatting | 0.1 |
| Persona Pattern | Core | Domain Expertise | 0.6 |
| Prompt Chaining | Core | Complex Pipelines | Varies |
| Tree of Thought | Reasoning | Decision Making | 0.5 |
| Graph of Thought | Reasoning | Non-linear Analysis | 0.7 |
| Self-Consistency | Reasoning | Accuracy Improvement | 0.7 |
| Reflexion | Reasoning | Self-Correction | 0.5-0.7 |
| Skeleton-of-Thought | Creative | Long-form Content | 0.3-0.7 |
| Play Off | Creative | Brainstorming | 0.8 |
| APE | Meta | Prompt Optimization | 1.0 |
| Meta-Prompting | Meta | Prompt Design | 0.7 |
| ReAct | Agentic | Tool Use | 0.3 |
| Interview Pattern | Agentic | Information Gathering | 0.7 |

---

## Resources

* **OpenAI API Documentation**: [https://platform.openai.com/docs](https://platform.openai.com/docs)
* **OpenAI Python SDK**: [https://github.com/openai/openai-python](https://github.com/openai/openai-python)
* **Prompt Engineering Guide**: [https://www.promptingguide.ai/](https://www.promptingguide.ai/)

---

## Contributing

Contributions are welcome! If you have a new prompt engineering technique to add or improvements to existing notebooks, please open a pull request.

## License

This project is open source and available under the MIT License.
