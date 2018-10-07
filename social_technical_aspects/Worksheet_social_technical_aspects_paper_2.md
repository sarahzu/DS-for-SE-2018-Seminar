## Does Distributed Development Affect Software Quality? An Empirical Case Study of Windows Vista

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_

The main goal of this study is to examine whether or not the global software development within the same company leads to more post-release failures. Based on prior observations the authors formulated and examined the following hypothesis:

H1: Binaries that are developed by teams of engineers that are distributed will have more post-release failures than those developed by collocated engineers.

Additionally, they wanted to find out whether binaries that are distributed differ from collocated binaries. They believe that managers may choose to only develop simpler and less critical software in a distributed fashion. This leads to the following hypothesis which was examined:

H2: Binaries that are distributed will be less complex, experience less code churn, and have fewer dependencies than collocated binaries.


2. Why is this paper **important**?

It is important to thoughtfully examine the effects of globally distributed software development, because it is increasingly used due to its benefits, such as for example the reduction of the cost by using cheaper employees located in lower-cost economies or the opportunity to take advantage of large pools of skilled labour. There are many advantages, however, it is also critical to examine the possible disadvantages that may arise such as for example more software failures. Knowing whether global software development leads to more failures helps the company to decide, if their software should be developed in a distributed fashion or by collocated teams. 

Unlike other existing papers, this paper study the effect of globally distributed software development within the same company, because they want to focus on the issues which are solely dependent of geographical distribution and not on other factors of outsourcing such as for example expertise finding. The findings of this paper are therefore more reliable for globally distribted software development within the same company compared to other studies. Additionally, this paper focuses on post-release failures, because they can have a huge negative impact on company reputation and marketshare.

3. What is the **methodology** used to answer the research question(s) or reach the goal?

For this study they focused as mentioned above on post-release failures of software development within the same company. They used geographical and commit data and divided the Vista binaries into two cateogries: Binaries developed by distributed teams and binaries developed by collocated teams. They examined the distributed development at multiple levels of geographical separation.
Additionally, they examined the complexity and mainentance characteristics of distributed and collocated binaraires in order to see whether if there are differences that can influence the post-release quality. It is possible that this is a confounding variable.


4. What **data** does the paper use?

They used data of the Windows Vista commorcial software project which involved a few thousand developers and consisted of thousand of files which contained machine code. The three main properties used were code quality, geographical location and code ownership. The code quality is represented by post-release failures which were examined at the level of individual executables and libraries. 
Using the people management software they got the geographical location of each developer at Microsoft. The following geographic levels were used: Building, Cafeteria, Campus, Locality, Continent and World. The code ownership was examined by using the the number of commits made by each developer to each binary.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?



6. What are the **limitations** of using this methodology on the results?



7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_

The results of this study indicate that there is a negligible difference in post-release failures when comparing components developed by collocated teams and components developed in a distributed fashion within the same company. Additionally, by controlling the confounding variable "number of developers working on a binary", they found that the difference becomes even less significant. So, their hypothesis H1 could not be confirmed. Considering earlier works, the study showed that organizational differences are stronger indicators of quality than the geographical distribution. 

As for the evaluation of the seconed hypothesis H2, they concluded that there is no discernible difference in the measured metrics (functions, cemplexity, churn size, edits, etc.) between distributed and collocated binaries.

8. What did you **not understand** of this paper?
