## The Impact of Code Review Coverage and Code Review Participation on Software Quality

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_

The author’s goal was to research the relationship between modern code review processes and software quality. To be more precise, they analyse the relationship between software quality and two separate aspects: Code review coverage (how much changes have been code reviewed) and code review participation (how many reviewer where involved). They formulated two research questions:

RQ1: Does a relationship between code review coverage and post-release defects exist?
RQ2: Does a relationship between code review participation and post-release defects exist?

2. Why is this paper **important**?

Other prior works had shown that code inspections are an effective method to identify defects. With code reviews it is possible to detect defects at an early stage in the development process and this furthermore reduces defects that may occur later on because of earlier defects. 
The knowledge about the relationship between software quality and  review coverage/ participation will give the developers a better understanding about modern code review techniques and what elements of a code review process should not be omitted to receive good results. This may also encourage project managers to invest more in code review to achieve better code quality.

3. What is the **methodology** used to answer the research question(s) or reach the goal?

The authors have done a case study to answer their research questions. The case study was performed on large, successful and rapidly-evolving open source systems with globally distributed development teams. The authors defined two restrictions for the systems they wanted to study: 1. the systems had to have a large number reviewed integrated patches. 2. the code review process had to be traceable. They focused on Qt, VTK and ITK systems, which are all using the Gerrit code review tool and do not violate the restrictions. 

They extracted the review data from the Gerrit review database, got the Gerrit change Ids form the VCS commits and calculated the version control metrics. For the calculation, they took VCS commit messages and searched for defect identifiers. They used multiple metrics (product metrics, process metrics and human factors) to measure their data. 

With this data, they build Multiple Linear Regression (MLR) models to help them understand the relationship between post-release defects and code review coverage/participation. To make the model less vulnerable to outliers, they performed a log transformation and minimised multicollinearity with the help of Spearman ranks and Variance Inflation Factor scores. To better interpret the MLR model, the authors used explanatory variable impact analysis including the calculation of the predicted defect count and concrete predicted defect count. 

4. What **data** does the paper use?

They used code review data which was extracted from the Gerrit review database of all studied systems.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?

Product metrics: For this metric the complexity (measured with Scitools Understand) is divided by  the size of a component (part of the source code with the same tag).
Process metrics: This metric measures the change activity of a new release. It takes the time period and development branch into account and uses prior defects, churn (total number of lines added and removed), and change entropy (distribution of change process complexity across files) to calculate how the process has changed. 
Human factors: This metric measures the developers code ownership as well as his/her expertise in respect to a period of time.
Log transformation: Can only be used on natural numbers. This transformation takes a value x and processes it in the following formula: log(x + 1). Similarly a Logit Transformation uses the formula log(x / 1 - x). 
Variance Inflation Factor: correlation measure, where a value of 1 means no correlation and a value greater than 1 means that collinearity exists.
Predicted Defect Count: Number of defects the model estimated to be within the component.
Concrete Predicted Defect Count: Predicted Defect Count except that the value cannot be zero. 

6. What are the **limitations** of using this methodology on the results?


7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_

The authors draw the conclusion that code review coverage and participation are both related to software quality. Low code review coverage and participation lead to additional post-release defects. So to sum up, if code review is poorly done, it has a negative impact on the software quality in large systems using modern code reviewing tools. 

8. What did you **not understand** of this paper?
