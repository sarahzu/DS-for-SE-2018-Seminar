# Predicting Defects for Eclipse

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_ (Alice)

Research Question: Which programs are more failure-prone than others? Which files/packages have defects (a classification problem)? Which are the files/packages with the most defects (a ranking problem)? Does complex code implify more defects?
The goal is to support a allocation of resouces for quality assurance to parts of a system that are most defect-prone. Proove the hypothesis with complexity measures. Another goal is to provide their data to futur researches in software engineering. 

2. Why is this paper **important**? (Sarah)

The authors discovered that the combination of complexity metrics can predict defects suggesting that more complex code lead to more defects. If developers know that more complex code is more likely to leads to defects, they can focus on finding these specific parts in their project and therefore save time by the debugging process. In addition, the authors made their gathered data available to the public. Therefore, other researchers can use their data for similar or more enhanced studies. 

3. What is the **methodology** used to answer the research question(s) or reach the goal? (Alice)

They used experiments using Eclipse bug data set. They computed the Spearman correlation between the number of pre-releases and post-releas defects and the complextity metrics in the data set. They build logist logistic regression models for the Eclipse bug data set to predict wheter files/packages have post-release defects. 
 
In order to predict the files/packages that have most post-release defects we used linear regression models. Using these models we predicted for each file/package the number of expected post-release defects and compared  the  resulting  ranking  to  the  observed  ranking using Spearman correlation.

4. What **data** does the paper use? (Alice)

Eclipse bug data set: They identified everything that was related to a bug and categorized it as pre-release or post-release defect.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model? (Sarah)

Classification: Classification is used to predict if a file or package will have at least one defect. The authors used precision (how many of the found fils were failure-prone), recall (how many of all failure-prone files were found), accuracy (combination of precision and recall) to check the quality of the classification model. 

Rankng: The authors tried to order the files/packages, were files/packages with more defects come first, so they predict a ranking. To measure the quality of this ranking, they used Spearman correlation, which is the correleation between a prediction and an observed ranking. High correlation (high quality) is indicated with the value 1 or -1 and no correlation is indicated with value 0.

6. What are the **limitations** of using this methodology on the results? (Alice)

However, our predictions are far from being perfect. 
They  therefore  raise  follow-up  questions:  Are  there better  indicators  for  defects  than  complexity  metrics? 
How  applicable  are  models  across  projects  and  over time? How do we integrate prediction models into the development process?  

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_ (Sarah)

The experiments in this paper showed that the combination of complexity metrics can predict defects, suggesting that the more complex code it, the more defects it has.  

8. What did you **not understand** of this paper?

There were some complex terms used that weren't explained in the paper: E.g. Nested block depth, Non-static fields, McCabe cyclomatic complexity ...
However, (not enough knowledge)


# How, and Why, Process Metrics Are Better

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.) (Alice)
2. Why is this paper **important**? (Sarah)
3. What is the **methodology** used to answer the research question(s) or reach the goal? (Alice)
4. What **data** does the paper use? (Alice)
5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model? (Sarah)
6. What are the **limitations** of using this methodology on the results? (Alice)
7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_(Sarah)
8. What did you **not understand** of this paper?
