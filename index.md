---
layout: default
---

# Interpretable-NLP

In this repo, I try to collect some reading material about interpretable natural languages processing research. 

## Goal  
- Draw a picture about hot research topics in Interpretable NLP.   
- This could be used in a semester-length discussion group / seminar about interpretable NLP.  

## Target audience  
Anyone interested in doing Interpretable NLP in SPOC lab.  

## Topics to be included  

1. **Introduction**  
    *Why should we care about interpretable NLP?*  
    - We want to build NLP systems with better performance.  
      - Leverage language as a resource: which linguistic knowledge do the systems have?  
      - SoTA, even commercial models still have imperfectness (e.g., negated negative should be positive or neutral, and switching locations should not change the sentiment), according to [Checklist](https://www.aclweb.org/anthology/2020.acl-main.442/).  
    - "Good performance" requires much more than just "high accuracy".  
      - ["Utility Is in the Users' Eyes"](https://www.aclweb.org/anthology/2020.emnlp-main.393/)  
      - High accuracy could be caused by shortcut learning. More in section 7.    
    - We want to build NLP systems that deploy well in the society.  
      - Early experiment e.g., the HitchBot project (2013-2015): dealing with real people is complicated.  
      - Good performance on experimental datasets doesn't necessarily generalize to the real world.
      - Fairness, accountability, and transparency (FAccT). We want to "open the black boxes". Recent discussions include: [On the Danger of Stochastic Parrots](https://www.technologyreview.com/2020/12/04/1013294/google-ai-ethics-research-paper-forced-out-timnit-gebru/).  

    *What do interpretable NLP research include?*  
    - Mainly about the ACL/EMNLP/NAACL track "Interpretability and analysis of NLP models". BlackboxNLP workshop is also relevant.  
    - Connection to: FAccT, theory, psycholinguistics, ML4H  
    - Two recent tutorials, each discussing some topics: 
      - ACL 2020 tutorial [Interpretability and Analysis in Neural NLP](https://sebastiangehrmann.com/assets/files/acl_2020_interpretability_tutorial.pdf) (topics: diagnostic classifiers, behavioral tests)  
      - EMNLP 2020 tutorial [Interpreting Predictions of NLP Models](https://github.com/Eric-Wallace/interpretability-tutorial-emnlp2020) (topics: influencing samples in datasets, etc.)  
    - Relevant: [CS 335 Fair, Accountable, and Transparent Deep Learning](https://hci.stanford.edu/courses/cs335/2020/sp) -- this is more on the DL / ML / algorithm side. There are some overlapping with Interpretable NLP.  


2. **Background: language modeling, DNNs in NLP**  
    - Word embedding, language models, neural language models  
    - Early approaches of word embeddings: SVD ("Latent Semantic Analysis") [(Landauer and Dumais, 2005)](https://pcl.sitehost.iu.edu/rgoldsto/courses/concepts/landauer.pdf)  
    - A Neural Probabilistic Language Model [(Bengio et al., 2003)](https://dl.acm.org/doi/10.5555/944919.944966)  
    - Word2vec and *the traditional NLP pipeline* [(Collobert and Weston, 2008)](https://dl.acm.org/doi/10.1145/1390156.1390177)  
    - SoTA LM for some time: AWD-LSTM [(Merity et al., 2017)](https://arxiv.org/abs/1708.02182)  
    - Contextualized language models: ELMo, BERT, GPT-2, XLNet, ALBERT  
    - On Losses for Modern Neural LMs [(Aroca-Ouellette and Rudzicz, 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.403/)  


3. **Background: Interpretability, explainable AI**  
    - Review / positional papers:
      - The Mythos of Model Interpretability [(Lipton, 2016)](https://arxiv.org/abs/1606.03490)  
      - A Diagnostic Study of Explainability Techniques for Text Classification [(Atanasova et al., 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.263)  
    - Post-hoc, local, linear interpretations [(Ribeiro 2016, LIME)](https://arxiv.org/abs/1602.04938)  
    - SHAP (SHapley Additive exPlanations): a game theoretic approach to explain the output of a model. [paper](https://proceedings.neurips.cc/paper/2017/hash/8a20a8621978632d76c43dfd28b67767-Abstract.html), [SHAP package](https://shap.readthedocs.io/en/latest/)   
    - Explain by attention / heatmaps:  
      - Is Attention Interpretable? [(Serrano and Smith, 2019)](https://arxiv.org/abs/1906.03731)  
      - Attention is Not Explanation [(Jain and Wallace, 2019)](https://arxiv.org/abs/1902.10186)  
      - Attention is Not Not Explanation [(Wiegreffe and Pinter, 2019)](https://arxiv.org/abs/1908.04626)  
    - Explain with CCA:  
      - Deep-CCA [(Andrew et al., 2013)](https://ttic.uchicago.edu/~klivescu/papers/andrew_icml2013.pdf)    
      - SVCCA: Singular Vector Canonical Correlation Analysis for Deep Learning Dynamics and Interpretability [(Raghu et al., 2017)](https://arxiv.org/abs/1706.05806)  


4. **Topic: The geometry of embeddings**
    - Linear analogy  
      - The promising "linear analogy" property of Mikolov word2vec, and subsequent debates: "man is to doctor as woman is to doctor" [(Nissim et al., 2019)](https://arxiv.org/abs/1905.09866)   
      - GloVe (Pennington et al., 2016), Levy and Goldberg (2015), then Kawin's linear analogy paper, and then:  
      - Embedding explained: towards understanding word embeddings [(Allen and Hospidales, 2019)](https://arxiv.org/pdf/1901.09813.pdf)  
      - Why are such low-dimensional interpretations (e.g., linear analogy) possible for deep neural representations? A relevant work: Measuring the Intrinsic Dimension of Objective Landscapes [(Li et al., 2018)](https://arxiv.org/abs/1804.08838)  
    - Isotropy  
      - Skip-gram negative sampling results in words distributed in a narrow cone (highly isotropic) [(Mimno and Thompson, 2017)](https://www.cs.cornell.edu/~laurejt/papers/sgns-geometry-2017.pdf)  
      - We can discourage isotropy during training [(Wang et al., 2019)](http://proceedings.mlr.press/v97/wang19f/wang19f.pdf) or by post-processing [(Mu and Viswanath, 2018)](https://openreview.net/forum?id=HkuGJ3kCb), to get better embeddings.  
      - Analyzing the (an-)isotropy in contextualized word representations [(Ethayarajh, 2019)](https://www.aclweb.org/anthology/D19-1006/)  
    - Visualizing and measuring the geometry of BERT [(Reif et al., 2019)](https://papers.nips.cc/paper/2019/hash/159c1ffe5b61b41b3c4d8f4c2150f6c4-Abstract.html). Their goal is to interpret the geometry, but the methodology is similar to Hewitt and Manning, (2019). Analyzing the geometry evolves into "reducing the dimensions of representations into interpretable dimensions", i.e., diagnostic classification.   


5. **Topic: Diagnostic classifiers**  
    - [(Alain and Bengio, 2017)](https://arxiv.org/abs/1610.01644): linear classifier as diagnostic classifiers  
    - [(Ettinger, 2016)](https://www.aclweb.org/anthology/W16-2524/): Probing for semantic evidence of composition by means of simple classification tasks  
    - Various probing papers: "what to probe for"
      - [(Hewitt Manning, 2019)](https://www.aclweb.org/anthology/N19-1419/): A structural probe for finding syntax in word representations  
      - [(Tenney et al., 2019)](https://arxiv.org/abs/1905.05950): BERT rediscovers traditional NLP pipeline  
    - Developing the methods for probing: "how to probe"
      - [(Hewitt and Liang, 2019)](https://www.aclweb.org/anthology/D19-1275/) the "good probe or good representations" dichotomy  
      - [(Pimentel et al., 2020)](https://www.aclweb.org/anthology/2020.acl-main.420/) an information theoretic framework  
      - [(Zhu and Rudzicz, 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.744/) an information theoretic explanation for the dichotomy. Limitations of diagnostic classifier probing.  


6. **Topic: Psycholinguistic tests on NLP models**
    - Colorless green RNNs dream hierarchically [(Gulordava et al., 2018)](https://www.aclweb.org/anthology/N18-1108/)  
    - Targeted syntactic evaluation of language models [(Marvin and Linzen, 2018)](https://www.aclweb.org/anthology/D18-1151/)  
    - BLiMP: The benchmark of linguistic minimal pairs for English [(Warstadt et al., 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00321)  
    - What BERT is not: Lessons from a New Suite of Psycholinguistic Diagnostics for Language Models [(Ettinger, 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00298)  
    - Investigating the linguistic knowledge of NLP models [(Bacon, 2020)](https://escholarship.org/uc/item/7tk21797)    
    - Climbing towards NLU [(Bender and Koller, 2020)](https://www.aclweb.org/anthology/2020.acl-main.463/)  
    - When is BERT surprised? (2021)  


7. **Topic: Spurious correlations, shortcut learning**    
    - The "right for the wrong reasons" problem
      - Right for the wrong reasons: diagnosing syntactic heuristics in natural language inference [(McCoy et al., 2019)](https://www.aclweb.org/anthology/P19-1334/)  
      - [(Niven and Kao, 2019)](https://www.aclweb.org/anthology/P19-1459/)  
      - This "shortcut learning" problem happens in multiple scenarios (Geirhos et al., 2020)  
      - Empirical evidence to spurious correlations [(Tu et al., 2020)](https://arxiv.org/abs/2007.06778)  
    - How to solve this problem?
      - Prepare models against shortcuts by fitting the residual [(He et al., 2019)](https://arxiv.org/abs/1908.10763)  
      - Prepare models against shortcuts by constructing challenging datasets [(Gardner et al., 2020)](https://arxiv.org/abs/2004.02709), [(Kaushik et al., 2020)](https://openreview.net/forum?id=Sklgs0NFvr)  
      - Make the datasets a little bit more difficult ("the innoculation setting") [(Warstadt et al., 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.16/)  


8. **Topic: Influence of samples, understanding the datasets**  
    - Saliency maps: how does each data sample affect the model predictions? (Hard to compute)  
    - Influence function: which sample would change the prediction the most, if removed?  
      - Understanding Black-box Predictions via Influence Functions [(Koh and Liang, 2017)](https://arxiv.org/abs/1703.04730)  
      - Understanding the Origin of Bias in Word Embeddings [(Brunet et al., 2019)](https://arxiv.org/abs/1810.03611)  
      - Explaining Black Box Predictions and Unveiling Data Artifacts with Influence Functions [(Han et al., 2020)](https://arxiv.org/abs/2005.06676)  
    - Adversarial explanations:  
      - Input perturbation: what will the model predict if we replace this input word?  
      - Input marginalization [(Kim et al., 2020)](https://arxiv.org/abs/2010.13984)  
      - Adversarial Examples Are Not Bugs; They Are Features [(Ilyas et al., 2019)](https://papers.nips.cc/paper/2019/hash/e2c420d928d4bf8ce0ff2ec19b371514-Abstract.html)  
    - Which decision rules / "anchors" trigger the prediction? E.g., Anchors [(Ribeiro et al., 2018)](https://www.aaai.org/ocs/index.php/AAAI/AAAI18/paper/view/16982/15850), and Universal adversarial triggers [(Wallace et al., 2019)](https://arxiv.org/abs/1908.07125)  
    - Other methods to understand the datasets:  
      - Dataset Cartography: Mapping and Diagnosing Datasets with Training Dynamics [(Swayamdipta et al., 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.746/)  
      - With Little Power Comes Great Responsibility [(Card et al., 2020)](https://arxiv.org/abs/2010.06595)  
      - Use task-specific information to describe the difficulties of text-based classification datasets (2021)  


9. **Topic: Rationales in classification**  
    - Dataset: e-SNLI [(Camburu et al., 2018)](https://arxiv.org/abs/1812.01193)  
    - Generating plausible counterfactual explanations with deep transformers in financial text classification [(Yang et al., 2020)](https://arxiv.org/abs/2010.12512)  
    - Towards explainable NLP: A generative explanation framework for text classification [(Liu et al., 2019)](https://www.aclweb.org/anthology/P19-1560/)  
    - Evaluating and characterizing human rationales [(Carton et al., 2020)](aclweb.org/anthology/2020.emnlp-main.747/)  


10. **Topic: Causal interpretations**  
    - Causal analysis recap.  
      - Motivation: Pearl's three "rungs" on the ladder of causality (observation, intervention, counterfactual reasoning), from [the Book of Why](https://www.nytimes.com/2018/06/01/business/dealbook/review-the-book-of-why-examines-the-science-of-cause-and-effect.html).  
      - Structural causal models  
      - Inverse probability weighting, residualization,propensity score matching  
      - Causal effects. [Notes about front door and back door criteria](https://cse.sc.edu/~javidian/Notes_Presentations/BackFrontDoor.pdf)  
    - A Causal Framework for Explaining the Predictions of Black-box S2S Models [(Alvarez-Melis and Jaakkola, 2017)](https://www.aclweb.org/anthology/D17-1042/)  
    - Deconfounding Lexicon Inductions for Interpretable Social Science [(Pryzant et al., 2018)](https://www.aclweb.org/anthology/N18-1146/)  
    - Topics to avoid: Demoting Latent Confounds in Text Classification [(Han and Tsvetkov, 2019)](https://www.aclweb.org/anthology/D19-1425/)  


11. **Topic: Theoretical interpretations**  
    - RNNs as Weighted Language Recognizers [(Chen et al., 2018)](https://www.aclweb.org/anthology/N18-1205/)  
    - Theoretical Limitations of Self-attentions [(Hahn, 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00306)  
    - A Formal Hierarchy of RNN Architectures [(Merrill et al., 2020)](https://arxiv.org/abs/2004.08500)  
    - Every Model Learned by Gradient Descent is Approximately a Kernel Machine [(Domingos, 2020)](https://arxiv.org/abs/2012.00152)  
    - Blog post: How to Stop Worrying about Compositionality? [(Herbelot, 2020)](https://thegradient.pub/how-to-stop-worrying-about-compositionality-2/)  


12. **Topic: Fairness, Accountability, Transparency (FAccT)**  
    - Man Is to Computer Programmer as Woman Is to Homemaker? Debiasing Word Embeddings [(Bolukbasi et al., 2016)](https://arxiv.org/abs/1607.06520)    
    - Men Also Like Shopping: Reducing Gender Bias Amplification Using Corpus-level Constraints [(Zhao et al., 2017)](https://www.aclweb.org/anthology/D17-1323/)  
    - The Geometry of Culture: Analyzing the Meanings of Class through Word Embeddings [(Kozlowski et al., 2019)](https://journals.sagepub.com/doi/full/10.1177/0003122419877135) 
    - The Woman Worked as a Babysitter: On Biases in Language Generation [(Sheng et al., 2019)](https://www.aclweb.org/anthology/D19-1339/)  


13. **Topic: Adversarial Attacks, Robustness, OOD generalization**
    - Adversarial attacks (Ref: Lecture 12 in CS 335)  
    - Robustness  
      - Certified robustness to adversarial word substitutions [(Jia et al., 2019)](https://arxiv.org/abs/1909.00986)  
      - Exploring the Privacy-Preserving Properties of Word Embeddings: Algorithmic Validation Study [(Abdalla et al., 2020)](https://www.jmir.org/2020/7/e18055/)  
    - OOD generalization  
      - The robust decision rules / "causal inductive biases" are those that are generalizable across domains  
      - How can we accelerate progress towards human-like language generalization? [(Linzen, 2020)](https://www.aclweb.org/anthology/2020.acl-main.465/)  
