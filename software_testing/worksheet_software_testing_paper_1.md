## When, How, and Why Developers (Do Not) Test in Their IDEs

## Questions

1. What is the **main research question/goal**?

The main goal is to study how developers test in their IDE and to identify the habits of how developers drive software development with testing.  To understand the testing patterns the researchers compared the _state of the practice_ to the _state of the art_ of testing and tried to answer the following research questions:
RQ1: _When and Why Do Developers Test?_
RQ2: _How and Why Do Developers Run Tests?_
RQ3: _How Do Developers React to Test Runs?_
RQ4: _Do Developers Follow Test-Driven Development (TDD)?_
RQ5: _How Much Do Developers Test?_


2. Why is this paper **important**?

It is substantial to gain knowledge about how, when and why developers actually test, since this knowledge can be used to determine whether the used testing practices could be one reason for the observed bug proneness of software in practice. 

This paper wants to gain a better understanding of the actual testing practices and questions the common expectations and beliefs about software testing. Since this study was done in a large and varied population of software engineers in the real world, the findings can be used to form a new basis for further researches and practitioners: 

* Further researches can build their contributions on the findings in this paper instead of on the common expectations and beliefs. By doing so, they can make their findings more valid. 
* Software Engineers can use the findings to change their testing behaviour. When they are aware that they overestimate their testing time, they might start to put more effort to perform tests, which might lead to better software quality.


3. What is the **methodology** used to answer the research question(s) or reach the goal?

In order to answer the research questions, they study the testing behaviour of 416 participants in a longitudinal, large-scale field study that has run for five months. The investigation focused on tests that are done inside the IDE by the developer. To extract developer’s activity, they used low-inference observation instruments that are installed within their Eclipse IDE. 

Additionally, they used a mixed-methods approach to compare the results from the automated monitoring of developers with WatchDog to the subjective answers in surveys.

For the research question 4 they applied the Beck’s definition of Test-Driven development (TDD) to the interval concept they used with WatchDog. With that, they provided a verifiable definition of TDD in practice: Newly created non-finite automatons made it possible to recognize the usage of TDD. They were converted to equivalent regular expressions which were then used to match against observed sequences of intervals to check a developer’s adherence to TDD.


4. What **data** does the paper use?

As mentioned in question 3, they used data collected from 416 software engineers from industry as well as open-source projects around the word. They could objectively observe how and when developers test in Eclipse with the usage of the plugin WatchDog. 

_Participants_: 
They attracted study participants using various methods: For example, they provided a high-profile project website, offered razzle prizes, delivered useful WatchDog functionalities such as feedback on development behaviour, wrote articles and blogs and gave presentations at conferences. The participants were most likely interested in testing because the researchers tried to put emphasis on the testing focus of the plugin to attract developers during the participant acquisition.
* Country: The considered participants came from 68 different countries. The most of them were from the United States (25%).
* Operating System: 75% of the participants use Windows, 14% MacOS and 11% Linux.
* Programming experience: 60% users had less experience than 3 years. 20% were very experienced developers with more than or equal to 7 years of experience.

_Testing Behaviour Data_: 
The data they used for this study was collected from the 1. November 2014 to 1. March 2015. In total they observed 24,255 hours of working time in Eclipse in the 460 projects that were registered. Student data were analysed separately and data from deprecated versions of WatchDog was filtered out. 
Using listeners for UI events related to programming behaviour and testing, they collected in total 1’337’872 user actions (intervals) from the 416 participants. Intervals are grouped events and have a specific type (_EclipseOpen, Perspective, UserActive, JUnitExecution, Reading, Typing_) and start and end time. Each interval was enriched with further information which they used for the analysis: For example, a _Reading_ or _Typing_ interval additionally contained information about the number of code lines, the file name, and type of code: production or test code.

_Survey Data_: 
To collect initial data about the participants, they made them fill out a short survey when they registered as a user for WatchDog. This survey collected data about the participants programming expertise, their beliefs about their testing behaviour and which testing frameworks they employ. 


5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?

For each test made in this study they firstly checked the distribution of the used data by performing a Shapiro-Wilk Normality test.  They performed non-parametric tests to investigate their research questions, because all distributions significantly deviated from a normal distribution according to the Shapiro-Wilk Normality tests.
* Wilcoxon Rank Sum test: Done in order to check whether there is a significant statistical difference between two distributions.
* Spearman rank-order correlation: Performed for correlation analyses.

6. What are the **limitations** of using this methodology on the results?


7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_


8. What did you **not understand** of this paper?

