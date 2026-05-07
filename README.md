# Blog Writing Agent

Production-style AI Blog Writing Agent built using LangGraph, LangChain, OpenAI, Gemini, Tavily, Streamlit, and LangSmith.

This project demonstrates how modern AI agents are designed using orchestrator-worker architectures instead of simple prompt chaining. The system plans before execution, performs internet research when required, decomposes tasks into parallel subtasks, coordinates multiple worker agents, generates citation-aware content, automatically adds contextual images, and produces complete end-to-end blogs with full workflow observability using LangSmith.

---

## Overview

The Blog Writing Agent is a multi-agent AI system designed to automate the complete blog generation lifecycle using graph-based orchestration.

The system:
- Understands the blog topic
- Determines whether internet research is required
- Performs web research dynamically
- Creates structured execution plans
- Assigns subtasks to worker agents
- Generates blog sections in parallel
- Merges outputs into a coherent article
- Adds contextual images automatically
- Produces production-style long-form blogs
- Tracks workflow execution using LangSmith

The architecture follows modern agentic AI design patterns using LangGraph stateful workflows and orchestrator-worker coordination.

---

## Workflow Architecture

### Main Workflow

```text
START
  │
  ▼
Router
  │
  ├──► Research
  │
  ▼
Orchestrator
  │
  ▼
Worker Agents
  │
  ▼
Reducer
  │
  ▼
END
```

### Image Generation Workflow

```text
START
  │
  ▼
Merge Content
  │
  ▼
Decide Images
  │
  ▼
Generate and Place Images
  │
  ▼
END
```

The system separates content generation and image placement into dedicated workflows for modularity and scalability.

---

## System Design

### Router Node
The router acts as the decision-making layer.

Responsibilities:
- Analyze user query
- Determine whether research is required
- Route execution path dynamically
- Control workflow transitions

---

### Research Node
The research workflow performs internet-based information retrieval.

Capabilities:
- Tavily-powered web search
- Context collection
- Citation gathering
- Research summarization

This step ensures generated blogs remain grounded in real-world information.

---

### Orchestrator Node
The orchestrator coordinates the full execution pipeline.

Responsibilities:
- Task planning
- Task decomposition
- Worker assignment
- Parallel execution management
- State coordination

The orchestrator transforms high-level goals into structured subtasks.

---

### Worker Nodes
Worker agents independently generate content sections.

Capabilities:
- Parallel section generation
- Context-aware writing
- Citation integration
- Specialized content generation

Example worker tasks:
- Introduction generation
- Technical explanation
- Research synthesis
- Conclusion generation

---

### Reducer Node
The reducer combines outputs from multiple worker agents.

Responsibilities:
- Merge generated sections
- Remove inconsistencies
- Ensure coherence
- Generate final structured blog

---

### Image Workflow
The image pipeline runs after content generation.

Responsibilities:
- Analyze generated content
- Identify sections requiring visuals
- Generate or retrieve relevant images
- Place images contextually within the blog

This creates visually enriched blog outputs automatically.

---

## Key Features

### Planning-Based AI Agent
- Plans execution before generation
- Breaks large tasks into smaller subtasks
- Improves reasoning and workflow quality

### Orchestrator–Worker Architecture
- Centralized orchestration
- Distributed worker execution
- Scalable agent coordination

### Parallel Processing
- Multiple worker agents execute simultaneously
- Faster content generation
- Efficient workflow execution

### Research-Aware Generation
- Dynamic internet research
- Real-time contextual grounding
- Tavily integration

### Citation-Aware Content
- Automatic reference integration
- Source-grounded generation
- Reduced hallucinations

### Automatic Image Placement
- Detects where visuals are needed
- Context-aware image integration
- Enhanced readability

### Stateful LangGraph Workflow
- Persistent workflow state
- Node-based execution
- Graph-driven orchestration

### LangSmith Observability
- Workflow tracing
- Node-level execution monitoring
- Agent debugging
- Prompt tracking
- Performance analysis

