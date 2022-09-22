## Introduction

Today’s world of natural language processing (NLP) is driven by powerful transformer-based models that can automatically caption images, answer open-ended questions, engage in free dialog, and summarize long-form bodies of text -- of course, with varying degrees of success. Success here is typically measured by the accuracy (Did the model produce a correct response?) and fluency (Is the output coherent in the native language?) of the generated text. While these two measures of success are of top priority, they neglect a fundamental aspect of language -- _style_.

Consider the fictitious scenario where you engage an AI-powered chatbot to assist you with a shopping return for a damaged item. After sharing your intent with the bot, it responds with either of the following generated messages:

1. “Give me a picture of the damage.”
2. “Could you please send me a picture of the damage?”

While the first option may contain the correct next action (requesting proof of damage) with sound grammer, something about it feels brash and slightly off-putting in a customer experience setting where politeness is highly valued for customer retention. That’s because the expressed tone of politeness plays a critical role in smooth human communication. Of course, this is a non-trivial task for a machine learning model to be aware of as the phenomenon of politeness is rich, multifaceted, and depends on the culture, language, and social structure of both the speaker and addressed person^[[Politeness Transfer: A Tag and Generate Approach](https://arxiv.org/pdf/2004.14257.pdf)].

This quick example highlights the importance of personalization and user-centered design in the successful implementation of new technology. For artificial intelligence systems to generate text that is seamlessly accepted into society, it is necessary to model language with consideration for style, which goes beyond merely just expressing semantics. In NLP, the task of adjusting the style of a sentence by rewriting it into a new style while retaining the original semantic meaning is referred to as _text style transfer (TST)_.

Through this report, we explore text style transfer through an applied use case -- neutralizing subjectivity bias in text. We’ll start by providing an introduction to TST as a task and its potential use cases. Then, we’ll discuss our applied use case, modeling approach, and present a set of custom evaluation metrics for effectively quantifying model performance. Finally, we conclude with a discussion of ethics centered around our prototype: [Exploring Intelligent Writing Assistance](https://huggingface.co/spaces/cffl/Exploring_Intelligent_Writing_Assistance).
