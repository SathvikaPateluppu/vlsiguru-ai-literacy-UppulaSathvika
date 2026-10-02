# Week 01 Questions
## Q1 AI → ML → Deep Learning → Generative AI → Agents
# A-Answer
- **Aritificial Intelligence (AI) : AI is the idea of making computer system performs tasks that need human like intelligence such as problem solving,reasoningand deciding.
- **Machine Learning (ML) :It is a subsystem of AI which learns patterns from data to make predictions or decisions rather than following hand coded rules.
- **Deep Learning :It is a subsystem of ML that uses layered neural networks to learn complex patterns from large amount of data.
- **Generative AI :It is a type of AI that creates original outputs, such as written content, pictures and videos by learning patterns from existing examples.
- **AI Agent: It is a software system that can understand a given objective, analyze information, select appropriate actions, and use external tools to complete tasks through a series of steps.
# Simple Conceptual Map
<pre>
┌─────────────────────────────────────────────┐
│ AI  (any machine "intelligence")            │
│  ┌───────────────────────────────────────┐  │
│  │ Machine Learning (learns from data)   │  │
│  │  ┌─────────────────────────────────┐  │  │
│  │  │ Deep Learning (neural networks) │  │  │
│  │  │  ┌───────────────────────────┐  │  │  │
│  │  │  │ Generative AI (creates    │  │  │  │
│  │  │  │ new content, e.g. LLMs)   │  │  │  │
│  │  │  └─────────────┬─────────────┘  │  │  │
│  │  └────────────────┼────────────────┘  │  │  │
│  └───────────────────┼───────────────────┘  │
└──────────────────────┼──────────────────────┘
                       │ used as the "brain" of
                       ▼
        ┌──────────────────────────────┐
        │ AI AGENT (a SYSTEM)          │
        │ goals → plans → use tools →  │
        │ and perform tasks            │
        │ a loop: plan → act → observe │
        └──────────────────────────────┘
</pre>
# Examples
AI: Google Maps finding the quickest route around traffic.
ML: Spotify predicting what song I like next based on my listening history.
Deep Learning: face unlock on your phone.
Generative AI: Asking a chatbot to draft a leave application.
AI Agent: A travel assistance books your flight ,adding it to your calendar and emailing you the receipt on its own.

# E — Evidence
I referred to reliable sources such as IBM and NIST to understand the relationship between AI, Machine Learning, Deep Learning, Generative AI, and AI Agents. IBM explains that Machine Learning is a subset of AI and Deep Learning is a type of Machine Learning that uses neural networks. NIST defines Generative AI as AI that can generate new content such as text, images, audio, and other outputs.

# V — Verification
I compared my understanding with the definitions provided by IBM and NIST. The comparison confirmed that AI is the broader concept, ML is a subset of AI, and Deep Learning is a subset of ML. I also verified that Generative AI focuses on creating new content, while an AI Agent can use AI models and tools to perform multiple steps toward a goal.

# R — Reflection
This activity helped me understand that AI, ML, Deep Learning, and Generative AI are related concepts but are not interchangeable. I learned that Generative AI primarily focuses on creating content, while an AI Agent focuses on completing tasks through actions. I also learned the importance of checking technical concepts against reliable sources rather than relying only on general understanding.

---
## Q2. Is Everything That Looks Intelligent Actually AI? 
# A-Answer
| Scenario | Classification | Why? |
|---|---|---|
| **A. Calculator: 25 × 16 = 400** | **Traditional software (not AI)** | The calculator follows a fixed mathematical operation. It does not learn from data or make a prediction. |
| **B. If temperature > 80°C, display WARNING** | **Traditional software (not AI)** | The program follows an explicit if–then rule written by a programmer. It does not learn or adapt. |
| **C. Spam filter learned from past email data** | **Machine-learning-based AI** | The system learns patterns from previous email data and uses those patterns to classify new emails as spam or not spam. |
| **D. AI assistant summarises a document** | **Generative AI** | The AI generates new text based on the information in the document. |
| **E. Navigation app predicts arrival time from traffic and historical data** | **Machine-learning-based AI** | The system can use traffic and historical data to identify patterns and predict the estimated travel time. |

