# Microsoft Foundry AI Agents & Workflows – Complete Structured Summary

This document summarizes the core concepts required to design, build, orchestrate, and maintain AI agents using Microsoft Foundry, the Microsoft Agent Framework, A2A protocol, workflows, and Foundry IQ knowledge integration.

---

# 1. AI Agents Fundamentals

## What is an AI Agent

An AI agent is a software service that uses generative AI to understand context and perform tasks on behalf of users or systems.

Agents can:

- Understand requests
- Make decisions
- Execute tasks
- Use external tools
- Access knowledge
- Operate autonomously
- Maintain conversation memory

Unlike traditional chatbots, agents:

- Take actions
- Execute workflows
- Integrate with systems
- Automate processes

---

## Why AI Agents Are Useful

### Automation

Agents automate repetitive tasks and workflows.

Examples:

- Expense claims
- Scheduling
- Data processing

---

### Decision Support

Agents analyze large amounts of data and provide recommendations.

Capabilities:

- Trend analysis
- Predictions
- Insights

---

### Scalability

Agents scale operations without proportional increases in staff.

---

### 24/7 Availability

Agents operate continuously without interruption.

---

## AI Agent Use Cases

### Productivity Agents

Examples:

- Scheduling
- Email drafting
- Task management

---

### Research Agents

Examples:

- Market monitoring
- Report generation
- Data collection

---

### Sales Agents

Examples:

- Lead qualification
- Follow-ups
- Meeting scheduling

---

### Customer Service Agents

Examples:

- FAQ handling
- Support tickets
- Refund processing

---

### Developer Agents

Examples:

- Code review
- Bug fixing
- Repository management

---

# 2. Single-Agent vs Multi-Agent Systems

## Single-Agent Scenario

Example:

Expense management agent.

Capabilities:

- Answer policy questions
- Submit expense claims
- Route approvals

Core capabilities:

### Knowledge Integration

Uses policy documents as grounding.

### Task Automation

Uses functions to execute tasks.

### Decision-Making

Routes requests using rules.

---

## Multi-Agent Scenario

Multiple agents collaborate.

Example:

Travel agent + Expense agent.

Capabilities:

- Book flights
- Book hotels
- Submit expenses automatically

Benefits:

- End-to-end automation
- Specialization
- Scalability

---

# 3. Security for AI Agents

Agents introduce new risks because they:

- Access sensitive data
- Make decisions
- Act autonomously

## Security Best Practices

### Access Control

- RBAC
- Least privilege

---

### Input Validation

- Prompt filtering
- Injection prevention

---

### Human Oversight

- Human approval for critical actions

---

### Logging

- Full traceability

---

### Dependency Monitoring

- Audit external APIs and plugins

---

### Model Maintenance

- Detect drift
- Prevent poisoning

---

# 4. Agent Development Options

## Traditional AI Frameworks

Enhance applications with intelligence.

Examples:

- Recommendation systems
- Chatbots
- Voice assistants

Capabilities:

- Personalization
- Automation
- NLP interfaces

---

## AI Agent Frameworks

Enable autonomous agents.

Capabilities:

- Multi-agent collaboration
- Workflow automation
- Context awareness

---

## Microsoft Agent Development Tools

### Foundry Agent Service

Managed Azure service for agent development.

Supports:

- Multiple models
- Enterprise security
- Data integration

---

### OpenAI Assistants API

Subset of Foundry capabilities.

Supports:

- OpenAI models only

---

### Microsoft Agent Framework

SDK for:

- Multi-agent orchestration
- Workflows

---

### AutoGen

Open-source agent framework.

Good for:

- Research
- Prototyping

---

### Microsoft 365 Agents SDK

Supports:

- Self-hosted agents
- Multiple channels

---

### Copilot Studio

Low-code agent development.

Supports:

- Visual design
- Microsoft 365 integration

---

### Copilot Studio Lite

Declarative agent creation.

For business users.

---

# 5. Microsoft Foundry Agent Service

## Purpose

Managed service for building and running agents.

Benefits:

- No infrastructure management
- Reduced code
- Scalable deployment

---

## Agent Components

### Model

Generative AI model.

Used for:

- Reasoning
- Response generation

---

### Knowledge

Data sources:

