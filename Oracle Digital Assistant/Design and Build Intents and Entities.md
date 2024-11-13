# Design and Build Intents and Entities

# Design and Build Intents and Entities: Encoding Words as Numbers

## Table of Contents

1. [Introduction](#introduction)
2. [Encoding Words as Numbers](#encoding-words-as-numbers)
   - [ASCII Encoding](#ascii-encoding)
   - [Tokenization](#tokenization)
   - [Challenges in Tokenization](#challenges-in-tokenization)
3. [Sentence Encoding and Embeddings](#sentence-encoding-and-embeddings)
   - [High-Dimensional Vectors](#high-dimensional-vectors)
   - [Embeddings](#embeddings)
   - [Pretrained Models and Fine-Tuning](#pretrained-models-and-fine-tuning)
4. [Why Good Intent Design Is Important](#why-good-intent-design-is-important)
   - [Intent Classification](#intent-classification)
   - [Best Practices for Intent Design](#best-practices-for-intent-design)
5. [Partitioning Intents and Skills](#partitioning-intents-and-skills)
   - [Linguistic Spacing of Intents](#linguistic-spacing-of-intents)
   - [Skill Partitioning](#skill-partitioning)
6. [Enhancing the NLP Model](#enhancing-the-nlp-model)
   - [Unresolved Intent](#unresolved-intent)
   - [Understanding the Model](#understanding-the-model)
   - [Common Pitfalls](#common-pitfalls)
7. [Conclusion](#conclusion)
8. [References](#references)

---

## Introduction

In the realm of Natural Language Processing (NLP), designing and building intents and entities is crucial for creating effective conversational agents and chatbots. Encoding words as numbers is a fundamental step that allows machines to process and understand human language. This document delves into the methodologies of encoding words, the importance of good intent design, and best practices for enhancing NLP models.

---

## Encoding Words as Numbers

Converting textual data into numerical representations is essential for machine processing. This section explores how words and sentences are transformed into numbers.

### ASCII Encoding

ASCII (American Standard Code for Information Interchange) is a character encoding standard that represents text in computers. Each character is assigned a numerical value.

- **Example**:
  - The word **"listen"** is encoded as **76, 73, 83, 84, 69, 78**.
  - The word **"silent"** is encoded as **83, 73, 76, 69, 78, 84**.

### Tokenization

Tokenization involves breaking down text into smaller units called tokens, which can be words, characters, or subwords.

- **Example**:
  - **"I love my dog"** → `[1, 2, 3, 4]`
  - **"I love my cat"** → `[1, 2, 3, 5]`
  - **"Love my club"** → `[1, 2, 3, 6]`

### Challenges in Tokenization

- **Homonyms and Synonyms**: Words that sound the same but have different meanings can confuse the model.
- **Out-of-Vocabulary Words**: Words not present in the training data may not be recognized.
- **Contextual Meaning**: Tokenization alone may not capture the context in which a word is used.

---

## Sentence Encoding and Embeddings

After tokenization, sentences are transformed into numerical vectors that capture semantic meaning.

### High-Dimensional Vectors

- **Definition**: Arrays of numbers where each element represents a dimension in the vector space.
- **Purpose**: Capture the semantic relationships between words in a sentence.
- **Visualization**: Each word or sentence becomes a single point in a multi-dimensional space.

### Embeddings

- **Definition**: Numerical representations of words or phrases in a continuous vector space.
- **Function**: Embeddings allow us to find similarities and relations between words.
- **Lookups**: Enable tracking of semantic similarity by measuring distances between vectors.

### Pretrained Models and Fine-Tuning

- **Pretrained Models**: Models trained on large datasets that can understand general language patterns.
- **Fine-Tuning**: Refining these models by adding domain-specific training utterances.
- **Benefits**:
  - Improved accuracy in specific use cases.
  - Reduced training time compared to building models from scratch.

---

## Why Good Intent Design Is Important

Effective intent design enhances the performance of conversational agents by improving intent classification and maintenance.

### Intent Classification

- **Definition**: The process of categorizing user inputs into predefined intents.
- **Importance**: Accurate classification ensures appropriate responses and actions.
- **Nature**: It's a classification problem, not an understanding one.

### Best Practices for Intent Design

1. **Well-Defined Intents**: Each intent should have a clear focus and purpose.
2. **Singular Linguistic Focus**: Intents should be unique and not overlap with others.
3. **Understanding Variations**: Recognize that there are multiple ways to express the same intent.
   - Example: "Please reset my password" vs. "I can't log in to my account."
4. **Avoid Overlapping Intents**: Prevent confusion by ensuring intents are linguistically distinct.
5. **Refactoring**: Be willing to reorganize intents as needed based on testing and user interactions.

---

## Partitioning Intents and Skills

Organizing intents and skills effectively leads to better model performance and easier maintenance.

### Linguistic Spacing of Intents

- **Concept**: Intents should be as "linguistically spaced" as possible.
- **Focus**: Emphasize what makes an intent unique.
- **Use Cases**: Think of intents as mapping directly to specific user needs or scenarios.

### Skill Partitioning

- **Definition**: Dividing skills (groups of intents) based on common themes or functionalities.
- **Benefits**:
  - Easier development and reuse.
  - Efficient digital assistant routing.
- **Approach**:
  - Focus on commonality such as use case or linguistic patterns.
  - Ensure each skill is unique compared to others.

- **Examples**:
  - **Well-Partitioned Skills**:
    - Salary inquiries
    - Medical coverage details
    - Company car policies
  - **Poorly Partitioned Skills**:
    - Mixing unrelated topics like vacation policies and company history.

---

## Enhancing the NLP Model

Improving the model involves understanding its limitations and implementing strategies to overcome common issues.

### Unresolved Intent

- **Definition**: A special intent representing inputs that don't match any defined intents.
- **Usage**:
  - Typically doesn't require training utterances.
  - Helps handle out-of-domain utterances gracefully.
- **Exception**: May need training utterances if the digital assistant should avoid responding to certain inputs.

### Understanding the Model

- **Visualization**: If possible, visualize the representation of utterances to understand model behavior.
- **Testing**: Regularly test the model to identify areas of confusion or misclassification.

### Common Pitfalls

1. **Overlapping Intents**:
   - Makes it hard for the model to classify accurately.
   - Leads to frequent disambiguation requests.
2. **Formulaic and Overfitting**:
   - Lack of variation in training data causes the model to perform poorly on real-world inputs.
3. **"Big Bucket" Intents**:
   - Generic intents that cover too many scenarios.
   - Relying on entities to derive meaning can be unreliable.
   - Better to create specific intents for distinct actions.

---

## Conclusion

Encoding words as numbers is a foundational aspect of NLP that enables machines to process and interpret human language. Good intent and entity design are crucial for building effective conversational agents. By focusing on unique linguistic features, properly partitioning intents and skills, and avoiding common pitfalls, developers can create NLP models that are both robust and user-friendly.

# Best Practices for Designing Utterances and Entities in NLP

## Table of Contents

1. [Introduction](#introduction)
2. [Best Practices for Designing Utterances](#best-practices-for-designing-utterances)
   - [Unique and Distinct Utterances](#unique-and-distinct-utterances)
   - [Natural Variance](#natural-variance)
   - [Grammatically Complete and Correct Sentences](#grammatically-complete-and-correct-sentences)
   - [Quality over Quantity](#quality-over-quantity)
3. [Approaches for Creating Utterances](#approaches-for-creating-utterances)
   - [Manual Creation](#manual-creation)
   - [Data Manufacturing](#data-manufacturing)
   - [Automated Generation](#automated-generation)
   - [Mixed Approach](#mixed-approach)
4. [Crowdsourcing with Data Manufacturing](#crowdsourcing-with-data-manufacturing)
   - [Benefits of Crowdsourcing](#benefits-of-crowdsourcing)
   - [Implementing in Oracle Digital Assistant](#implementing-in-oracle-digital-assistant)
5. [Testing Strategies for NLP Models](#testing-strategies-for-nlp-models)
   - [Benefits of Solid Testing](#benefits-of-solid-testing)
   - [Types of NLP Tests](#types-of-nlp-tests)
   - [Test Suites](#test-suites)
6. [Conversational AI and Entities](#conversational-ai-and-entities)
   - [Machine Learning in Conversational AI](#machine-learning-in-conversational-ai)
   - [Entity Extraction and Slot Filling](#entity-extraction-and-slot-filling)
7. [Entities in Oracle Digital Assistant](#entities-in-oracle-digital-assistant)
   - [Types of Entities](#types-of-entities)
   - [Entity Properties](#entity-properties)
8. [Best Practices with Composite Bag Entities](#best-practices-with-composite-bag-entities)
   - [Advantages of Composite Bags](#advantages-of-composite-bags)
   - [Entity Event Handlers](#entity-event-handlers)
9. [Best Practices with Other Features](#best-practices-with-other-features)
   - [DATE_TIME Entity Properties](#date_time-entity-properties)
   - [Value List and ML Entities](#value-list-and-ml-entities)
10. [Conclusion](#conclusion)
11. [References](#references)

---

## Introduction

Designing effective utterances and entities is pivotal in building robust Natural Language Processing (NLP) models for conversational AI applications. This document provides best practices, approaches for creating utterances, testing strategies, and insights into entity management within Oracle Digital Assistant.

---

## Best Practices for Designing Utterances

Crafting high-quality utterances enhances the NLP model's ability to understand and classify user inputs accurately.

### Unique and Distinct Utterances

- **Focus on the "Sweet Spot"**: Ensure each utterance is specific to an intent without overlapping with others.
- **Understand Boundaries**: Be clear about what each intent covers to prevent ambiguity.
- **Avoid Repetition**: Duplicate phrases can skew the model's understanding.

### Natural Variance

- **Vary Structure and Focus**: Use different sentence structures and emphases.
- **Provide Variations of Terms**: Include synonyms and alternative expressions to enrich context.
- **Identify Different Classes of Sentences**: Incorporate questions, statements, commands, etc.

### Grammatically Complete and Correct Sentences

- **Contextual Learning**: The model learns from the context provided by complete sentences.
- **Avoid Training Typos**: No need to include misspellings or grammatical errors; the model generalizes from correct usage.

### Quality over Quantity

- **Balanced Dataset**: Keep the number of utterances roughly balanced between intents.
- **Incremental Growth**: Start with 30-40 utterances per intent; increase to 80-100 for production.
- **Avoid Skewed Results**: Ensure that certain phrases or words are not overrepresented in one intent.

---

## Approaches for Creating Utterances

Different methods can be employed to generate utterances for training NLP models.

### Manual Creation

- **Quick Start**: Easy to begin with and allows for immediate development.
- **Best Practices Application**: Easier to ensure quality and adherence to guidelines.
- **Limitations**: May be biased by the developer's perspective and requires time for curation.

### Data Manufacturing

- **Crowdsourcing**: Engaging external contributors to generate diverse utterances.
- **Quality Control**: Depends on the crowd's understanding and adherence to instructions.
- **Augmentation**: Useful for expanding and diversifying the dataset.

### Automated Generation

- **Not Recommended for Intents**: Tends to produce formulaic and overfitted utterances.
- **Behind the Scenes**: Some platforms already perform automatic variations internally.
- **Use with Caution**: May not reflect natural language use.

### Mixed Approach

- **Combining Methods**: Start with manual creation and augment with crowdsourcing.
- **Speed and Diversity**: Balances quick development with a rich dataset.
- **Avoids Bottlenecks**: Ensures continuous progress without overloading any single method.

---

## Crowdsourcing with Data Manufacturing

Utilizing crowdsourcing can significantly enhance the variety and naturalness of utterances.

### Benefits of Crowdsourcing

- **Real-World Language**: Captures how different people might naturally express intents.
- **Diverse Perspectives**: Reduces developer bias by incorporating varied linguistic styles.
- **Scaling**: Allows for rapid expansion of the dataset.

### Implementing in Oracle Digital Assistant

- **Data Manufacturing Jobs**: Create paraphrasing, annotation, and validation tasks.
- **Sharing Jobs**: Generate a URL to distribute the task to crowd workers.
- **Multiple Jobs**: Consider creating several smaller tasks to prevent worker overload.

---

## Testing Strategies for NLP Models

A solid testing strategy ensures that the NLP model performs reliably across various scenarios.

### Benefits of Solid Testing

- **Identifying Impact**: Recognize how changes in utterances affect the model.
- **Consistency**: Provides a reproducible baseline for comparison over time.
- **Continuous Improvement**: Helps measure whether the model is becoming smarter.

### Types of NLP Tests

1. **Positive (In-Domain) Tests**:
   - Test utterances that should resolve to specific intents.
   - Example: "Can I order a pizza?" for the "Order Pizza" intent.

2. **Negative (Out-of-Domain) Tests**:
   - Utterances that should not match any intent.
   - Examples:
     - Out-of-domain: "You threw out the pizza, that's totally out of order."
     - Out-of-scope: "I want to order a new BMW."
     - Random: "The cookie cutter cuts cookies."
     - Neighbor: Utterances from other skills that should not resolve in the current context.

### Test Suites

- **Skill-Level Utterance Tester**:
  - Provides detailed test results.
  - Allows comparison of runs over time.
- **Digital Assistant-Level Utterance Tester**:
  - Defines the context in which an intent should be resolved.
  - Useful for end-to-end testing across multiple skills.

---

## Conversational AI and Entities

Understanding the role of entities is essential in building conversational AI systems.

### Machine Learning in Conversational AI

- **Artificial Intelligence Discipline**: Conversational AI is a branch of AI focusing on dialogue systems.
- **Machine Learning Models**: Uses NLP and Named Entity Recognition (NER) to process user inputs.
- **Intent Detection and Entity Extraction**: Determines what the user wants and extracts relevant information.

### Entity Extraction and Slot Filling

- **Entities**: Extract specific pieces of information from user inputs (e.g., dates, locations, names).
- **Slot Filling**: Stores extracted entities in predefined variables for use in the conversation.
- **Conversation Flow**: Determines the order in which the bot asks for information.

---

## Entities in Oracle Digital Assistant

Oracle Digital Assistant offers various types of entities to manage user inputs effectively.

### Types of Entities

1. **System Entities**:
   - Built-in entities like `DATE_TIME`, `NUMBER`, `CURRENCY`, `EMAIL`, etc.
   - Ready to use without configuration.

2. **Custom Entities**:
   - **Value List**: A list of predefined values with optional synonyms.
   - **Regular Expressions**: Patterns to match specific formats (e.g., license plates).
   - **Derived**: Entities derived from other entities.
   - **Dynamic**: Value lists that can be updated at runtime.
   - **Machine Learning (ML) Entities**: Uses models to identify entity values, including unknown values.
   - **Composite Bags**: Groups multiple entities into a single business object.

### Entity Properties

- **Common Properties**:
  - Name, description, prompts, and whether multiple values are allowed.
  - Disambiguation settings for handling ambiguous inputs.
- **Specific Properties**:
  - **Value Lists**: Fuzzy matching, value translations, prefixes/postfixes.
  - **Composite Bags**: Out-of-order extraction, extraction rules, prompt conditions.
- **System Entities**:
  - No configurable properties but can be wrapped in composite bags for additional control.

---

## Best Practices with Composite Bag Entities

Composite bags are powerful tools for managing complex entities.

### Advantages of Composite Bags

- **Simplifies Dialog Design**: Manages multiple entities within a single dialog flow component.
- **Versatility**: Can handle validation, dependencies, and complex business logic.
- **Out-of-Order Extraction**: Allows users to provide information in any order.
- **Error Handling**: Provides mechanisms for validation errors and prompts.

### Entity Event Handlers

- **Purpose**: Extend the capabilities of composite bags beyond default behaviors.
- **Complex Validation**: Implement advanced validation rules not possible with standard expressions.
- **Backend Integration**: Perform backend checks during entity resolution.
- **Referencing Other Bags**: Allows composite bags to interact with each other.

---

## Best Practices with Other Features

Additional considerations when working with entities.

### DATE_TIME Entity Properties

- **Date Ambiguity**:
  - Phrases like "I want to book a flight for Monday" can be ambiguous.
  - Use the Ambiguity Resolution Rule to specify `Past`, `Future`, or `Nearest`.
- **Locale Consideration**:
  - Be aware of date formats (e.g., MM/DD/YYYY vs. DD/MM/YYYY) based on user locale.

### Value List and ML Entities

- **Value List Entities**:
  - Always include synonyms to capture different expressions of the same value.
- **Machine Learning Entities**:
  - Use when it's impractical to list all possible values.
  - Extracts both known and unknown values.
  - Requires training with annotated utterances.

---

## Conclusion

Designing utterances and entities with best practices in mind significantly enhances the effectiveness of NLP models in conversational AI. By employing strategies like natural variance, balanced datasets, and rigorous testing, developers can build more robust and user-friendly applications. Utilizing features like composite bag entities and crowdsourcing further refines the model's capabilities, ensuring it meets real-world user needs.
Here's a summary of the key concepts in fine-tuning routing, smart dialog configuration, channel integration, and web widget customization for Oracle Digital Assistant (ODA):

### Fine-Tuning Routing
Routing in a digital assistant uses confidence thresholds to determine the best match for user intents and skills, balancing user experience and accuracy.

- **Routing Parameters**:
  - **Confidence Threshold**: Sets the minimum score (0–1 scale) needed for a skill or intent match.
  - **Win Margin**: Sets the margin a skill or intent must exceed over others to prevent ambiguity.
  - **Consider All Threshold**: Defines the threshold where the assistant considers multiple skills as potential matches.

### Examples of Routing Parameters
For example, with a **Confidence Threshold of 40%** and **Win Margin of 10%**, if Skill A has a score of 78% and Skill B has 69%, Skill A is selected due to the higher score, clearing the win margin threshold.

### Smart Dialog Configuration
Customizable prompts and settings manage user interactions, including how the assistant handles interruptions, flow changes, and resumes.
- **Interrupt Prompt Confidence Threshold**: Adjusts how often the assistant asks clarifying questions.
- **Skill Settings**: Skills can be enabled, exposed, or grouped for contextual routing. Grouped skills treat related skills as "in context."

### Conversation Tester
The conversation tester allows developers to simulate user interactions, inspect variables, and understand routing decisions. Tabs include:
- **Dialog Flow**: Shows dialog states, variables, and values.
- **Routing**: Displays confidence scores and rules.
- **JSON**: Shows the raw payload exchanged between the assistant and client.

### Channels in Oracle Digital Assistant
Channels are adapters that connect digital assistants to messaging platforms or endpoints, categorized as:
- **User Channels**: Enable user interactions via messengers like Facebook Messenger, Slack, Microsoft Teams, Twilio, and more.
- **Agent Integrations**: Integrate with Oracle B2C, B2B, or third-party agent systems.
- **External Events**: Include application-initiated conversations or events.

Channels support message format conversions, and custom channels can be built with webhooks.

### Web Channels & SDK Integration
Oracle Web SDK integrates a digital assistant into a web application, providing:
- **Declarative Configuration**: Includes zero-downtime configuration, access control, domain allowlisting, JWT tokens, and secret keys for secure client authentication.
- **Feature Flags**: Enable/disable messenger features like a "Clear Message" button or speech recognition.
- **Customizable Look & Feel**: Modify colors, fonts, themes, and icons with CSS.
- **Initial Welcome Messages**: Display an introductory message when users load the page.

### Adding a Web Widget
To add the ODA web widget:
1. Copy `web-sdk.js` and `settings.js` from the SDK to your site.
2. Configure the widget through an external configuration file for easier customization.
3. Options include headless mode, page load chat window, and partial message display via a known delimiter.

This configuration enables seamless integration with ODA and customization for a tailored user experience across multiple messaging platforms and web pages.

In Oracle Digital Assistant (ODA), **Resource Bundles** are used to manage the text responses for digital assistants and skills, enabling consistent messaging across languages and channels. Here’s a breakdown of their purpose and functionality:

### Key Functions of Resource Bundles
1. **Centralized Message Management**: Resource bundles store all text responses, prompts, and messages outside the source code, allowing for easy updates and changes without altering the code itself.
2. **Multilingual Support**: Essential for creating multilingual digital assistants, resource bundles allow for adaptive responses across multiple languages and channels.

### Organizing Resource Bundles
Resource bundles are organized into categories:
- **Default Bundle**: Contains messages for the base language.
- **User-Defined Bundles**: Specific to skills, supporting intents, Q&A, and other skill-related messages.

### Managing Entries in Resource Bundles
- **Keys**: Unique identifiers for each message string, enabling easy reference.
- **Text**: The actual message displayed to the user.
- **Annotations**: Provide hints or context for translators, copywriters, or developers.

### Best Practices for Resource Bundle Keys
- **Unique Naming**: Ensure key names are unique within each skill.
- **Contextual Naming**: Include context in the key names, such as "prompt," "error," or "label," for better organization and tracking.

### Views in the Message Bundle Panel
- **View by Key**: Shows translation strings for each key, useful for comparing translations across languages.
- **View by Language**: Lists all keys for a language, allowing easy searching and editing of messages.

### Multilingual Support and Translation
Oracle Digital Assistant can detect user language and adapt responses accordingly, supporting both **native language training** and **translation services**:

1. **Native Language Support**:
   - **Primary Language Training**: Train the assistant in the primary language, with secondary languages added later.
   - **Zero-Shot and Few-Shot Training**: Start with the primary language (zero-shot) and add specific phrases for secondary languages (few-shot) to improve understanding.
   - **Entity Translation**: Translate value list and dynamic entities to ensure relevant values are available in all languages.

2. **Translation Services**:
   - Supported translation APIs, including OCI Language, Google Translation API, and Microsoft Translate, enable translation for skills not natively supported.
   - Configure translation in **Digital Assistant Settings** for supported languages.

### Choosing Between Native Language Support and Translation Services
It’s crucial to use a consistent approach across all skills in a digital assistant:
- **Native Language Support**: Recommended where possible for high accuracy. All skills must support the same languages.
- **Translation Services**: Useful for skills not natively supported, with automatic language detection and translation.

### Detecting and Using Language in Skills
- **Detect Language Component**: Sets the `profile.languageTag` variable based on the detected user language.
- **Profile.LanguageTag**: This variable stores the two-letter country code for the user language and is used to access the correct resource bundle.

### Customizing the Web SDK for Multiple Languages
For web applications, the **Oracle Web SDK** allows integration of resource bundles and translation capabilities. Features include:
- **Message Customization**: Configure messages to appear as per language and channel requirements.
- **Look & Feel Adjustments**: Customize themes and colors to align with different language requirements.
  
### Summary of Benefits for Businesses
A well-configured resource bundle strategy enables Oracle Digital Assistants to serve multiple languages, handle regional variations, and keep data secure in the Oracle Cloud. This approach improves user experience and ensures seamless, multilingual interactions.
