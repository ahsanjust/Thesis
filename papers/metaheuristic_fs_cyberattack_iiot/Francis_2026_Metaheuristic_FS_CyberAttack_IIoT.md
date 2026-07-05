# A Systematic Review of Metaheuristic Based Feature Selection Strategies for Cyber-Attack Detection in the IIoT

**Authors:** Georg Thamer Francis[^1] · Alireza Souri[^2] · Nihat Inanç[^3]

**Journal:** Artificial Intelligence Review (2026) 59:73

**DOI:** https://doi.org/10.1007/s10462-025-11473-7

**Published:** 5 January 2026 · **Received:** 2 July 2025 · **Accepted:** 14 December 2025

**© The Author(s) 2026**

[^1]: Department of Software Engineering, Halic University, 34060 Istanbul, Turkey — georgethamer1@gmail.com
[^2]: Department of Computer Engineering, Halic University, 34060 Istanbul, Turkey — alirezasouri@halic.edu.tr
[^3]: Department of Electrical and Electronics Engineering, Halic University, 34060 Istanbul, Turkey — nihatinanc@halic.edu.tr

---

## Abstract

The Industrial Internet of Things (IIoT) has been spreading across all fields of applicable environments, one of the most crucial ones being the industrial environment. IIoT is the integration of the internet within various industrial fields such as smart manufacturing, supply chain optimization, and predictive maintenance. These applications require two key features to be efficient, that is, real-time processing and connection security and reliability. From this standpoint arise the studies of cyberattack detection in industrial environments. Many methodologies have approached this field using traditional or hybridized machine learning or deep learning algorithms. In this review paper, we explore 36 of the most recent cyber-attack detection systems using metaheuristic models, mainly metaheuristic feature selection (MFS) algorithms. Additionally, we also explore hybrid models of metaheuristics and machine learning or deep learning models that are used to increase the accuracy of the models on various benchmark datasets. Our SLR separates the MFS utilized in this field into four main types, including Swarm Intelligence (SI), Evolutionary Algorithms (EA), Physics-Based (PHY), and Human-Behavior-Inspired (HBI). Our findings showed that SI-MFS dominates the field, with 25/36 case studies proposing it, while EA was proposed in 3/36 and PHY and HBI were each proposed in 2/36. We also demonstrate the most effective methodologies, such as FS-ID, MFS-D, and Novel Hybrid MFS. We also outline potential open challenges and gaps that require resolution.

**Keywords:** Metaheuristic algorithms · Feature selection algorithms · Intrusion detection · IoT · IIoT · Machine learning · Deep learning

---

## 1 Introduction

Industrial Internet of Things (IIoT) security has become an essential requirement in any IIoT environment ever since cyberattacks began evolving through attackers, and its integration with industrial applications further cemented this necessity in industrial fields (Mekala et al. 2023). One of the most effectively known ways that have been used to mitigate these cyberattacks is metaheuristic algorithms (Hussain et al. 2019), specifically metaheuristic feature selection (MFS) algorithms (Mohammed et al. 2024; Li et al. 2025).

Metaheuristics are mathematical optimization problems that simulate nature or human intelligence. Metaheuristics can be sorted into two basic categories:

- **Single-solution-based (SSB):** Initiate with a single unique solution that gets modified while iterating (Jaddi and Abdullah 2020).
- **Population-based (PB):** Creates many solutions and then optimizes with the number of iterations (Samsuddin et al. 2018; Velasco et al. 2024). PB algorithms are advantageous over SSB for dodging falling for local optima and multi-solution-assisted in-depth examination of search space (Agrawal et al. 2021).

Metaheuristics can also be subdivided based on their behavior into four categories:

1. **Evolution-Based:** Derived from natural evolution. The most famous is the Genetic Algorithm (GA). They evolve through selection, crossover, and mutation (Maier et al. 2019).
2. **Swarm Intelligence (SI) Based:** Derived from animals' social behavior. Famous SI algorithms include PSO, FFA, ACO, GWO, BA, and WOA (Brezočnik et al. 2018; Tang et al. 2021; Zedadra et al. 2018; Khare et al. 2023).
3. **Physics-Based:** Derived from the universe's physics rules, like simulated annealing, GSA, and harmony search (Seyyedabbasi 2024).
4. **Human Behaviour Related:** Purely derived from human behavior, like tabu search, teaching learning-based (TLB), and league championship (Rai et al. 2022).

Feature selection metaheuristics (MFS) algorithms are search algorithms for optimization techniques used to propose new feature subsets to be used for evaluating algorithms in a dataset by measuring the effectiveness of different feature subsets (Dissanayake 2021). For cyberattacks, metaheuristic feature selection (FS) algorithms followed by a machine or deep learning model have been a common approach to detect them, more often in IoT (Hu et al. 2024). FS algorithms consist of three different types:

- **Filter Methods** (Arya and Gupta 2023; Kumar et al. 2021; Lyu et al. 2023; Soe et al. 2020)
- **Wrapper Methods** (Maldonado et al. 2022; Maseno and Wang 2024)
- **Embedded Methods** (Kasongo and Sun 2020; Agrawal et al. 2021)

Most of the FS algorithms used in this field are wrapper-based FS, consisting of three components: search strategy, predictor function, and evaluation or fitness function.

IIoT datasets, specifically IIoT intrusion detection (ID) datasets, as IIoT devices generate massive quantities of data from numerous sensors and devices. Therefore, IIoT intrusion detection datasets also exhibit high dimensionality and noise. Therefore, feature selection (FS) can be applied to enhance the quality of the dataset for testing intrusion detection (ID) algorithms, improving their accuracy and reducing their time complexity. Furthermore, this paper will discuss multi-feature selection (MFS), an excellent optimization methodology for this purpose.

This paper examines 36 modern case studies that use individual or hybrid metaheuristic algorithms for feature selection of intrusion detection data in IIoT and their effectiveness in improving machine and deep learning classification in IIoT domains. The contributions of this work include the following:

- The work effectively illustrates the most efficient metaheuristic methodologies for intrusion detection in IIoT.
- Provides a comprehensive technical analysis of improved feature selection and improved intrusion detection and points out the research gaps that are yet to be fulfilled by metaheuristics and key trade-offs.
- Identify open challenges, dominant trends, and industrial practical feasibility and barriers to adoption.

Furthermore, we inquire about the methodological questions below:

1. **MQ1:** What types of metaheuristic algorithms have been employed for feature selection in intrusion detection systems within IIoT environments?
2. **MQ2:** Which metaheuristic-based feature selection algorithms demonstrate the highest performance in IIoT intrusion detection systems?
3. **MQ3:** What are the most commonly used benchmark datasets for evaluating intrusion detection in IIoT?
4. **MQ4:** What novel metaheuristic models and novel hybrid metaheuristic models have been proposed for intrusion detection in IIoT?
5. **MQ5:** What types of intrusion detection algorithms are integrated with metaheuristic-based feature selection methods in IIoT?
6. **MQ6:** What are the most frequently reported limitations and research gaps in existing MFS-based IIoT intrusion detection approaches?
7. **MQ7:** What future research directions and open challenges have been identified in employing metaheuristic-based feature selection for IIoT intrusion detection?

The remainder of this paper is divided as follows. Section 2 highlights similar works to ours. Section 3 presents a summary of the selected research methodologies. Section 4 is a visualization of the taxonomy of MFS-based IDS algorithms. Section 5 presents technical analysis and discussion. Section 6 presents open challenges. And finally, Sect. 8 concludes the paper.

---

## 2 Related Work

This section highlights related works, including recent systematic literature reviews similar to our SLR and case studies that were ultimately excluded from this study.

### 2.1 Similar Review Papers

This subsection highlights key reviews that are similar to our work and compares them with it. This comparison can be seen in Table 1.

Hu et al. (2024) presented a comprehensive analysis of nature-inspired and meta-heuristic algorithms for designing intrusion detection systems in cloud/edge and IoT environments. This paper provides a comprehensive review of nature-inspired algorithms applied to intrusion detection systems (IDS) in cloud, edge, and IoT environments. It focuses on the challenges of designing IDS for these ecosystems and evaluates various metaheuristics, such as PSO, GWO, and ALO, for feature selection and optimization. The datasets used include NSL-KDD, CICIDS-2017, and UNSW-NB15, which are general-purpose datasets for network intrusion detection. While the paper discusses diverse FS and ID algorithms that achieved high accuracy and detection rates, it primarily addresses general IoT and cloud/edge environments, with a limited focus on the unique challenges of IIoT.

A second review paper, which included MFS algorithms, is Mallidi and Ramisetty (2025) performed an SLR of ML and DL techniques for evolving cyber threat detection in IoT ecosystems, focusing majorly on FS and data balancing optimization mechanisms. They examined a diversity of metaheuristic FS (MFS) models, such as GA, PSO, ACO, and relatively novel hybridized methods. They also examined how datasets like NSL-KDD, CICIDS-2017, UNSW-NB15, ToN-IoT, and BoT-IoT were being functionalized to train models in this context. This SLR, however, while it includes MFS algorithms, is not designated specifically for them nor specifically designated for their usage in an IIoT context.

Additionally, Sadeghian et al. (2025) investigated how nature-inspired algorithms revolutionized feature selection (FS) from 2018 to 2022, examining techniques ranging from GAs to PSO and ACO. These computational approaches excel at transmitting complex feature spaces and have proven particularly effective in cybersecurity applications like IDS. The study reveals that hybrid methods combining different selection strategies—such as FFA, GSA, and ACO—are consistently defeating regular techniques on established datasets like KDD-CUP 99 by discovering optimal feature subsets that upgrade detection rates while minimizing computational overhead. While these algorithms successfully address challenges like local optima and feature redundancy, the researchers argue that algorithm selection should be designated for specific dataset traits and application necessities rather than any total assumption of a single approach that is projected to excel universally across all domains.

