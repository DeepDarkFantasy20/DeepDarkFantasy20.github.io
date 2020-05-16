#### Research Proposal

Improve large-scale vision model selection in transfer learning

Yixin Chen



##### Introduction and Background

Thanks to the powerful GPUs(Graphic cards) which are really suitable for deep learning and huge human-annotated datasets(ImageNet[2]) which contain nearly millions of image data, the Computer vision and Machine learning techniques have been changing the world. However, in real-world situations, researchers are often faced with the dilemma where limited labeled training data are available.

​	The common practice is to transfer pre-trained models(**encoded-Knowledge**, the remainder **of the proposal** use PTM to indicate pre-trained models) to help resolve our target task. It’s reasonable when referring to the real-world common sense, a person living in northern hemisphere can infer summer in southern hemisphere from northern's cold climate in December although he/she never comes to southern hemisphere. That’s the interesting thing in transferring, one can utilize some known knowledge to learn other unknowns. So as in transfer learning, by definition, some already-encoded knowledge in one domain could help assist in solving our target tasks in another domain.

​	This research proposal will focus on model selection analysis in transfer learning and it will propose some methods to do large-scale model selection.



#####Introduction and Background(back-up)

Driven by massive human-annotated data(ImageNet[2]) and advanced deep models(ResNet[4]), the

field of Artificial Intelligence has made great breakthrough in recent years. Thanks to the powerful

GPUs which are really suitable for deep learning and huge datasets which contain nearly millions of

image data, the Computer vision and Machine learning techniques have been changing the world.

However, in real-world situations, researchers are often faced with the dilemma where limited

labeled training data are available.  Using traditional approaches with limited labeled training

data will surely lead to an overfitting problem, which yields poor results.

​	The common practice is to transfer pre-trained models to help resolve our target task. It’s rea-

sonable when referring to the real-world common sense, a person living in northern hemisphere will

know the season of southern hemisphere in December although he/she never comes to southern

hemisphere, because he/she can infer summer in southern hemisphere from the northern hemi-

sphere’s cold climate in December. That’s the interesting thing in transferring, one can utilize

some known knowledge to discover other unknowns. So as in transfer learning, by definition, some

already encoded knowledge in one domain could help assist in solving our target tasks in another

domain, for instance, a pre-trained model expertises in classifying between several breeds of cats

can also be used to classify between several breeds of dogs because cats and dogs share some

common features like they all have four legs and they are fluffy.

​	This research proposal will focus on model selection analysis in transfer learning and it will

propose some methods to do large-scale model selection.



##### Problem Statement

Based on such background, another problem has arisen in transfer learning, confronted with massive PTMs, which model should we adopt to benefit the current target task most?  Currently the model selection is done blindly by using ImageNet PTMs(These models excel at 1000 categories classification) which however won't always produce satisfactory results for all the tasks, as some tasks(not classification-like) are significantly different from ImageNet.

​	First, there are numerous existing tasks and heterogeneous models, theoretically, large amount of tasks can be adopted to transfer to some other tasks, so it’s rather difficult to conduct large-scale experiments to measure the transfer-ability between PTMs due to the expensive computer processing time and even worse when a new task joins. Despite the computational cost, it’s still impossible to say that we have picked up the right PTM because there didn’t exist a system that contains all the models over the world, and there weren’t any ready-made PTM w.r.t. a brand new task.

​	More specifically, the following research questions need to be addressed:

- what are the new progress to reduce the computational cost in large-scale model selection?
- what are the intrinsic meaning of transfer learning?  Can we be inspired by deep model explainability to help us understand intrinsic meaning of transfer learning and benefit the research of model selection?

- what are the current industrial applications in transfer learning?







#####Problem Statement(back-up)

The importance of transfer learning is known to us all while we only have limited labeled training

data. Yet another problem has arisen in transfer learning, confronted with massive pre-trained

models, which model should we adopt to benefit the current target task most?  Currently the