- Bing
- Azure AI Search
- Documents

---

### Tools

Functions that perform actions.

Examples:

- Search tools
- Code interpreter
- Custom tools

---

### Threads

Conversation sessions.

Contain:

- Messages
- Files
- Context

---

# 6. Visual Studio Code Agent Development

## Foundry VS Code Extension

Provides:

- Agent creation
- Testing
- Deployment
- Code generation

---

## Features

### Agent Designer

Configure:

- Instructions
- Tools
- Models

---

### Playground

Real-time testing.

---

### Code Generation

Integration samples.

---

### Deployment

Direct deployment.

---

## Agent Configuration

Properties:

- Name
- Model
- Description
- Instructions
- Agent ID

---

## Agent Instructions Best Practices

- Be specific
- Provide context
- Define boundaries
- Include examples
- Define tone

---

## Agent Threads

### Threads

Conversation sessions.

### Messages

Interactions.

### Runs

Agent executions.

---

# 7. Microsoft Agent Framework

## Multi-Agent Orchestration

Allows:

- Specialized agents
- Complex workflows
- Dynamic coordination

---

## Workflows

Structured task sequences.

Support:

- Multiple agents
- Custom logic
- Checkpointing

---

## Workflow Components

### Executors

Workers performing tasks.

Can be:

- Agents
- Code components

---

### Edges

Define message flow.

Types:

Direct edges  
Conditional edges  
Switch-case edges  
Fan-out edges  
Fan-in edges

---

# 8. Orchestration Patterns

## 8.1 Concurrent Orchestration

Multiple agents run in parallel.

### Use When

- Independent tasks
- Brainstorming
- Voting
- Ensemble reasoning

### Avoid When

- Sequential dependencies
- Resource limits
- Data conflicts

---

## 8.2 Sequential Orchestration

Agents run in pipeline order.

Output → Input.

### Use When

- Multi-step processes
- Data pipelines
- Stepwise refinement

### Avoid When

- Tasks parallelizable
- Dynamic routing required

---

## 8.3 Group Chat Orchestration

Agents collaborate in conversation.

Chat manager controls flow.

Supports:

- Human input
- Iterative discussion

### Maker-Checker Pattern

Maker produces output.  
Checker reviews.

---

## 8.4 Handoff Orchestration

Agents transfer control dynamically.

### Use When

- Expertise emerges dynamically
- Multi-domain tasks

---

## 8.5 Magentic Orchestration

Dynamic planning orchestration.

Uses:

- Shared context
- Task ledger
- Dynamic planning

Best for:

- Open-ended problems

---

# 9. Agent-to-Agent (A2A) Protocol

Standard protocol for agent collaboration.

Supports:

- Interoperability
- Secure communication
- Context sharing

---

## Advantages

### Cross-Platform Collaboration

Agents from different vendors cooperate.

---

### Flexible Model Selection

Each agent uses its own LLM.

---

### Built-in Authentication

Secure communication.

---

# 10. Agent Skills

Define agent capabilities.

Elements:

- ID
- Name
- Description
- Tags
- Examples
- Input/output modes

---

# 11. Agent Card

Agent metadata document.

Contains:

- Identity
- Endpoint
- Capabilities
- Skills
- Authentication

Endpoint example:
/.well-known/agent-card.json


---

# 12. Agent Executor

Core component of A2A agent.

Responsibilities:

- Execute tasks
- Send responses
- Stream outputs
- Handle cancellation

---

## Methods

### Execute

Processes requests.

Uses:

- RequestContext
- EventQueue

---

### Cancel

Stops tasks if supported.

---

# 13. A2A Agent Server

Hosting enables:

- Discovery
- Communication
- Task lifecycle

---

## Components

### Agent Card

Capabilities description.

---

### Request Handler

Routes requests.

Uses:

- Task Store

---

### Server Application

Examples:

- Starlette
- Uvicorn

---

# 14. A2A Client

Responsibilities:

- Fetch Agent Card
- Send requests
- Handle responses

---

## Request Types

### Non-streaming

Single response.

---

### Streaming

Incremental responses.

---

## Response Types

Direct messages  
Task objects

---

# 15. Microsoft Foundry Workflows

## Definition

Visual orchestration system.

Declarative approach.

---

