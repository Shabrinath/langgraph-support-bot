# Intelligent Support Ticket Routing with LangGraph

This repository provides a clear and practical example of how to use **LangGraph** (built on top of **LangChain**) to create an intelligent support ticket system. It showcases how you can leverage language models to automatically categorize incoming support tickets, route them to the appropriate team or agent, and even generate helpful responses—all within a flexible, graph-based workflow. The project is designed to be simple to understand, yet demonstrates the powerful capabilities of LangGraph for building real-world, automated support solutions.

<img width="346" height="466" alt="image" src="https://github.com/user-attachments/assets/e417cb87-b640-4f65-a492-abb1c3b9550f" />



## What is LangChain & LangGraph?

### LangChain
**LangChain** is a framework for building applications with language models. It simplifies LLM integration, prompt management, and tool connections.

### LangGraph

**LangGraph** is LangChain's graph-based workflow engine for building flexible, intelligent workflows using a graph structure. It allows you to design and execute complex processes by connecting different steps (nodes) and defining how information (state) flows between them.

#### Key Terminology

- **State**: The data or context that is passed and updated throughout the workflow. In a support ticket system, the state might include the ticket text, its category, and any generated replies.
- **Node**: A single step or operation in the workflow graph. Each node performs a specific function, such as receiving a ticket, categorizing it, or generating a reply.
- **Edge**: The connection between nodes, representing the possible transitions or flow of state from one node to another. Edges can be conditional, allowing for branching logic based on the current state.
- **Start**: The entry point of the workflow graph, where processing begins. This is typically the node that receives the initial input or state.
- **End**: The termination point(s) of the workflow, where processing stops. Once the state reaches an end node, the workflow is complete.

#### Features

- **State Management**: Maintain and update context (state) across multiple steps in the workflow.
- **Conditional Routing**: Make dynamic decisions and route the workflow based on outputs from language models or other logic.
- **Complex Workflows**: Design multi-step processes with branching, loops, and parallelism.
- **Human-in-the-Loop**: Integrate human decision points seamlessly within automated workflows.

LangGraph makes it easy to visualize, build, and manage sophisticated workflows for tasks like support ticket triage, using clear graph-based concepts.

## How This Repository Helps

This repository demonstrates a **simple yet complex workflow** that showcases:

1. **Intelligent Routing**: Automatically categorizes support tickets using LLM
2. **Conditional Processing**: Different handling paths based on ticket type
3. **State Persistence**: Maintains ticket information throughout the workflow
4. **Real-world Application**: Practical support ticket management system

### Workflow Overview
```
📩 Receive Ticket → 🤖 Categorize (LLM) → Branch:
                                    ├── DevOps → 🤖 Auto-Reply (LLM/RAG)
                                    └── Billing → 👤 Human Support
```

## Quick Start

### Prerequisites
- Python 3.8+
- OpenAI API key

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd langgraph
   ```

2. **Install dependencies**
   ```bash
   pip install langchain langchain-openai langgraph
   ```

3. **Set up environment**
   ```bash
   export OPENAI_API_KEY="your-api-key-here"
   ```

### Execution Steps

1. **Run the support workflow**
   ```bash
   python support-langgraph.py
   ```

2. **Test with different ticket types**
   - **DevOps tickets**: "My Kubernetes pods keep restarting with CrashLoopBackOff"
   - **Billing tickets**: "I was charged twice for my subscription this month"

### Expected Output
```
📩 Received ticket: My Kubernetes pods keep restarting with CrashLoopBackOff.
🤖 DevOps Reply: I can help you troubleshoot the CrashLoopBackOff issue...
```

## Key Features Demonstrated

- ✅ **LLM Integration**: Uses GPT-4o-mini for intelligent categorization
- ✅ **State Management**: Maintains ticket data across workflow steps
- ✅ **Conditional Logic**: Routes tickets based on LLM classification
- ✅ **Modular Design**: Easy to extend with new categories or handlers
- ✅ **Real-time Processing**: Immediate ticket handling and response

## Extending the Workflow

This simple example can be extended to:
- Add more ticket categories (Security, Feature Request, etc.)
- Integrate with ticketing systems (Jira, Zendesk)
- Add human approval steps
- Implement escalation logic
- Store results in databases
- Add notification systems

## Why This Matters

This repository shows how **LangGraph makes complex AI workflows simple**:
- **Before**: Complex state management, manual routing logic, hardcoded conditions
- **After**: Declarative workflow definition, automatic state handling, LLM-driven decisions

Perfect for developers learning to build production-ready AI applications with structured, maintainable code.
