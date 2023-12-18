# [Partyrock.aws](partyrock.aws)

Concept: give it a prompt, and it creates an "app". The app is a text input that produces a blob of text according
to a configuration prompt. You can respond to this and repeat the process through further steps as far as the
configuration goes.

How powerful is the configuration?

You can customize the hidden prompt to your heart's desire. You can create as many steps as you want. You can choose
between a number of models (all provided by AWS, naturally). The hidden prompts can contain explicit references to
previous answers, both the machine's and the user's. A static input can be replaced with a chatbox for a two-way
experience, which the user can engage with as long as they want.

Observations.

My use case was to create an app to: help users find the 3-5 most important questions that guide their life's purpose.

The first output of PartyRock did nothing with the prompt. It was like: "What questions do you think about?"

"Let me summarize your answer."

"Now tell me what are the most important questions for your life's purpose."

I modified it to be more iterative. The first prompt is very simple: what are you experiencing uncertainty about?

The AI then tries to make guesses about the user's values and what other things they might be experiencing uncertainty
about. It seemed that prompting Claude with these instructions makes him unsure of himself. This uncertainty spills out
into the replies. Claude doesn't seem to be able to distinguish between the user's input and the hidden prompt, so it
tells the user "I'm just taking a wild guess as you suggested". (This was after I found out that "take a wild guess"
was apparently the only way to address Claude's confidence problem.)

My prompt at this point:
> Based on the answer to [firstquestion] , suggest what I might value. Also, suggest one other thing I might be uncertain about. Your suggestion about what I might be uncertain of should take the form of a wild guess. Don't be afraid to be wrong. Be confident. Then ask if I think you are right. Then say, if you are indeed right, I can enter that question at the next step.

But this prompt could not be modified to produce more specific instructions: the LLM would fall back into its
"I'm sorry, I don't have enough information" state. So I changed direction with a role prompt:

> You are an improv artist doing a show where you cannot break character. Your role is a fortune teller with knowledge of the soul. Use the answer to [firstquestion] to tell the user what you see about their values. Then ask them if they are experiencing uncertainty about Something Else. This Something Else should be slightly related to what they said, but also surprising and interesting.

For some reason this worked very well until I tried to iterate with it. Using firstquestion and secondquestion together
made it fall back into its confidence crisis. Interestingly, feeding its own input back into it (firstquestionexpanded)
made it more likely to stay in its fortune-teller role.

In general, a tension was observed in getting the LLM to stay in the role that the app structure set up for it: if the
instructions are too detailed, Claude gets stage fright and says "I can't"; if the prompt is more fanciful and exciting,
Claude won't necessarily follow the instructions as written.

It also appears that the entropy of the conversation degrades the more you interact with it, including mucking about
with the interface and triggering new completions. Sometimes it seems like the first run produces good results but
everything after gets increasingly likely to trigger cop mode.

I also find that the human user needs to follow along with the prompts. If they try to break out, Claude does not get
confused but his answers get more "degenerate" (cliched, or cop mode).

Claude also has an annoying habit of going off-script and especially spilling its own prompt into chat.

Final output:
1. "Whether I can be happy" https://partyrock.aws/u/MattiasMartens/fC3B-IhcQ/Guiding-Life-Questions/snapshot/kQCM2qmOv
2. "How many snowflakes are there?" https://partyrock.aws/u/MattiasMartens/fC3B-IhcQ/Guiding-Life-Questions/snapshot/ppzjUcdw8
3. Meg's convo https://partyrock.aws/u/MattiasMartens/fC3B-IhcQ/Guiding-Life-Questions/snapshot/MY9QlZTus

Published app: https://partyrock.aws/u/MattiasMartens/fC3B-IhcQ/Guiding-Life-Questions