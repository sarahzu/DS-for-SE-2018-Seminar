## Does Refactoring of Test Smells Induce Fixing Flaky Tests?

## Questions

1. What is the **main research question/goal**? _(there may be more than one, but usually there is an overarching research question/goal.)_

In order to improve general research about the detection and automatic fixing of flaky tests (tests that can result both in a passing of failing results for the same code), the authors tried to increase the comprehension in flaky tests by analysing the role of test smells. Test smells are poor design our implementation choices used in test cases. They investigated three particular test smells, namely Resource Optimism (test case that makes optimistic assumptions about the state of external resources), Indirect Testing (testing a specific class by looking at their product class) and Test Run War (resource interference which happens when a test method allocates resources which are also used by one or more other test methods). 

The author’s hypothesis waw, that test smells provide a useful information source to find flaky tests. Also, the refactoring of test smells may lead to the resolution of the test’s flakiness. 

To investigate their hypothesis, they defined the following research questions:

RQ1: What causes flaky tests?

RQ2: How well can flaky tests be explained when test smells are present?

RQ3: How well can refactoring the test smells help to remove flakiness?

2. Why is this paper **important**?

Regression testing is a very powerful method which allows developers to ensure that source code changes do not introduce further bugs or system failures. The results of software tests are a key component in software development because developers rely on them to decide how they further proceed in the project. 
Flaky test are unreliable test cases. Their outcome is not at all deterministic. If flaky test are used, the developers are going to use unstable results to decide on their next steps and this might have disastrous consequences. For instance, the flaky tests can hide real bugs from the developers which then won’t get fixed and may cause other system defects. Or the flaky tests can show bugs to developers that are not actually there and wast their time while they try to fix a defect which is not present. As a third consequence, developers might loose their general faith in test cases and will ignore the results of correct tests. So the detection of flaky tests is a very important and needed field of research. Therefore, the topic of this paper is of high importance. 

3. What is the **methodology** used to answer the research question(s) or reach the goal?

Firstly the authors defined the test smells they wanted to use, namely Resource Optimism, Indirect Testing and Test Run War. They decided on these three, because they are related to test flakiness. To collect the data (more detail about the data is covered in question 4), they cloned all the open-source software projects they wanted to use form GitHub, detected the test smells with a detection tool and identified if the test had a non-deterministic outcome. In a next step, the authors identified the flaky tests. To do so, they run the JUnit classes in each subject system for multiple times and checked the outcome of the tests for each run. If one outcome was different than the others, the test was identified as a flaky test. To find the right amount of iterations for this process, they empirically calibrated it on a different software system not used for the study. They concluded that ten would be a suitable number of iterations. With this method, they found out, that 45% of the test methods they investigated were indeed flaky. 

In order to check RQ1, the authors had to manually check each flaky test they found. Only then were they able to identify the root cause for the flakiness. They analysed the source code and the JUnit log reporting the thrown exceptions while running the test. They also separated the tests into ten categories of smell tests, to better distinguish their nature. 

To investigate RQ2, the authors firstly had to determine which of the previously found flaky tests have also been affected by one of the considered test smells. This procedure helped them to measure to what extend the two aspects appeared together. To do so, they used a new manual analysis process which measured in how many cases the test smells were related to the flakiness of the tests. Additionally, they used the Kendall rank correlation test to measure the strength of the relationship between test smells and flaky tests. 

In order to analyse RQ3 the authors manually analysed the source code of the test methods which were involved in a design problem. They furthermore performed refactoring operations on them. After this step, the test smells were removed from the source code. After the source code was cleaned by the test smells, they again performed the flaky test identification process. This procedure provided them with the information if refactoring operations does have an effect on test flakiness. 

4. What **data** does the paper use?

The source code of 19’532 Unit test method which belong to 18 large open-source software systems (several Apache products, Elastic Search, Hibernate, JHotDraw, JFreeChart and HSQLDB). 

5. If there is a **statistical model**, what is the product, behavior, or process being modeled? What are the key characteristics of the model?

New manual analysis process: Measuring the number of occurrences were the presence of a test smell is related to the test flakiness. In more detail, this method includes the identification of the test smell instances related to the root cause of the previously identified flaky tests. So with this measure it is possible to directly map the characteristics of the test smell to the cause of the flakiness of the test.

Kendall rank correlation: This measure measures the ordinal association between two quantities. If the two quantities have a similar rank, the Kendall’s coefficient is going to be high.  

6. What are the **limitations** of using this methodology on the results?

A lot of the measuring was done manually by the authors. This leads to the question of how precise the results from the measure was. Also, for the identification of the flaky tests, they used a tool which had not a 100% accuracy. Also, it is possible that the number of iterations they used were not enough to find all flaky tests. Therefore, it is possible that not all flaky tests in the observed programs were used for the study. Refactoring code can have a positive effect, but it can also lead to undesired effects which can lead to additional bugs. Even though the authors tested their refactored code, it remains possible that some refactoring could lead to unwanted behaviour of the code.  

The project was conducted on 18 open-source projects. However, 13 out of these 18 projects belonged to the APACHE SOFTWARE FOUNDATION. So it is possible that some of the findings are only valid in projects that resemble Apache projects. Furthermore, only big open-source projects were analysed. We have no indication if the results are also valid vor small projects or commercial ones. Therefore, the findings of the paper have to be treated with caution when companies try to apply them to their own projects. They have to check if their software resembles some of the 18 observers open-source projects before they can discuss if the results are useful for their individual case.  
Furthermore, only three types of test smells were analysed. However, there exist many more and the results of the paper do not apply to these test smells. This fact has to be kept in mind when using the results of the paper, because e.g. refactoring the code may remove flaky tests that were caused by one of the observed test smells, but it maybe could not  be possible to remove flaky tests that are caused by a test smell which was not analysed. So further research in this area is needed to widen the spectrum of usage. 

7. What is **the answer** to the research question? _(in case of a goal: What is the contribution of the paper towards that goal?)_

They found out that flaky tests are quite common (45% of their analysed tests were flaky) and often contain one of the considered test smells (61% of the analysed tests). The most prominent cause for flaky tests are asynchronous waits, input-output issues, concurrency problems, test order dependency and network issues. Also, the half of the found flaky tests (54% of the analysed tests) contained a test code smell which caused the flakiness of the test. Additionally, the authors found out that it is possible to remove the design flaws by refactoring the test smells (54% of the flaky tests were removed after refactoring). Moreover, refactoring also fixed the flaky tests whose flakiness was caused by one of the observed test smell.

8. What did you **not understand** of this paper?
