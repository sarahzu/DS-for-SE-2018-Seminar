## Convergent Contemporary Software Peer Review Practices

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_

This paper aims to explore aspects of contemporary peer review in software projects that have varying domains, organisations and development processes. The authors assume that if peer review practices in different projects have become similar, then these practices may represent successful methods of review. In order to check their assumption they firstly explored the following main research question:

"_How do the parameters of peer review differ in multiple disparate projects?_"

The following parameters of review were considered:
* _What peer review process (e.g., Fagan inspection vs Commit-then-review) does the project use?_
* _How long do reviews take and how often are reviews performed?_
* _What is the size of artifact under review?_
* _How many people are involved in review?_
* _How eﬀective is review in terms of problems discussed?_
* _Does review spread knowledge about the system across the development team?_

2. Why is this paper **important**?

Peer review refers to the practice of other authors inspecting software code. It is performed to find errors/defects and improve the overall quality of the software. In addition to this, peer review has many other advantages, as for example sharing knowledge and team cohesion. So, it is important to thoughtfully explore this practice and find efficient methods. 

Studies have shown that traditional review practices limit software adoption and review efficiency. The traditional review practices evolved over time to contemporary peer reviews which follow less rigid practices. This paper is important since it is one of the first studies that explores aspects of contemporary peer review. If they find similar peer review practices which evolved in different projects, then these practices may represent successful and efficient review methods. Using this knowledge it will be possible to make suggestions for other software projects on how to perform efficient peer review.


3. What is the **methodology** used to answer the research question(s) or reach the goal?

They used Yin’s multiple cases study methodology. So, they analysed each case separately, and tried to find patterns of similarity or difference. Analytical generalizations can be made from the findings which helps the researchers to develop a theory or a framework of findings.  In this paper the researchers developed a framework that describes the convergent and divergent practices of contemporary peer reviews. 

Data Extraction: 
They used different ways to extract the required data from the various projects that were investigated, because each of the project used different peer reviewing tools. How the data was extracted in each project is described in question 4.

Plotting Data:
To visualize their data and ease the comparison, they used beanplots and boxplots:
* Beanplot: Used to show the distribution density for multiple samples along the y-axis and the medians (represented by horizontal lines). For this paper, this plot was used for the distribution density of number of reviews, review intervals, number of lines changed and of files seen.
* Boxplot: Used for smaller ranges of non-normal data and shows the quartiles and median (bold line inside the box). The authors used these plots for count data that is highly concentrated: Reviewers per review, comments per review and number of resubmissions per review. 

In order to answer the question _”Does review spread knowledge about the system across the development team?”_ they tried to provide a preliminary measurement of knowledge sharing. In addition to the already developed measure “number of files a developer has modified” (submitted), they also measured “number of files a developer has reviewed” (reviewed) and “number of files he knows about” (submitted ∪ reviewed). They then used a beanplot to compare the number of files a developer has modified and the total number of files he/she knows about to check for each project by how much reviews increase the number of files a developer knows about in the medium case.


4. What **data** does the paper use?

To explore their research question, the data was extracted data from different projects. Since the projects used different methods and tools for their reviews, the authors had to use different ways to extract the data from each project:
* Lucent (comparison data): They collected self-report data from reviewers on a compiler project by attending inspection meetings. 
* 6 OSS projects (comparison data): Review data of Apache, Subversion, Linux, FreeBSD, KDE and Gnome was extracted form mailing lists.
* Microsoft data (new data): They extracted the data from the CodeFlow tool which centrally stores all data about code reviews by building a service to mine the required information: Who created the review, which are the modified files, how many changes were submitted, comments of reviewers, who signed off.
* Google Chrome and Android (new data): From these projects they gathered information about authors and reviewer’s activity, files changed, comments made and dates of submission and completion by querying the Gerrit servers. 
* AMD (new data): They extracted a summary of the data from the used CodeCollaborator tool. The problem of this data was, that it didn’t contain all the required parameters of review for the exploration. For example, the number of comments per review was missing.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?

We did not find any specific statistical model that was used. In order to report their findings, the authors solely compared and reported the processes and medians of each review parameter of the projects. The parameters that were compared between the projects to find the convergent practices were _review intervals, completion times, change sizes, number of reviews and knowledge spreading_.

6. What are the **limitations** of using this methodology on the results?

* As mentioned above, they studied many different projects which used different review tools and processes. So, the extracted data from these projects are not controlled and may have many confounding variables such as for example incentives for reviews or tools used. Even though the authors attempted to clean the data by using similar measures, we still have to take note that the data was collected differently in each project. Therefore, comparisons should be made with caution.
*	The datasets of AMD and Lucent weren’t complete as they could only use a summary and not the raw data. They were missing some data that were required for the comparisons, which limits the validity of the findings.
*	To find the convergent/divergent practices they compared, as mentioned in question 3, the medians of the review parameters. However, they did not use any statistical tests to check if the observed differences between the traditional software inspection (e.g. Lucent) and the contemporary peer review practices were statistically significant. 
*	We think that the used measure of knowledge sharing though peer review is not optimal and can still be improved, as this measure does not consider that if people review similar files, the knowledge shared through peer review is not as big as when people review totally different files. So, they only considered the number of the reviewed files and the number of files that have been modified but did not consider the content of the files that are reviewed. 
*	In the threats to validity section they mentioned that when a ﬁnding was unusual they would read the associated reviews and discuss them with developers. They for example found that sometimes reviews are used for awareness purposes and removed these reviews from the projects. This seemed to us a bit biased, as they only that that for findings that were unusual. What if the findings that were “usual” also had issues in the data? 

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_


8. What did you **not understand** of this paper?

