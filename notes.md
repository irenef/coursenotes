# Course Notes for Module 8, COS597e

## Part III. Ethics of Inference Making
// TODO [insert transition from part 2 to part 3]

### Validity and Ethics of Past Research 
As we discussed previously, inference making has received significant criticisms in the commercial settings. It is the same case in the research world as well, and conflicts are further worsened with the attempts to use machine learning techniques to infer attributes that could bring actual societal consequences if they were to be exercised, as opposed to merely on a personal level. In this section, we will discuss two research studies that touched such ethical limit, and analyze some main attention and criticisms that they have received. 

#### Case 1: Inference on Criminality from Facial Images 
The paper "Automated Inference on Criminality using Face Images" by Wu et al. was the first paper ever to propose the notion of inferring human criminality from only facial images and nothing else. The study implemented four common classifiers: logistic regression, KNN, SVM, CNN) with facial images of 1856 real people. Half of which were convicted criminals. The images were claimed to be controlled for sensitive attributes such as race, gender, age and other attributes such as facial expressions, source camera types, etc. The researchers also listed some advantages of automated inference on criminality which include the system being independent from human biases, fair and equal judgment on all candidates, etc. However, none of this changes the fact that this paper is standing on shaky ground. Although the study has some technical flaws that raise questions to its validity, the following analysis will focus on the ethical concerns. 

##### Criticism 1: Likelihood of Conviction vs. Propensity for Crime
The paper spent some effort laying down groundwork for the argument that the human face itself is enough for inferencing criminality. At the very beginning, it claims that "in all cultures and all periods of recorded human history, people share the belief that the face alone suffices to reveal innate traits of a person" (Wu et al., 1). It also provided several "facts" found through several papers in psychology, sociology, and other related fields. The paper also quoted a "tantalizing" question in physiognomy that is associated with their own study: "what facial features influence average Joe's **impulsive and yet consensual judgments** on social attributes of a non-acquaintance member of their own species" (Wu et al., 1)? In other words, the study wishes to provide solution to the question of what kind of facial features would lead people to a certain conclusion about the owner of the face. However, the word "criminality" is defined as the quality or state of being criminal, which should be distinguished from the state of being perceived as a criminal. 

It is important to make the distinction between the likelihood of conviction and propensity for crime for several reasons. There are countless human-dependent factors involved in the conviction process that are not necessarily associated with the criminality or the level of criminality. For example, as pointed out by the authors, one's first impressions of someone are mainly influenced by the appearance of that person, and they, although possible to overturn later on, are difficult to eliminate completely in one's future judgment of the person. The presence of unquantifiable human bias has an impact on the likelihood of conviction for a suspect, but not on the criminality for a suspect, because the latter is already an unchangeable value at the time of the crime. Thus, the two notions cannot be made equivalent.  

In judging one's criminality, a judge is partially influenced by his/her first impression of the suspect/defendant, which is mainly based on his/her appearance. Consider a naive but possible scenario, the suspect is innocent but is convicted because some made-up evidence is presented against them. The judge does not consider the possibility that the evidence is made up because the judge is already subconsciously convinced that he/she is the criminal because he/she looks like one. In that case, the likelihood of conviction is high but the criminality score is 0. It implies that human bias is already a factor in the data generating phase, and therefore it is incorrect to say this model is independent of human biases. 

In short, this paper failed to acknowledge the distinction between a person's criminality and the likelihood of being convicted. It should have been named "Automated Inference on Likelihood of Conviction using Face Images" instead. 

##### Criticism 2: Inconsistent Data Source 
The study used three different data sources for the two classes of interest: criminals and non-criminals. In section 2 of the paper by Wu et al., it states that the 1126 ID photos of the non-criminals were scraped from the Internet using a Web crawler. For the ID photos of the criminals, 330 of the 730 photos were of wanted suspects and were published on Chinese government-administered websites. The other 400 were provided by a city police department in China. The inconsistency in data source introduces unquantifiable biases to the dataset since institutions have different standards and procedures for conviction. More importantly, it is not guaranteed that the 1126 faces in the first subset are really of people who have never been convicted since they are just photos of civilians scraped from the Internet. However, the validity of the true values is undecidable with current data because three separate data sources are involved. One could argue that having several data sources is common practice, but the consistency of the data for this study should be held to higher standards with such an extraordinary claim. 

##### A Summary of Criticisms from Students
Other than the criticisms discussed above, these are some main points from reading responses: 
	1. The photos of the non-criminals were posted on websites presumably designed for promotional purposes, so they tend to look more put together. 
	2. Are factors such as the source and facial expressions really controlled for in the analysis? One of the features with strong indication is the angle between the nose and the lips, which might be skewed with the presence of a smile or not. 
	3. Sample size is small and undiverse in terms of race, gender, geographical location, etc.
	4. Feedback loops could be a big problem when machine learning is applied to social issues such as criminality. 
	5. The study does not differentiate a crime from another. Criminality is treated as binary variable and all criminals are considered to be in the same class regardless of the types of crimes or the level of criminality. 