Finally, Souri et al. (2024) proposed a cloud-based cyber-threat detection architecture for hyper-automation procedures in IIoT environments. The research introduces a hybrid Ensemble Bagged Trees Detection (EBTD) model with an ANOVA (Analysis of Variance)-based FS method to identify malicious patterns in industrial systems. The EBTD algorithm outperforms other ML approaches, including SVM, decision tree, and ANN. It scores a near-perfect detection accuracy of 99.51% on UNSW-NB15 and 99.86% on NSL-KDD datasets, while majorly reducing computation time. The architecture is specifically designated for hyper-automation applications in Industry 5.0 environments, focusing on cloud-based security for industrial communication systems. One limitation of the approach is that, although it performs well on benchmark datasets, the precision and recall results for detecting exploits are not sufficiently high, indicating limitations in the FS strategy for certain types of attacks.

**Table 1: Comparison of related works with this study**

| Study | Publication Year | Primary Focus | FS Role | IIoT-Specific | Key Distinction |
|-------|-----------------|---------------|---------|---------------|-----------------|
| Hu et al. (2024) | 2024 | Nature-inspired and meta-heuristic algorithms for IDS in cloud/edge and IoT | Metaheuristic FS for optimization | Limited | General IoT and cloud/edge environments |
| Mallidi and Ramisetty (2025) | 2024 | ML/DL approaches for IoT intrusion detection with feature selection and data balancing | Metaheuristic FS among broader techniques | Limited | Systematic review of ML/DL with feature selection as one aspect |
| Sadeghian et al. (2025) | 2025 | Nature-inspired algorithms for feature selection (2018–2022) | Primary focus on metaheuristic FS | No | General cybersecurity/IDS applications without IIoT focus |
| Souri et al. (2024) | 2024 | Cloud-based cyber-threat detection for hyper-automation in IIoT | ANOVA-based FS (statistical) | Yes—Industry 5.0 hyper-automation | Cloud-based ensemble approach with statistical FS, limitations in detecting exploits |
| **Our Study** | **Nov/2025** | **Cyber-attack detection in IIoT using metaheuristic feature selection (2018–2025)** | **Primary focus on MFS algorithms** | **Yes—Dedicated** | **Explicit IIoT focus addressing industrial requirements (real-time processing, security), MFS as main methodology, industrial cyber-attack context** |

### 2.2 Excluded Case Studies

This subsection highlights similar case studies that were eventually excluded from this work.

First, Sangaiah et al. (2023) proposed a Hybrid Ant-Bee Colony Optimization (HABCO) for FS with ID classifiers in a cloud of things (CoT). They addressed the pressing security issues of CoT, which require robust monitoring tools for identifying malicious behaviors involving a large number of connected devices. By formulating FS as an optimization problem, HABCO integrates ACO and ABC algorithms sequentially to select the optimal feature attributes that discriminate between benign and malignant network behavior. The proposed approach was evaluated on the KDD Cup 99 data set using seven different classifiers, and it achieved higher accuracy rates in the range of 2.87–4.63% compared to other state-of-the-art approaches. While this work uses an MFS model and covers most of our inclusion criteria, it focuses on CoT rather than IIoT; we excluded it from our work.

Another work that has a similar inclusion–exclusion situation is Davahli et al. (2020a) and Davahli et al. (2020b) proposed a novel hybridization of an evolutionary and an SI metaheuristic, first for FS in WSNs in IoT and second in IoT wireless networks. The hybrid MFS model followed sequentially by an SVM classifier was experimented on with the real-world AWID dataset and scored an accuracy of 99.09%. The paper details time complexity to be lightweight, with an FS time of 1147.156 s and a detection time of 10.906 s. However, this paper lacks details on overfitting analysis and is limited with its experiments to a single dataset. Despite the impressive novel MFS, the paper focuses on wireless networks in relation to the IoT approach rather than IIoT; therefore, it was excluded as a case study.

Many resources proposed MFS for ID in IoT but were too general to be included in IIoT-specific terms. For instance, Prasath and Perumal (2019) proposed a hybrid FS-ID algorithm that mixes PSO with a Bayes net classifier. The model, nicknamed MHBNC, was tested on the NSL-KDD dataset, scoring an overall accuracy of 82.99% over 4 attack types and normal data. The paper, like many of its peers, does not detail time complexity nor overfitting analysis. Furthermore, the paper presents this model for general use on network intrusion detection (ID) or Internet of Things (IoT) applications but lacks specific details for Industrial Internet of Things (IIoT) contexts. Additionally, its sole reliance on the NSL-KDD dataset raises concerns about its applicability as a case study in more specialized environments. For these reasons, it was excluded as a case study and included only as a resource.

Another example is Alamiedy et al. (2020) proposed a NIDS utilizing an FS-ID sequence of a multi-objective GWO and an SVM. The testing was conducted on the NSL-KDD dataset and had 4 attack types to classify, those being DoS, Probe, R2L, and U2R. The model scored accuracies of 93.64%, 91.02%, 57.73%, and 53.70% on the aforementioned attacks, respectively. This research, however, did not address either time complexity or overfitting. Furthermore, it targeted general IoT usage and was only tested on a general dataset, that is, NSL-KDD. Thus, it was excluded as a case study and included only as a related work.

An additional example is Karthikeyan et al. (2025) integrated an MFS with ensemble learning techniques for cyber threat recognition in IoT. For this, an adaptive Harris hawk optimizer (HHO) was applied on the CICIDS-2017 and NSL-KDD datasets along with a hybrid bidirectional gated recurrent unit (GRU) and WAE (Wasserstein autoencoder) and DBN (deep belief network), with the FS-ID executed sequentially. The proposed model achieved accuracies of 99.44% and 98.85% on the aforementioned datasets, respectively. A notable weakness of this paper is that it lacks a detailed description of time complexity and only states that the model is computationally efficient. Furthermore, this paper lacks relevance to IIoT, and thus was not considered to be a case study.

Other case studies targeted IIoT but applied a non-metaheuristic FS while utilizing metaheuristics for hyperparameter optimization rather than FS. For instance, Khafaga et al. (2023) presented a voting classifier and metaheuristic optimization for network intrusion detection. This paper proposes a NIDS with a voting perceptron (VP) based at its core on three classifiers: NN, RF, and KNN. The VP's parameters were enhanced using a modified whale optimization technique (WOA) led by a dipper-throated optimizer (DTO), where both WOA and DTO are metaheuristics. The model produced was executed on the RPL-NIDS17 dataset. SMOTE and LSH techniques were utilized to balance the dataset's traffic. FS was applied using an unspecified algorithm. The NN, RF, and KNN achieved a total accuracy of 95.1%, with an AUC of 99% and an MSE of 2.50E-08. These results outperformed the previous approaches; however, this research lacks a detailed explanation of the feature selection algorithm used. It also could have used a secondary dataset like CICIDS-2017.

Another example is Asif (2025), who presented robust ID in IoT using a stacked ensemble network with GA and DNN. This research aims at detecting various cyber threats in different network environments. It created a novel FS algorithm for the channel and spatial attention (CASA) technique, which enables focus on distinguished sets of features while avoiding useless or noisy data. CASA was followed by a hybrid CNN that is optimized with a GA meta-learner. Four datasets were used: Edge-IIoTset, IoT_Malware, the Blended Malware dataset, and UNSW-NB15. It got accuracies of 99.71%, 96.17%, 96.37%, and 99.15%, respectively. The weakness of this paper is that it signified a computational complexity trade-off, as the ensemble technique raises overhead with no valuable performance benefits, in addition to a lack of real-world testing.

Furthermore, another example lies in Shukla et al. (2025), who suggested a feature selection method and an MHO followed by a hybridized DL model for IoT FS-HPO-ID. It utilized a Levy flight mathematical technique based on the grasshopper optimization algorithm (GOA) for hyperparameter optimization (HPO) and a kernel principal component analysis (K-PCA) for FS. It was followed sequentially by a hybrid DNN-LSTM and tested on the NSL-KDD, TON-IoT, and CIC-IDS 2017, scoring accuracies of 98.67%, 97.22%, and 98.54%, respectively. Training time was 10,392 sec (NSL-KDD), 10,031 sec (TON-IoT), and 11,007 sec (CIC-IDS 2017), which is reasonable given its DL usage, and it is faster than base forms of CNN, DNN, LSTM, CNN-LSTM, or DNN-LSTM. The research mentioned functionalizing adaptive synthetic oversampling and 5-fold cross-validation to remove any overfitting. The paper has relevance to IIoT through the TON-IoT dataset and also industrial mentions in its text. However, the FS method used, K-PCA, is not metaheuristic, and metaheuristics in this research were only used for hyperparameters.

Another similar situation includes Chen and Mir (2025), who suggested an FS method and an MHO followed by a hybridized DL model for IIoT FS-HPO-ID. It utilized a Reptile Search Algorithm combined with an Improved Whale Optimization Algorithm (RSA-IWOA) for hyperparameter optimization and Principal Component Analysis (PCA) for FS. It was followed sequentially by a hybrid CNN-LSTM and tested on the UNSW-NB15, TON-IoT, and NCTUKM-IIOT datasets, scoring accuracies of 97.6%, 98.9%, and 98.7%, respectively. Training time with the proposed method was 50 min (with PCA and 45 features) compared to 78 min (without PCA and all features), producing efficiency enhancements through dimensionality reduction. The paper has strong relevance to IIoT through its focus on industrial control systems, use of the TON-IoT and NCTUKM-IIOT datasets, and extensive discussion of industrial applications. However, the FS method used, PCA, is not metaheuristic, and metaheuristics in this research were only used for hyperparameters.

Other papers excluded for different reasons include Bhattacharyya et al. (2020), who innovated a novel MFS method by hybridizing the Mayfly algorithm and Harmony Search (MA-HS). This is a novel cross-category hybridization since MA is an SI algorithm while HS is physics-based. This model, followed by classification, achieved high accuracies across many datasets. The research additionally provides a comparative analysis of the proposed model against other models such as PSO, GSA, SSA, and HHO. However, this research presents it as a general-purpose FS model and not for IDS or IoT usage. For this reason, it was excluded as a case study.