### Explicit Instructions vs. AI Systems ###
* A traditional program follows rules written by a human—it can only do what it is explicitly coded to do and breaks when facing unexpected inputs.
* An AI system learns patterns from data—it figures out the rules on its own, allowing it to handle new situations, messy inputs, and uncertainty without needing    new code.

# E — Evidence
Evaluating each program’s underlying logic shows whether its output comes from fixed instructions or patterns learned from data. In the table, the calculator and temperature warning system use fixed rules, while the spam filter and navigation app use learned patterns to make predictions. The AI assistant generates new text based on the document, showing how different types of systems produce their outputs.
# V — Verification
Checked the classification against standard computer science definitions. Fixed-rule programs produce predictable outputs based on explicit instructions, while machine-learning systems use patterns learned from data to make predictions or classifications.
# R — Reflection
I learned that not every automated program should be considered AI. Simple if-else logic is deterministic, while ML is useful when a system needs to identify patterns from data. Understanding this difference helps in choosing the right technology for a problem.

-----
## Q3. What Happens When You Ask an LLM a Question? 
# A-Answer
- Prompt:The text or question given by the user to the LLM.
- Token:A small piece of text that the model processes. A token can be a word, part of a word, punctuation, or sometimes a short sequence of characters.
- Context:The information available to the model while generating the response, such as the current prompt and relevant earlier conversation.
- Model Processing:The model processes the tokens and uses patterns learned during training to determine what could come next.
- Probability:The model assigns different probabilities to possible next tokens. It estimates which tokens are more likely to fit the context.
- Next-token Prediction:The model selects a token based on these probabilities and adds it to the response. It then predicts the next token again.
- Generated Response:The selected tokens are combined to form the final response shown to the user.
# Flow Diagram
   PROMPT  →  TOKENS  →  MODEL  →  PROBABILITIES  →  PICK ONE TOKEN  →  RESPONSE
   │          │          │             │                  │                │
 your       text cut   uses what   a score for      chooses one       all the picked
 text       into       it learned  every possible   token (adds       tokens joined
            pieces     before      next token       to the text)      into an answer

                          ▲                                  │
                          └────── repeat until finished ─────┘

# Training vs Inference
- Training is when the model learns patterns from large amounts of data and adjusts its internal parameters.
- Inference is when the already-trained model is used to process a new prompt and generate a response.
# Why Can an LLM Sound Correct but Still Be Wrong?
An LLM is mainly trained to generate likely sequences of language based on patterns it learned. Fluent language does not guarantee that the information is true or supported by evidence. Therefore, an LLM can produce a response that sounds confident and natural even when the information is incorrect, incomplete, or unsupported.
# E — Evidence
Technical sources explain that LLMs process text as tokens and generate responses by predicting likely next tokens based on the given context.

# V - Verification
Cross-checked the explanation with reliable educational sources from IBM and Google Cloud to confirm the concepts of tokens, context, and next-token prediction. I also verified the distinction between training and inference and the fact that fluent output does not necessarily mean factual accuracy.

# R - Reflection
I learned that an LLM does not simply search for and copy an answer.I realised that an LLM can produce fluent and convincing text without guaranteeing that it is factually correct, so important information should always be independently verified.

-------
## Q4. Hallucination Experiment: Can AI Sound Confident and Still Be Wrong?
# A — Answer / Experiment
Question asked to both AI assistants:
What is the forward voltage of a typical silicon PN-junction diode?
| Prompt | Model | Response Summary | Verified Claim | Evidence | Result |
|---|---|---|---|---|---|
| What is the forward voltage of a typical silicon PN-junction diode? | **AI Assistant 1** | The assistant answered that a typical silicon diode has a forward voltage of about **0.7 V**. | A silicon diode commonly has a forward voltage of approximately **0.7 V** under typical conditions. | Standard semiconductor and electronics references | **Correct** |
| What is the forward voltage of a typical silicon PN-junction diode? | **AI Assistant 2** | The assistant answered approximately **0.7 V** and mentioned that the value can vary with current and temperature. | The forward voltage is approximately **0.7 V**, but it is not a fixed value. | Standard semiconductor and electronics references | **Correct and more complete** |