model selection is done blindly by using ImageNet PTMs. However, the ImageNet

PTMs will not always produce satisfactory results for all the tasks, as some tasks are

significantly different from ImageNet.

​	First, there are hundreds of different existing tasks and pre-trained heterogeneous models(i.e.,

different domains and architectures), theoretically, large amount of tasks can be adopted to assist

in resolving some other tasks, so it’s rather difficult to conduct large-scale experiments to measure

the transfer-ability between PTMs as the computational complexity is of square order

and even when a new task joins, it will cost growing expensive GPU hours to complete and

perfect this affinity between each PTMs. Then, assumed that we don’t care about the

computational cost, it’s still impossible to say that we have picked up the right pre-trained model

because there didn’t exist a system that contains all the models over the world, and there weren’t

any ready-made pre-trained models w.r.t. a brand new task.

​	In summary, there is a need for a better understanding of intrinsic meaning of transfer learn-

ing and a structured approach to do large-scale model selection. More specifically, the following

research questions need to be addressed:

- what are the intrinsic meaning of transfer learning?  Can we be inspired by deep model

  explainability to help us understand transfer learning and benefit the research of model

  selection?



- what are the new progress to reduce the computational cost in large-scale model selection?

- How can we deal with the situation whether there are suitable pre-trained models at hand

  or not?

- what are the current industrial applications in transfer learning?



##### Objectives

The long term goal of this research project is to develop an automatic large-scale transfer learning system that measure numerous PTMs' inter-transfer-ability by explainability or some other solid approaches. The objective of the current study is to develop faster and cheaper ways to accelerate the speed of measuring the transfer-ability and explore explainability inside the deep models to better illustrate the significance of transfer-ability. Particulaly, the study has the following sub-objectives:

- To provide a comprehensive review of model selection and deep model explainability reseach

  in transfer learning.

- To develop a novel metric for measuring the transfer-ability in a cheaper way without

  losing much optimality.

- To review current industry practices and researches in regards to transfer learning.

- To design a unified framework for automatic measurement in transfer learning.

​	The result of this study will be valuable to the industry practitioners as well as related software developers to easily conduct transfer learning experiments and tackle plenty of tough fields where few labeled data were provided.





#####Objectives(back-up)

The long term goal of this research project is to develop an automatic large-scale transfer learning

system that adopt numerous PTMs and measure their inter-transfer-ability by explain-

ability or some other solid approaches, then choose the better source models to help improving

the performance of new tasks. The objective of the current study is to develop faster and cheaper

ways to accelerate the speed of measuring the transfer-ability and explore explainability inside the

deep models to better illustrate the significance of transfer-ability. Particulaly, the study has the

following sub-objectives:



- To provide a comprehensive review of model selection and deep model explainability reseach

  in transfer learning.

- To develop a novel metric for measuring the transfer-ability in a more cheap way without

  losing much optimality.

- To review current industry practices and researches in regards to transfer learning.

- To design a unified framework for automatic measurement in transfer learning.

  The result of this study will be valuable to the industry practitioners as well as related software

developers to easily conduct transfer learning experiments and tackle plenty of tough fields where

few labeled data were provided.



##### Preliminary Literature Review

Currently, many dedicated researchers make contributions to transfer learning, W. Dai et al.[1] proposed to re-weight some labeled data in source domain for use in the target domain. Razavian et al.[6] stated that good feature representations extracted from deep models can reduce the error in transfer learning.  J. Gao et al.[3] discovered that shared parameters between the source domain and target domain models can benefit transfer learning. L. Mihalkova et al.[5] built mapping of relational knowledge between the source and the target domain. 

​	Recently, Zamir et al.[8] proposed a transferring structure, termed taskonomy, but expensive computational cost made it hard to extend once new tasks join. J. Song et al.[7] improved taskonomy by generating transfer-ability from attribution maps, but it’s difficult to deal with the situations that few or no PTMs are available.

