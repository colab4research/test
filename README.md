---

## Main Responses

---

We thank the reviewers for their constructive feedback. We are pleased that all reviewers recognize the importance and soundness of the methodology in this work. Below please find our responses to the questions and we will incorporate all feedback. 

> **R1Q1:Can you please justify why using multifaceted hierarchical attention network is a significant technical contribution?**

The reason that the MHAN is a significant contribution is because this network can utilize multiple features of bug report independently to achieve prediction effectively. In the other hand, we provide a new idea to mine the semantic knowledge of multiple features of bug report, which can also be consider as a contribution. Also, as far as we know, there still no one apply this network on bug report classification. 

> **R1Q2:Why do you think the experimental dataset is sufficient to support the conclusions?**

Nice point! Indeed, the prediction performance could vary in some model configurations. But since we apply Scott-Knot statistical test on all comparisons, the uncertainty of the result has been mitigated, and hence we can generalize this problem to a larger scale. 

> **R1Q3:If possible, could you please provide more details about the labeling process?**

In the data labelling process, two authors identify whether a report is a performance bug report by following a systematic inclusion and exclusion criteria. While labeling the performance bug reports, the inter-rater agreements which is only confirmed once agreed by two authors. The inter-rater agreements were measured using Kappa coefficient were measured using Kappa coefficient; any disagreements were reconciled until the coefficient becomes substantial. From this, we achieve at least 0.7 between the authors (which means a sustainable agreement).  


> **R3Q1:Why the MHPurf variant provides all information but performs comparatively bad to the other variants?**



> **R3Q2:Is there something else part of the content or does the content only consist of title + description?**

In this paper, 'Content' refers to the textual information of 'Title' and 'Description' after extraction of 'Code' and 'Command', where 'Code' for reproduction is a common feature in the description of a GitHub report and 'Command'is the code snippet that is not part of the code block but is mixed with the texts in the description.