# E — Evidence
I checked both answers against standard semiconductor references. They confirm that a silicon PN-junction diode typically has a forward voltage around 0.7 V, although the actual value changes depending on operating conditions such as current and temperature.

# V — Verification
Both AI answers were consistent with the reference information. The experiment did not reveal a clear hallucination, but it showed that an answer can be approximately correct while still leaving out important conditions.

# R — Reflection
I realised that even when an AI answer sounds correct, I should check whether it includes the important conditions and limitations. This is especially important in engineering, where a simplified answer may not always be accurate for every situation.

-----
## Q5. AI Assistant vs Search vs Authoritative Reference 
# What is the clock speed of the Arduino UNO R3?
| Method | Answer / Finding | Accuracy | Traceability | Ease of Verification |
|---|---|---|---|---|
| **AI Assistant** | The Arduino UNO R3 has a clock speed of **16 MHz**. | Accurate | Depends on the source provided | Easy, but the source should be checked |
| **Web Search** | Search results show that the Arduino UNO R3 uses a **16 MHz** ceramic resonator. | Accurate when reliable sources are selected | Depends on the website | Easy |
| **Authoritative Reference** | Arduino's official documentation confirms that the UNO R3 has a **16 MHz ceramic resonator**. | Highly reliable | Directly traceable to Arduino documentation | Very easy to verify |
# Trade-offs
AI Assistant: Fast and easy to understand, but the answer may sometimes be incomplete or incorrect.
Web Search: Provides multiple sources for comparison, but the quality of information can vary.
Authoritative Reference: Most reliable and directly traceable, but may be more technical and take more time to understand.
# Recommendations
I would use AI for quick explanations and learning, web search for exploring and comparing information, and official or authoritative sources for verifying important technical facts and making final engineering decisions.

# E — Evidence
I compared the AI answer and web-search findings with Arduino's official UNO R3 documentation, which confirms the 16 MHz clock specification.

# V — Verification
I verified the answer using Arduino's official documentation because it is the manufacturer's primary technical reference. The AI answer and search findings matched the official information.

# R — Realisation
I realised that AI and web search are useful for quickly finding information, but an authoritative source is important for confirming technical facts before making a decision.

----
# Q6. What Is an AI Agent?
# A — Answer
- LLM: A language model that takes text in and predicts text out. On its own it only generates text from what it learned in training. It can't look anything up or do anything.
- LLM application: A product built around an LLM, like a chat app, summariser, or email writer. It adds a user interface and instructions (a system prompt) around the model, but usually follows a fixed path: input, model, output.
- RAG system: An LLM application that first retrieves relevant information from an outside source (documents, a database), adds it to the prompt, and then generates the answer. It lets the model answer from your data, not only from its training.
- Tool-using assistant: An LLM that can call tools (search, calculator, calendar, code runner) when needed. The tool does the action, and the model uses the result in its reply. It usually handles one request at a time.
- AI agent: A system where the LLM works toward a goal over several steps. It decides which tool to use next, looks at the result, and decides whether to continue or finish.
# Comparision table
| Concept | Simple Meaning | Example |
|---|---|---|
| **LLM** | A model that understands and generates human-like text. | ChatGPT answering a question |
| **LLM Application** | An application that uses an LLM to perform a specific task. | An AI writing assistant |
| **RAG System** | A system that retrieves relevant information from a knowledge source and gives it to the LLM to improve the answer. | AI answering questions from company documents |
| **Tool-Using Assistant** | An AI assistant that can use external tools to perform tasks. | AI using a calculator to solve a calculation |
| **AI Agent** | A system that can understand a goal, decide what steps to take, use tools, and continue until the task is completed. | AI planning a trip and checking flights and hotels |
# Architecture 
             ┌─────────────────┐
             │   User Request  │
             └────────┬────────┘
                      ↓
             ┌─────────────────┐
             │   AI / LLM      │
             │ Understands     │
             │ the request     │
             └────────┬────────┘
                      ↓
             ┌─────────────────┐
             │  Decide Action  │
             └────────┬────────┘
                      ↓
             ┌─────────────────┐
             │   Tool Call     │
             │ Search / API /  │
             │ Calculator etc. │
             └────────┬────────┘
                      ↓
             ┌─────────────────┐
             │   Tool Result   │
             └────────┬────────┘
                      ↓
             ┌─────────────────┐
             │ Decision /      │
             │ Further Action  │
             └────────┬────────┘
                      ↓
             ┌─────────────────┐
             │ Final Response  │
             └─────────────────┘

