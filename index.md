---
layout: default
---

# Interpretable-NLP

There is a rise in interpretability in Natural Languages Processing research, but few resource is available online. This seminar aims at drawing a picture of interpretability in NLP research, and review interesting relevant topics. 

Anyone interested in doing Interpretable NLP e.g., in [SPOC lab](https://twitter.com/SPOClab) is welcome.  

## Meeting Time & Location
- Time: Tuesdays 9:00-10:00 ET (Toronto time)  
- Location: [Zoom](https://utoronto.zoom.us/meeting/register/tZMlcOCpqjIuHNeGNTZOnFJc0b0zV3O9_ikL)  
- Discussion: [GitHub issues](https://github.com/ZiningZhu/Interpretable-NLP/issues)  
- Slides: [OneDrive](https://tinyurl.com/interpretable-nlp-slides)  


## Tentative Topics  

1. **Introduction (Jan 12, 2021)**    
    - Why should we care about interpretable NLP?  
      - We want to build NLP systems with better performance.  
      - "Good performance" requires much more than just "high accuracy".    
      - We want to build NLP systems that deploy well in the society.  
    - What do interpretable NLP research include?   
      - Mainly about the ACL/EMNLP/NAACL track "Interpretability and analysis of NLP models". BlackboxNLP workshop is also relevant.  
      - Connection to: FAccT, theory, psycholinguistics, ML4H  


2. **Background: language modeling, DNNs in NLP (Jan 19, 2021)**  
   - A view of NLP: it is a window for understanding knowledge & intelligence.
   - Many popular tasks and models (e.g., neural networks for language modeling) are developed along this goal: LSA, probabilistic neural LM, word2vec / GloVe, contextualized LM, ...


3. **Background: Interpretability, explainable AI (Feb 2, 2021)**  
   - Some principles of model interpretability.  
   - Some early methods to interpret models, including:
     - A local, (almost-) linear, post-hoc method: LIME
     - A method based on Shapley values: SHAP
     - Attention-based methods
     - SVCCA
   - Interpretability to humans might be complicated.  


4. **Topic: The geometry of embeddings (Feb 9, 2021)**  
   - Three viewpoints in interpreting the geometry:
      - Linear Analogy  
      - Anisotropy  
      - Manifold
   - How can we use these understanding to build better embeddings?  
      - New methods could benefit old models!
      - Consider frequency & isotropy might help 


5. **Topic: Probing (Feb 16, 2021)**  
   - What is probe and how to probe?
     - Probe as a diagnostic classifier
       - Probe for semantic evidence, syntax, or other aspects in NLP pipeline  
       - An information theory framework
     - Extend "probe" to e.g., without parameters  
   - What can probes do?  
     - Assess & remove bias  
     - Assess the utility of features  


6. **Topic: Psycholinguistic tests on NLP models**
    - Colorless green RNNs dream hierarchically [(Gulordava et al., 2018)](https://www.aclweb.org/anthology/N18-1108/)  
    - Targeted syntactic evaluation of language models [(Marvin and Linzen, 2018)](https://www.aclweb.org/anthology/D18-1151/)  
    - BLiMP: The benchmark of linguistic minimal pairs for English [(Warstadt et al., 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00321)  
    - What BERT is not: Lessons from a New Suite of Psycholinguistic Diagnostics for Language Models [(Ettinger, 2020)](https://www.mitpressjournals.org/doi/full/10.1162/tacl_a_00298)  
    - Investigating the linguistic knowledge of NLP models [(Bacon, 2020)](https://escholarship.org/uc/item/7tk21797)    
    - Climbing towards NLU [(Bender and Koller, 2020)](https://www.aclweb.org/anthology/2020.acl-main.463/)  
    <!--- When is BERT surprised? (2021)-->  


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
      <!--- Use task-specific information to describe the difficulties of text-based classification datasets (2021)  -->


9.  **Topic: Rationales in classification**  
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
    - Lipstick on a Pig: Debiasing Methods Cover up Systematic Gender Biases in Word Embeddings But do not Remove Them [(Gonen and Goldberg, 2019)](https://www.aclweb.org/anthology/N19-1061/)  


13. **Topic: Adversarial Attacks, Robustness, OOD generalization**
    - Adversarial attacks (Ref: Lecture 12 in CS 335)  
    - Robustness  
      - Certified robustness to adversarial word substitutions [(Jia et al., 2019)](https://arxiv.org/abs/1909.00986)  
      - Exploring the Privacy-Preserving Properties of Word Embeddings: Algorithmic Validation Study [(Abdalla et al., 2020)](https://www.jmir.org/2020/7/e18055/)  
    - OOD generalization  
      - The robust decision rules / "causal inductive biases" are those that are generalizable across domains  
      - How can we accelerate progress towards human-like language generalization? [(Linzen, 2020)](https://www.aclweb.org/anthology/2020.acl-main.465/)  


14. **Topic: Interpretability and Dialogue**  
    - [(Tutek and Šnajder, 2018)](https://www.aclweb.org/anthology/W18-5427/)  