​	A literature review shows that past studies are primarily focused on how to improve accuracy of transfer learning and how to do model selection in a small range. They are blindly adopting unsuitable source models to transfer and what is missing from the past studies is the importance of real extensibility and fast processment. I've done research about transfer learning before, from those research experiences, I realize the limitations of current studies and I have sufficient preparations to go on with further research.



#####Preliminary Literature Review(back-up)

Currently, many dedicated researchers make contributions to transfer learning, W. Dai et al.[1]

proposed to re-weight some labeled data in source domain for use in the target domain. Razavian

et al.[6] stated that good feature representations extracted from deep models can reduce the error

in tackling diverse range of tasks in transfer learning.  J. Gao et al.[3] discovered that shared

parameters between the source domain and target domain models can benefit transfer learning.

L. Mihalkova et al.[5] built mapping of relational knowledge between the source domain and the

target domain.

​	Previously, some researchers proposed some heuristic methods to do model selection but they’re

not accurate enough for large-scale transferring. Recently, Zamir et al.[8] proposed a fully compu-

tational transferring structure, termed taskonomy, but expensive computational cost made it hard

to extend once new tasks join. J. Song et al.[7] improved taskonomy by generating transfer-ability

from attribution maps, but it’s difficult to deal with the situations that few or no pre-trained

models are available.

​	A preliminary literature review shows that past studies are primarily focused on how to improve

accuracy of transfer learning and how to do model selection in a small range. They are blindly

adopting unsuitable source models to transfer and what is missing from the past studies is the

importance of real extensibility which makes sense in practice in industry when lots of challenging

problems need to be addressed.

​	As for me, I have involved in some research projects about transfer learning, some of my papers

are accepted by international conferences and the others are under review. From those experiences,

I realize the limitations of current studies and I have sufficient preparations to go on with further

research.



##### Methodology

The primary research method for this study is algorithm design and experimental research. Figuring out the intrinsic explainability and developing effective algorithm is the very first step towards designing a large-scale model selection system.

​	This study will first review the existing algorithms for establishing measurement metrics and some cutting-edge studies in explainability. Based on this understanding, a new measuring method will be developed to do inference about estimating transfer-ability accurately and quickly between each PTMs. In the second stage of this study, large-scale model selection experiments are conducted and more PTMs are collected in a pool to be the base of our systems. Then, when the sizes of our systems become larger, we will omit some PTMs or even discard some PTMs which merely take effect. As for some brand new tasks which don’t have mature PTMs, we plan to develop some heuristic methods to explore the inner structure and compare with existing tasks at first, then basically select some best source tasks to conduct early-stage transfer learning and later update these primitive pre-trained source models using Iterative Method.

​	Finally, a framework is unified and it’s equipped with the ability to discover new PTMs, collect them into the model pool, automatically transfer them to a new specified target task in best performance, and it is updating all the time.



#####Methodology(back-up)

The primary research method for this study is algorithm design and experimental research. Figur-

ing out the intrinsic explainability from deep models and developing advanced effective algorithm

is the very first step towards designing a large-scale model selection system in transfer learning.

​	This study will first review the existing algorithms for establishing measurement metrics and

some cutting-edge studies in explainability. Based on this understanding, a new measuring method

will be developed to do inference about estimating transfer-ability accurately and quickly between

each pre-trained models. In the second stage of this study, large-scale model selection experiments

are conducted and more pre-trained models are collected in a pool to be the base of our systems.

Then, when the sizes of our systems become larger, we will omit some pre-trained models to reduce

the computational complexity using some applications in deep model explainability or even discard

some pre-trained models which merely take effect from the pool. As for some brand new tasks

which don’t have mature pre-trained models, we plan to develop some heuristic methods to explore

the inner structure and compare with existing tasks at first, then basically select some best source

tasks to conduct early-stage transfer learning and later update these primitive pre-trained source

models using Iterative Method.

