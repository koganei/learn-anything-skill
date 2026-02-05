# Learn Anything Skill

An interactive learning system for Claude Code that researches any coding or development topic and presents it as a structured, personalized learning path with progressive difficulty levels.

## Overview

The Learn Anything Skill transforms Claude into an AI productivity coach that can teach you any technical subject. It automatically researches topics online, structures them into comprehensive learning paths, and delivers content interactively with personalized teaching based on your background and goals.

## Features

### 🔍 Research-Driven Learning
- **Automated Research**: Spawns research agents to comprehensively study any topic using web search
- **Current Information**: Emphasizes 2025-2026 best practices and modern approaches
- **Structured Organization**: Breaks down subjects into logical topics across difficulty levels
- **Two-Level Research**: Subject-level overview (500-1000+ lines) plus detailed per-topic research (200-500+ lines)

### 📚 Progressive Learning Paths
- **Foundations (01-05)**: Core concepts with no prerequisites
- **Intermediate (06-09)**: Building on basics with practical applications
- **Advanced (10-11)**: Complex patterns and optimization
- **Use Case Guides (12-17)**: Scenario-based learning for real-world situations

### 🎯 Interactive Teaching
- **Chunk-Based Delivery**: Content presented in small, digestible pieces
- **Active Learning**: Waits for acknowledgment before continuing
- **Hands-On Practice**: Exercises tailored to your environment
- **Understanding Checks**: Multiple-choice questions to verify comprehension
- **Pacing Control**: You control the speed and depth of learning

### 🎨 ASCII Diagram Support
Terminal-friendly visual aids that render perfectly without external tools:

```
React Component Hierarchy
=========================

              ┌─────────────┐
              │     App     │
              └──────┬──────┘
                     │
        ┌────────────┼────────────┐
        │            │            │
        ▼            ▼            ▼
   ┌────────┐  ┌─────────┐  ┌────────┐
   │ Header │  │  Main   │  │ Footer │
   └────────┘  └────┬────┘  └────────┘
                    │
           ┌────────┼────────┐
           │        │        │
           ▼        ▼        ▼
      ┌────────┐ ┌────┐ ┌────────┐
      │Sidebar │ │Feed│ │ Widget │
      └────────┘ └────┘ └────────┘
```

**7 diagram types included:**
- Flowcharts (decision logic, process flows)
- Hierarchies (component trees, org charts)
- State Transitions (lifecycle, state machines)
- Sequences (API calls, interactions)
- Relationships (database schemas, data models)
- Architecture (microservices, system layouts)
- Comparisons (side-by-side approaches)

### 💾 Persistent Learning
- **Progress Tracking**: Remembers which topics you've completed
- **User Context**: Captures your background, goals, projects, and learning style
- **Session Continuity**: Resume learning exactly where you left off
- **Personalized Teaching**: Future topics adapt based on your conversation history

### 🧠 Context-Aware Personalization
The skill maintains detailed user context including:
- Your technical background and experience level
- Your learning goals and use cases
- Your projects and work environment
- What teaching styles work best for you
- Concepts you grasped quickly vs. struggled with
- Your interests and follow-up questions

## Installation

### Download from Release

