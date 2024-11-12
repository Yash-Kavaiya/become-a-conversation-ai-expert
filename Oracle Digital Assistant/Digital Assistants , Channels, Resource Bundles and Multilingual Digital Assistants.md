# Digital Assistants , Channels, Resource Bundles and Multilingual Digital Assistants

A digital assistant is an advanced type of chatbot that acts as a unified interface to combine and orchestrate multiple individual chatbots, or "skills," into a single, cohesive user experience. Unlike early chatbots, which mainly focused on specific tasks like customer service automation or handling structured processes, digital assistants are designed to handle a wider range of user-oriented tasks. They are context-aware, meaning they can understand and remember past interactions, adapt to the user's needs, and learn from user interactions to improve the quality of assistance.

### Key Characteristics of Digital Assistants:
- **Unified User Experience**: A digital assistant integrates multiple skills or chatbots, allowing users to seamlessly switch between different services or tasks.
- **Context Awareness**: Digital assistants remember context across conversations, which helps in providing relevant responses and a more natural user experience.
- **Learning Capability**: They adapt over time by learning from user interactions, improving responses, and personalizing suggestions.

### How Digital Assistants Work:
Digital assistants use intelligent routing to decide which skill or chatbot to activate based on the user's input. They:
- Provide a single interface to multiple skills.
- Route user messages to the appropriate skill, even handling ambiguous requests.
- Handle non-linear requests and interruptions effectively, maintaining conversation flow and user satisfaction.

### Creating and Managing a Digital Assistant:
A digital assistant can be created in several ways:
- **From Scratch**: Building all components and skills.
- **By Cloning**: Replicating an existing assistant.
- **New Versioning**: Updating an existing assistant by creating a new version for edits.
- **Importing**: Using pre-built assistants or skills by importing them into the system.

The lifecycle of a digital assistant typically starts in draft mode and then moves to publishing, which locks the assistant to prevent changes. If updates are needed after publishing, a new version is created. Exporting a digital assistant provides an archive of its setup, including all skills.

### System Intents and Skills:
System intents are built-in functionalities designed to manage general requests, such as:
- **Help**: Detects if users need help, either within the current skill or for the entire assistant.
- **Exit**: Allows users to end a conversation, either for the current skill or the entire assistant.
- **UnresolvedIntent**: Triggers when an input does not match any skills, typically displaying a help menu.

### Explicit vs. Implicit Invocation:
- **Explicit Invocation**: The assistant calls a skill directly based on user request.
- **Implicit Invocation**: The assistant evaluates user input against candidate skills and routes the message accordingly.

### Configuration and Testing:
Configuration options allow fine-tuning of routing, prompt customization, and system dialog behavior. Conversation testing is essential in digital assistant development, helping to:
- Simulate and record user interactions.
- Inspect variable usage and routing logic.
- View conversation branches across skills.

### Why Use a Digital Assistant?
Even with a single skill, a digital assistant is beneficial because it provides structured handling for general flows, such as greetings, help requests, and exit commands. It allows a structured and scalable framework that supports future expansion into multi-skill capabilities.

### Digital Assistant Routing Overview

In human conversations, context can switch frequently, and digital assistants must handle these changes fluidly. Digital assistant routing acts as "traffic control" for managing user messages across multiple topics and skills, ensuring that each message is directed to the most suitable skill or intent. This process helps maintain conversational context and supports seamless topic switching.

- **Context Switching**: Just as humans can switch topics, digital assistants can manage multiple contexts by routing user inputs to the most relevant skill or intent.
- **Intelligent Routing**: Routing decisions are powered by an NLP model that calculates confidence scores to determine the most relevant skill or intent for each user message.
- **Routing as a Container**: The digital assistant acts as an intelligent container, holding one or more skills and managing the flow of conversations.

### Components of Digital Assistant Routing

1. **ODA Instance**: This represents the digital assistant instance itself, connecting various skills and channels.
2. **Skills**: Skills represent specific functionalities or task-oriented areas, such as:
   - **Bank Skill**: Tasks like checking balance or transferring money.
   - **Retail Skill**: For actions like checking gift card balance or listing stores.
   - **Pizza Skill**: For ordering or canceling pizzas.

When a user sends a message, the routing model selects the most suitable skill based on the context and confidence scores.

### Routing Terminology

- **Implicit Routing**: Routing decisions are made based on the user's message and the current conversation context. If a message aligns with multiple skills, the assistant may ask clarifying questions to disambiguate the user's request.
  
- **Explicit Routing**: Occurs when a user specifies the skill they want to interact with, such as “Ask Spotify to play the Rolling Stones.” This direct reference allows the assistant to route the message to the correct skill without ambiguity.

- **Candidate Skill**: Skills that could potentially handle the user message. Each candidate skill is evaluated based on a confidence score.

- **Candidate Flow**: The specific intent within a candidate skill that could handle the user's message.

- **System Intents**: Built-in intents like "help," "exit," or "unresolved," which handle general requests outside of specific skills.

### Implicit Routing Model

1. **Determine Candidate DA System Intent**: The assistant checks the confidence scores for system intents (e.g., help, exit).
2. **Evaluate Candidate Skills**: The assistant then evaluates candidate skills based on their confidence scores to find the most relevant option.
3. **Identify Candidate Flows**: Within each skill, the assistant evaluates which specific intent (flow) has the highest confidence score to handle the user message.

### Conversation Context Management

Digital assistants are context-aware, and this awareness influences how they route messages:
- **Contextual Weight**: The current skill is given more priority during intent resolution, meaning that the assistant gives extra weight to the active skill.
- **Pinned Context**: When a skill is explicitly invoked, the conversation context is “pinned” to that skill, awaiting further messages relevant to that skill. The assistant treats this referenced skill as the primary context until a new topic or skill is invoked.
