## Mining Email Social Networks

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_

The goal of this research was to study the relationship between communication and coordination (C&C) activities of software developers and their software development activity by using open source software e-mail archives. More precisely the authors are interested in the connection between the mailing list activities of developers and the their respective changes in the source code. So the authors defined a few sub-goals:

1) Defining the properties of the social network of developers
2) Finding out if developers who send a lot of messages also make a lot of source code changes
3) Finding out if there is a difference between developers and non-developers in the social network
4) Finding out if being the most active developer is correlated to having the highest status among developers

2. Why is this paper **important**?

Software development with a large-scale often faces the challenge of communication and coordination among their developers. The C&C activities are often complex and the effort put into building them is quit high. Therefore, to know how the C&C activities are related to the actual development processes may help companies to see why it is important to improve their C&C activities. Furthermore, it shows them how important it is to not only look at both sides individually, but to have both C&C activities and software development in mind while improving the whole system. This could lead to more productive C&C activities among the developers which will improves the source code development. 

3. What is the **methodology** used to answer the research question(s) or reach the goal?

Firstly, the authors had to distinguish the authors in the open source mailing list archives. One person could have several aliases as e-mail names. However, when the developers made cvs comments, they had to use their cvs account, so with this account it is possible to distinguish the developers. So the authors had to correlate the email names with the cvs account names of the developers to know which developer contributed which content. 

To do so they used an automatic message crawler to identify pairs of name and email addresses (<name, email> tuples). Each of these tuples was marked with an id. Then they clustered similar tuples together by using similarity measures (normalize name, name similarity, names-email Similarity, email similarity and cumulative ID similarity). The same technique was used to map cvs account names to email aliases. 

The next step was to describe the behavior of the participants of the mailing list. To describe the behavior, the authors constructed their results in histograms. The first four histograms that visualize the relation between number of participants with number of messages, message replaying behavior, in-degree and out-degree. Another histogram presented the relationship between the number of messages sent by an user and the number of distinct responding users who replied to that user. Lastly, the authors constructed a pruned email social network graph that indicate which users have sent more than 150 messages to which other users. Within these figures a Pareto distribution and small-world network characteristics were visible. 

Finally, to answer the question of how email activities relates to software development activities, the authors analyzed how many changes were made by each user in the cvs archives (users who did not made any changes to the source code or documentation were omitted). They calculated the Spearman's correlation between the number of messages send by an user and the number of source code/documentation changes the user made. A high correlation value indicates that the more source code/documentation changes the user does, the more C&C activity he/she has to undertake to reach this amount of work. They also calculated the in-betweenness of nodes in the social network.

4. What **data** does the paper use?

They used the email activity on the Apache HTTP Server Developer mailing list from 1990 to the current state of the paper (101,637 messages). For every email the header, the message identifier, the sender, the sent time and the identifier of the message that the original message replied to was identified. So in the end, the authors could create communication links between pairs of individuals.

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?

Levenshtein distance is used to calculate the similarity between two strings, e.g. between to email addresses. The number of different letters in the string is used for this calculation. 

Betweenness: the betweenness of a node v in a graph is calculated by the sum of all shortest paths between two nodes that goes through node v divided by the total number of shortest paths (which do not need to go through v). 

6. What are the **limitations** of using this methodology on the results?

The study was only conducted within open source software development context. So the conclusions cannot be used in the context of non-open source software. Also, the data which was used was all gathered from the same mailing list, namely the one from the Apache HTTP Server Developer project. Therefore the study is limited to the content and structure of this particular mailing list archive.

So if a commercial software company want to use the findings of this paper, they first have to check if their C&C activities are similar to the Apache HTTP Server Developer mailing list. Otherwise, the findings of the paper are not useful for the company. It is unlikely that there will be a study in the future where the C&C activities of commercial software organization is being analyzed. The cause to this is, like the authors stated, the fact that the data of commercial companies are not publicly available. So to get useful insights in their C&C activities, every company would have to conduct their own study with their individual data. So the paper does give us a good picture about how source code development is linked to C&C activities in one specific example, but the findings are not enough to help commercial software companies to improve their systems.

Even among open source software, the findings have to be treated with care, because not all open source software projects are build and structured the same way like it was done in Apache HTTP Server Developer.

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_

In a email social network, only a few member are responsible for the majority of messages. The social network presents a small-world characteristic. There is a strong relationship between the number of messages a user sends and the number of different users that respond to them. The number of activities on the mailing lists are strongly correlated with source code change activities. However they are lesser correlated with document change activities. Developers who commit changes have a more significant role in the email community, so non-developers play a less significant role. The importance of a person in a social network is correlated to his/her code change activity. 

8. What did you **not understand** of this paper?

We did not understand how the authors calculated the out-degree and in-degree. That's why we did not include these two measures in question 5.