### Production-Oriented Architecture
- Modular agent design
- Extensible workflow structure
- Real-world AI system architecture

---

## Tech Stack

| Category | Technologies |
|---|---|
| Workflow Orchestration | LangGraph |
| LLM Framework | LangChain |
| LLM Providers | OpenAI, Gemini |
| Web Research | Tavily |
| Frontend | Streamlit |
| Observability | LangSmith |
| Language | Python |
| Architecture | Multi-Agent Systems |
| Workflow Type | Orchestrator–Worker |

---

## Repository Structure

```bash
Blog-Writing-Agent/
│
├── agents/
├── router/
├── orchestrator/
├── workers/
├── reducer/
├── research/
├── image_workflow/
├── prompts/
├── utils/
├── outputs/
│
├── bwa.py
├── bwa_frontend.py
├── requirements.txt
├── .env
└── README.md
```

---

## End-to-End Workflow

### Step 1: User Topic Input

Example:
```text
"Write a blog on Multi-Agent AI Systems"
```

---

### Step 2: Query Routing
The router determines:
- Whether research is required
- Which execution path to follow

---

### Step 3: Research Phase
The research node:
- Performs internet searches
- Collects relevant information
- Extracts supporting references

---

### Step 4: Planning and Orchestration
The orchestrator:
- Breaks the task into sections
- Assigns subtasks to worker agents
- Coordinates execution flow

---

### Step 5: Parallel Worker Execution
Worker agents independently generate:
- Introduction
- Technical sections
- Examples
- Summaries
- Conclusions

---

### Step 6: Content Reduction
The reducer:
- Merges outputs
- Removes redundancy
- Creates coherent final content

---

### Step 7: Image Pipeline
The image workflow:
- Identifies image placement opportunities
- Generates contextual visuals
- Inserts images into relevant sections

---

### Step 8: LangSmith Monitoring
LangSmith tracks:
- Workflow execution
- Agent transitions
- Prompt flows
- Node latency
- Debugging traces

---

### Step 9: Final Blog Output
The system produces:
- Structured long-form blog
- Citation-aware content
- Image-enhanced article
- End-to-end AI-generated output

---

## Installation

### Clone Repository

```bash
git clone git@github.com:Sudhanshud98/Blog-Writing-Agent.git
cd Blog-Writing-Agent
```

---

### Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate
```

---

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file:

```env
OPENAI_API_KEY=
GOOGLE_API_KEY=
TAVILY_API_KEY=
LANGCHAIN_API_KEY=
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=Blog-Writing-Agent
```

---

## Running the Project

### Run Backend Workflow

```bash
python bwa.py
```

### Run Streamlit Frontend

```bash
streamlit run bwa_frontend.py
```

---

## Example Use Cases

- AI-powered technical blogging
- Automated research article generation
- SEO-assisted content pipelines
- Long-form AI content generation
- Research-backed article writing
- Autonomous writing systems

---

## Skills Demonstrated

- LangGraph orchestration
- Multi-agent AI systems
- Planning-based workflows
- Agentic AI architecture
- Parallel agent execution
- Research-aware AI systems
- Prompt engineering
- Streamlit application development
- Internet-connected AI agents
- Stateful workflow orchestration
- LangSmith observability
- End-to-end LLM application design

---

## Production Enhancements

### Observability
- Workflow debugging
- Agent execution monitoring

### Advanced Retrieval
- RAG pipelines
- Vector database integration
- Hybrid retrieval systems

### Advanced Agent Coordination
- Reflection agents
- Self-correction workflows
- Hierarchical planning systems

### Deployment
- Docker containerization
- Cloud deployment pipelines
- API-based serving

---

## Future Improvements

- Human-in-the-loop editing
- Memory-enabled agents
- Autonomous SEO optimization
- Real-time streaming generation
- Multi-language blog generation
- CMS publishing integration
- Agent feedback loops

---

## Contributors

Sudhanshu Deshpande

---
