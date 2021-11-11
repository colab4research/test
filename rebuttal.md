---

## Main Responses

---

We thank the reviewers for their constructive feedback. We are pleased that all reviewers recognize the importance and soundness of the methodology in this work. Below please find our responses to the questions and we will incorporate all feedback. 

> **R1Q1:Can you please justify why using multifaceted hierarchical attention network is a significant technical contribution?**

The reason that the MHAN is a significant contribution is that this network can utilize multiple features of bug reports independently to achieve prediction effectively. On the other hand, we provide a new idea to mine the semantic knowledge of multiple features of bug report, which can also be considered as a contribution. Also, as far as we know, there is still no one applying this network on bug report classification. 

> **R1Q2:Why do you think the experimental dataset is sufficient to support the conclusions?**

Nice point! Indeed, the prediction performance could vary in some model configurations. But since we apply Scott-Knot statistical test on all comparisons, the uncertainty of the result has been mitigated, and hence we can generalize this problem to a larger scale. 

> **R1Q3:If possible, could you please provide more details about the labeling process?**

In the data labelling process, two authors identify whether a report is a performance bug report by following systematic inclusion and exclusion criteria. While labeling the performance bug reports, the inter-rater agreements which is only confirmed once agreed by two authors. The inter-rater agreements were measured using Kappa coefficient; any disagreements were reconciled until the coefficient becomes substantial. From this, we achieve at least 0.7 between the authors (which means a sustainable agreement).   

> **R2-comment1:** I am very confused with the use of the word "performance" in this paper, which, as far as I can tell, stands for accuracy, but I'm not sure. If so, the title should be "Multifaceted Hierarchical Accuracy Bug Report Identification for Deep Learning Projects". The intro starts by justifying this word in this way: "[performance bug means] and, in the context of DL systems, insufficient prediction accuracy and loss [62]." Reading paper [62] I find no traces of such definition. At some point [62] even says: "The small number of performance inefficiency issues suggests either performance issues rarely occur or these issues are difficult to detect." 

As found by Reviewer 3, Nistor et al. [33] indicate that 'the training process based on an invalid DL model is ineffective even though it does not necessarily result in a TensorFlow error. This explains the poor performance of the trained model in terms of accuracy and loss.'. Moreover, they report that 'Another (second) TF user posted an issue reporting heavily blurred predicted images and poor loss performance.'. The referenced contexts above explain that Nistor et al. [33] consider low accuracy/loss value as poor performance issues. But as Reviewer 3 suggested, we will revise this context to emphasize two different meanings of the word "performance" (timeliness vs. accuracy/loss)

Indeed, the small number of performance inefficiency issues suggests either performance issues rarely occur or these issues are difficult to detect. But this does not mean we should give up discovering a way to detect those issues because they can lead to severe consequences in DL systems.  

> **R3Q1:Why the MHPurf variant provides all information but performs comparatively bad to the other variants?**

More information could sometimes be beneficial to the DL classifier. But it may cause over-fitting as well. Besides, it should be not due to fewer neurons per feature. Instead, the amount of paramters for each feature remains unchanged because thier network structures are the same except the encoder part. 

> **R3Q2:Is there something else part of the content or does the content only consist of title + description?**

顺着他的意思

In this paper, 'Content' refers to the textual information of 'Title' and 'Description' after extraction of 'Code' and 'Command', where 'Code' for reproduction is a common feature in the description of a GitHub report and 'Command' is the code snippet that is not part of the code block but is mixed with the texts in the description.

---

## Additional Responses

---

> **R1-comment1:** In RQ3, the paper includes many baselines. I was wondering why not include Bert-based text classification.

bert unfair

> **R1-comment2:** I would suggest to move the definition of performance bugs in Section 4.1 to some early part of the paper. Maybe consider presenting the results in Table 5/6/7 in box plots which might be easier to observe than the table format?

Thank you very much for your advice. We will revise accordingly.

> **R2-comment2:** On the other hand, later on, this submission says: "Our work here is to automatically identify those GitHub reports that are related to the performance of DL framework." So it looks like it is performance bugs not of the application itself but of the underlying DL framework? I found it really difficult to understand what exactly the work is trying to do.

When we are talking about the phrase 'DL framework', it refers to 'DL application' or 'DL project' as well. We will revise accordingly by using the same terms to mitigate reader's confusion.

> **R2-comment3:** Related to this, the paper fails to convince me that the problem that is targeted by the work -- automatic identification of either performance or accuracy bug reports -- is important. Why do we need an automatic tool for this? In fact, taking [62] at face value, it looks like there aren't that many performance bug reports in DL applications.

In our work. during the labeling process, we took four months (around 120 working days) to label a total of 3,712 GitHub reports for all the DL projects considered, which is labor-intensive. However, over 64,000 GitHub reports for only three DL projects (TensorFlow, Pytorch and Keras) is still lacking performance bug labelling. Hence, So we think this has been proved sufficiently that an automatic tool is needed. 

> **R3-comment1:** A bottleneck for the presented method is the required data set. It took the authors about 120 working days to manually label the data. In order to scale up the approach, the authors should search for already available data sets. I wonder whether commit messages of already fixed bugs could serve as a source for labels.

Nice point! Actually, we did conduct a similar experiment to see the performance of this model on Ohira et al.'s dataset [34] for the task of performance bug report classification. But poor results were obtained due to its extreme unbalance of positive samples.

承认有limitation，用我们这个模型之后在进行人工处理会更方便

> **R3-comment2:** As a fellow reviewer pointed out, there is a problem with the notion of "performance bug". This, I think, is due to the quote from [62] in the introduction of the paper. In [62], the authors discuss the bug to mix up the computation model of Tensorflow, i.e. using Tensorflow in a wrong way. At the end of this discussion, they state "This explains the poor performance of the trained model in terms of accuracy and loss." This is "performance" in the sense of accuracy, not at all related to performance in the sense of timeliness! The authors in this submission now state "This “performance degradation” contains poor user experience, degraded responsiveness, waste computational resources [19], and, in the context of DL systems, insufficient prediction accuracy and loss [62]." I disagree, as these are two different meanings of the word "performance" (timeliness vs. accuracy). So the part "in the context of DL systems, insufficient prediction accuracy and loss [62]." should be deleted. This mistake, however, leads to the problem that the notion of "performance bug" in the paper is unclear.

Perfect suggestion! We are very much glad to have your brilliant advice on how to revise this context. We will revise accordingly to avoid confusion on the definition of "performance bug".  