Benmessahel et al. (2019) propose utilizing SI locust swarm optimizer (LSO) and evolutionary neural networks for weight training and ID in IoT. The model scored detection accuracies of 95.42% and 94.02% on the UNSW-NB15 and NSL-KDD, respectively. Benmessahel et al. (2018) also proposed a similar idea but utilizing the physics-based multiverse optimizer (MVO) and evolutionary neural networks for weight training instead of LSO. This variation scored detection accuracies of 96.61% and 98.21% on the UNSW-NB15 and NSL-KDD, respectively. Both papers are a great example of the evolution of metaheuristic usages to be used beyond just FS. Both papers, however, do not explicitly perform FS; therefore, they were excluded as case studies.

After a careful literature review, we deduced that a research gap exists: there is no comprehensive summary of modern metaheuristic algorithms that are functionalized for feature selection of IIoT intrusion-detection data. Thus, we held this systematic literature review to identify, compare, and synthesize these methods.

---

## 3 Selected Research Methodology

This section outlines the key methodologies used in attack detection using IIoT metaheuristics, focusing on feature selection (FS) methods and classification models. We examine the most utilized and practical approaches in IDS for IIoT.

### 3.1 Summary of Methodologies

This subsection outlines the most utilized MFS-based methodologies for IIoT attack detection.

#### 3.1.1 Feature Selection Techniques and Classification Models

In 36 analyzed case studies, a total of 26 different types of metaheuristic algorithms were proposed for feature selection. 23 of these 26 were population-based algorithms, while 3 were single-solution-based.

Out of 36 case studies, 27 case studies applied single MFSs individually, while 9 hybridized two or more MFSs. 30 case studies applied FS-ID sequentially, while 6 case studies hybridized the MFS algorithm with the ID into a single algorithm. 32 case studies utilized population-based metaheuristics, while only 4 used single-solution-based ones (two TS, CVS, and GRASP). 24 case studies utilized swarm intelligence (SI) metaheuristics, while 4 utilized evolutionary (all genetic algorithms), 2 used physics-based (FWA and CVS), 2 used human behavior-based (TS), and 3 case studies proposed hybrid MFS between the origin categories.

The most used evolutionary MFS algorithm was GA, with 5 usages, three times individually and twice in novel hybrids, placing it as the most used MFS algorithm overall. Second overall are PSO and GWO with 4 usages each, with each being used 3 times individually and once in a novel hybrid. PSO and GWO are the most used SI algorithms overall.

On the physics-based algorithms side, only two algorithms were used, one each: CVS and FWA. In HBI, only TS was used twice. All remaining algorithms were only used once overall, displaying a wide vision across the current popularity of these models. All of the FS algorithms used were wrapper-based methods, as metaheuristic optimizers are designated to search into the feature space to find optimized subsets based on classifier performance (Chandrashekar and Sahin 2014).

For classification, RF was the most used ML classifier with 4/36 case studies, while deep learning's ANN, CNN, and RNN were tied with 6 usages each.

The trend heads towards sequentializing the FS-ID process rather than hybridizing it, with 30/36 of the case studies following this sequential order, and only 4/36 papers hybridizing the MFS with the IDS model, with the remaining two not specifying. Meanwhile, 10/36 cases used hybrid MFS approaches, 25/36 used MFS individually and a single case, MFS was hybridized with a non-metaheuristic for FS (TS + Cellular Automata). 8/36 cases have used hybrid ID methods. 17/36 cases generally use hybrid algorithms of any type, meaning the likelihood of a case study using a hybrid algorithm is 47.2%.

**Table 2: Metaheuristic Feature Selection Algorithm Usage Analysis**

| Algorithm | Total | Individual MFS | Hybrid with Another MFS |
|-----------|-------|----------------|------------------------|
| Particle Swarm Optimization (PSO) | 4 | 3 | 1 |
| Genetic Algorithm (GA) | 5 | 3 | 2 |
| Firefly Algorithm (FFA) | 3 | 3 | 0 |
| Gray Wolf Optimizer (GWO) | 4 | 3 | 1 |
| Tabu Search (TS) | 2 | 2 | 0 |
| Whale Optimization Algorithm (WOA) | 2 | 1 | 1 |
| Sailfish Optimizer (SFO) | 1 | 0 | 1 |
| Artificial Fisher Swarm Algorithm (AFSA) | 2 | 1 | 1 |
| Grasshopper Optimization Algorithm (GOA) | 1 | 0 | 1 |
| Bat Algorithm (BA) | 1 | 1 | 0 |
| Tuna Swarm Optimization (TSO) | 1 | 1 | 0 |
| Bird Swarm Optimization (BSO) | 1 | 0 | 1 |
| Gorilla Troops Optimizer (GTO) | 2 | 0 | 2 |
| Crow Search Algorithm (CSA) | 1 | 1 | 0 |
| Salp Swarm Algorithm (SSA) | 2 | 1 | 1 |
| Seagull Optimization Algorithm (SOA) | 1 | 0 | 1 |
| Elephant Herding Optimization (EHO) | 1 | 0 | 1 |
| Harris Hawk Optimizer (HHO) | 1 | 1 | 0 |
| Aquila Optimizer (AQUO) | 1 | 1 | 0 |
| Deer Hunting Optimization Algorithm (DHOA) | 1 | 1 | 0 |
| Sunflower Optimizing Algorithm (SFOA) | 1 | 1 | 0 |
| Fireworks Algorithm (FWA) | 1 | 1 | 0 |
| Chaotic Vortex Search (CVS) | 1 | 1 | 0 |
| Gravitational Search Algorithm (GSA) | 1 | 0 | 1 |
| Spider Wasp Optimization (SWO) | 1 | 0 | 1 |
| Artificial Bee Colony (ABC) | 1 | 0 | 1 |
| Bowerbird Courtship Feature Selection (BBFS) | 1 | 1 | 0 |

**Table 3: Machine Learning Algorithm Usage with MFS**

| Algorithm | Total | Independent | Hybrid with Another ID |
|-----------|-------|-------------|----------------------|
| Random Forest | 4 | 4 | 0 |
| XGBoost | 3 | 3 | 0 |
| K-Nearest Neighbour | 2 | 2 | 0 |
| SPAARC | 1 | 1 | 0 |
| K-means | 1 | 0 | 1 |
| Expert Classifier Approach (ECA) | 1 | 1 | 0 |
| Bagging | 1 | 0 | 1 |
| Logistic Regression (LR) | 1 | 0 | 1 |
| LightGBM | 1 | 0 | 1 |

**Table 4: Deep Learning Algorithm Usage with MFS**

| Algorithm | Total | Independent | Hybrid |
|-----------|-------|-------------|--------|
| Convolutional Neural Network (CNN) | 6 | 2 | 4 |
| Deep Neural Network (DNN) | 2 | 2 | 0 |
| Bidirectional LSTM (BiLSTM) | 2 | 0 | 2 |
| Long Short-Term Memory (LSTM) | 1 | 0 | 1 |
| Artificial Neural Network (ANN) | 6 | 4 | 2 |
| Recurrent Neural Network (RNN) | 6 | 4 | 2 |
| Autoencoder | 2 | 1 | 1 |
| Capsule Network (CapsNets) | 1 | 0 | 1 |
| Deep Belief Network (DBN) | 1 | 0 | 1 |

**Table 5: Comparison of Single vs Hybrid Feature Selection Algorithms**

| Metric | Single MFS | Hybrid MFS |
|--------|------------|------------|
| Top Performers | HHO (100%), FFA (99.92%), IBSWO (99.9%) | DOFFA (100%), Coati-GWO (99.91%), HAEMPSO (99.9%) |
| Mean Accuracy | 97.27% | 97.94% |
| Median Accuracy | 99.5% | 98.96% |
| Minimum Accuracy | 79.11% (PSO) | 91.6% (SAEHO) |
| Maximum Accuracy | 100% (HHO) | 100% (DOFA) |
| Number of Algorithms | 26 | 10 |

**Table 6: Comparison of Single vs Hybrid Intrusion Detection Algorithms**

| Metric | Single ID | Hybrid ID |
|--------|-----------|-----------|
| Top Performers | RF (100%), RNN (100%), SPARRC (99.9962%) | IBSWO Hybrid (99.9%), PSO-KMeans (99.8%), CNN-BiLSTM+Attention (99.8%) |
| Mean Accuracy | 96.59% | 98.51% |
| Median Accuracy | 99.20% | 99.37% |
| Minimum Accuracy | 76.00% (CNN-DBN) | 89.54% (NN-LSTM) |
| Maximum Accuracy | 100.00% (RF) | 99.90% (IBSWO Hybrid) |
| Number of Case Studies | 28 | 8 |

This distribution reflects strategic methodological evolution in the field. Simple metaheuristics often encounter early convergence or optimization inefficiencies when applied to complex threat detection scenarios. The 47.2% of studies employing hybrid approaches demonstrate the value of combining complementary algorithmic strengths, with these hybrids scoring impressive accuracy improvements over their individual classical implementations.

However, this improvement in accuracy trades off with computational costs that can restrict the ease of deployment in resource-limited IIoT devices. Only 7/36 of the case studies actually mention their models' time complexity in detail, while 5/36 claimed lightweight and 24/36 did not detail it.

This is a noteworthy observation of the disconnection between algorithmic sophistication and practical implementation. The low 7/36 or 19.4% indicates a crucial research gap, as understanding resource requirements is necessary to interpret theoretical performance into operating value. The lack of edge device validation is very problematic, as algorithms scoring well on research clusters may be absolutely impractical for deployment on actual IIoT devices.

Furthermore, there is the dataset mismatch issue. 13.9% of the research used IoT testbeds, while 50% of them used IoT datasets with some industrial relevance, and only 36.1% used IIoT-specific datasets. While the industrial relevance is strong, it adds up with the general IoT datasets to 63.9% non-industrial-specific datasets, which suggests many proposed solutions may not adequately address the unique issues of industrial environments, although they are still good proposals to try. The domination of TCP/IP-focused threat detection overlooks industrial protocol-specific threats (Modbus/TCP, EtherNet/IP), which have different statistical properties and necessitate designated feature engineering.

Dataset attack categories include:

