# [Prompt Structure in Conversations with Generative AI](https://www.nngroup.com/articles/ai-prompt-structure/)

- Prompt request formats:
  1. Question
  2. Implicit request ("I need...")
  3. Commands
  4. Incomplete sentence (this one is my favourite)

> As explained in our article on AI-conversation types, funneling conversations start with vague, underspecified prompts
and require a lot of back-and-forth between the user and the bot., as the user is using subsequent prompts to articulate
some of their requirements.

- Suggestion of UX for LLMs: "apple-picking", where the user can pick a fragment of an LLM's reply and continue the
  conversation from there.

> **not all prompts need framing**. When the information need is broad and is centered on learning, framing may not be necessary. It can be okay to start with an unframed question and then use the bot’s answer to determine the best direction that the conversation should take.


- ChatGPT GPT feature is a built-in pre-prompting tool: 'The GPT feature of ChatGPT also allows users to create customized agents (or GPTs) that always consider a task-specific set of instructions as part of prompt framing.'
- Perplexity AI copilot does a type of reverse prompting, generating questions to clarify a prompt before answering: "_Perplexity AI’s Copilot feature attempts to gather neccessary framing details after the user submits their prompt but before producing output. In this case, Copilot requested the occasion when the user asked for help finding a gift for a friend._"
	- This type of thing is helpful with "can you" questions, where the AI may not have enough information to begin performing the task in its first answer.
- "Bots should attempt to make _Give me more_ prompts more specific by **asking framing questions and suggesting followup prompts** that help users define their query."
- "Tools need to **distinguish fillers from information requests** to prevent users from feeling flooded with unwanted information."

> The user’s information need is like an iceberg. The visible tip of this iceberg is the direct prompt, while the submerged layers are the critical mass that gives the prompt its true shape and direction. The more of these submerged layers is revealed in the prompt, the more effective the AI can be in meeting the user’s information need.
- "Tacit knowledge!" although in this case more like "Tacit need"



Further reading from the same source:
https://www.nngroup.com/articles/generative-ai-diary/
https://www.nngroup.com/articles/ai-bot-comparison/
https://www.nngroup.com/articles/AI-conversation-types/