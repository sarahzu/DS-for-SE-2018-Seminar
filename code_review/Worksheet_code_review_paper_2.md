## The Impact of Code Review Coverage and Code Review Participation on Software Quality

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_

The author’s goal was to research the relationship between modern code review processes and software quality. To be more precise, they analyse the relationship between software quality and two separate aspects: Code review coverage (how much code changes have been reviewed) and code review participation (how many reviewers where involved and how did they proceed in the reviewing process). They formulated two research questions:

RQ1: Does a relationship between code review coverage and post-release defects exist?

RQ2: Does a relationship between code review participation and post-release defects exist?

2. Why is this paper **important**?

Other prior works had shown that code inspections are an effective method to identify defects. With code reviews it is possible to detect defects at an early stage in the development process and this furthermore reduces defects that may occur later on because of earlier defects. 
The knowledge about the relationship between software quality and  review coverage/ participation will give the developers a better understanding about modern code review techniques and what elements of a code review process should not be omitted to receive good results. This may also encourage project managers to invest more in code review to achieve better code quality.

3. What is the **methodology** used to answer the research question(s) or reach the goal?

The authors have done a case study to answer their research questions. The case study was performed on large, successful and rapidly-evolving open source systems with globally distributed development teams. The authors defined two restrictions for the systems they wanted to study: 1. the systems had to have a large number reviewed integrated patches. 2. the code review process had to be traceable. They focused on Qt, VTK and ITK systems, which are all using the Gerrit code review tool and do not violate the restrictions. 

They extracted the review data from the Gerrit review database, got the Gerrit change Ids form the VCS commits and calculated the version control metrics. For the calculation, they took VCS commit messages and searched for defect identifiers. They used multiple metrics (product metrics, process metrics and human factors) to measure their data. 

With this data, they build Multiple Linear Regression (MLR) models to help them understand the relationship between post-release defects and code review coverage/participation. To make the model less vulnerable to outliers, they performed a log transformation and minimised multicollinearity with the help of Spearman ranks and Variance Inflation Factor scores. To better interpret the MLR model, the authors used explanatory variable impact analysis including the calculation of the predicted defect count and concrete predicted defect count. 

Finally, they added the code review coverage metric and the the participation metrics to the MLR model. This finalised model could then be used to draw their conclusions.

4. What **data** does the paper use?

They used code review data which was extracted from the Gerrit review database of all studied systems.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?

Product metrics: For this metric the McCabe’s cyclomatic complexity (measured with Scitools Understand) is divided by the size (number of line of code) of a component (part of the source code with the same tag).

Process metrics: This metric measures the change activity of a new release. It takes the time period and development branch into account and uses prior defects, churn (total number of lines added and removed), and change entropy (distribution of change process complexity across files) to calculate how the process has changed. 

Human factors: This metric measures the developers code ownership as well as his/her expertise in respect to a period of time.

Log transformation: Can only be used on natural numbers. This transformation takes a value x and processes it in the following formula: log(x + 1). Similarly a Logit Transformation uses the formula log(x / 1 - x). 

Variance Inflation Factor: correlation measure, where a value of 1 means no correlation and a value greater than 1 means that collinearity exists.

Predicted Defect Count: Number of defects the model estimated to be within the component.

Concrete Predicted Defect Count: Predicted Defect Count except that the value cannot be zero. 

Code review coverage metrics: proportion of reviews changes in the past and proportion of reviewed churns in the past. 

Participation metrics: proportion of changes only approved by the author himself, proportion of hastily code reviews and the proportion of non-discussed changes to a component. 

6. What are the **limitations** of using this methodology on the results?

The criteria for the used systems were very strict, therefore only three open source systems were used for their study, so the study is not enough representative. Furthermore, the systems they analysed where large, successful and rapidly-evolving open source systems. Small and not very successful projects are not represented. One could argue, that the shown effects and relationships only appear, because the systems are very big and successful. 

The models are build with the assumption that every post release has the same weight, however, in real life it is mostly the case that some post-release defects are more severe than other defects. So it is not clear if the defects used in the study were only relatively small defects or major ones. Depending on the usage of the findings of the paper, this piece of information is very important. 

The time spend on reviews could not be measured exactly therefore the authors had to rely on heuristics. This however is a thread to validity, because if the result is not exactly measured the whole calculation gets imprecise. This fact must be considered when someone wants to use the findings of the study to improve their development process.


7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_

The authors draw the conclusion that code review coverage and participation are both related to software quality. Low code review coverage and low participation lead to additional post-release defects. 

So to sum up, if modern code review lacks enough code coverage and participation of the members, it has a negative impact on the software quality in large systems using modern code reviewing tools. If these two factors however are sufficiently included, the software quality of the source code can be improved. 

8. What did you **not understand** of this paper?

This paper used a lot of statistical metrics. Even though the different metrics were explained in the paper, we had some difficulties to draw the connection between these metrics. We are not sure if we understood each metric 100% correctly even after doing some research. 