- **Industrial IoT (IIoT) Datasets:** Physical Process Manipulation, SCADA/ICS Attacks, Industrial Protocol Exploits (Modbus, DNP3, CAN), PLC/Controller Compromise, Data Injection/False Readings, DoS on Industrial Systems
- **IoT Datasets with Industrial Relevance:** DDoS/Botnet Attacks, Network Intrusion, Port Scanning/Reconnaissance, Brute Force/Exploitation, Malware (Trojans, Worms), Data Exfiltration
- **IoT Datasets:** Web Attacks (SQL Injection, XSS), DDoS/DoS, Malware (Ransomware, Spyware), Password Attacks, DNS-based Attacks, Memory-based Exploits

---

## 4 Taxonomy of MFS-Based IDS Algorithms

This section presents our review methodology and then conducts a study of 36 recently presented IDS that use metaheuristic feature selection models and presents a taxonomy that highlights them. It consists of SI algorithms, evolutionary algorithms, physical-based algorithms, human-behavior-inspired approaches, and novel hybrid approaches.

### 4.1 Review Methodology

We followed an SLR methodology. To validate broad coverage of recent literature, Google Scholar was queried with the string:

```
("Metaheuristic" AND "Feature Selection" AND "Intrusion Detection" AND "IIoT" OR "IoT")
```

The string gave 1050 results; we screened the first 100 search results ranked by relevance for inclusion in our work. We filtered these results based on the following inclusion and exclusion criteria:

**Inclusion Criteria:**
- Studies published in peer-reviewed articles and conferences of the 5th edition and above.
- Studies exclusively using metaheuristics for feature selection for intrusion detection in an IIoT-relevant context.
- Publications available in English.
- Studies published between 2018 and 2025.
- Studies published by reputable publishers (Springer, Wiley, MDPI, IEEE, Elsevier, Sage).
- Studies that present empirical results of our relevant context.

**Exclusion Criteria:**
- Non-peer-reviewed articles (e.g., blogs, opinions, magazines).
- Studies that use metaheuristics for purposes other than feature selection for ID-IIoT.
- Publications prior to 2018.
- Research papers published in journals below Q3.
- Duplicate studies or extended versions of previously published work without significant new contributions.

We also added some case studies manually or through reviewers' recommendations.

### 4.2 Taxonomy

The taxonomy displayed significant patterns in how MFS algorithms are developing for IoT/IIoT IDS. The SI technique dominates the landscape (69.44%), with variants of PSO, GWO, and FFA being the most used, and cases of using PSO, FFA, BA, and HHO scoring strong performances. This prevalence is likely due to the natural capabilities of swarm algorithms to equalize between exploration and exploitation in high-dimensional attribute spaces typical to networking traffic data.

Future metaheuristic feature selection research should prioritize:
- Standardizing computational efficiency metrics while also reporting accuracy is essential.
- Validation on resource-constrained hardware reflecting actual deployment conditions.
- Industrial-specific dataset utilization with domain-relevant attack vectors.
- Dynamic feature selection approaches that can adapt to evolving attack patterns.
- Explainability mechanisms to support security analyst decision making.

The most promising direction seems to involve developing adaptable hybrid techniques that can dynamically balance accuracy and computational requirements based on the threat context and available resources, effectively optimizing the optimization process itself.

### 4.3 Swarm Intelligence MFS

**Shanbhag et al. (2024)** — Leveraging Metaheuristics for FS with ML Classification for Malicious Packet Detection in Computer Networks. They experimented with NSS-KDD and kddcupdata_10% datasets using 48 combinations of FS and ML algorithms. They proposed GA, GWO, and PSO combined with one of four ML algorithms: RF, LR, GNB, and DT. The combination achieving the highest was RF-PSO_RF with an accuracy of 99.5787%. One notable missing piece of information is the computational complexity.

**Saheed et al. (2023)** — A novel hybrid autoencoder and modified PSO (HAEMPSO) feature selection followed by DNN for classification. Experiments used 10-fold cross-validation on UNSW-NB15 and BoT-IoT. HAEMPSO-DNN gave accuracies of 98.8% and 99.9% on generic attack and benign categories. The research limits DL testing to DNN and does not provide comprehensive clarification of time complexity.

**Anushiya & Lavanya (2023)** — Proposed GA_FR_CNN for ID and AAFSO for attribute selection. AAFSO (assimilated artificial fish swarm optimization) simulates fish movement. Tested on UNSW-NB15 and BOT-IoT, scoring accuracies of 94.488% and 93.7756%. Lacks any description of computational complexity.

**Gaber et al. (2023)** — IDS for IIoT using PSO and BA with RF for classification. Tested on WUSTL-IIOT-2021. PSO-RF achieved 99.7% accuracy, while BA-RF achieved 99.9% accuracy. A notable advantage is the use of a designated IIoT dataset. Complexity is said to be small due to highly reduced parameters.

**Sanju (2023)** — HHO for FS and RNN as classifier. The MM-WMVEDL model yielded accuracies of 98.12%, 99.98%, and 100% on IoT-23, CICIDS2017, and UNSW-NB15 respectively. Time complexity was not discussed.

**Sagu et al. (2023)** — Proposed SAEHO (seagull-adapted elephant herding) and SU-CMO for FS with DL (CNN-DBN and Bi-LSTM-GRU). Evaluated on UNSW-NB15. At 80% learning rate, SAEHO-CNN-DBN achieved 91.6% accuracy. Time complexity was not detailed.

**Li et al. (2024)** — ASFOA (adaptive sunflower optimizing technique) combined with deep random NN to produce MH-DRNN IIoT IDS. Achieved 99.2% accuracy on UNSW-NB15. Could have benefited from a secondary dataset and lacks detailed time complexity description.

**Bajpai et al. (2024)** — WOA for FS with XGBoost for ID. WOA-BOOST achieved 99.2% and 99.5% accuracy on IoTID20 and UNSW-NB15 respectively. Lacks details on computational complexity.

**Chander & Kumar (2023)** — DHOA (deer hunting optimizing technique) for FS with cascaded RNN for ID. SSO was used to optimize CRNN. Achieved 99.31% and 97.88% on UNSW-NB15 and UCI-SECOM. Lacks detailed computation complexity exploration.

**Prasad et al. (2025)** — Coati-GWO for FS with conditional variational AE (CVAE) for ID. Scored 99.91% accuracy on RT-IoT2022. Lacks real-world experimentation and detailed time complexity.

**Logeswari et al. (2025)** — Quantum-PSO combined with ANFIS for MFS. CapsNets hybridized with ARNN as multi-stage classifier. Achieved 98.96% on BOT-IoT and 98.83% on TON-IoT. Has high computational overhead compared to traditional FS.

**Alzubi et al. (2025)** — SSA with ANN for ID. Tested on Edge-IIoTset, WUSTL-IIoT-2021, and IoTID20, achieving accuracies of 88.241%, 93.610%, and 97.698%. May struggle with long training times on large datasets.

**Thamer Francis et al. (2025)** — FFA-based attribute selection and SPAARC (split-point mechanism) for SD-IIoT. Achieved 99.9962% and 99.991% on DDoS_SDN and XIIoT_ID. SPAARC is 70% faster than classic CART DT but without explicit time complexity notation.

**Maazalahi & Hosseini (2025)** — Hybrid SFO-WOA for FS with PSO-KMeans for ID. Achieved 99.8% on BOT-IoT and 99.5% on UNSW-NB15. One of the few works detailing computational complexity, though slower than basic metaheuristics without clustering.

**Kocherla et al. (2024)** — Improved CSA (ICSA) for FS with stacking RNN for ID. Tested on NSL-KDD with 98.3% accuracy. Does not clarify time complexity.

**Taher et al. (2023)** — Hybrid AFSA-GOA-KNN for FS with improved HHO-NN for ID. Achieved 98.7% on N-BaIoT across 10 attack types. Time complexity said to be significantly reduced but not formally described.

**Kareem et al. (2022)** — Hybrid GTO-BSA (Gorilla Troops Optimizer for Bird Swarms) for FS with KNN for ID. Tested on NSL-KDD (95%), UNSW-NB15 (71%), CICIDS-2017 (98%), and BoT-IoT (94%). GTO-BSA has computation complexity of O(T×N×D). Lacks real-world deployment.

**Jovanovic et al. (2024)** — DOFFA (diversity-oriented firefly algorithm) for FS with ELM or XGBoost. Achieved 100% on DTM and EFPADD, 99.52% on BoT-IoT, and 94.94% on UNSW-NB15. Computational complexity is O(T×N²) — same as FFA.

**Ogunseyi & Thiyagarajan (2025)** — HS-FFA (hybridized statistical and firefly algorithm) for FS with ANN-LSTM for ID. Achieved 98.42% on NF-Bot-IoT-V2 and 89.54% on IoTID20. Detailed time complexity as O(n×k+k²). Quasi-real-time operation at 8.5 ms per sample. Struggles with zero-day attacks (54.76% accuracy).

**Fatani et al. (2021)** — Binary AQUO for FS with CNN for ID. Tested on NSL-KDD (76.002%), CICIDS2017 (99.911%), KDD99 (99.919%), and BoT-IoT (98.926%). Lacks formal time complexity description.

**Alblehai (2025)** — Improved TSO (ITSO) for FS with BiLSTM with self-attention for ID. Achieved 99.44% on Ton-IoT and 99.37% on Edge-IIoT. Lacks real-world experimentation and time complexity clarification.

**Mahato & Dutta (2025)** — GWO for FS with LightGBM for ID. Achieved 99.99% on UNSW-NB15, 99.99% on CIRA_CIC_DoHBrw, and 99.84% on BoT-IoT with execution times of 27.737s, 44.66s, and 1.40s respectively. Said to be lightweight. Lacks detailed overfitting analysis.

**Gong et al. (2025)** — HMDOA (hybrid metaheuristic dynamic optimization) using GTO, ABC, SSA, Levy flight, and KNN for FS with CNN for ID. Achieved 96.54%, 79.09%, and 99.40% on NSL-KDD, CIC_MalMem_2022, and RT_IOT2022. Time complexity: O(T×N×d), space complexity: O(N×d). Lacks proper overfitting analysis.