​	Finally, a framework is unified and it’s equipped with the ability to discover new pre-trained

models, collect them into the model pool, automatically transfer them to a new specified target

task in best performance, and it is updating all the time.



#####References

[1] Wenyuan Dai, Qiang Yang, Gui-Rong Xue, and Yong Yu.  Boosting for transfer learning. In ICML 07.

[2] J. Deng, W. Dong, R. Socher, L.-J. Li, K. Li, and L. Fei-Fei.  ImageNet:  A Large-Scale Hierarchical Image Database. In CVPR09, 2009.

[3] Jing Gao, Wei Fan, Jing Jiang, and Jiawei Han. Knowledge transfer via multiple model local structure mapping. In KDD ’08

[4] Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun. Deep residual learning for image recognition. CoRR, abs/1512.03385, 2015.

[5] Lilyana Mihalkova, Tuyen Huynh, and Raymond J. Mooney. Mapping and revising markov logic networks for transfer learning. In AAAI ’07.

[6] Ali Sharif Razavian, Hossein Azizpour, Josephine Sullivan, and Stefan Carlsson. Cnn features off-the-shelf: An astounding baseline for recognition. In CVPR Workshops, June 2014.

[7] Jie Song, Yixin Chen, Xinchao Wang, Chengchao Shen, and Mingli Song. Deep model transferability from attribution maps. In NeurIPS, 2019.

[8] Amir R. Zamir, Alexander Sax, William Shen, Leonidas J. Guibas, Jitendra Malik, and Silvio Savarese.  Taskonomy: Disentangling task transfer learning.  In CVPR, June 2018.







#### Past Research Experience

- Cross Research on Wireless Communication and Machine Learning(Apr. 2018 - May. 2019)

  Laboratory of Information and Communication, College of Information Science and Electronic Engineering, Zhejiang University.

  Supervisor: Prof. Guanding Yu

  Our research topic is 'Improve Resource Allocation Efficiency by Machine Learning', we first modeled joint User-BaseStation Resource Allocation problem into a mixed integer non-linear programming(MINLP) problem, it is a mathmatical optimization problem and it's a NP-hard problem, which means intractable and high computational-cost. Our aim is to accelerate the speed of algorithms without losing much optimality. To this end, we adopted branch-and-bound algorithms to solve the original optimization problem, then we use machine learning techniques to speed up this process, it achieved 1.5x speed up with only losing about 1 percent optimality in some cases, which yields good results. In Wireless Communication, such gap can be tolerable because users are more concerned about Qos(Quality of Service) and speed of establishing communication links.

  As for me, in this research project I am responsible for coding and conducting experiments, which are of vital importance because these experiments reflect the effect of our algorithm.



- Deep Model Transferability from Attribution Maps(Mar. 2019 - Jun. 2019)

  Laboratory of Visual Intelligence and Pattern Analysis, College of Computer Science and Technology, Zhejiang University.

  Supervisor: Prof. Mingli Song 

  We focused on Transfer Learning and Computer Vision. Our aim is to speed up the period of measuring transferability between several heterogenous models(different architectures, task etc.). Recently, some related work directly conducted transfer learning experiment to measure transferability between each models, but it costs unaffordable GPU hours(expensive computer processing time). We propose a novel and cheap method to measure task transferability, comparing heterogenous models by projecting them into a common space using attribution maps. The keypoint of this study is that we only need some pre-trained models which are easy to get via Internet and requires no labeled data which is vital in most deep learning researches but hard to obtain in real-world scenarios, our approaches will not need any labeled data, which means good application in industry practisions. Also, the high speed reduces the expensive computational cost, which contributes to good extensibility of our study. This paper is accepted by NeurIPS 2019 already and will be published soon.



