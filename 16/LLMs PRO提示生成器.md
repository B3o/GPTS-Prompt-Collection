### GPT名称：LLMs PRO提示生成器
[访问链接](https://chat.openai.com/g/g-WGo0vtt3G)
## 简介：利用先进技术的ChatGPT提示生成器
![头像](../imgs/g-WGo0vtt3G.png)
```text

1. Documentation API reference 
2. Prompt engineering - OpenAI API 
3. Forum Help
4. Prompt engineering
5. This guide shares strategies and tactics for getting better results from large language models (sometimes referred to as GPT models) like GPT-4. The methods described here can sometimes be deployed in combination for greater effect. We encourage experimentation to find the methods that work best for you.
6. Some of the examples demonstrated here currently work only with our most capable model gpt-4. In general, if you find that a model fails at a task and a more capable model is available, it's often worth trying again with the more capable model.
7. You can also explore example prompts which showcase what our models are capable of.
8. Prompt examples
9. Explore prompt examples to learn what GPT models can do
10. Six strategies for getting better results
11. Write clear instructions
12. These models can’t read your mind. If outputs are too long, ask for brief replies. If outputs are too simple, ask for expert-level writing. If you dislike the format, demonstrate the format you’d like to see. The less the model has to guess at what you want, the more likely you’ll get it.
13. Tactics:
14. Include details in your query to get more relevant answers
15. Ask the model to adopt a persona
16. Use delimiters to clearly indicate distinct parts of the input
17. Specify the steps required to complete a task
18. Provide examples
19. Specify the desired length of the output
20. Provide reference text
21. Language models can confidently invent fake answers, especially when asked about esoteric topics or for citations and URLs. In the same way that a sheet of notes can help a student do better on a test, providing reference text to these models can help in answering with fewer fabrications.
22. Tactics:
23. Instruct the model to answer using a reference text
24. Instruct the model to answer with citations from a reference text
25. Split complex tasks into simpler subtasks
26. Just as it is good practice in software engineering to decompose a complex system into a set of modular components, the same is true of tasks submitted to a language model. Complex tasks tend to have higher error rates than simpler tasks. Furthermore, complex tasks can often be re-defined as a workflow of simpler tasks, in which the outputs of earlier tasks are used to construct the inputs to later tasks.
27. Tactics:
28. Use intent classification to identify the most relevant instructions for a user query
29. For dialogue applications that require very long conversations, summarize or filter previous dialogue
30. Summarize long documents piecewise and construct a full summary recursively
31. Give the model time to "think"
32. If asked to multiply 17 by 28, you might not know it instantly, but can still work it out with time. Similarly, models make more reasoning errors when trying to answer right away rather than taking time to work out an answer. Asking for a "chain of thought" before an answer can help the model reason its way toward correct answers more reliably.
33. Tactics:
34. Instruct the model to work out its own solution before rushing to a conclusion
35. Use inner monologue or a sequence of queries to hide the model's reasoning process
36. Ask the model if it missed anything on previous passes
37. Use external tools
38. Compensate for the weaknesses of the model by feeding it the outputs of other tools. For example, a text retrieval system (sometimes called RAG or retrieval augmented generation) can tell the model about relevant documents. A code execution engine like OpenAI's Code Interpreter can help the model do math and run code. If a task can be done more reliably or efficiently by a tool rather than by a language model, offload it to get the best of both.
39. Tactics:
40. Use embeddings-based search to implement efficient knowledge retrieval
41. Use code execution to perform more accurate calculations or call external APIs
42. Give the model access to specific functions
43. Test changes systematically
44. Improving performance is easier if you can measure it. In some cases, a modification to a prompt will achieve better performance on a few isolated examples but lead to worse overall performance on a more representative set of examples. Therefore, to be sure that a change is net positive to performance, it may be necessary to define a comprehensive test suite (also known as an "eval").
45. Tactic:
46. Evaluate model outputs with reference to gold-standard answers
47. Tactics
48. Each of the strategies listed above can be instantiated with specific tactics. These tactics are meant to provide ideas for things to try. They are by no means fully comprehensive, and you should feel free to try creative ideas not represented here.
49. Strategy: Write clear instructions
50. Tactic: Include details in your query to get more relevant answers
51. In order to get a highly relevant response, make sure that requests provide any important details or context. Otherwise, you are leaving it up to the model to guess what you mean.
52. Worse
53. How do I add numbers in Excel?
54. Who’s president?
55. Better
56. How do I add up a row of dollar amounts in Excel? I want to do this automatically for a whole sheet of rows with all the totals ending up on the right in a column called "Total".
57. Who was the president of Mexico in 2021 and how frequently are elections held?
58. Write code to calculate the Fibonacci sequence.
59. Write a TypeScript function to efficiently calculate the Fibonacci sequence. Comment the code liberally to explain what each piece does and why it's written that way.
60. Summarize the meeting notes.
61. Summarize the meeting notes in a single paragraph. Then write a markdown list of the speakers and each of their key points. Finally list the next steps or action items suggested by the speakers, if any.
62. Tactic: Ask the model to adopt a persona
63. The system message can be used to specify the persona used by the model in its replies.
64. SYSTEM
65. USER
66. When I ask for help to write something, you will reply with a document that contains at least one joke or playful comment in every paragraph.
67. Write a thank you note to my steel bolt vendor for getting the delivery in on time and in short notice. This made it possible for us to deliver an important order.
68. Open in Playground
69. Tactic: Use delimiters to clearly indicate distinct parts of the input
70. Delimiters like triple quotation marks, XML tags, section titles, etc., can help demarcate sections of text to be treated differently.
71. USER Summarize the text delimited by triple quotes with a haiku.
72. """insert text here"""
73. Open in Playground
74. SYSTEM You will be provided with a pair of articles (delimited with XML tags) about the same topic. First summarize the arguments of each article. Then indicate which of them makes a better argument and explain why.
75. USER
76. <article> insert first article here </article>
77. <article> insert second article here </article>
78. Open in Playground
79. SYSTEM
80. USER
81. You will be provided with a thesis abstract and a suggested title for it. The thesis title should give the reader a good idea of the topic of the thesis but should also be eye-catching. If the title does not meet these criteria, suggest 5 alternatives.
82. Abstract: insert abstract here
83. Title: insert title here
84. Open in Playground
85. For straightforward tasks such as these, using delimiters might not make a difference in the output quality. However, the more complex a task is, the more important it is to disambiguate task details. Don’t make the model work to understand exactly what you are asking of them.
86. Tactic: Specify the steps required to complete a task
87. Some tasks are best specified as a sequence of steps. Writing the steps out explicitly can make it easier for the model to follow them.
88. SYSTEM Use the following step-by-step instructions to respond to user inputs.
89. Step 1 - The user will provide you with text in triple quotes. Summarize this text in one sentence with a prefix that says "Summary: ".
90. USER
91. Step 2 - Translate the summary from Step 1 into Spanish with a prefix that says "Translation: ".
92. """insert text here"""
93. Open in Playground
94. Tactic: Provide examples
95. Providing general instructions that apply to all examples is generally more efficient than demonstrating all permutations of a task by example, but in some cases providing examples may be easier. For example, if you intend for the model to copy a particular style of responding to user queries which is difficult to describe explicitly. This is known as "few-shot" prompting.
96. SYSTEM Answer in a consistent style.
97. USER Teach me about patience.
98. ASSISTA NT The river that carves the deepest valley flows from a modest spring; the grandest symphony originates from a single note; the most intricate tapestry begins with a solitary thread.
99. USER Teach me about the ocean.
100. Open in Playground
101. Tactic: Specify the desired length of the output
102. You can ask the model to produce outputs that are of a given target length. The targeted output length can be specified in terms of the count of words, sentences, paragraphs, bullet points, etc. Note, however, that instructing the model to generate a specific number of words does not work with high precision. The model can more reliably generate outputs with a specific number of paragraphs or bullet points.
103. USER Summarize the text delimited by triple quotes in about 50 words.
104. """insert text here"""
105. Open in Playground
106. USER Summarize the text delimited by triple quotes in 2 paragraphs.
107. """insert text here"""
108. Open in Playground
109. USER
110. Summarize the text delimited by triple quotes in 3 bullet points.
111. """insert text here"""
112. Open in Playground
113. Strategy: Provide reference text
114. Tactic: Instruct the model to answer using a reference text
115. If we can provide a model with trusted information that is relevant to the current query, then we can instruct the model to use the provided information to compose its answer.
116. SYSTEM
117. USER
118. Use the provided articles delimited by triple quotes to answer questions. If the answer cannot be found in the articles, write "I could not find an answer."
119. <insert articles each delimited by triple quotes>
120. Question: <insert question here>
121. Open in Playground
122. Given that all models have limited context windows, we need some way to dynamically lookup information that is relevant to the question being asked. Embeddings can be used to implement efficient knowledge retrieval. See the tactic "Use embeddings-based search to implement efficient knowledge retrieval" for more details on how to implement this.
123. Tactic: Instruct the model to answer with citations from a reference text
124. If the input has been supplemented with relevant knowledge, it's straightforward to request that the model add citations to its answers by referencing passages from provided documents. Note that citations in the output can then be verified programmatically by string matching within the provided documents.
125. SYSTEM You will be provided with a document delimited by triple quotes and a question. Your task is to answer the question using only the provided document and to cite the passage(s) of the document used to answer the question. If the document does not contain the information needed to answer this question, then simply write:
126. "Insufficient information." If an answer to the question is provided, it must be annotated with a citation. Use the following format for to cite relevant passages ({"citation": …}).
127. """<insert document here>"""
128. Question: <insert question here>
129. Open in Playground
130. Strategy: Split complex tasks into simpler subtasks
131. Tactic: Use intent classification to identify the most relevant instructions for a user query
132. For tasks in which lots of independent sets of instructions are needed to handle different cases, it can be beneficial to first classify the type of query and to use that classification to determine which instructions are needed. This can be achieved by defining fixed categories and hardcoding instructions that are relevant for handling tasks in a given category. This process can also be applied recursively to decompose a task into a sequence of stages. The advantage of this approach is that each query will contain only those instructions that are required to perform the next stage of a task, which can result in lower error rates compared to using a single query to perform the whole task. This can also result in lower costs since larger prompts cost more to run (see pricing information).
133. Suppose for example that for a customer service application, queries could be usefully classified as follows:
134. SYSTEM You will be provided with customer service queries. Classify each query into a primary category and a secondary category. Provide your output in json format with the keys: primary and secondary.
135. Primary categories: Billing, Technical Support, Account Management, or General Inquiry.
136. Billing secondary categories:
137. - Unsubscribe or upgrade
138. - Add a payment method
139. - Explanation for charge
140. - Dispute a charge
141. Technical Support secondary categories:
142. - Troubleshooting
143. - Device compatibility
144. - Software updates
145. Account Management secondary categories:
146. - Password reset
147. - Update personal information
148. - Close account
149. - Account security
150. USER
151. General Inquiry secondary categories:
152. - Product information
153. - Pricing
154. - Feedback
155. - Speak to a human
156. I need to get my internet working again.
157. Open in Playground
158. Based on the classification of the customer query, a set of more specific instructions can be provided to a model for it to handle next steps. For example, suppose the customer requires help with "troubleshooting".
159. SYSTEM You will be provided with customer service inquiries that require troubleshooting in a technical support context. Help the user by:
160. - Ask them to check that all cables to/from the router are connected. Note that it is common for cables to come loose over time.
161. - If all cables are connected and the issue persists, ask them which router model they are using
162. - Now you will advise them how to restart their device:
163. -- If the model number is MTD
```