**Mallidi & Ramisetty (2025)** — BBFS (Bowerbird courtship feature selection) with LR in edge tier and 1D CNN in cloud tier. Achieved 99.70% and ~100% on WUSTL-IIoT. Time complexity: O(T×N×(logN+|F|×C(F))). Edge LR inference minimized from 52ms to 38ms, cloud CNN from 27.86s to 18.28s.

**Table 7: Swarm Intelligence MFS — Summary of Case Studies**

| Study | FS Algorithm | ID Algorithm | Dataset(s) | Accuracy |
|-------|--------------|--------------|------------|----------|
| Shanbhag et al. (2024) | RF-PSO | RF | NSL-KDD | 99.58% |
| Saheed et al. (2023) | HAE-M-PSO | DNN | UNSW-NB15, BoT-IoT | 99.9% |
| Anushiya & Lavanya (2023) | AAFSO | GA-FR-CNN | UNSW-NB15, Bot-IoT | 94.5%, 93.8% |
| Gaber et al. (2023) | BA | RF | WUSTL-IIoT-2021 | 99.9% |
| Sanju (2023) | HHO | RNN | IoT-23, CICIDS2017 | 100% |
| Sagu et al. (2023) | SAEHO | CNN-DBN | UNSW-NB15 | 91.6% |
| Li et al. (2024) | ASFOA | Deep Random NN | UNSW-NB15 | 99.2% |
| Bajpai et al. (2024) | WOA | XGBoost | IoTID20, UNSW-NB15 | 99.5% |
| Chander & Kumar (2023) | DHOA | Cascaded RNN | UNSW-NB15, UCI-SECOM | 99.3% |
| Prasad et al. (2025) | Coati-GWO | CVAE | RT-IoT2022 | 99.91% |
| Logeswari et al. (2025) | Quantum-PSO | CapsNets+ARNN | Bot-IoT, TON-IoT | 98.96% |
| Alzubi et al. (2025) | SSA | ANN | Edge-IIoTset, WUSTL-IIoT | 97.7% |
| Francis et al. (2025) | FFA | SPARRC | DDoS-SDN, XIIoT-ID | 99.9962% |
| Maazalahi & Hosseini (2025) | SFO-WOA | PSO-KMeans | Bot-IoT, UNSW-NB15 | 99.8% |
| Kocherla et al. (2024) | ICSA | SRNN | NSL-KDD | 98.3% |
| Taher et al. (2023) | AFSA-GOA-KNN | Improved HHO-NN | N-BaIoT | 98.7% |
| Kareem et al. (2022) | GTO-BSA | KNN | NSL-KDD, CICIDS-2017 | 98% |
| Jovanovic et al. (2024) | DOFFA | XGBoost | BoT-IoT, UNSW-NB15 | 100% |
| Ogunseyi & Thiyagarajan (2025) | HS-FFA | ANN-LSTM | NF-Bot-IoT-V2 | 98.42% |
| Fatani et al. (2021) | AQUO | CNN | NSL-KDD, CICIDS2017 | 99.9% |
| Alblehai (2025) | ITSO | BiLSTM-SA | Ton-IoT, Edge-IIoT | 99.44% |
| Mahato & Dutta (2025) | GWO | LightGBM | UNSW-NB15, BoT-IoT | 99.99% |
| Gong et al. (2025) | HMDOA(GTO+ABC+SSA) | CNN | NSL-KDD, RT-IoT2022 | 99.4% |
| Mallidi & Ramisetty (2025) | BBFS | LR (edge), CNN (cloud) | WUSTL-IIoT | 99.7%, 100% |

### 4.4 Evolutionary

**Fang et al. (2024)** — BGA for FS with ANN for ID in ICS. Tested on SWaT and WADI testbeds, achieving 98.08% and 91.874% accuracy with response times of 87.13s and 16.98s. Does not provide detailed time complexity analysis.

**Fang et al. (2025)** — IGA for FS with CNN-BiLSTM with Attention Mechanism (ACBLST) for ID. Achieved 99.8% on TON_IoT. Relies on a single dataset. Does not include formal time complexity analysis.

**Sharma & Singh (2025)** — GA for FS with CNN ensemble (Xception, VGG16, VGG19) for ID. Achieved 99.73% on CIC-IoT-2023 and 95.33% on UNSW-NB15. Lacked time complexity description.

**Khan et al. (2025)** — GA for MFS with ANN (L2 regularization, dropout) for ID. Achieved 99.7% on IoTID20 and IoT-Botnet. Does not detail time complexity and has some misclassifications in low-profile attack categories.

**Table 8: Evolutionary Algorithms MFS — Summary of Case Studies**

| Study | FS Algorithm | ID Algorithm | Dataset(s) | Accuracy |
|-------|--------------|--------------|------------|----------|
| Fang et al. (2024) | BGA | ANN | SWaT, WADI | 98.08% |
| Fang et al. (2025) | IGA | CNN-BiLSTM+AM | TON_IoT | 99.8% |
| Sharma & Singh (2025) | GA | CNN Ensemble | CIC-IoT-2023, UNSW-NB15 | 99.73% |
| Khan et al. (2025) | GA | ANN | IoTID20, IoT-Botnet | 99.7% |

### 4.5 Physics Based

**Jayasankar et al. (2024)** — FWA for FS with DRNN for ID. Achieved 96.11% accuracy, 97.31% DR, 3.03% FPR. Does not explicitly mention the dataset name or link.

**Geetha et al. (2024)** — CVS (chaotic vortex search) for FS with FLN (fast learning network) for ID. Achieved 99.77% on CICIDS-2017 and 99.68% on BoT-IoT. Does not detail time complexity. Lacks real-world deployment.

**Table 9: Physics Based MFS — Summary of Case Studies**

| Study | FS Algorithm | ID Algorithm | Dataset(s) | Accuracy |
|-------|--------------|--------------|------------|----------|
| Jayasankar et al. (2024) | FWA | DRNN | – | 96.11% |
| Geetha et al. (2024) | CVS | FLN | CICIDS-2017, BoT-IoT | 99.77% |

### 4.6 Human Behaviour Inspired

**Nazir et al. (2023)** — CA-TS (Cellular Automata Tabu Search) for FS with RF for ID. Achieved 99.50% accuracy with 0.004% FPR using only 13 features on TON-IoT. Cost function: 4.496. Only tested on a single dataset.

**Nazir & Khan (2021)** — TS (Tabu Search) for FS with RF for ID. Achieved 85.12% accuracy with 3.7% FPR considering 16 attributes on UNSW-NB15. Could have benefited from a secondary dataset.

**Table 10: Human Behaviour Based MFS — Summary of Case Studies**

| Study | FS Algorithm | ID Algorithm | Dataset(s) | Accuracy |
|-------|--------------|--------------|------------|----------|
| Nazir et al. (2023) | CA-TS | RF | TON-IoT | 99.50% |
| Nazir & Khan (2021) | TS | RF | UNSW-NB15 | 85.12% |

### 4.7 Novel Hybridizations

**Dey et al. (2023)** — GSGW-DT (BGSA+BGWO with decision tree) for FS with RF for ID. Achieved 99.41% accuracy, 99.09% DR, 99.33% F1, 0.03% FPR on UNSW-NB15. Tested only on a single dataset. Not specific to IoT/IIoT traffic.

**Mohammad Shtayat et al. (2025)** — IBSWO (GA-SWO) for FS. Achieved 98.7%, 99.9%, and 99.7% accuracy on UNSW-NB15, TON_IoT, and NCTUK-IIOT. Lacks specific explanation of actual ID algorithms used to classify. Does not provide formal time complexity.

**Dakic et al. (2024)** — GA-PSO (genetic self-adjusted PSO) for FS with XGBoost and KNN for ID. Achieved 79.10% and 79.11% accuracy on CAN dataset. Dataset is field-specific. Does not clarify time complexity.

**Table 11: Novel Hybrid MFS — Summary of Case Studies**

| Study | FS Algorithm | ID Algorithm | Dataset(s) | Accuracy |
|-------|--------------|--------------|------------|----------|
| Dey et al. (2023) | GSGW-DT | RF | UNSW-NB15 | 99.41% |
| Mohammad Shtayat et al. (2025) | IBSWO(GA-SWO) | Unspecified | UNSW-NB15, TON-IoT | 99.9% |
| Dakic et al. (2024) | GSA-PSO | XGBoost | CAN-dataset | 79.11% |

### 4.8 Other Metaheuristic Types

**Quincozes et al. (2022)** — Utilized GRASP, a stochastic single-solution-based optimization metaheuristic for FS. Used ECA for ID. Tested on WSN-DS and SWaT datasets. Achieved accuracies ranging from 99.26% to 99.99% on multiclass and 99.65% on binary classification. Lacks detailed time complexity clarification.

---

## 5 Technical Analysis and Discussion

This section presents a crucial technical evaluation of the revised methodologies, focusing on enriched FS techniques and ID headways in IIoT environments. We examine algorithmic curations, performance trade-offs, and unaddressed challenges.

### 5.1 Effective Methodologies

The combination of PSO-RF emerged as a high-scoring approach (Shanbhag et al. 2024), as well as the PSO-DL methodology, appearing in two case studies. The PSO-RF pairing's popularity originates from PSO's direct implementation and RF's inherent robustness, continuously scoring a minimum of 99% accuracy on well-known datasets like NSL-KDD and CICIDS-2017. The PSO-DL techniques also had high scores, such as HAEMPSO-DNN with 99.90% on TON_IoT. However, PSO-RF risks overfitting to dataset-specific patterns, reducing generalization, while the PSO-DL technique faces scalability challenges in large-scale IIoT applications due to its high computational requirements.

The integration of GWO-RF and GWO-DL is as effective but struggles with similar vulnerabilities. Many other usages of MFS + DL (e.g., Anushiya and Lavanya 2023; Fatani et al. 2021; Fang et al. 2024) all score high results but again struggle with the same computational requirements paradox.

Another common methodology is MFS + gradient boosting. In Jovanovic et al. (2024), Dakic et al. (2024), and Bajpai et al. (2024), XGBoost was proposed as the best performer, preceded by FFA, GSA-PSO, and WOA respectively. GWO-LightGBM demonstrated strong performance, leveraging GWO's effective exploration-exploitation balance to enhance LightGBM's gradient boosting capabilities, as evidenced by Mahato and Dutta (2025), scoring 99.41% accuracy on UNSW-NB15.