#### Case 2: Inference on Sexual Orientation from Facial Images 
As the title of the paper, "Deep Neural Networks Are More Accurate Than Humans at Detecting Sexual Orientation from Facial Images," suggests, Kosinski et al. attempt to infer one's sexual orientation from facial images only. The study used deep neural networks to extract features from 35,326 facial images, which are inputted into a logistic regression model to predict sexual orientation. The paper claims high accuracy in its results and concludes that homosexual men and women tend to have "gender-atypical facial morphology, expression, and grooming styles" (Kosinski, 2). There are several strong criticisms that question both the ethics and the validity of the study. 

##### Criticism 1: White Participants Only 
The results of the paper are based on facial images of white people only. The paper claims that it was difficult to obtain a more diverse dataset because the prejudice against gay people and the adoption of online dating websites is unevenly distributed across different racial groups (Kosinski, 34). This is more of a validity issue than ethics, because the study is not guaranteed to be generalizable to other racial groups. The study does acknowledge this limitation, and provides some supporting arguments: the current results of this study are consistent with the PHT of sexual orientation, which was supported by past research on mammals including human, and faces are likely to be affected by the exposure to gender-atypical androgen levels to a similar degree regardless of racial differences. However, without further medical proof or empirical results from a more diverse dataset, it is invalid and unethical to claim that the study can be generalized beyond the studied population. 

##### Criticism 2: "Out" Participants Only 
Another limitation of the dataset is that all participants are openly homosexual. It is possible that people who are openly gay have similar ways to present themselves in pictures, which would not be found on gay people who do not wish to be identified as homosexual. It is also possible that people with certain facial features that are commonly perceived as gay are more likely to come out of the closet. In both cases, the model trained on the faces of only openly gay participants would not work, or become less accurate, when detecting secretly gay individuals. The paper counters the argument by pointing out other factors that would cause an individual to come out such as social and cultural factors, and that some participants still wish to be discreet when it comes to their sexual orientation. However, it does not change the fact that the facial features studied and their distribution do not represent closeted gay individuals, and that the accuracy will drop significantly when applied to a more representative dataset. 

##### Criticism 3: "Warning" Argument
If this sexual orientation predicting tool gets exercised or even commercialized, it could be used on individuals without their consent since facial images of a person are not difficult to obtain nowadays with modern mobile devices or from online. That means individuals could have their sexual orientation falsely identified, or correctly identified when they wish to keep it unknown. This is a main privacy concern shared by many critics. The authors try to liberate themselves from this issue by stating that they only used widely available tools and methods, and publicly available data. They claim that they "did not create a privacy-invading tool, but rather showed that basic and widely used methods pose serious privacy threats" (Kosinski, 35), and this tool will be developed sooner or later by someone else if not by them. Furthermore, the authors claim that the intention of this study is to warn policy makers so that they are aware of such risks and take preventive measures before the tool becomes widely available to the general public. However, this argument does not stand because presenting the possibility of such inference making introduces a vulnerability of which was unknown, especially considering there is no existing law or policy regulating this practice. To make an analogy, a bomb can be made with widely available commodities too, but publishing the formula online introduces risks that most people were unaware. Both cases should be considered unethical. 

##### A Summary of Criticisms from Students
Other than the criticisms discussed above, these are some main points from reading responses: 
	1. The authors claim that the model is invariant to facial expressions. However, some critics point out the model, VGG-Face, can be trained to classify facial expressions, and therefore facial expressions could be taken into account implicitly.
	2. The authors and the paper didn’t explicitly state that they had the permission to scrape the images from the dating site. It could have violated the privacy of the site’s users and the site’s terms of service.
	3. high accuracy of 91% was reported in many news outlets, however, that is the result from one specific scenario, where the algorithm is asked to identify the person who has a higher chance of being gay between two people.

### Ways to Regulate Inference Making Research 
Kosinski et al. were right about one thing -- policymakers should be aware that there will only be more research like the two discussed above, and preventive measures should be taken before such tools become widely available. This section will discuss several possible ways to regulate research or tools that involves inference making of sensitive attributes.

	1. Companies should disclose existing and potential inferences.
		E.g. if a discount store wishes to infer pregnancy of its customers from their 
		shopping behavior, it should inform its customers of this practice or even ask 
		them to sign an agreement before any shopping record is used for inference making. 
		Some claim that it would not be privacy-invading if only public data is used. 
		However, that is not valid because when individuals agreed to release their data 
		as public, they were not aware of the possibility of such inference making. 
		It is therefore still unethical to make inference on sensitive attributes from 
		public data.   
	2. Make domain expertise mandatory. 
		Another way is to require domain expertise for research that involve inference 
		making on sensitive attributes. In other words, researchers are only allowed to 
		work in their own field. The drawback of this method is that it hinders 
		interdisciplinary collaboration. 
	3. Hold research to higher standards via IRB process, and hold surprising inferences 
	   to even higher standards.    
		Two separate sets of standards could be put in place for research that make 
		inference on sensitive attributes and research that make surprising inferences 
		such as the two cases analyzed above.