## Nodes

### Invoke Nodes

Invoke agents.

---

### Flow Nodes

If/Else  
Go To  
For Each

---

### Data Nodes

Set Variable  
Reset Variable  
Parse Value

---

### Chat Nodes

User interaction.

---

### End Node

Workflow completion.

---

## Variables

Provide shared state.

---

## Execution Paths

Define logic flow.

---

# 16. Workflow Patterns

## Sequential Workflow

Fixed order pipeline.

---

## Human-in-the-Loop

User approval steps.

---

## Group Chat Workflow

Multi-agent collaboration.

---

# 17. Power Fx

Low-code workflow language.

Used for:

- Conditions
- Variables
- Loops

Examples:

Upper(Local.Input)

Local.Confidence > 0.8

Sum(Local.ItemList, Amount)

---

# 18. Workflow Maintenance

## Visual vs YAML

Both synchronized.

Visual:

- Easy understanding

YAML:

- Advanced editing
- Source control

---

## Versioning

- Automatic versions
- Immutable
- Rollback possible

---

## Notes

Documentation inside workflows.

---

## Best Practices

- Remove unused nodes
- Handle structured outputs
- Document logic
- Use version history

---

# 19. Knowledge-Enabled Agents

## Problem

Traditional agents:

- No private data
- Knowledge cutoff
- Generic responses
- Hallucinations

---

# 20. Retrieval Augmented Generation (RAG)

## Process

### Retrieve

Search knowledge base.

### Augment

Combine context + query.

### Generate

Create response.

---

## Benefits

### Real-Time Updates

No retraining needed.

---

### Source Transparency

Document citations.

---

### Factual Grounding

Reduced hallucinations.

---

# 21. Foundry IQ

## Definition

Managed knowledge platform built on Azure AI Search.

Shared knowledge across agents.

---

## Advantages

- Centralized knowledge
- Reusable
- Automatic indexing
- Reduced infrastructure work

---

## Knowledge Bases

Organized by business domain.

Examples:

- Product Documentation
- HR Policies

---

## Data Sources

Supports:

- SharePoint
- Blob Storage
- OneLake
- Search indexes

---

## Data Processing Pipeline

### Discovery

Scan storage.

### Processing

Chunking + embeddings.

### Indexing

Searchable content.

### Monitoring

Automatic updates.

---

## Retrieval Intelligence

Foundry IQ automatically:

- Analyzes queries
- Selects search strategy
- Ranks results
- Provides citations

---

## Shared Knowledge Advantage

Multiple agents reuse knowledge bases.

Benefits:

- Consistency
- Scalability
- Immediate updates

---

# 22. Foundry IQ Data Sources

Knowledge bases in Foundry IQ depend on the quality and coverage of their data sources. Properly configured data sources ensure agents have the context required to answer questions accurately.

Data sources are configured during knowledge base setup and determine what information agents can retrieve.

Foundry IQ supports multiple data source types, allowing agents to access both internal and external information.

---

## 22.1 Azure AI Search Index

Azure AI Search Index provides enterprise-scale search capabilities for Foundry IQ knowledge bases.

This option is ideal when an organization already uses Azure AI Search and wants to reuse existing indexes.

Agents query the index to retrieve relevant information based on user questions.

### Capabilities

- Semantic ranking
- Custom scoring
- Faceted navigation
- Multi-language support

### Benefits

Semantic ranking:

- Returns contextually relevant results instead of simple keyword matches.

Custom scoring:

- Prioritizes results using business-specific logic.

Faceted navigation:

- Filters results by categories or attributes.

Multi-language support:

- Supports content in multiple languages.

---

## 22.2 Azure Blob Storage

Azure Blob Storage allows agents to retrieve documents directly from blob containers.

Foundry IQ processes the content and makes it searchable.

### Supported file types

- PDF files
- Word documents (.docx)
- Text files (.txt)
- Markdown files (.md)
- HTML files

### Best Practices

Organize blobs into containers by:

- Topic
- Department
- Access level

Benefits:

- Easier governance
- Better organization
- Easier updates

---

## 22.3 Web Source

Web access grounds agents with real-time information from the internet through Bing.

Agents can retrieve current information beyond internal knowledge bases.

### Useful for

