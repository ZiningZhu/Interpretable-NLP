---
layout: default
---

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
      - Understand the blackbox systems, empirically and theoretically  
      - Leverage language as a resource: which linguistic knowledge do the systems have?  
    - We want to build NLP systems that deploy well in the society.  
      - Early experiment e.g., the HitchBot project (2013-2015): dealing with real people is hard.  
      - Fairness, accountability, and trustworthiness (FAccT). E.g., [On the danger of stochastic parrots](https://www.technologyreview.com/2020/12/04/1013294/google-ai-ethics-research-paper-forced-out-timnit-gebru/)  
      - SoTA, even commercial models are far from perfect yet, according to [Checklist](https://www.aclweb.org/anthology/2020.acl-main.442/)  
      - Develop more useful "goodness" criteria: ["Utility is in the users' eyes"](https://www.aclweb.org/anthology/2020.emnlp-main.393/)    

    *What do interpretable NLP research include?*  
    - Mainly about the ACL/EMNLP/NAACL track "Interpretability and analysis of NLP models"  
    - BlackboxNLP workshop  
    - Connection to: FAccT, theory, psycholinguistics, ML4H  
    - Related material: ACL 2020 tutorial [Interpretability and Analysis in Neural NLP](https://sebastiangehrmann.com/assets/files/acl_2020_interpretability_tutorial.pdf)  
    - Related material: EMNLP 2020 tutorial [Interpreting Predictions of NLP Models](https://github.com/Eric-Wallace/interpretability-tutorial-emnlp2020)  


2. **Background: language modeling, DNNs in NLP**  
    - Word embedding, language models, neural language models  
    - Previous approaches of word embeddings: SVD (latent semantic analysis)  
    - Neural probabilistic LMs (Bengio 2003)  
    - Word2vec and *the traditional NLP pipeline* (Collobert & Westin, 2008)  
    - SOTA LM for a long time: AWD-LSTM (Merity et al., 2017)  
    - Contextualized language models: ELMo, BERT, GPT-2, XLNet, ALBERT  
    - On losses for modern neural LMs [(Aroca-Ouellette and Rudzicz, 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.403/) 


3. **Background: Interpretability, explainable AI**  
    - Review / positional papers:
      - The mythos of model interpretability [(Lipton, 2016)](https://arxiv.org/abs/1606.03490)  
      - A diagnostic study of explainability techniques for text classification [(Atanasova et al., 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.263)  
    - Post-hoc, local, linear interpretations [(Ribeiro 2016, LIME)](https://arxiv.org/abs/1602.04938)  
    - SHAP (SHapley Additive exPlanations): a game theoretic approach to explain the output of a model. [paper](https://proceedings.neurips.cc/paper/2017/hash/8a20a8621978632d76c43dfd28b67767-Abstract.html) [SHAP package](https://shap.readthedocs.io/en/latest/)   
    - Explain by attention / heatmaps:
      - Attention is not explanation [(Jain and Wallace, 2019)](https://arxiv.org/abs/1902.10186)  
      - Attention is not not explanation [(Wiegreffe and Pinter, 2019)](https://arxiv.org/abs/1908.04626)  
    - Explain with CCA:  
      - Deep-CCA [(Andrew et al., 2013)](https://ttic.uchicago.edu/~klivescu/papers/andrew_icml2013.pdf)    
      - SVCCA: singular vector canonical correlation analysis for deep learning dynamics and interpretability [(Raghu et al., 2017)](https://arxiv.org/abs/1706.05806)  

    <!--3. Can I beg Frank to give a guest lecture here? (E.g., Interpretability and surgical safety?) -->  

4. **Topic: The geometry of embeddings**
    - Linear analogy  
      - The promising story (linear analogy) of Mikolov word2vec, and subsequent debates re: whether this is true  
      - GloVe, and then Kawin's linear analogy paper  
    - Isotropy  
      - Skip-gram negative sampling results in words distributed in a narrow cone (highly isotropic) [(Mimno and Thompson, 2017)](https://www.cs.cornell.edu/~laurejt/papers/sgns-geometry-2017.pdf)  
      - We can discourage isotropy during training [(Wang et al., 2019)](http://proceedings.mlr.press/v97/wang19f/wang19f.pdf) or by post-processing [(Mu and Viswanath, 2018)](https://openreview.net/forum?id=HkuGJ3kCb), to get better embeddings.  
      - Analyzing the (an-)isotropy in contextualized word representations [(Ethayarajh, 2019)](https://www.aclweb.org/anthology/D19-1006/)  
    - Visualizing and measuring the geometry of BERT [(Reif et al., 2019)](https://papers.nips.cc/paper/2019/hash/159c1ffe5b61b41b3c4d8f4c2150f6c4-Abstract.html) 


5. **Topic: Diagnostic classifiers**  
    - [(Alain and Bengio 2017)](https://arxiv.org/abs/1610.01644): linear classifier as diagnostic classifiers  
    - [(Ettinger 2016)](https://www.aclweb.org/anthology/W16-2524/): Probing for semantic evidence of composition by means of simple classification tasks  
    - Various probing papers: "what to probe for"
      - [(Hewitt Manning 2019)](https://www.aclweb.org/anthology/N19-1419/): A structural probe for finding syntax in word representations  
      - [(Tenney et al., 2019)](https://arxiv.org/abs/1905.05950): BERT rediscovers traditional NLP pipeline  
    - Developing the methods for probing: "how to probe"
      - [(Hewitt & Liang 2019)](https://www.aclweb.org/anthology/D19-1275/) the "good probe or good representations" dichotomy  
      - [(Pimentel et al 2020)](https://www.aclweb.org/anthology/2020.acl-main.420/) an information theoretic framework  
      - [(Zhu and Rudzicz 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.744/) an information theoretic explanation for the dichotomy. Limitations of diagnostic classifier probing.  
      - [(Voita and Titov 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.14/) Probe with minimum description length.  


6. **Topic: Psycholinguistic tests on NLP models**
    - Colorless green RNNs dream hierarchically [(Gulordava et al., 2018)](https://www.aclweb.org/anthology/N18-1108/)  
    - Targeted syntactic evaluation of language models [(Marvin & Linzen, 2018)](https://www.aclweb.org/anthology/D18-1151/)  
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
      - Prepare models against shortcuts by challenging datasets [(Gardner et al., 2020)](https://arxiv.org/abs/2004.02709), [(Kaushik et al., 2020)](https://openreview.net/forum?id=Sklgs0NFvr)
      - Prepare models against shortcuts by fitting the residual [(He et al., 2019)](https://arxiv.org/abs/1908.10763)  


8. **Topic: Influence of samples, understanding the datasets**  
    - Saliency maps: how does each data sample affect the model predictions? (Hard to compute)  
    - Influence function: which sample would change the prediction the most, if removed?  
      - Understanding Black-box Predictions via Influence Functions [(Koh and Liang, 2017)](https://arxiv.org/abs/1703.04730)  
      - Understanding the origin of bias in word embeddings [(Brunet et al., 2019)](https://arxiv.org/abs/1810.03611)  
      - Explaining black box predictions and unveiling data artifacts with influence functions [(Han et al., 2020)](https://arxiv.org/abs/2005.06676)  
    - Adversarial explanations:  
      - Input perturbation
      - Input marginalization [(Kim et al., 2020)](https://arxiv.org/abs/2010.13984)  
    - Which decision rules / "anchors" trigger the prediction? E.g., Anchors [(Ribeiro et al., 2018)](https://www.aaai.org/ocs/index.php/AAAI/AAAI18/paper/view/16982/15850), and Universal adversarial triggers [(Wallace et al., 2019)](https://arxiv.org/abs/1908.07125)  
    - Other methods to understand the datasets:  
      - Dataset cartography: mapping and diagnosing datasets with training dynamics [(Swayamdipta et al., 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.746/)  
      - With little power comes great responsibility [(Card et al., 2020)](https://arxiv.org/abs/2010.06595)  
      - Use task-specific information to describe the difficulty of the classification datasets (2021)  


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
    - A causal framework for explaining the predictions of black-box S2S models [(Alvarez-Melis and Jaakkola, 2017)](https://www.aclweb.org/anthology/D17-1042/)  
    - Deconfounding lexicon inductions for interpretable social science [(Pryzant et al., 2018)](https://www.aclweb.org/anthology/N18-1146/)  


11. **Topic: Theoretical interpretations**  
    - RNNs as weighted language recognizers [(Chen et al., 2018)](https://www.aclweb.org/anthology/N18-1205/)  
    - Theoretical limitations of self-attentions [(Hahn, 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00306)  
    - A formal hierarchy of RNN architectures [(Merrill et al., 2020)](https://arxiv.org/abs/2004.08500)  
    - TODO - connections to Learning theory?  


12. **Connections to Fairness, Accountability, Trustworthiness (FAccT)**  
    - Unveiling and mitigating the bias in language models  
    - Bolukbasi's paper. 
    - Jieyu Zhao's papers. 
    - Yulia Tsevkov's papers. 
    - The fairness-accuracy tradeoff?   
    - **TODO**  


13. **Connections to OOD generalization**
    - Certified robustness to adversarial word substitutions [(Jia et al., 2019)](https://arxiv.org/abs/1909.00986)  
    - [How can we accelerate progress towards human-like language generalization?](https://www.aclweb.org/anthology/2020.acl-main.465/)  
    - TODO  