1. Download `learn-skill.skill` from the [latest release](https://github.com/koganei/learn-anything-skill/releases/latest)
2. Install it in Claude Code using the appropriate command

### Build from Source

```bash
# Clone the repository
git clone https://github.com/koganei/learn-anything-skill.git
cd learn-anything-skill

# The skill is ready to use - just reference the directory in Claude Code
# Or package it yourself if you have the packaging tools
```

## Usage

### Starting a New Learning Path

Invoke the skill with any technical topic:

```
/learn-skill React Hooks
```

Or just ask Claude naturally:

```
Teach me about TypeScript
Help me learn GraphQL
I want to understand Docker
```

### Example Session

```
User: /learn-skill React Hooks

Claude: [Researches React Hooks comprehensively]
        [Structures 17 topics across difficulty levels]

        # Welcome to React Hooks Learning!

        ## 📚 LEARNING PATH
        → Foundations (01-05)
        → Intermediate (06-09)
        → Advanced (10-11)

        ## 🎯 USE CASE GUIDES
        → Day-to-Day (12-14)
        → Modernization (15-16)
        → Quality (17)

        What would you like to explore?

User: 1

Claude: [Researches Topic 01 in detail based on your context]
        [Presents content in interactive chunks]

        ## Understanding What React Hooks Are

        React Hooks are functions that let you "hook into" React
        features from function components...

        Does this make sense so far?

User: Yes, continue

Claude: [Continues with next chunk]
        [Provides hands-on example]
        [Checks understanding]
        [Updates your user context]
```

### Resuming Previous Learning

```
User: /learn-skill React Hooks

Claude: Welcome back to React Hooks! You've completed 3 of 17 topics (18%).
        Last time you finished Topic 03: Working with useEffect.

        Ready to continue with Topic 04: The Rules of Hooks?
```

## How It Works

### Research & Structure Phase

1. **Check for Existing Progress**: Looks for `~/.claude-learn-skill/[subject-slug]/`
2. **Subject Research**: If new, spawns research agent to gather comprehensive information (500-1000+ lines)
3. **Structure Topics**: Organizes into foundations, intermediate, advanced, and use-case guides
4. **Initialize Files**: Creates learning path, progress tracking, and user context files

### Interactive Teaching Phase

1. **User Selects Topic**: By number, name, or description
2. **Topic Research**: Spawns detailed research agent for that specific topic (200-500+ lines)
3. **Personalized Content**: Uses your user context to tailor examples and pace
4. **Chunk-Based Delivery**: Presents content in small pieces with interaction
5. **Hands-On Practice**: Provides exercises relevant to your environment
6. **Progress Updates**: Tracks completion and updates user context continuously

### File Structure

```
~/.claude-learn-skill/
├── react-hooks/
│   ├── learning_path.json          # Topic structure and metadata
│   ├── progress.json                # Your progress tracking
│   ├── user_context.md              # Detailed user-specific learning context
│   ├── research/
│   │   ├── initial_research.md     # Subject-level research (500-1000+ lines)
│   │   ├── topic_01_research.md    # Topic-level research (200-500 lines)
│   │   └── topic_02_research.md
│   └── topics/
│       ├── 01_what-are-hooks.md    # Topic guides
│       └── 02_understanding-usestate.md
└── typescript/
    └── [similar structure]
```

## Examples of Topics You Can Learn

- **Languages**: TypeScript, Python, Rust, Go, etc.
- **Frameworks**: React, Vue, Angular, Next.js, etc.
- **Tools**: Docker, Kubernetes, Git, Webpack, etc.
- **Concepts**: Design patterns, algorithms, architecture, etc.
- **Practices**: Testing, CI/CD, code review, refactoring, etc.
- **Platforms**: AWS, GCP, Azure, etc.

## ASCII Diagram Examples

### Flowchart
```
User Authentication Flow
========================

    ┌─────────────┐
    │ User Login  │
    │   Request   │
    └──────┬──────┘
           │
           ▼
    ┌──────────────┐      NO
    │  Credentials ├─────────────┐
    │   Valid?     │             │
    └──────┬───────┘             │
           │ YES                 │
           ▼                     ▼
    ┌──────────────┐      ┌─────────────┐
    │ Generate JWT │      │Return Error │
    │    Token     │      │   401       │
    └──────┬───────┘      └─────────────┘
           │
           ▼
    ┌──────────────┐
    │Return Token  │
    │   200 OK     │
    └──────────────┘
```

### Sequence Diagram
```
API Request Flow
================

Client          Frontend         Backend        Database
  │                │                │               │
  │──Login Click──→│                │               │
  │                │──POST /auth───→│               │
  │                │                │──Query User──→│
  │                │                │←──User Data───│
  │                │                │               │
  │                │←────JWT────────│               │
  │←─Set Cookie────│                │               │
```

## Key Features in Detail

### Personalized Learning

The skill captures and uses detailed context about you:
- Your background and what you already know
- Your learning goals and why you're studying this
- Your technical environment (tools, platform, IDE)
- Your real-world projects and use cases
- What teaching styles work best for you
- Concepts you understand quickly vs. need more time with

### Adaptive Teaching

Each topic's research and teaching adapts based on:
- How you responded to previous topics
- Questions you've asked
- Hands-on challenges you've faced
- Your expressed interests and goals
- Your preferred pace and depth

### Quality Research

- **Extensive**: 500-1000+ lines for subject overview, 200-500+ lines per topic
- **Current**: Emphasizes 2025-2026 best practices
- **Comprehensive**: Covers foundations through advanced patterns
- **Practical**: Real-world examples and use cases
- **Personalized**: Topic research incorporates your specific context

## Contributing

Contributions are welcome! Feel free to:
- Report issues or suggest improvements
- Submit pull requests
- Share examples of effective learning paths
- Suggest new diagram types or teaching patterns

## License

MIT License - feel free to use and modify as needed.

## Acknowledgments

Built using the Claude Code skill system. Powered by Claude Sonnet 4.5.