- News and recent events
- Current pricing
- Frequently changing information
- External topics

Benefits:

- Real-time knowledge
- Broader coverage
- Reduced knowledge gaps

---

## 22.4 SharePoint Remote

SharePoint Remote retrieves content directly from SharePoint without indexing.

Agents search SharePoint in real time.

### Benefits

No index maintenance:

- No indexing pipeline required.

Always current:

- Uses latest content.

Permission-aware:

- Respects SharePoint permissions.

Simple setup:

- Minimal configuration required.

---

## 22.5 SharePoint Indexed

SharePoint Indexed stores SharePoint content inside Azure AI Search.

Unlike remote access, indexing processes documents in advance.

### Benefits

Faster response times

Advanced search features

Custom analyzers

AI enrichment pipelines

Unified indexing with other sources

### Use Cases

- Specialized terminology
- Advanced search requirements
- Large document sets

---

## 22.6 Microsoft OneLake

Microsoft OneLake provides access to unstructured data stored in Microsoft Fabric lakehouses.

Agents retrieve files and documents stored in OneLake.

### Use Cases

Business intelligence reports:

- Agents reference analytical findings.

Data documentation:

- Agents explain datasets.

Analytical insights:

- Agents provide data-driven responses.

Research outputs:

- Agents reference research content.

Benefits:

- Integration with Microsoft Fabric
- Data-driven answers
- Access to analytics results

---

# 23. Configure Retrieval with Foundry IQ

After building knowledge bases and configuring data sources, retrieval behavior must be configured.

Even well-indexed knowledge bases can produce poor results if retrieval behavior is not clearly defined.

Retrieval configuration ensures agents consistently use knowledge bases and produce grounded responses.

---

## 23.1 Retrieval Instructions

Agent instructions define how agents use knowledge bases.

Instructions act as a contract describing:

- When retrieval occurs
- How sources are cited
- What happens when information is missing

Poor instruction example:

"Answer HR questions using the knowledge base."

This instruction is ambiguous because:

- Retrieval may not always occur
- Citations may be missing
- Fallback behavior is undefined

---

## 23.2 Effective Retrieval Instructions

Effective instructions define three behaviors.

### When to Retrieve

Agents should:

- Always search the knowledge base
- Prefer knowledge base over training data

---

### How to Cite Sources

Instructions should define:

- Citation format
- Source references

Benefits:

- Transparency
- Trust
- Verification

---

### Fallback Behavior

Instructions should define behavior when information is missing.

Examples:

- Inform the user no information was found
- Suggest contacting support
- Request clarification

---

## 23.3 Testing Retrieval Behavior

Instructions must be validated through testing.

### Testing Process

1 Create a conversation session

2 Send test queries

3 Analyze responses

Testing should include:

- Simple questions
- Complex questions
- Edge cases

---

## 23.4 Response Quality Criteria

High-quality retrieval responses include four characteristics.

### Grounding

Responses must:

- Use knowledge base content
- Avoid unsupported statements

---

### Citation

Responses must:

- Include source references
- Attribute factual claims

---

### Relevance

Responses must:

- Use relevant documents
- Answer the question directly

---

### Completeness

Responses must:

- Provide full answers
- Avoid partial information

---

## 23.5 Iterative Improvement

If responses are inconsistent:

- Improve instructions
- Add rules
- Clarify edge cases

Iterate until retrieval behavior becomes stable.

---

## 23.6 Retrieval Strategies

Different agents require different retrieval strategies.

Examples:

Customer support agents:

- Direct factual retrieval

Research assistants:

- Broader context retrieval

---

## 23.7 Monitoring Retrieval in Production

After deployment, monitoring is required.

Users behave differently than test scenarios.

Monitoring helps identify:

- Knowledge gaps
- Edge cases
- Retrieval failures

---

### Metrics to Track

Citation frequency:

- Measures grounding consistency.

Fallback frequency:

- Indicates missing knowledge.

Query types:

- Identifies common user needs.

Retrieval accuracy:

- Measures document relevance.

---

## 23.8 Continuous Improvement

Use monitoring data to improve:

- Knowledge bases
- Retrieval instructions
- Search configurations

Reliable retrieval requires:

- Clear instructions
- Systematic testing
- Continuous monitoring

---