Hybrid SI methods, including GTO-BSA (Kareem et al. 2022), IBSWO (Mohammad Shtayat et al. 2025), and SAEHO (Sagu et al. 2023), were employed in six studies, proposing outstanding solutions to population-based problems but raising the complexity further due to their usage of advanced operators like IBSWO's flat crossover.

| Methodology | Accuracy Range | Strengths | Weaknesses |
|-------------|----------------|-----------|------------|
| PSO + RF | 99.5–99.7% | Robust, Generalizable | Computationally heavy |
| Metaheuristic + XGBoost | 99.2–99.7% | High precision, low FPR | Requires hyperparameter tuning |
| Hybrid SI (IBSWO, GTO-BSA, SAEHO) | 95–99.9% | Cross-dataset reliability | Complex implementation |
| DL with Metaheuristics | 97–100% | Handles high-dimensional data | Black-box nature, high resource needs |

### 5.2 Critical Gaps

- **Dataset diversity:** 13.9% use general IoT datasets, 50% use IoT with industrial relevance rather than IIoT-specific datasets.
- **Computational Efficiency:** Only 19.4% discuss time complexity in detail, 13.9% claim lightweight, 66.7% do not detail it.
- **Real-World Validation:** The majority of papers lack application in live IIoT environments.

### 5.3 Key Trade-offs

| Algorithm Class | Strengths | Limitations |
|-----------------|-----------|-------------|
| Swarm Intelligence | Good exploration, simpler implementation, high accuracy (PSO-RF: 99.7%) | Prone to premature convergence, trapped in local optima |
| Evolutionary Algorithms | Robust global search, handles large feature spaces, stable convergence | Computationally expensive, complex parameter tuning |
| Physics-Based | Well-balanced exploration/exploitation, mathematically well-grounded | Slower convergence, sensitive to parameter settings |
| Human Behavior-Based | Better at avoiding local optima through memory mechanisms | Complex implementation, requires domain knowledge |
| Hybrid SI Algorithms | Highest accuracy (GTO-BSA: 95–98%), compensates for individual weaknesses | Most computationally complex, difficult theoretical analysis |

### 5.4 Performance Benchmarks

| Model | Accuracy | F1-Score | FPR | Dataset |
|-------|----------|----------|-----|---------|
| GTO-BSA + RF | 98.2% | 97.8% | 0.02% | CICIDS-2017 |
| HAEMPSO-DNN | 99.9% | 99.7% | 0.01% | BoT-IoT |
| IBSWO + SVM | 99.7% | 99.5% | 0.03% | TON_IoT |
| Coati-GWO + CVAE | 99.91% | 98.11% | 0.01% | RT-IoT2022 |
| ITSO-BiLSTM-SA | 99.44% | 99.39% | 0.03% | TON-IoT |
| IGA-ACBLST | 99.8% | 99.7% | 0.02% | TON-IoT |

---

## 6 Overall Findings

### 6.1 Dominant Trends

- 34/36 case studies included FS-ML or FS-DL.
- 30/36 cases: MFS executed first, followed sequentially by ML/DL classifier.
- 10/33 case studies combined two or more MFS algorithms.
- 18/36 papers use purely DL for ID.
- 12/36 case studies use individual ML algorithms.

### 6.2 Limitations of Metaheuristics

1. **Black-box nature:** Few papers clarify why certain features were selected, decreasing trust in critical IIoT systems.
2. **Overfitting risk:** High accuracy on small curated datasets may not generalize.
3. **Runtime performance:** Only evaluated in 9/33 case studies; real-time processing (<1ms latency) is mandatory for IIoT.

#### 6.2.1 Dataset Mismatch

- **Dataset Mismatch:** 63.9% use general IoT datasets, only 36.1% use IIoT-specific data.
- **Hardware Constraints:** None test on edge devices (e.g., Raspberry Pi).
- **Attack Coverage Gap:** Most focus on DDoS (16–21/36) and scanning (10–15/36); only 3–4 address IIoT-specific threats (Gaber et al. 2023; Fang et al. 2024; Mohammad Shtayat et al. 2025). Industrial protocol exploits such as Modbus/TCP and DNP3 are largely ignored despite their critical importance in industrial environments.

#### 6.2.2 Barriers to Adoption

- **Proprietary Protocols:** Industrial systems such as PROFINET necessitate protocol-aware IDS, but only 2 papers (Gaber et al. 2023) work around this.
- **Regulatory Compliance:** No study aligns with IEC 62443 or NIST SP 800-82 standards for IIoT security.

#### 6.2.3 Pathways to Real-World Deployment

- **Co-Design with Industry:** Partner with manufacturers to collect real IIoT traffic from smart factories.
- **Edge-Native Algorithms:** Optimize metaheuristics for MCUs such as ARM Cortex-M using quantization.
- **Benchmarking Frameworks:** Develop IIoT-designated evaluation metrics such as latency-per-feature.

### 6.3 Open Challenges

1. **Real-time applicability:** Merely 12/36 papers address latency for IIoT applications.
2. **Dynamic Data Adaptation:** Most methods presume static feature spaces, disregarding IIoT's streaming data.
3. **IIoT-specific datasets:** Usage of IIoT-specific datasets rather than general IoT-purposed.

---

## 7 PC Specifications and Software

The PC specifications used to conduct this review are as follows:

- **Processor:** 12th Gen Intel(R) Core(TM) i7-12650 H (2.30 GHz)
- **Installed RAM:** 16.0 GB
- **System type:** 64-bit operating system, x64-based processor

Python was utilized to generate the figures (Van Rossum and Drake 2009), specifically matplotlib (Hunter 2007). The taxonomy was built using Miro (2023). The manuscript was written in LaTeX (Lamport 1986) using Overleaf (Digital Science UK Limited 2023).

---

## 8 Conclusion

In this systematic literature review, we case-studied 36 recent IDS approaches based on MFS usages for ID in IIoT. We discovered that:

- **SI algorithms dominate** the field, although the most utilized algorithm overall is the evolutionary GA with 5 usages, against 4 usages at most in SI for PSO. Other trending SI algorithms include FFA and GWO.
- **DL dominates** classification, with CNN, ANN, and RNN being employed 6 times each overall, 10 times independently, and 8 times in hybrids. Random Forest (4/36) remains the dominant ML classifier, with PSO-RF combinations showing consistent accuracy between 95 and 99.5% across datasets.
- **All metaheuristic FS approaches are wrapper-based** by nature.
- **10/36 use hybrid MFS algorithms.**
- **Notable high performers:** IBSWO, Coati-GWO-CVAE, FFA-SPAARC, and HAEMPSO-DNN, all achieving >99.7% accuracy.

**Key Trade-offs:**
- Swarm intelligence algorithms offer simpler implementation but risk premature convergence.
- Hybrid approaches achieve superior accuracy at the cost of computational complexity.

**Critical Gaps:**
1. Dataset mismatch (13.9% using generic data and 50% using IoT with industrial relevance rather than IIoT-specific data).
2. Limited attack coverage (only four articles addressing industrial-specific threats).
3. Lack of edge device validation.
4. Insufficient evaluation of real-time performance (only four articles).

Those gaps also present feasibility problems in implementing the models of the case studies, which leaves some open challenges, including real-time applicability of these models and the usage of IIoT-specific datasets for the specific purposes the authors are building their models for.

**Future Work:**
- IIoT-specific attack detection.
- Real-time applicability of metaheuristic feature selection.
- AI explainability, interpretability, and feature importance.
- Online/streaming adaptation for FS in IIoT.
- Drift handling and incremental/online feature selection.

---

## 9 Supplementary Information

Additional supporting information may be found in the online version of the article at the publisher's website.

**Supplementary Information:** The online version contains supplementary material available at https://doi.org/10.1007/s10462-025-11473-7.

---

## Author Contributions

G.T.F. and A.S. wrote the main manuscript text, edited figures and tables. N.I. prepared grammar checking and editing on the main text and resources. All authors reviewed the manuscript.

**Funding:** No funding was received for this article.
**Data Availability:** No datasets were generated or analysed during the current study.

## Declarations

**Conflict of interest:** The authors declare they have no conflict of interest.
**Consent for publication:** Not applicable.
**Ethics approval and consent to participate:** Not applicable.
**Materials availability:** Not applicable.
**Code availability:** Not applicable.

**Open Access:** This article is licensed under a Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License, which permits any non-commercial use, sharing, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if you modified the licensed material. You do not have permission under this licence to share adapted material derived from this article or parts of it. The images or other third party material in this article are included in the article's Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article's Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit http://creativecommons.org/licenses/by-nc-nd/4.0/.

---

## References

Agrawal P, Abutarboush HF, Ganesh T, Mohamed AW (2021) Metaheuristic algorithms on feature selection: a survey of one decade of research (2009–2019). IEEE Access 9:26766–26791

Alamiedy TA, Anbar M, Alqattan ZN, Alzubi QM (2020) Anomaly-based intrusion detection system using multi-objective grey wolf optimisation algorithm. J Amb Intell Humaniz Comput 11(9):3735–3756

Alblehai F (2025) Artificial intelligence-driven cybersecurity system for internet of things using self-attention deep learning and metaheuristic algorithms. Sci Rep 15(1):13215

Alsaedi A, Moustafa N, Tari Z, Mahmood A, Anwar A (2020) TON_IoT telemetry dataset a new generation dataset of IoT and IIoT for data-driven intrusion detection systems. IEEE Access 8:165130–165150. https://doi.org/10.1109/ACCESS.2020.3022862

Alzubi OA, Alzubi JA, Qiqieh I, Al-Zoubi A (2025) An IoT intrusion detection approach based on Salp swarm and artificial neural network. Int J Netw Manag 35(1):2296

Anushiya R, Lavanya V (2023) A new deep-learning with swarm based feature selection for intelligent intrusion detection for the internet of things. Meas Sens 26:100700

Arya L, Gupta GP (2023) Ensemble filter-based feature selection model for cyber attack detection in industrial internet of things. In: 2023 9th international conference on advanced computing and communication systems (ICACCS). IEEE, vol 1, pp 834–840

