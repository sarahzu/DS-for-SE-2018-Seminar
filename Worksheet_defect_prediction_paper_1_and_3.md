# Predicting Defects for Eclipse

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_ (Alice)

The main goal is to find out which programs are more failure-prone than others. This information allows the allocation of resouces for quality assurance to the most defect-prone parts of a system. 
In order to reach this goal, the authors of the paper examined the following research questions:
* Which files/packages have defects? 
* Which are the files/packages with the most defects? Does complex code implify more defects?

Another goal is to support future empirical research based on bug data by making their Eclipse bug data set publicly available.

2. Why is this paper **important**? (Sarah)

The authors discovered that the combination of complexity metrics can predict defects suggesting that more complex code lead to more defects. If developers know that more complex code is more likely to leads to defects, they can focus on finding these specific parts in their project and therefore save time by the debugging process. In addition, the authors made their gathered data available to the public. Therefore, other researchers can use their data for similar or more enhanced studies. 

3. What is the **methodology** used to answer the research question(s) or reach the goal? (Alice)

They used experiments using Eclipse bug data set. They computed the Spearman correlation between the number of pre-releases and post-releas defects and the complextity metrics in the data set. They build logist logistic regression models for the Eclipse bug data set to predict wheter files/packages have post-release defects. 
 
In order to predict the files/packages that have most post-release defects we used linear regression models. Using these models we predicted for each file/package the number of expected post-release defects and compared  the  resulting  ranking  to  the  observed  ranking using Spearman correlation.

4. What **data** does the paper use? (Alice)

Eclipse bug data set: They identified everything that was related to a bug and categorized it as pre-release or post-release defect.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model? (Sarah)

Classification: Classification is used to predict if a file or package will have at least one defect. The authors used precision (how many of the found fils were failure-prone), recall (how many of all failure-prone files were found), accuracy (proportion of correct prediction of failor-prone files) to check the quality of the classification model. 

Rankng: The authors tried to order the files/packages, were files/packages with more defects come first, so they predict a ranking. To measure the quality of this ranking, they used Spearman correlation, which is the correleation between a prediction and an observed ranking. High correlation (high quality) is indicated with the value 1 or -1 and no correlation is indicated with value 0.

6. What are the **limitations** of using this methodology on the results? (Alice)

However, our predictions are far from being perfect. 
They  therefore  raise  follow-up  questions:  Are  there better  indicators  for  defects  than  complexity  metrics? 
How  applicable  are  models  across  projects  and  over time? How do we integrate prediction models into the development process?  

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_ (Sarah)

The authors showed with their experiments that a combination of complexity metrics can predict defects. They suggest that more complex code contains most likely more defects.

8. What did you **not understand** of this paper?

There were some complex terms used that weren't explained in the paper: E.g. Nested block depth, Non-static fields, McCabe cyclomatic complexity. This might be the case because we are not that knwoledgeable in that research field yet.


# How, and Why, Process Metrics Are Better

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.) (Alice)


2. Why is this paper **important**? (Sarah)

With the help of defect prediction techniques the efforts of quality-assurance can be directed on the most defect-prone files. So the building of a good prediction model can lead to time and efford savings in software engineering. The understanding of such models is therefore an important aspect in the field of defect prediction. Also, if you know which metrics are more effective in which situation, it helps you decide on the best metric for a specific project.

3. What is the **methodology** used to answer the research question(s) or reach the goal? (Alice)


4. What **data** does the paper use? (Alice)


5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model? (Sarah)

Classification is used to predict if a file is defect-prone. The authors presented precision (how many of the found fils were failure-prone), recall (how many of all failure-prone files were found), accuracy (proportion of correct prediction of failor-prone files) and f-measure (harmonic mean of recall and precision) to check the quality of the classification model. However, these methods use a minimum treshold on the probability value. The authors used a threshold invariant method, called Receiver Operating Characteristic (ROC) which models a curve. The curve plots the true positive rates against false positive rates for all possible thresholds (value between 0 and 1). The area under the curve  is abrevated as AUC. To also take the cost of a bug-fix into account, the authors considered a cost effectivenesss measure. This measure predict defects and orders them according to their defect density.

The authors used the Spearman correlation (correleation between a prediction and an observed ranking) as a measure of stasis. With a resulting plot, it is possible to see how similiar files are between to successive releases.

6. What are the **limitations** of using this methodology on the results? (Alice)


7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_(Sarah)

The results of the paper suggest that process metrics are more useful than code metrics on non-recurring defects (so for defect prediction in general) because code metrics do not evolve with the changing distribution of defects and therefore only focus on recurring defets.

8. What did you **not understand** of this paper? 

The result of RQ 2 was not clear. Did they proof their hypothesis or not? Where is Figure 6b? We couldn't find this graphic in the paper. There also appeared some unexplained terms which we were not familiar with, for instance Wilcoxon Test or Benjamini-Hochberg correction.

