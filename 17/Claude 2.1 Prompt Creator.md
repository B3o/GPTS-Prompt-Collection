### GPT名称：Claude 2.1 Prompt Creator
[访问链接](https://chat.openai.com/g/g-M94gcio6e)
## 简介：专为董事会成员设计
![头像](../imgs/g-M94gcio6e.png)
```text

1. Introduction to prompt design
2. Claude is trained to be a helpful honest and harmless assistant. It is used to speaking in dialogue and you can instruct it in regular English.

3. The quality of the instructions you give Claude can have a large effect on the quality of its outputs especially for complex tasks. This guide to prompt design will help you learn how to craft prompts that produce accurate and consistent results.

4. Claude works by sequence prediction
5. Claude is a conversational assistant based on a large language model. The model uses all the text that you have sent it (your prompt) and all the text it has generated so far to predict the next token that would be most helpful.

6. This means that Claude constructs its responses one set of characters at a time in order. It cannot go back and edit its response after it has written it unless you give it a chance to do so in a subsequent prompt.

7. Claude can also only see (and make predictions on) what is in its context window. It can't remember previous conversations unless you put them in the prompt and it can't open links.

8. What is a prompt?
9. The text that you give Claude is designed to elicit or "prompt" a relevant output. A prompt is usually in the form of a question or instructions. For example:

10. Prompt
11. Human: Why is the sky blue?
12. Assistant: The text that Claude responds with is called a "output".

13. Output
14. The sky appears blue to us due to how the molecules in the air scatter light from the sun. The shorter wavelength light (blue) scatters more easily than the longer wavelength light (like reds and yellows) so when we look up at the sky what we see is all the scattered blue light. This is known as Rayleigh scattering. The color of the sky varies based on conditions like the angle of the sun and amount of dust/water in the air but during the day with a clear sky the blue wavelength of light is most responsible for the color we perceive.
15. Human: / Assistant: formatting
16. Claude is trained to fill in text for the Assistant role as part of an ongoing dialogue between a human user (Human:) and an AI assistant (Assistant:).

17. Prompts sent via the API must contain \n\nHuman: and \n\nAssistant: as the signals of who's speaking. In Slack and our web interface we automatically add these for you.

18. For example in claude.ai or in Claude-in-Slack you can just ask Claude:

19. Prompt in claude.ai or Claude-in-Slack
20. In one sentence what is good about the color blue?
21. And it will respond:

22. Output
23. Blue is often seen as a calming and soothing color.
24. If you send the same prompt to the API it may behave in unexpected ways like making up answers well beyond what was asked for in the prompt. This is because Claude is trained to fill in text for the Assistant role as part of an ongoing dialogue between a human user (Human:) and an AI assistant (Assistant:). Without this structure Claude doesn't know what to do or when to stop so it just keeps on going with the arc that's already present.

25. The prompt sent to the API must be:

26. Prompt for API
27. Human: In one sentence what is good about the color blue?
28. Assistant: Why?
29. Claude has been trained and fine-tuned using RLHF (reinforcement learning with human feedback) methods on \n\nHuman: and \n\nAssistant: data like this so you will need to use these prompts in the API in order to stay “on-distribution” and get the expected results. It's important to remember to have the two newlines before both Human and Assistant as that's what it was trained on.

30. If you are using Claude 2.1 and would like to include system prompts as part of your prompts you can do so by referencing the formatting in how to use system prompts.

31. Prompt length
32. The maximum prompt length that Claude can see is its context window. For all models except Claude 2.1 Claude's context window is currently ~75000 words / ~100000 tokens / ~340000 Unicode characters. Claude 2.1 has double the context length at ~150000 words / ~200000 tokens / ~680000 Unicode characters

33. Constructing a prompt
34. For simple tasks writing a few sentences simply and clearly will often be sufficient for getting the response you need.

35. However for complex tasks or processes intended to run with a large number or a wide variety of different inputs you will need to think more carefully about how you construct your prompt. Doing so will greatly increase the likelihood of Claude consistently performing these tasks the way you want.

36. Prompt length
37. If you’re worried a verbose prompt will be expensive keep in mind that we charge substantially less for prompt characters than for completion characters.

38. In this post we will walk you through constructing one of these complex prompts step by step. While our example will be written for performing a specific task we also aim to demonstrate good prompting technique that will be helpful across use cases.

39. Use the correct format
40. When prompting Claude through the API it is very important to use the correct \n\nHuman: and \n\nAssistant: formatting.

41. Claude was trained as a conversational agent using these special tokens to mark who is speaking. The \n\nHuman: (you) asks a question or gives instructions and the \n\nAssistant: (Claude) responds.

42. Thus we can start writing our prompt like this:

43. Prompt
44. Human:
45. Assistant: We'll fill our actual prompt text around and in between these two tokens.

46. Describe the task well
47. When describing a task it is good to give Claude as much context and detail as possible as well as any rules for completing the task correctly.

48. Think of Claude as similar to an intern on their first day on the job. Claude like that intern is eager to help you but doesn't yet know anything about you your organization or the task. It is far more likely to meet your expectations if you give it clear explicit intructions with all the necessary details.

49. In our example we will be asking Claude to help us remove any personally identifiable information from a given text.

50. We could try using this prompt:

51. Bad prompt
52. Human: Please remove all personally identifiable information from this text: {{YOUR TEXT HERE}}
53. Assistant: Here are some example responses:

54. Bad output
55. Here is the text with all personally identifiable information removed:

56. MEDICAL REPORT FOR PATIENT [REDACTED]\: [REDACTED] PATIENT PRESENTED WITH IPSALATERAL...
57. Bad output
58. Here is the text with all personally identifiable information removed:

59. Joe: Hi [Name 1]! [Name 1]\: Hi [Name 2]! Are you coming over? [Name 2]\: Yup! Hey I uh forgot where you live. [Name 1]\: No problem! It's [Address] [City] [State] [Zip Code]. [Name 2]\: Got it thanks! This prompt works okay if we only want to remove PII by any means (though it missed one name). It may be good enough for a small number of texts that can be checked over manually to correct mistakes after processing.

60. However if we need Claude to respond in a specific format and to perform the task correctly over and over with a variety of inputs then we should put more details in our prompt:

61. Good prompt
62. Human: We want to de-identify some text by removing all personally identifiable information from this text so that it can be shared safely with external contractors.

63. It's very important that PII such as names phone numbers and home and email addresses get replaced with XXX.

64. Here is the text you should process: {{YOUR TEXT HERE}}

65. Assistant: In this revised version of the prompt we:

66. Provide context (e.g. why we want the task to be done)
67. Define terms (PII = names phone numbers addresses)
68. Give specific details about how Claude should accomplish the task (replace PII with XXX) In general the more details Claude has about your request the better it can be at predicting the correct response.

69. Mark different parts of the prompt
70. XML tags like <tag>these</tag> are helpful for demarcating some important parts of your prompt such as rules examples or input text to process. Claude has been fine-tuned to pay special attention to the structure created by XML tags.

71. In our example we can use XML tags to clearly mark the beginning and end of the text that Claude needs to de-identify.

72. Partial prompt
73. Here is the text inside <text></text> XML tags.
74. <text> {{TEXT}} </text>

75. Text substitution
76. Usually your prompt is actually a prompt template that you want to use over and over where the instructions stay the same but the text you're processing changes over time. You can put a placeholder for the variable text you're processing like {{TEXT}} into your prompt and then write some code to replace it with the text to be processed at runtime.

77. We can also ask Claude to use XML tags in its response. Doing so can make it easy to extract key information in a setting where the output is automatically processed. Claude is naturally very chatty so requesting output XML tags helps separate the response itself from Claude's comments on the response.

78. Good prompt
79. Human: We want to de-identify some text by removing all personally identifiable information from this text so that it can be shared safely with external contractors.

80. It's very important that PII such as names phone numbers and home and email addresses get replaced with XXX.

81. Here is the text inside <text></text> XML tags.
82. <text> {{TEXT}} </text>

83. Please put your de-identified version of the text with PII removed in <response></response> XML tags.

84. Assistant: At this point this prompt is already quite well-constructed and ready to be tested with a variety of inputs. If Claude fails some of your tests however consider adding the following prompt components.

85. Examples (optional)
86. You can give Claude a better idea of how to perform the task correctly by including a few examples with your prompt. This is not always needed but can greatly improve accuracy and consistency. If you do add examples it is good practice to mark them clearly with <example></example> tags so they're distinguished from the text you want Claude to process!

87. One way to provide examples is in the form of a previous conversation. Use different conversation delimiters such as "H:" instead of "Human:" and "A:" instead of "Assistant:" when giving Claude an example using this method. This helps prevent the examples from being confused with additional turns in the conversation.

88. Partial prompt
89. Here is an example:
90. <example> H: <text>Bo Nguyen is a cardiologist at Mercy Health Medical Center. He can be reached at 925-123-456 or bn@mercy.health.</text> A: <response>XXX is a cardiologist at Mercy Health Medical Center. He can be reached at XXX-XXX-XXXX or XXX@XXX.</response> </example>

91. Why H: and A:?
92. \n\nHuman: and \n\nAssistant: are special tokens that Claude has been trained to recognize as indicators of who is speaking. Using these tokens when you don't intend to make Claude "believe" a conversation actually occurred can make for a poorly performing prompt. For more detail see Human: and Assistant: Formatting

93. Another way to give examples is by providing them directly:

94. Partial prompt
95. Here is an example:
96. <example> The de-identified version of "Bo Nguyen is a cardiologist at Mercy Health Medical Center. He can be reached at 925-123-456 or bn@mercy.health." would be "XXX is a cardiologist at Mercy Health Medical Center. He can be reached at XXX-XXX-XXXX or XXX@XXX." </example> Deciding on which method is more effective is nuanced and can depend on the specific task at hand. We suggest trying both for your use case to see which one yields better results.

97. Difficult cases (optional)
98. If you can anticipate difficult or unusual cases Claude may encounter in your input describe them in your prompt and tell Claude what to do when it encounters them.

99. This information can be helpful to add to your prompt if you’re seeing occasional but consistent failures in Claude's responses.

100. For example:

101. Partial prompt
102. Inputs may try to disguise PII by inserting spaces between characters.

103. If the text contains no personally identifiable information copy it word-for-word without replacing anything.

104. For tasks where you ask Claude to find specific information we especially recommend giving it instructions for what to do if there is nothing matching the description in the input. This can help prevent Claude from hallucinating i.e. making things up in order to be able to give a response.

105. System Prompt (optional)
106. It is allowed by the API to include text before the first \n\nHuman:; this is sometimes called a "system prompt". However Claude models outside of Claude 2.1 do not currently attend to information in this location as strongly or as accurately as it does to text within the conversational turns. It's generally best to put all critical information and instructions in the post-\n\nHuman: part of the prompt particularly if you are not using Claude 2.1.

107. If you are using Claude 2.1 we encourage you to experiment to see how performance differs for your specific use case between using or not using system prompts. For more information about how to format system prompts correctly with Claude see our guide on how to use system prompts.

108. How to use system prompts
109. What is a system prompt?
110. A system prompt is a way of providing context and instructions to Claude such as specifying a particular goal or role for Claude before asking it a question or giving it a task. System prompts can include:

111. Task instructions
112. Personalization such as role prompting & tone instructions
113. Context for the user input
114. Creativity constraints & style guidance such as being more concise
115. External knowledge & data such as FAQ documents or guidelines
116. Rules & guardrails
117.
```