#### Student Comments: Criteria for "Crossing The Line"
// TODO insert ideas from students 


## Part IV. Appendix: Does Everything Predict Everything  
// TODO insert transition between part 3 and part 4

### Limitations of Prediction

#### An Experiment 

Consider F(x) = 1 - 2x<sup>2</sup>, x is a member of [-1, 1]. Then F<sup>100</sup> is a black box, and the goal is to maximize R<sup>2</sup> because R<sup>2</sup> is a measure of how close the data are to the fitted regression (Devore, Minitab blog). 

Then let us change x by a small amount by adding 10<sup>-10</sup> to it and plug it into our black box. However, F<sup>100</sup>(x+10<sup>-10</sup>) is uncorrelated with F<sup>100</sup>(x). In that case, the R<sup>2</sup> value is 0, which means the model explains "none of the variability of the response data around its mean" (Minitab blog). In other words, our predictions using the black box model will not better better than random guesses. 

#### Chaos Theory 
This experiment above demonstrated a case in Chaos theory. Chaos theory is a mathematical study that focuses on nonlinear dynamical systems. The term "dynamical" refers to the property where the system changes over time and the calculation of the new state is based on its current state (Boeing). Chaos theory is thought to be originated from natural systems, as many natural phenomena behave like nonlinear dynamical systems. For example, weather and climate are two natural phenomena people have been studying since long ago in order to predict them more accurately. However, the brief experiment above exemplifies the limitation that researchers run into when designing a model to predict behavior in a nonlinear dynamical system. The butterfly effect is also an example of the chaos theory -- a butterfly flaps its wings in China, which causes a hurricane in Texas. It is an analogy that describes small changes could cause big difference in a future state in a nonlinear dynamical system (Minitab blog). 

In addition, data collection methods are limited. There will always be noise in the input as well. All of those factors add up together, so a prediction is fundamentally flawed, especially when it comes to more complex problems such as predicting criminality. Thus, researchers face enormous limitations when building a prediction model for any target that resembles a nonlinear dynamical system.

Prediction problems face limitations of different levels depending on how "ambitious" the problem is. For example, very different accuracy should be expected for inference making of gender and identity. The accuracy for gender would be higher than for identity. Another case to consider is reconstructing human face with DNA. Modern biological theories support that DNA decides facial features. However, science is not quite there yet and the performance of current models are not better than random (Regalado).  

#### Student Responses 
Students were asked to predict the difficulties of the following inference problems in the next decade or two. To simplify the discussion, it is assumed that unlimited amounts of training data and hardware will be available. 

Please note that only the quantifiable and unambiguous answers are counted. 
The four categories are ranked as the following: almost perfect > high accuracy > better than random > not better than random

	1. Identifying faces in a crowd
		- not better than random: 0
		- better than random: 0
		- high accuracy: 0
		- almost perfect: 12
	2. Generating an image of a person’s face given their DNA
		- not better than random: 4
		- better than random: 3
		- high accuracy: 4
		- almost perfect: 0
	3. Predicting 2-year recidivism risk (given everything observable about a person)
		- not better than random: 0
		- better than random: 6
		- high accuracy: 1
		- almost perfect: 4
	4. Inferring a person’s sexual orientation from photos of their face
		- not better than random: 2
		- better than random: 5
		- high accuracy: 4
		- almost perfect: 0
	5. Inferring an author’s gender based on text written by them
		- not better than random: 0
		- better than random: 1
		- high accuracy: 4
		- almost perfect: 6
  

## References 

"Automated Inference on Criminality using Face Images" - Wu et al.

"Deep Neural Networks Are More Accurate Than Humans at Detecting Sexual Orientation from Facial Images" - Kosinski et al. 

Devore, Jay L. (2011). Probability and Statistics for Engineering and the Sciences (8th ed.). Boston, MA: Cengage Learning. pp. 508–510. ISBN 0-538-73352-7.

"Regression Analysis: How Do I Interpret R-squared and Assess the Goodness-of-Fit?" The Minitab Blog

Boeing (2015). "Chaos Theory and the Logistic Map". Retrieved 2015-07-16.

Does Your Genome Predict Your Face? Not Quite Yet. MIT Technology Review. - Antonio Regalado