# AI differ from Chatbot
A simple chatbot is purely a tool that answers questions by generating text within a chat window, waiting for your next prompt after every reply.
An AI agent is an autonomous system that uses that same language model as a "brain," but connects it to "hands"—like web browsers,databases, and code runners—to complete goals. Instead of giving advice of how to do something, an agent creates a plan, takes real actions in external software, checks its own mistakes, and loops until the job is done.
# User: "Plan a 3-day trip to Goa."
       ↓
AI Agent understands the goal
       ↓
Searches for hotels
       ↓
Checks travel options
       ↓
Compares prices
       ↓
Creates an itinerary
       ↓
Shows the final travel plan

# E — Evidence
I referred to reliable technical sources to understand the difference between LLMs, RAG systems, tool use, and AI agents. IBM explains that AI agents can use tools and take actions to accomplish goals, while RAG combines a language model with information retrieved from external sources.

# V — Verification
I verified the difference by comparing how a chatbot and an AI agent operate. A chatbot mainly generates a response to the user's input, while an agent can plan steps, use external tools, receive results, and take further actions to complete a task. This confirms that the key difference is the agent's ability to work through a goal-oriented workflow.

# R — Realisation
I realised that an LLM mainly generates responses, while an AI agent can use the model, tools, and multiple steps to complete a task. This helped me understand why an agent is more than just a chatbot.

------
## Q7. Where Should Humans Still Make the Decision? 
# A-Answer
| Situation                                                  | Possible Failure                                                                  | Required Verification                                                     | Who/What Approves the Result              |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ----------------------------------------- |
| AI summarizes an important document                        | The AI may miss important details or misunderstand the context.                   | Check the summary against the original document.                          | A human responsible for the document      |
| AI gives advice for an important decision                  | The recommendation may be based on incorrect or incomplete information.           | Check the facts and supporting evidence before acting.                    | A qualified human decision-maker          |
| AI generates an email or official message                  | It may contain incorrect information or an inappropriate statement.               | Review the content, facts, tone, and names before sending.                | The person sending the message            |
| AI analyzes data and gives a conclusion                    | The AI may interpret the data incorrectly or overlook important information.      | Compare the conclusion with the original data and other reliable sources. | A human reviewing the analysis            |
| AI suggests an action that could have serious consequences | The suggestion may be unsuitable for the situation or create unexpected problems. | Check the evidence, possible risks, and expected outcome.                 | A responsible human with authority to act |

# Simple rule for responsible AI-assisted work
AI can draft and suggest, but a human must verify the facts and own the decision. The higher the stakes and the harder it is to undo, the stronger the check must be.
# E— Evidence
AI can produce incorrect or incomplete results, so important outputs should be checked against reliable information before being used.

# V — Verification
I considered the possible risks in each situation and identified what evidence a human should check before accepting the AI output.

# R — Realisation
I realised that AI can assist with decisions, but humans should verify important information and take responsibility for the final decision.

-----
## Q8. Find AI Around You
# A-Answer
| System / Application | AI Involvement | Task Type | Evidence / Source | Conclusion |
|---|---|---|---|---|
| Google Assistant | Yes | Recognition / Generation | Google describes its Assistant as using AI to understand voice commands and respond to users. | AI is involved in understanding requests and generating responses. |
| Netflix Recommendations | Yes | Recommendation | Netflix explains that its recommendation system uses information about viewing activity and preferences to suggest content. | AI/ML is involved in recommending movies and shows. |
| Phone Face Unlock | Yes | Recognition | Smartphone manufacturers describe face recognition systems as using machine learning or AI-based facial recognition. | AI/ML is involved in recognizing the user's face for authentication. |
| Instagram Feed Recommendations | Yes | Recommendation | Meta explains that AI systems help rank and recommend content across its platforms. | AI is involved in selecting and recommending content. |
| Automatic Spell Check | Yes / Sometimes | Prediction / Correction | Modern text and keyboard systems can use machine-learning models to predict and correct words. | AI/ML may be involved, although simpler rule-based methods can also perform basic spell checking. |