- Deep Attribution Graph for Deep Knowledge Transferability(Jul. 2019 - Sep. 2019)

  Laboratory of Visual Intelligence and Pattern Analysis, College of Computer Science and Technology, Zhejiang University.

  Supervisor: Prof. Mingli Song 

  We focused on Knowledge Representation and Transfer Learning, our motivation is attempting to seek the relationship between each input data and see how this inner relationship could make sense in transfer learning. We proposed a new method to encode the deep knowledge inside deep models as graphs and conducted similarity analysis. We generated graph for each model and compare them with each other, it's cheap and fast with our method to get the similarity, which is useful to indicate the transferability of each pairs of model. In the application of our study, we answered two questions in transfer learning: model selection and transfer layer selection, our method can reveal clear relationship between the effect of transfer learning and our generated graphs w.r.t. selected models. This work is submitted to AAAI 2020, under peer-review.

#### Proposed Research Topic - Please describe your proposed research topic

Computer Vision(CV) is a fascinating field of Computer Science, those researches about CV aim to make computers behave like human's visual perceptron and sense the visual world. It has been developing rapidly since the invention of powerful graphic cards and huge datasets. Many advanced and valuable products are derived from Computer Vision, like face recognition systems and auto-pilot from TESLA etc..

Machine Learning(ML) is a research field that teaches computers to learn from experiences and get performance in some tasks. Unlike programming, Machine Learning is always regarded as implicit programming and it can realize some magical breakthrough that traditional computer technologies were unable to do.

####Reasons for wishing to pursue PhD studies

My interest in Computer Science is the main motivation for me to choose to pursue PhD studies. I love Computer Science from an early age, though I don't major in Computer Science in my undergraduate, I still choose some major courses in Computer Science and get excellent grades. During my undergraduate, I found some interesting reseach fields and some mysterious problems in Computer Science, which makes me willing to dive into it. I love research and participated in some research projects from sophomore, it makes me feel excited to conduct cutting-edge research in Computer Science and design novel algorithms that change the world. PhD studies consist these aforementioned all, not like master or Mphil studies, the long-period studying time enable a student to calm down and complete real meaningful research, which suits me very well. And I believe that, a person who is the expert of one research field and is recognized by colleagues can be eligible to the PhD degree, which is the highest degree and means a lot to me.

As for Hong Kong, which is the known cosmopolitan city of high prosperity over the world, it must be a good chance to study and greet lots of precious opportunities in Hong Kong. Besides, Hong Kong Universities enjoy good reputations and they are famous for Computer Science especially Computer Vision, it will be awesome to get educated under supervision of great professors in Hong Kong Universities. Also, different from mainland China, more English education will be provided, and there will be more chances for us to have academic communications with some foreign peers and teachers.

All in all, pursuing PhD degree has always been my dream, and Hong Kong will definitely play an important role as the proper platform in my graduate time for me to realize that. 

#### Long-term Career Plan

As a PhD applicant, I desire to do research about Computer Science, especially Computer Vision. Certainly, after graduation, I will look forward to continuing doing research about Computer Vision. Becoming a professor and leading a research team in unniversities will be my first choice, I not only love to do research by myself, but also wish to lead a group where group members conduct diverse range of research directions in Computer Vision, in the end, all things unite and return to one big research breakthrough. Choosing to be a professor in universities will also provide me a suitable place to calm down and do real research.

My second choice is to be a researcher in some research groups or technology companies. One important reason that Computer Vision attracts me is that it's practical and intuitive, many fascinating techniques such as face recognition, object tracking and medical Image processing are all derivative from Computer Vision. Those big technology companies which are equipped with plentiful computational resources make it possible to realize some fancy ideas in research. I am interested in designing and inventing vision technologies that change the way people live, like real autonomous vehicles and so on. It's exciting when I imagine that the research project I participate in will be utilized by some other people in the world.

For long-term career plan, I wish I can work with some like-minded people and make Computer Vision and Artificial Intelligence more applied in daily life.

#### Contributions to ..