Asif S (2025) OSEN-IoT: an optimized stack ensemble network with genetic algorithm for robust intrusion detection in heterogeneous IoT networks. Expert Syst Appl 276:127183

Bajpai S, Sharma K, Chaurasia BK (2024) A hybrid meta-heuristics algorithm: XGBoost-based approach for ids in IoT. SN Comput Sci 5(5):537

Benmessahel I, Xie K, Chellal M (2018) A new evolutionary neural networks based on intrusion detection systems using multiverse optimization. Appl Intell 48(8):2315–2327

Benmessahel I, Xie K, Chellal M, Semong T (2019) A new evolutionary neural networks based on intrusion detection systems using locust swarm optimization. Evol Intell 12(2):131–146

Bhattacharyya T, Chatterjee B, Singh PK, Yoon JH, Geem ZW, Sarkar R (2020) Mayfly in harmony: a new hybrid meta-heuristic feature selection algorithm. IEEE Access 8:195929–195945

Brezočnik L, Fister I Jr, Podgorelec V (2018) Swarm intelligence algorithms for feature selection: a review. Appl Sci 8(9):1521

Chander N, Upendra Kumar M (2023) Metaheuristic feature selection with deep learning enabled cascaded recurrent neural network for anomaly detection in industrial internet of things environment. Clust Comput 26(3):1801–1819

Chandrashekar G, Sahin F (2014) A survey on feature selection methods. Comput Elect Eng 40(1):16–28

Chen Y, Mir M (2025) An intrusion detection system for industrial IoT using CNN-LSTM and reptile search algorithm. Clust Comput 28(7):452

Dakic P, Zivkovic M, Jovanovic L, Bacanin N, Antonijevic M, Kaljevic J, Simic V (2024) Intrusion detection using metaheuristic optimization within IoT/IIoT systems and software of autonomous vehicles. Sci Rep 14(1):22884

Davahli A, Shamsi M, Abaei G (2020a) A lightweight anomaly detection model using SVM for WSNS in IoT through a hybrid feature selection algorithm based on ga and gwo. J Comput Secur 7(1):63–79

Davahli A, Shamsi M, Abaei G (2020b) Hybridizing genetic algorithm and grey wolf optimizer to advance an intelligent and lightweight intrusion detection system for IoT wireless networks. J Amb Intell Humaniz Comput 11(11):5581–5609

Dey AK, Gupta GP, Sahu SP (2023) A metaheuristic-based ensemble feature selection framework for cyber threat detection in IoT-enabled networks. Decis Analyt J 7:100206

Digital Science UK Limited (2023) Overleaf: online LaTeX editor. Accessed 15 Nov 2025. https://www.overleaf.com

Dissanayake MB (2021) Feature engineering for cyber-attack detection in internet of things. Int J Wirel Microwave Technol 11(6):46–54

Fang Y, Yao Y, Lin X, Wang J, Zhai H (2024) A feature selection based on genetic algorithm for intrusion detection of industrial control systems. Comput Secur 139:103675

Fang Y, Jia Y, Bai G, Hong R, Linglin X, Ai C, Asim M, Li Z, et al (2025) Deciphering ton-IoT threats: metaheuristic and deep learning for attack classification. Expert Syst Appl 127414

Fatani A, Dahou A, Al-Qaness MA, Lu S, Elaziz MA (2021) Advanced feature extraction and selection approach using deep learning and Aquila optimizer for IoT intrusion detection system. Sensors 22(1):140

Gaber T, Awotunde JB, Folorunso SO, Ajagbe SA, Eldesouky E (2023) Industrial internet of things intrusion detection method using machine learning and optimization techniques. Wirel Commun Mob Comput 2023(1):3939895

Geetha R, Jegatheesan A, Dhanaraj RK, Vijayalakshmi K, Nayyar A, Arulkumar V, Velmurugan J, Thavasimuthu R (2024) CVS-FLN: a novel IoT-IDS model based on metaheuristic feature selection and neural network classification model. Multimedia Tools Appl 83(39):86557–86591

Gong X, Yang Y, Zhang Y, Li N, Guan Y, Jiang R (2025) Feature selection method for network intrusion based on hybrid meta-heuristic dynamic optimization algorithm. Comput Secur 104512

Hu W, Cao Q, Darbandi M, Jafari Navimipour N (2024) A deep analysis of nature-inspired and meta-heuristic algorithms for designing intrusion detection systems in cloud/edge and iot: state-of-the-art techniques, challenges, and future directions. Clust Comput 27(7):8789–8815

Hunter JD (2007) Matplotlib: a 2D graphics environment. Comput Sci Eng 9(3):90–95. https://doi.org/10.1109/MCSE.2007.55

Hussain K, Mohd Salleh MN, Cheng S, Shi Y (2019) Metaheuristic research: a comprehensive survey. Artif Intell Rev 52(4):2191–2233

iTrust SUoT (2016) Design: secure water treatment (SWaT) dataset. iTrust Centre for Research in Cyber Security. https://itrust.sutd.edu.sg/itrust-labs-home/itrust-labs_swat/

iTrust SUoT (2017) Design: water distribution (WADI) dataset. iTrust Centre for Research in Cyber Security. https://itrust.sutd.edu.sg/itrust-labs-home/itrust-labs_wadi/

Jaddi NS, Abdullah S (2020) Global search in single-solution-based metaheuristics. Data Technol Appl 54(3):275–296

Jayasankar T, Kiruba Buri R, Maheswaravenkatesh P (2024) Intrusion detection system using metaheuristic fireworks optimization based feature selection with deep learning on internet of things environment. J Forecast 43(2):415–428

Jovanovic L, Bacanin N, Zivkovic M, Antonijevic M, Jovanovic B, Sretenovic MB, Strumberger I (2024) Machine learning tuning by diversity oriented firefly metaheuristics for industry 4.0. Expert Syst 41(2):13293

Kareem SS, Mostafa RR, Hashim FA, El-Bakry HM (2022) An effective feature selection model using hybrid metaheuristic algorithms for IoT intrusion detection. Sensors 22(4):1396

Karthikeyan M, Brindha R, Vianny MM, Vaitheeshwaran V, Bachute M, Mishra S, Dash BB (2025) Integration of metaheuristic based feature selection with ensemble representation learning models for privacy aware cyberattack detection in iot environments. Sci Rep 15(1):22887

Kasongo SM, Sun Y (2020) Performance analysis of intrusion detection systems using a feature selection method on the UNSW-NB15 dataset. J Big Data 7(1):105

Khafaga DS, Karim FK, Abdelhamid AA, El-kenawy E-SM, Alkahtani HK, Khodadadi N, Hadwan M, Ibrahim A (2023) Voting classifier and metaheuristic optimization for network intrusion detection. Comput Mater Contin 74(2)

Khan MZ, Reshi AA, Shafi S, Aljubayri I (2025) An adaptive hybrid framework for IIoT intrusion detection using neural networks and feature optimization using genetic algorithms. Discov Sustain 6(1):382

Khare O, Ahmed S, Singh Y (2023) An overview of swarm intelligence-based algorithms. In: Design and applications of nature inspired optimization: contribution of women leaders in the field, pp 1–18

Kocherla R, Molugu S, Nandalal V, Dhal PK, Saranya N, Basu Mallik B, Girimurugan R (2024) Deep learning based stacked recurrent neural networks for intrusion detection in industrial control systems using bio inspired meta heuristics. In: Proceedings of the fifth international conference on emerging trends in mathematical sciences & computing (IEMSC-24). Springer, pp 207–221

Koroniotis N, Moustafa N, Sitnikova E, Turnbull BP (2018) Towards the development of realistic botnet dataset in the internet of things for network forensic analytics: bot-IoT dataset. CoRR arXiv:1811.00701

Kumar P, Gupta GP, Tripathi R (2021) Toward design of an intelligent cyber attack detection system using hybrid feature reduced approach for IoT networks. Arab J Sci Eng 46(4):3749–3778

Lamport L (1986) LaTeX. https://www.latex-project.org

Li J, Othman MS, Hewan C, Yusuf LM (2025) IoT security: a systematic literature review of feature selection methods for machine learning-based attack classification. Int J Electron Secur Digit Forensics 17(1–2):60–107

Li X, Xie C, Zhao Z, Wang C, Yu H (2024) Anomaly detection algorithm of industrial internet of things data platform based on deep learning. IEEE Trans Green Commun Netw

Logeswari G, Roselind JD, Tamilarasi K, Nivethitha V (2025) A comprehensive approach to intrusion detection in IoT environments using hybrid feature selection and multi-stage classification techniques. IEEE Access

Lyu Y, Feng Y, Sakurai K (2023) A survey on feature selection techniques based on filtering methods for cyber attack detection. Information 14(3):191

Maazalahi M, Hosseini S (2025) Machine learning and metaheuristic optimization algorithms for feature selection and botnet attack detection. Knowl Inf Syst 67(4):3549–3597

Mahato S, Dutta S (2025) Ensemble based meta-heuristic optimized approach for network intrusion detection using LightGBM. Clust Comput 28(12):759

Maier HR, Razavi S, Kapelan Z, Matott LS, Kasprzyk J, Tolson BA (2019) Introductory overview: optimization using evolutionary algorithms and other metaheuristics. Environ Model Softw 114:195–213

Maldonado J, Riff MC, Neveu B (2022) A review of recent approaches on wrapper feature selection for intrusion detection. Expert Syst Appl 198:116822

Mallidi SKR, Ramisetty RR (2025a) Optimizing intrusion detection for IoT: a systematic review of machine learning and deep learning approaches with feature selection and data balancing. Wiley Interdiscip Rev Data Min Knowl Discov 15(2):70008

Mallidi SKR, Ramisetty RR (2025b) A multi-level intrusion detection system for industrial IoT using bowerbird courtship-inspired feature selection and hybrid data balancing. Discov Comput 28(1):109

Maseno EM, Wang Z (2024) Hybrid wrapper feature selection method based on genetic algorithm and extreme learning machine for intrusion detection. J Big Data 11(1):24