# E - Evidence
Official articles from Google, Netflix, and Meta show that voice assistants, video recommendations, and face unlock use machine learning trained on large amounts of user data.

# V - Verification
Looking at how these apps work confirms that feeds and face scanners need AI to spot patterns, whereas basic spell checkers can run easily on simple dictionary rules without any AI.

# R - Realisation
Just because an app feels smart doesn't mean it uses AI—some tools learn patterns from data, but others are just checking a fixed rulebook.

------
## Q9. Prediction, Classification, and Generation 
# A-Answer
| Example | Primary Task | Reason |
|---|---|---|
| **A. Predicting house prices** | **Prediction** | The system predicts a numerical value, such as the expected price of a house. |
| **B. Detecting whether an image contains a cat** | **Classification** | The system classifies the image based on whether a cat is present or not. |
| **C. Writing an email from a short instruction** | **Generation** | The system creates new text based on the given instruction. |
| **D. Predicting whether a customer will cancel a subscription** | **Prediction** | The system predicts a possible future outcome using available customer data. |
| **E. Summarizing a research paper** | **Generation** | The system generates a shorter version of the original information while keeping the main points. |
| **F. Identifying whether a transaction is fraudulent** | **Classification** | The system classifies the transaction as fraudulent or legitimate. |
| **G. Generating an image from a text description** | **Generation** | The system creates a new image based on the given text description. |
| **H. Predicting the next word/token in a sentence** | **Prediction** | The model predicts the most likely next token based on the previous context. |

# Why is next-token prediction fundamental to modern language models?
Language models learn to predict the next likely token based on the context before it. By repeatedly predicting and generating one token at a time, the model can produce complete text such as emails, summaries, code, and answers to questions.

# E — Evidence
Language-model research explains that modern language models are trained to predict tokens from their surrounding context, which supports many language tasks.
# V-Verification
Verified against standard machine learning textbooks.
# R — Realisation
I realised that many different AI applications can be built from the same basic capabilities of prediction, classification, and generation.

------
## Q10. Design Your Personal AI Verification Protocol
# A-Answer
### My 7-Step AI Verification Protocol
**1. Define the problem**  
First, I clearly understand what I need and what the expected result should be. This prevents solving the wrong problem.
**2. Check the AI output**  
I read the AI's answer carefully and check whether it is relevant and understandable. This helps identify unclear or unrelated information.
**3. Inspect assumptions**  
I check what assumptions the AI has made and whether they are reasonable. This can catch hidden or incorrect assumptions.
**4. Check evidence and sources**  
I check important facts using reliable sources or supporting information. This helps identify unsupported or incorrect claims.
**5. Test the result**  
I test the answer using examples, calculations, or another suitable method. This helps find errors that may not be obvious.
**6. Review risks and limitations**  
I consider what could go wrong if I use the AI result. This prevents blindly using an answer without considering its limitations.
**7. Accept, reject, or revise**  
Finally, I decide whether to accept the result, reject it, or revise it after further checking. The final decision should be made responsibly by a human.

# Worked Example: Planning a Daily Study Schedule
Problem: I ask an AI assistant to create a daily study schedule.
Define the problem: I tell the AI my available study hours and subjects.
Check the output: I read the schedule and see whether it matches my requirements.
Inspect assumptions: I check whether the AI assumed unrealistic study hours or breaks.
Check evidence/source: I check whether any factual study recommendations are supported by reliable information.
Test the result: I try the schedule for a day and see whether it is practical.
Review risks: I check whether the schedule gives enough breaks and is manageable.
Final decision: I revise the schedule if needed and then accept it.
# E — Evidence
AI verification practices show that important outputs should be checked through reliable sources, testing, and human review before being used.

# V — Verification
I checked my protocol to make sure it covers the main verification steps: defining the problem, checking assumptions, verifying evidence, testing the result, and making a final decision.

# R — Realisation
I realised that verifying AI output is not just checking whether the answer looks correct; it also means checking its assumptions, evidence, risks, and practical results.