As a researcher, the ultimate goal for me is to conduct cutting-edge research and solve frontier research problems. Theoretical research is of vital importance to all other kinds of research, although it is sounding far away from real life, many new technologies are originated from theory. Having theoretical and fundamental research will build the base for other advanced researches, and if I were successful in these kinds of researches, I would not hesitate to share these scientific findings with peers and colleagues, helping others' researches step forward based on mine. The opposite of the theoretical is practical research, it's much closer to our everyday life. Since the invention of Computer, it has been changing the world year after year, the information renovation has made remarkable progress in nowaday's society. In my career, I would develop more advanced algorithms and exert more effort on making more useful information products to facilitate citizen's life in Hong Kong and even the whole world. If possible, I would like to establish a company to do practical research of Computer Science and Technology in Hong Kong, carrying out more comprehensive studies and developing a unified Artificial Intelligence system in the future.

As a future resident, it is my duty to make Hong Kong to be a better place. I love volunteering work, it is a pleasure to be a volunteer inside and outside school, helping other people and making contributions to society. When I am eligible to be a teaching assistant, I would do my best to assist professors to manage the courses and give good guidance to undergraduate students.

#### Other Remarks

I have maintained excellent academic grades over three consecutive years, and fortunately got two National Scholarships which are not easy to obtain in top universities, unlike other colleges, we have to prepare a 5-minutes defense in front of the whole college students and reply to professors' questions. Candidates need to be well-rounded, and the final decision is made by the whole commitee. Out of nearly 140 undergraduates, only two of them will get National Scholarship in one year. Although I've obtained some awards and prizes before, I am still strict with myself in undergraduate courses, 28% of my courses are full credits, 62% of my courses receive above 90 grades and my overall GPA are above 90.

I attended contest from my freshman year. I have participated in Calculous Contest and Physics Contest and fortunately got third-prize. Also, I have been awarded as Meritorious Winner in 2018 ICM. In my sophomore year, we got funded from Zhejiang Province Government to conduct research project about Artificial Intelligence and finished successfully. In my junior year, I joined vision lab of Computer Science Department and conduct research on Computer Vision and Machine Learning. At the same time, one paper was accepted by NeurIPS 2019, the top international Conference in Machine Learning and one paper was submitted to AAAI 2020, the top international Conference in Artificial Intelligence. Later, I received research intern offers from Microsoft Research Asia(MSRA) Machine Learning Group and Tencent Youtu X-lab, it will be great to work as an intern in big industry research groups.

I have good English skills, especially reading and writing. During the past years, I have read some top conference scientific papers and sometimes write essays in English, it will be natural for me to transfer my role to a PhD student from undergraduate. Besides, I have also got good grades in TOEFL and GRE exams, which is essential for students who want to pursue degrees abroad, and it proves that I have adequate preparations to pursue a PhD degree.    



#### Recommendation

 The applicant is the top student in the College where I take office, even in the whole university. He got really excellent academic ability with 2 National Scholarships and many other Scholarships. In my Information Theory class, he got full-grade and just behaved well in class quizes and after-class projects. 

  As a role of being his advisor of research projects, during the the whole period(about one year), we would have a meeting once a week, I could see that he was passionate to conduct frontier research and learn new things. It was easy and comfortable to work with him and discussed about research problems. Thanks to his proficiency in English and good ability of communication, he could quickly adapt to my lab's working rhythm and atmosphere. In the end of this project, he successfully completed it and received active response from other teachers. 

  The past year I haven't got in touch with him very regularly, but I heard that one of his papers was accepted by NIPS, the famous International Conference(CCF A), and only 7 papers of Zhejiang University were accepted in 2019, which makes it precious for an undergraduate to achieve such progress in research.

  Thus, I strongly recommend the applicant to apply for HKPFS and PhD program.

####Please describe the research ability and potential of the applicant, and explain any other dimensions of the applicant's experience and skills that are relevant to his/her application

The applicant has great passion and interest towards research. He is potential at discovering new problems and tackling difficulties. He shows seriousness and carefulness, which I reckon the very ability for research and the reason he got so excellent grades in three years. 

