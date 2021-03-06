# Predicting Defects for Eclipse

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_ 

The main goal is to find out which programs are more failure-prone than others. This information allows the allocation of resources for quality assurance to the most defect-prone parts of a system. 
In order to reach this goal, the authors of the paper examined the following research questions:
* Which files/packages have defects? 
* Which are the files/packages with the most defects? Does complex code implify more defects?

Another goal is to support future empirical research based on bug data by making their Eclipse bug data set publicly available.

2. Why is this paper **important**? 

The authors discovered that the combination of complexity metrics can predict defects suggesting that more complex code lead to more defects. If developers know that more complex code is more likely to leads to defects, they can focus on finding these specific parts in their project and therefore save time by the debugging process. In addition, the authors made their gathered data available to the public. Therefore, other researchers can use their data for similar or more enhanced studies. 

3. What is the **methodology** used to answer the research question(s) or reach the goal? 

In the first step they computed the Eclipse bug data set (see question 4). Using this data set they conducted experiments in order to examine the research questions. 

First, they computed the Spearman correlation between the number of pre-releases and post-release defects and the complexity metrics in the data set. Afterwards, they combined input features by building regression models for their data set. The regression models are used to predict whether files/packages have post-release defects. Lastly, they used linear regression models in order to predict files/packages which have the most post-release defects. The prediction of the ranking was compared to the actual ranking using the Spearman correlation.

Each experiment was done on the file level as well as the package level.

4. What **data** does the paper use? 

They computed the Eclipse bug data set based on data collected from version archives (CVS) and bug tracking systems (BUGZILLA): 
To compute the data set they firstly identified everything that was related to a bug using the version archives and mapped bug reports to releases with the bug tracking system. The bugs are then categorized into pre-release or post-release defects.
Additionally, for each case several complexity metrics were computed.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model? 

Classification: Classification is used to predict if a file or package will have at least one defect. The authors used precision (how many of the found files were failure-prone), recall (how many of all failure-prone files were found), accuracy (proportion of correct prediction of failure-prone files) to check the quality of the classification model. 

Ranking: The authors tried to order the files/packages, were files/packages with more defects come first, so they predict a ranking. To measure the quality of this ranking, they used Spearman correlation, which is the correlation between a prediction and an observed ranking. High correlation (high quality) is indicated with the value 1 or -1 and no correlation is indicated with value 0.

6. What are the **limitations** of using this methodology on the results? 

They found out that complexity metrics can predict defects, however, there might be other indicators such as for example process properties that can better predict defects. These indicators which have not been examined with this methodology. Additionally, the results do not show, whether if the models are applicable across projects and over time, since they solely used their own computed data set.

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_ (Sarah)

The authors showed with their experiments that a combination of complexity metrics can predict defects. They suggest that more complex code contains most likely more defects.

8. What did you **not understand** of this paper?

They used some complex terms that weren't explained in the paper: E.g. Nested block depth, Non-static fields, McCabe cyclomatic complexity. This, however, might be due to our lack of knowledge in this research field and is therefore not necessarily a weakness of the paper.


# How, and Why, Process Metrics Are Better

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.) 

The main goal of this paper is to not only find out whether process metrics are better predictors than code metrics but also to thoughtfully examine the reason why process metrics are better. In order to reach this goal they investigated several research questions in which they compared code metrics with defect metrics regarding different aspects such as performance, stability, portability (cross-project prediction) and stasis.


2. Why is this paper **important**? 

With the help of defect prediction techniques the efforts of quality-assurance can be directed on the most defect-prone files. So the building of a good prediction model can lead to time and effort savings in software engineering. The understanding of such models is therefore an important aspect in the field of defect prediction. Also, if you know which metrics are more effective in which situation, it helps you decide on the best metric for a specific project.

3. What is the **methodology** used to answer the research question(s) or reach the goal? 

They conducted defect-predictions studies at file-level with predictive metrics that have already been used in defect prediction literature. To reduce the risk of dependence on a specific learning technique, they used many different learning techniques such as Logistic Regression, SCM, Naive Bayes, etc. However, they solely show the results from Logistic Regression in the paper with the justification that prediction performance depend mostly on the types of metrics and not on the learning technique.
The models used for prediction are all binary classifiers which classify files as either defective or clean.
To build the models they used both code and process metrics. They then trained the models on a release and evaluate its performance on the following release. To compare the stability and sensitivity they evaluated the model on all future releases. To examine the portability they evaluated models trained on one project on all releases of other projects.

4. What **data** does the paper use? 

They studied 12 Java-based projects which are maintained by Apache Software Foundation and use the JIRA issue tracking system. The projects have a diverse range of domains. The following data was extracted and used for the evaluation of the research questions: Commit history from GIT repository, defect information and fixing commits from JIRA and changed lines, author, etc. from GIT for each fixing commit.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model? 

Classification is used to predict if a file is defect-prone. The authors presented precision (how many of the found files were failure-prone), recall (how many of all failure-prone files were found), accuracy (proportion of correct prediction of failure-prone files) and f-measure (harmonic mean of recall and precision) to check the quality of the classification model. However, these methods use a minimum threshold on the probability value. The authors used a threshold invariant method, called Receiver Operating Characteristic (ROC) which models a curve. The curve plots the true positive rates against false positive rates for all possible thresholds (value between 0 and 1). The area under the curve  is abbreviated as AUC. To also take the cost of a bug-fix into account, the authors considered a cost effectiveness measure. This measure predict defects and orders them according to their defect density.

The authors used the Spearman correlation (correlation between a prediction and an observed ranking) as a measure of stasis. With a resulting plot, it is possible to see how similar files are between successive releases.

6. What are the **limitations** of using this methodology on the results? 

In the paper the authors mention the threats of validity of this study and explained how their used methodology tackle these threats. The main problem, we believe, is the generalizability of the results to other non-Apache projects which are developed in using another language than Java.

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_

The results of the paper suggest that process metrics are more useful than code metrics on non-recurring defects (so for defect prediction in general) because code metrics do not evolve with the changing distribution of defects and therefore only focus on recurring defects.

8. What did you **not understand** of this paper? 

The result of RQ 2 was not clear to us. We did not see if the authors proofed their hypothesis or not? We were kind of confused that the paper referred to Figure 6b but there was no figure in the paper with the corresponding number. There also appeared some unexplained terms which we were not familiar with, for instance Wilcoxon Test or Benjamini-Hochberg correction.