Mekala SH, Baig Z, Anwar A, Zeadally S (2023) Cybersecurity for industrial IoT (IIoT): threats, countermeasures, challenges and future directions. Comput Commun 208:294–320. https://doi.org/10.1016/j.comcom.2023.06.020

Miro (2023) Miro. https://miro.com

Mohammad Shtayat M, Kamrul Hasan M, Kumar Budhati A, Solaiman R, Islam S, Pandey B, Saleh Abbas H, Saeed MMA (2025) An improved binary spider wasp optimization algorithm for intrusion detection for industrial internet of things. IEEE Open J Commun Soc 6:2926–2944. https://doi.org/10.1109/OJCOMS.2024.3421647

Mohammed SH, Al-Jumaily A, Singh MSJ, Jiménez VPG, Jaber AS, Hussein YS, Al-Najjar MMAK, Al-Jumeily D (2024) A review on the evaluation of feature selection using machine learning for cyber-attack detection in smart grid. IEEE Access 12:44023–44042

Nazir A, Khan RA (2021) A novel combinatorial optimization based feature selection method for network intrusion detection. Comput Secur 102:102164

Nazir A, Memon Z, Sadiq T, Rahman H, Khan IU (2023) A novel feature-selection algorithm in IoT networks for intrusion detection. Sensors 23(19):8153

Ogunseyi TB, Thiyagarajan G (2025) An explainable LSTM-based intrusion detection system optimized by firefly algorithm for IoT networks. Sensors 25(7):2288

Panigrahi R (2025) CICIDS2017. IEEE Dataport. https://doi.org/10.21227/akxq-9v09

Prasad KS, Udayakumar P, Laxmi Lydia E, Ahmed MA, Ishak MK, Karim FK, Mostafa SM (2025) A two-tier optimization strategy for feature selection in robust adversarial attack mitigation on internet of things network security. Sci Rep 15(1):2235

Prasath MK, Perumal B (2019) A meta-heuristic Bayesian network classification for intrusion detection. Int J Netw Manag 29(3):2047

Quincozes SE, Passos D, Albuquerque C, Mossé D, Ochi LS (2022) An extended assessment of metaheuristics-based feature selection for intrusion detection in CPS perception layer. Ann Telecommun 77(7):457–471

Rai R, Das A, Ray S, Dhal KG (2022) Human-inspired optimization algorithms: theoretical foundations, algorithms, open-research issues and application for multi-level thresholding. Arch Comput Methods Eng 29(7):5313–5352

Sadeghian Z, Akbari E, Nematzadeh H, Motameni H (2025) A review of feature selection methods based on meta-heuristic algorithms. J Exp Theor Artif Intell 37(1):1–51

Sagu A, Gill NS, Gulia P, Singh PK, Hong W-C (2023) Design of metaheuristic optimization algorithms for deep learning model for secure IoT environment. Sustainability 15(3):2204

Saheed YK, Usman AA, Sukat FD, Abdulrahman M (2023) A novel hybrid autoencoder and modified particle swarm optimization feature selection for intrusion detection in the internet of things network. Front Comput Sci 5:997159

Samsuddin S, Othman MS, Yusuf LM (2018) A review of single and population-based metaheuristic algorithms solving multi depot vehicle routing problem. Int J Softw Eng Comput Syst 4(2):80–93

Sangaiah AK, Javadpour A, Ja'fari F, Pinto P, Zhang W, Balasubramanian S (2023) A hybrid heuristics artificial intelligence feature selection for intrusion detection classifiers in cloud of things. Clust Comput 26(1):599–612

Sanju P (2023) Enhancing intrusion detection in IoT systems: a hybrid metaheuristics-deep learning approach with ensemble of recurrent neural networks. J Eng Res 11(4):356–361

Seyyedabbasi A (2024) A comprehensive survey: physics-based algorithms. Decis Mak Models 59–75

Shanbhag A, Vincent S, Gowda SB, Kumar OP, Francis SAJ (2024) Leveraging metaheuristics for feature selection with machine learning classification for malicious packet detection in computer networks. IEEE Access 12:21745–21764

Sharma HS, Singh KJ (2025) A genetic algorithm based feature selection and CNN based ensemble model for intrusion detection in IoT smart environments: a GA based feature selection and CNN based ensemble model. J Sci Ind Res JSIR 84(1):48–59

Sharmila BS, Nagapadma R (2023) RT-IoT2022. UCI Machine Learning Repository. https://doi.org/10.24432/C5P338

Shukla AK, Dwivedi S, Mishra A (2025) An effective hybrid deep learning metaheuristic model for robust IoT intrusion detection. Discov Comput 28:200. https://doi.org/10.1007/s10791-025-09708-w

Soe YN, Feng Y, Santosa PI, Hartanto R, Sakurai K (2020) Towards a lightweight detection system for cyber attacks in the IoT environment using corresponding features. Electronics 9(1):144

Souri A, Norouzi M, Alsenani Y (2024) A new cloud-based cyber-attack detection architecture for hyper-automation process in industrial internet of things. Clust Comput 27(3):3639–3655

Taher F, Abdel-Salam M, Elhoseny M, El-Hasnony IM (2023) Reliable machine learning model for IIoT botnet detection. IEEE Access 11:49319–49336

Tang J, Liu G, Pan Q (2021) A review on representative swarm intelligence algorithms for solving optimization problems: applications and trends. IEEE/CAA J Autom Sin 8(10):1627–1643

Thamer Francis G, Souri A, İnanç N (2025) A hybrid firefly-based attribute selection and split-point mechanism for securing software-defined industrial internet of things. J High Speed Netw 09266801251338138

Ullah I, Mahmoud QH (2020) A scheme for generating a dataset for anomalous activity detection in IoT networks. In: Canadian conference on artificial intelligence. Springer, pp 508–520

Van Rossum G, Drake FL (2009) Python. https://www.python.org

Velasco L, Guerrero H, Hospitaler A (2024) A literature review and critical analysis of metaheuristics recently developed. Arch Comput Methods Eng 31(1):125–146

Zedadra O, Guerrieri A, Jouandeau N, Spezzano G, Seridi H, Fortino G (2018) Swarm intelligence-based algorithms within IoT-based systems: a review. J Parallel Distrib Comput 122:173–187

Zhao R (2022) NSL-KDD. IEEE Dataport. https://doi.org/10.21227/8rpg-qt98

Zolanvari M (2021) WUSTL-IIOT-2021. IEEE Dataport. https://doi.org/10.21227/yftq-n229

---

## Abbreviations

| Abbreviation | Full Form |
|--------------|-----------|
| AAFSSO | Asymmetrical Artificial Fish Swarm Optimization |
| ABC | Artificial Bee Colony |
| AE | Autoencoder |
| AFSA | Artificial Fish Swarm Algorithm |
| AI | Artificial Intelligence |
| ANN | Artificial Neural Network |
| AQUO | Aquila Optimizer |
| ASFOA | Adaptive Sunflower Optimization Algorithm |
| BA | Bat Algorithm |
| BBFS | Bowerbird Courtship Feature Selection |
| BGSA | Binary Gravitational Search Algorithm |
| BGWO | Binary Grey Wolf Optimization |
| BSA | Bird Swarm Algorithm |
| CASA | Channel and Spatial Attention |
| CAT-S | Cellular Automata Tabu Search |
| CNN | Convolutional Neural Network |
| CRNN | Cascaded Recurrent Neural Network |
| CSA | Crow Search Algorithm |
| CVS | Chaotic Vortex Search |
| DFFA | Diversity-Enhanced Firefly Algorithm |
| DHOA | Deer Hunting Optimization Algorithm |
| DL | Deep Learning |
| DNN | Deep Neural Network |
| DRNN | Deep Recurrent Neural Network |
| DTO | Dipper-Throated Optimizer |
| EA | Evolutionary Algorithms |
| EFPADD | Elderly Fall Prediction and Detection |
| EHO | Elephant Herding Algorithm |
| ETM | Embedded Transformer Monitoring |
| FFA | Firefly Algorithm |
| FLN | Fast Learning Network |
| FR-CNN | Fast Recurrent Convolutional Neural Network |
| FS | Feature Selection |
| FS-ID | Feature Selection—Intrusion Detection |
| FWA | Fireworks Algorithm |
| GA | Genetic Algorithm |
| GNB | Gaussian Naive Bayes |
| GOA | Grasshopper Optimization Algorithm |
| GSA | Gravitational Search Algorithm |
| GTO | Gorilla Troops Algorithm |
| GWO | Gray Wolf Optimizer |
| HADE-DRNN | Heuristic Adaptive Differential Evolution-Deep Recurrent Neural Network |
| HAEMPSO | Hybrid Autoencoder and Modified Particle Swarm Optimization |
| HBI | Human Behavior Inspired |
| HGS | Hunger Games Search |
| HHO | Harris Hawk Optimizer |
| IBPSO | Improved Binary Particle Swarm Optimization |
| ID | Intrusion Detection |
| IDS | Intrusion Detection System |
| IIoT | Industrial Internet of Things |
| IoT | Internet of Things |
| KNN | K-Nearest Neighbors |
| LR | Logistic Regression |
| MFS | Metaheuristic Feature Selection |
| MFS-DL | Metaheuristic Feature Selection-Deep Learning |
| MIA | Mathematically Inspired Algorithm |
| ML | Machine Learning |
| PHY | Physics Based |
| PSO | Particle Swarm Optimization |
| RF | Random Forest |
| SA | Self Attention |
| SFO | Sailfish Optimization |
| SFOA | Sunflower Optimization Algorithm |
| SI | Swarm Intelligence |
| SMOTE | Synthetic Minority Oversampling Technique |
| SOA | Seagull Optimization Algorithm |
| SSA | Salp Swarm Algorithm |
| SSO | Sparrow Search Optimization |
| SVM | Support Vector Machine |
| SWO | Spider Wasp Optimization |
| TS | Tabu Search |
| TSO | Tuna Swarm Optimization |
| VP | Voting Perceptron |
| WOA | Whale Optimization Algorithm |
| XGBoost | Extreme Gradient Boosting |

---

*Paper converted to Markdown for AI-assisted reading. Based on the original publication in Artificial Intelligence Review (2026) 59:73.*