## Conclusion

At last, we’ve made it to the final chapter of this research report. We started by broadly introducing the NLP task of text style transfer and discussing the often overlooked, but important role that style plays in the successful adoption of NLP technologies. We then explored how conditional language modeling approaches can be applied to the task of automatically neutralizing subjectivity bias. In doing so, we were faced with the nuanced difficulty of evaluating natural language generation (NLG), and implemented automated metrics to quantify style transfer strength and content preservation for our model outputs. Finally, we discussed some ethical considerations that should be attended to when designing an NLG system and described our prototype.

We hope you’ve enjoyed this report as much as we’ve enjoyed researching and writing about this exciting topic. We’ll close out this series with a listing of all project outputs for quick reference.

:::info
**Research Report:**

- [You're reading it!](https://text-style-transfer.fastforwardlabs.com/)

**Blog Series:**

- [Part 1: An Introduction to Text Style Transfer](/2022/03/22/an-introduction-to-text-style-transfer.html)
- [Part 2: Neutralizing Subjectivity Bias with HuggingFace Transformers](/2022/05/05/neutralizing-subjectivity-bias-with-huggingface-transformers.html)
- [Part 3: Automated Metrics for Evaluating Text Style Transfer](/2022/07/11/automated-metrics-for-evaluating-text-style-transfer.html)
- [Part 4: Ethical Considerations When Designing NLG Systems](/2022/07/29/ethical-considerations-when-designing-an-nlg-system.html)

**Code:**

- Research Code - [Text Style Transfer: Neutralizing Subjectivity Bias with Huggingface Transformers](https://github.com/fastforwardlabs/text-style-transfer)
- Applied ML Prototype (AMP) - [Exploring Intelligent Writing Assistance](https://github.com/cloudera/CML_AMP_Intelligent_Writing_Assistance)

**HuggingFace Artifacts:**

- Model: [Subjective-neutral Style Classification](https://huggingface.co/cffl/bert-base-styleclassification-subjective-neutral)
- Model: [Subjective-to-neutral Style Transfer](https://huggingface.co/cffl/bart-base-styletransfer-subjective-to-neutral)
- Space: [Exploring Intelligent Writing Assistance](https://huggingface.co/spaces/cffl/Exploring_Intelligent_Writing_Assistance)
  :::