He is well-motivated and have 1~2 years of research experiences, so it'll be smooth for him to get to participate in research activities in the future PhD program. He not only spares no effort to overcome tough circumstances in research by himself, but also is willing to communicate with lab members, which makes him quite adaptable to new environment.









I have known the applicant for about 1 year and I am his research mentor.



The applicant has got great academic achievements during three years, as I know, he obtained many scholarships and awards especially 2 National Scholarships and Meritorious Winner in ICM(2018), which shows solid mathematical foundations for Computer Science studies. Also, excellence academic performance reflect his seriousness and full-attention, which I think it's of vital importance in research. 

  During his sophomore year of university, he joined my research group focusing on Transfer Learning. He conducted research on heterogeneous models transferring with efficient methods and metrics, and this conference paper was accepted by NeurIPS 2019(Top International Conference). Besides, he also conducted research on Knowledge Representation, which was utilized to solve two important problems in transfer learning, and this paper was accepted by AAAI 2020(Top International Conference). It's really challenging for an undergraduate to achieve such progress in research and I can see his potential and passion towards research. The university also awards him with First-class Research Scholarships twice. In my Lab, he will report to me or some other PhD students in a weekly routine, he has already adapted to this research circumstances, which helps a lot for his further PhD study.

  Herein, I gave him my highest recommendation without reservation and I hope he can have the precious opportunity to obtain HKPFS and study further at your prestigious university.

-------

The applicant is self-motivated and pay focused attention to research, he is good at conducting experiments to verify new research ideas and wouldn't stay at a spot for too long. From the very beginning, he can quickly accustom to my group and conduct early-stage research, which can't be separated from his great course grades and solid academic foundations. He is hard-working and never show careless to details, which is the most important quality of a researcher. 

  He has got a lot more research experiences than most other peer students I've ever seen. Before joining my group, he has participated in some research projects and contests. His goal to pursue PhD degree has never been changed since the time I met him, and I think it is the inner motivation that drives him to go on with further graduate study.



Guanding Yu (Format to be changed)

Dear Selection Committee,

My name is Guanding Yu. I am a professor at the College of Information Science and Electronic Engineering in Zhejiang University. I am writing this letter to give my highest possible recommendation for Mr. Yixin Chen to the PhD Program in your department. As his research mentor and course instructor for 1 year, I make this recommendation with great familiarity with him. 

The applicant is the top student in the College where I take office, even in the whole university. He got really excellent academic ability with 2 National Scholarships and many other Scholarships. In my Information Theory class, he got 98 and just behaved well in class quizes and after-class projects. 

  As a role of being his advisor of research projects, during the the whole period, we would have a meeting once a week, I could see that he was passionate to conduct frontier research and learn new things. It was easy and comfortable to work with him and discussed about research problems. Thanks to his proficiency in English and good ability of communication, he could quickly adapt to my lab's working rhythm and atmosphere. In the end of this project, he successfully completed it and received active response from other teachers. 

  The past year I haven't got in touch with him very regularly, but I heard that one of his papers was accepted by NIPS, the famous International Conference(CCF A), and only 7 papers of Zhejiang University were accepted in 2019, which makes it precious for an undergraduate to achieve such progress in research.

Thus, I strongly recommend the applicant to apply for HKPFS and PhD program.

The applicant has great passion and interest towards research. He has great potential in discovering new problems and tackling difficulties. He shows seriousness and carefulness, which I reckon the very ability for research and the reason he got so excellent grades in three years. 

  He is well-motivated and have 1~2 years of research experiences, so it'll be smooth for him to get to participate in research activities in the future PhD program. He not only spares no effort to overcome tough circumstances in research by himself, but also is willing to communicate with lab members, which makes him quite adaptable to new environment.

  He has critical thinking and makes good judgement, it's essential for him to behave independent in the research project.





