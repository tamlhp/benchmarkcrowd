This work presented a thorough evaluation and comparison of answer aggregate techniques widely used in crowdsourcing. We offered an overview of two major classes (non-iterative and iterative) of aggregate techniques, while discussing about the characteristics of the underlying probabilistic models. We then introduced the flexible and extensible benchmark framework, in which a new aggregate technique as well as a new measurement can be easily plugged. During the framework development, we made the best effort to re-implement and integrate the most representative aggregate techniques, and evaluated them in a fair manner. We also analyzed various performance factors for each technique, including _computation time, accuracy, sensitivity to spammer, adaptivity to multi labelling,_ and _worker estimation error_. The crowdsourcing process is simulated by letting six different types of workers answer binary or multiple-choice questions.

We here summarize our principal findings as a set of recommendations for how to select a well-suited aggregate technique on particular application scenarios:

  * Overall, EM and SLME achieve highest accuracies and work robustly against spammers. In particular, they by far outperformed the others, when the number of answers per question is high.
  * If the crowd contains many spammers (more than 30\%), consider using EM or SLME. The performance of non-iterative techniques (MD, HP, and ELICE) is not significantly lower than EM and SLME. Thus they are best suited for applications that require fast computation. In contrast, we strongly suggest not using GLAD and ITER since they are very sensitive to uniform spammers.
  * Only MD, HP, and EM can adapt to multi labelling. For binary labelling, EM is the winner. In case of 4 labels, MD and HP are also appropriate choices since the difference between them and EM is not distinguishable.
  * For applciations that require fast computation, MD and HP are the winners. Oppositely, we strongly suggest not using iterative techniques. Not only is their computation much higher than the non-iteraitve techniques, but also they require to re-compute the whole answer set upon the new arrival of worker answers.


| **category** | **winner** | **2nd best** | **worst** |
|:-------------|:-----------|:-------------|:----------|
| computation time | **MD** | ELICE | EM |
| accuracy | **EM** | SLME | ITER |
| robustness to spammers  | **SLME** | EM | ITER |
| adaptivity to multi labelling | **MD** | HP | EM |
| worker estimuation error | **EM** | SLME  | ITER  |


As a concluding remark, we recommend a potential application to use our benchmarking framework as a tool to find out the best-suited aggregate technique accordingly, since there is no absolute winner that outperforms the others in every case. As the benchmark source code as well as the datasets used in the benchmark are publicly available, we expect that the experimental results presented in this paper will be refined and improved by the research community, in particular when more data become available, more experiments are performed, and more techniques are integrated into the framework in the future.