---
layout: default
---

## Goal  
- Draw a picture about hot research topics in Interpretable NLP.   
- This could be used in a semester-length discussion group / seminar about interpretable NLP.  

## Target audience  
Anyone interested in doing Interpretable NLP in SPOC lab.  

## Topics to be included  

0. **Introduction**  
    *Why should we care about interpretable NLP?*  
    - Want to build NLP systems with better performances  
      - Understand the blackbox systems, empirically and theoretically  
      - Leverage language as a resource: which linguistic knowledge do the systems have?  
    - Want to build NLP systems that deploy well in the society  
      - Early experiment e.g., the HitchBot project (2013-2015): dealing with real people is hard.  
      - Fairness, accountability, and trustworthiness  
      - SoTA, even commercial models are far from perfect yet, according to [Checklist](https://www.aclweb.org/anthology/2020.acl-main.442/)  
      - Want to make the "goodness" criteria more useful: ["Utility is in the users' eyes"](https://www.aclweb.org/anthology/2020.emnlp-main.393/)  
      - On the danger of stochastic parrots  

    *What do interpretable NLP research about?*  
    - Mainly about the ACL/EMNLP/NAACL track "Interpretability and analysis of NLP models"  
    - BlackboxNLP workshop  
    - Connection to: FAccT, theory, psycholinguistics, ML4H  
    - Related material: ACL 2020 tutorial [Interpretability and Analysis in Neural NLP](https://sebastiangehrmann.com/assets/files/acl_2020_interpretability_tutorial.pdf)  
    - Related material: EMNLP 2020 tutorial [Interpreting Predictions of NLP Models](https://github.com/Eric-Wallace/interpretability-tutorial-emnlp2020)  

1. **Background: language modeling, DNNs in NLP**  
    - Word embedding, language models, neural language models  
    - Previous approaches of word embeddings: SVD (latent semantic analysis)  
    - Neural probabilistic LMs (Bengio 2003)  
    - Word2vec and *the traditional NLP pipeline* (Collobert & Westin, 2008)  
    - SOTA LM for a long time: AWD-LSTM (Merity et al., 2017)  
    - Contextualized language models: ELMo, BERT, GPT-2, XLNet, ALBERT  
    - On losses for modern neural LMs [(Aroca-Ouellette and Rudzicz, 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.403/) 


2. **Background: Interpretability, explainable AI**  
    - Review / positional papers:
      - The mythos of model interpretability [(Lipton, 2016)](https://arxiv.org/abs/1606.03490)  
      - A diagnostic study of explainability techniques for text classification [(Atanasova et al., 2020)](https://www.aclweb.org/anthology/2020.emnlp-main.263)  
    - Post-hoc, local, linear interpretations (Ribeiro 2016, LIME)  
    - SHAP (SHapley Additive exPlanations): a game theoretic approach to explain the output of a model  
    - Explain by attention / heatmaps:
      - Attention is not explanation  
      - Attention is not not explanation  
    - Explain with CCA:  
      - Deep-CCA  
      - SVCCA  

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
    - (Alain and Bengio 2017): linear classifier as diagnostic classifiers  
    - (Ettinger 2016): Diagnostic classification to query linguistic knowledge  
    - Various probing papers: "what to probe for"
      - (Hewitt Manning 2019): Finding syntax in LMs  
      - (Tenney et al., 2019): BERT rediscovers traditional NLP pipeline  
    - Developing the methods for probing: "how to probe"
      - (Hewitt & Liang 2019) the "good probe or good representations" dichotomy  
      - (Pimentel et al 2020) an information theoretic framework  
      - (Zhu and Rudzicz 2020) a reconciliation. Limitations of diagnostic classifier probing.  
      - (Voita and Titov 2020) Probe with minimum description length.  

6. **Topic: Psycholinguistic tests on NLP models**
    - Colorless green RNNs dream hierarchically [(Gulordava et al., 2018)](https://www.aclweb.org/anthology/N18-1108/)  
    - What BERT is not: Lessons from a New Suite of Psycholinguistic Diagnostics for Language Models [(Ettinger, 2020)](https://transacl.org/ojs/index.php/tacl/article/view/1852)  
    - When is BERT surprised? (**TODO**, 2021)  
    - Linguistic theory?  

7. **Topic: Spurious correlations, shortcut learning**    
    - Right for the wrong reasons. The HANS dataset (McCoy et al., 2019)  
    - (Niven and Kao, 2019)  
    - This "shortcut learning" problem happens in multiple scenarios (Geirhos et al., 2020)  
    - Empirical evidence to spurious correlations [(Tu et al., 2020)](https://arxiv.org/abs/2007.06778)  
    - Prepare models against shortcuts by challenging datasets [(Gardner et al., 2020)](https://arxiv.org/abs/2004.02709), [(Kaushik et al., 2020)](https://openreview.net/forum?id=Sklgs0NFvr)
    - Prepare models against shortcuts by fitting the residual [(He et al., 2019)](https://arxiv.org/abs/1908.10763)  
    - Task-specific information (**TODO**, 2021)  

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


9. **Topic: Rationales in classification**  
    - Dataset: e-SNLI [(Camburu et al., 2018)](https://arxiv.org/abs/1812.01193)  
    - Generating plausible counterfactual explanations with deep transformers in financial text classification [(Yang et al., 2020)](https://arxiv.org/abs/2010.12512)  
    - Towards explainable NLP: A generative explanation framework for text classification [(Liu et al., 2019)](https://www.aclweb.org/anthology/P19-1560/)  
    - Evaluating and characterizing human rationales [(Carton et al., 2020)](aclweb.org/anthology/2020.emnlp-main.747/)  


10. **Topic: Connection to Fairness, Accountability, Trustworthiness (FAccT)**  
    - Unveiling and mitigating the bias in language models  
    - Bolukbasi's paper. 
    - Jieyu Zhao's papers. 
    - Yulia Tsevkov's papers. 
    - The fairness-accuracy tradeoff?   


11. **Topic: Causal interpretations**  
    - Causal analysis recap.  
      - Motivation: Pearl's three "rungs" on the ladder of causality (observation, intervention, counterfactual reasoning), from [the Book of Why](https://www.nytimes.com/2018/06/01/business/dealbook/review-the-book-of-why-examines-the-science-of-cause-and-effect.html).  
      - Structural causal models  
      - Inverse probability weighting, residualization,propensity score matching  
      - Causal effects. [Notes about front door and back door criteria](https://cse.sc.edu/~javidian/Notes_Presentations/BackFrontDoor.pdf)  
    - A causal framework for explaining the predictions of black-box S2S models [(Alvarez-Melis and Jaakkola, 2017)](https://www.aclweb.org/anthology/D17-1042/)  
    - Deconfounding lexicon inductions for interpretable social science [(Pryzant et al., 2018)](https://www.aclweb.org/anthology/N18-1146/)  

12. **Topic: OOD generalization**
    - Certified robustness to adversarial word substitutions [(Jia et al., 2019)](https://arxiv.org/abs/1909.00986)  
    - [How can we accelerate progress towards human-like language generalization?](https://www.aclweb.org/anthology/2020.acl-main.465/)  
    - **TODO**


13. **Optional topic: Theoretical interpretations**  
    - RNNs as weighted language recognizers [(Chen et al., 2018)](https://www.aclweb.org/anthology/N18-1205/)  
    - Theoretical limitations of self-attentions [(Hahn, 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00306)  
    - A formal hierarchy of RNN architectures [(Merrill et al., 2020)](https://arxiv.org/abs/2004.08500)  
    - Learning theory?


14. **Future**   
    - Climbing up the ladders of NLU (Bender and Koller, 2020)  
