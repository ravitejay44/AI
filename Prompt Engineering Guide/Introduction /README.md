
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

**Note**- General recommendation is to alter Temperature or Top_p, not both. Similarly alter the Frequency or Presence Penality, not both


## Basics of Prompting

```
<Question>?
```

or

```
<Instruction>
```

or

```
Q: <Question>?
A:
```

Few-shot Prompting for QA format

```
Q: <Question>?
A: <Answer>
Q: <Question>?
A: <Answer>
Q: <Question>?
A: <Answer>
Q: <Question>?
A:
```

_Prompt:_

```
I like this movie // Positive
I dont like the cake // Negative
This is horrible // Negative
I love this house // 
```

_Output:_

```Positive```

## Elements of a Prompt

Prompt contains any of the following elements:
* **Instruction** - Task or instruction you want the model to perform
* **Context** - Additional context for LLM to provide better response
* **Input Data** - Input or question we are interested to find a response for
* **Output Indicator** - Type or format of the output

## Tips for Designing Prompts

* **Start Simple** - It is a iterative process so keep it simple. Break bigger tasks to simpler subtasks for better results
* **Instruction** - Instruct the model what you want by saying "Write". "Classify", "Translate". "Order" etc., Be more specific and relevant to the context. Separate the instruction and context with some clear separator like '###'
  
    _Prompt:_

    ```
    ### Instruction ###
    Translate the text below to Spanish:
    Text: "hello!"
    ```

    _Output:_

    ```¡Hola!```
  
* **Specificity** - Be very specific about the instruction and task. The more descriptive and detailed the prompt is, the better the results
* **Avoid Impreciseness** - Be specific and direct

  _Not Specific Enough:_

  ```
  Explain the concept prompt engineering. Keep the explanation short, only a few sentences, and don't be too descriptive.
  ```

  _Specific:_

  ```
  Use 2-3 sentences to explain the concept of prompt engineering to a high school student.
  ```
  
* **To do or Not to do** - Avoid saying what not to do but say what to do instead

## Task Specific Prompts

1. **Text Summarization**

   _Prompt:_

   ```
   Antibiotics are a type of medication used to treat bacterial infections. They work by either killing the bacteria or preventing them from reproducing, allowing the body’s immune system to fight off the infection. Antibiotics are usually taken orally in the form of pills, capsules, or liquid solutions, or sometimes administered intravenously. They are not effective against viral infections, and using them inappropriately can lead to antibiotic resistance.
   Explain the above in one sentence:
   ```

   _Output:_
   ```
   Antibiotics are medications used to treat bacterial infections by either killing the bacteria or stopping them from reproducing, but they are not effective against viruses and overuse can lead to antibiotic resistance.
   ```
   
3. **Information Extraction**

   _Prompt:_

   ```
   Author-contribution statements and acknowledgements in research papers should state clearly and specifically whether, and to what extent, the authors used AI technologies such as ChatGPT in the preparation of their manuscript and analysis. They should also indicate which LLMs were used. This will alert editors and reviewers to scrutinize manuscripts more carefully for potential biases, inaccuracies and improper source crediting. Likewise, scientific journals should be transparent about their use of LLMs, for example when selecting submitted manuscripts.
Mention the large language model based product mentioned in the paragraph above:
   ```
