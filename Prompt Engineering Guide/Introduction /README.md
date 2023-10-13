
# Introduction to Prompt Engineering

Gen AI is a rapidly evolving field and in that Prompt Engineering is a relatively new discipline for developing and optimizing prompts to efficiently use Large Language Models (LLM's). 

Reasons why Prompt Engineering is important

  1. Improve the answers that you get from LLM
  2. Provide context to LLM to better address your question

## LLM Settings

  1. <b>Temperature</b> - Lower the Temperature, the more deterministic the results in the sense that the highest probable next token is always picked. Increasing temperature could lead to more randomness thus encouraging more diverse and creative outputs. Lower the temperature for fact-based QA and increase the temperature for creative tasks like Poem Generation
  2. <b>Top_P</b> - A Sampling technique with temperature called nucleus sampling. You can control how deterministic the model is at generating a response. Keep low for factual, increase for creative tasks

  3. <b>Max Length </b> - Manage the number of tokens the model generates. Helps prevent long or irrelevant responses and control costs
  4. <b>Stop Sequences </b>- A 'stop sequence' is a string that stops the model from generating tokens. Also helps to control the length and structure of the model's response
  5. <b>Frequency Penalty </b> - The 'frequency penalty' applies a penalty on the next token proportional to how many times that token already appeared in the response and prompt
  6. <b>Presence Penalty </b>- The 'presence penalty' also applies a penalty on repeated tokens but, unlike the frequency penalty, the penalty is the same for all repeated tokens. A token that appears twice and a token that appears 10 times are penalized the same. Helps prevent repeating phrases too often. Increase it to generative creative response and lower for focused content

Note- General recommendation is to alter Temperature or Top_p, not both. Similarly alter the Frequency or Presence Penality, not both
