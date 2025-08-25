
Abstract---The decentralized and pseudonymous nature of

blockchain technology, while innovative, has created significant

loopholes for illicit financial activities, including money laun-

dering and fraud. Concurrently, the rise of quantum computing

presents a dual challenge: it threatens to break the cryptographic

foundations of current blockchain systems while also offering

powerful new tools for data analysis. This paper addresses the

detection of illicit cryptocurrency transactions by proposing a

forward-looking, conceptual framework that leverages Quantum

Machine Learning (QML). We begin by outlining the modern

crypto-fraud landscape and comparing it to fraudulent activities

in traditional financial systems. We then review the capabilities

and inherent limitations of classical detection methods, such as

graphical analysis and machine learning, which struggle with

the complexity, high dimensionality, and severe class imbalance

of illicit transaction data. Our proposed solution is a multi-

stage, hybrid quantum-classical framework that utilizes quantum

algorithms for feature selection and classification to identify

complex patterns currently intractable for classical systems.

While acknowledging the significant hardware and data-loading

challenges of the current NISQ (Noisy Intermediate-Scale Quan-

tum) era, this research provides a crucial roadmap for future

development. It envisions a system where the same quantum

principles that threaten blockchain's security can be harnessed

to become its most powerful defense.

Index Terms---Quantum Machine Learning, Blockchain, Cryp-

tocurrency, Fraud Detection, Anomaly Detection

I. INTRODUCTION

Blockchain is widely recognized as one of the most transfor-

mative technologies in digital finance due to its decentralized

and tamper-resistant architecture [1], [2]. It eliminates the

reliance on centralized intermediaries and enables peer-to-

peer transactions on a global scale. Despite these advantages,

blockchain's pseudonymity and lack of centralized oversight

create opportunities for abuse, particularly in the areas of

money laundering, fraud, and terrorist financing [3], [4]. Law

enforcement agencies face significant challenges in moni-

toring cross-border illicit activities, especially with privacy-

focused coins and decentralized finance (DeFi) ecosystems

[8], [9]. Simultaneously, quantum computing introduces ex-

istential concerns for blockchain security. Algorithms such as

Shor's and Grover's have been proven capable of breaking

widely deployed cryptographic systems [5], [6], raising the

risk of adversaries harvesting blockchain public keys today

for decryption in the future [10]. However, this same technol-

ogy can also empower Quantum Machine Learning (QML)

models to detect financial anomalies with superior accuracy,

leveraging quantum properties such as entanglement and su-

perposition [7], [11]. This paper addresses this paradoxical

relationship between blockchain and quantum computing by

introducing a hybrid QML framework for fraud detection.

Unlike classical approaches, which struggle with imbalanced

and high-dimensional datasets [26], QML offers advanced

computational capabilities to discover hidden correlations. By

rethinking quantum computing as both a threat and a tool, we

provide a roadmap toward a resilient financial ecosystem that

integrates post-quantum cryptography with quantum-enhanced

fraud detection [12]--[14].

A. Motivation

1) Blockchain Vulnerabilities: The inherent pseudonymity

of blockchain transactions creates an environment where illicit

actors can mask their identities and transaction trails [8],

[9]. Weaknesses in global regulatory frameworks---such as

inconsistent Anti-Money Laundering (AML) and Know Your

Customer (KYC) enforcement---enable exploitation through

unregulated exchanges [10]. DeFi platforms, which bypass

traditional banking structures, allow criminals to execute

anonymous lending, token swaps, and derivatives trading [15].

Moreover, techniques such as chain hopping and privacy coin

usage are increasingly adopted to make detection more difficult

[16]. Together, these vulnerabilities highlight the urgency for

advanced detection systems beyond conventional oversight

[17].

2) Quantum Threat to Cryptography: Quantum algorithms

represent a fundamental risk to blockchain's security infras-

tructure. Shor's algorithm threatens RSA and elliptic curve

cryptography, while Grover's algorithm accelerates brute-force

attacks against hash functions [5], [11]. Research indicates

that cryptocurrencies like Bitcoin and Ethereum, especially

when associated with addresses that reuse or expose public

keys, are particularly vulnerable [12]. Some estimates sug-

gest that within the next decade, scalable quantum systems

could feasibly compromise existing blockchain wallets [18].

This looming threat underscores the importance of simultane-

ously developing post-quantum cryptography (PQC) solutions

and quantum-enhanced fraud detection systems, transforming

blockchain's relationship with quantum technology from ad-

versarial to defensive [19], [20].

II. THE CRYPTO-FRAUD LANDSCAPE

A. Laundering Techniques in Cryptocurrencies

Money laundering within blockchain ecosystems has grown

increasingly sophisticated. Mixers and tumblers anonymize

funds by pooling transactions and redistributing them, making

it difficult to trace origins [13]. Privacy coins such as Monero

and Zcash employ cryptographic features like ring signatures

and zero-knowledge proofs to obscure both sender and receiver

information [14]. Chain hopping, or moving funds across mul-

tiple blockchains, further complicates detection by fragment-

ing audit trails [15]. Emerging laundering strategies include

NFT wash trading, where illicit funds are disguised as legit-

imate digital art transactions, and DeFi protocol exploitation,

which leverages flash loans and decentralized liquidity pools

[16]. These techniques illustrate how blockchain's strengths

can also become its most exploitable weaknesses [17].

B. Illicit Integration Methods

Once laundered, illicit funds are funneled back into the

economy through several channels. Darknet marketplaces,

operating through cryptocurrencies, remain hotspots for illegal

trade in drugs, weapons, and data [18]. Fraudulent Initial Coin

Offerings (ICOs) and shell corporations have also emerged

as preferred laundering tools, enabling criminals to project

legitimacy while disguising illicit activity [19]. Traditional

sectors, such as real estate and luxury assets, are increasingly

purchased with crypto proceeds due to their relative stability

and convertibility to fiat [20]. Compared to classical laundering

methods, blockchain's speed and borderless nature amplify

both scale and efficiency, posing new challenges for global

regulators [21].

III. COMPARATIVE PERSPECTIVE: TRADITIONAL

FINANCIAL FRAUD

A. Credit Card Fraud

Credit card fraud is one of the most common financial

crimes, often detected using anomaly-based monitoring sys-

tems [19]. Transactions are evaluated in real time against

established behavioral patterns, and deviations trigger alerts

[22]. Centralized oversight enables rapid intervention, block-

ing fraudulent transactions before further damage occurs.

However, unlike blockchain, centralized authorities provide a

structured reporting system that enhances accountability [23].

B. Wire Transfer Fraud

Wire transfer fraud involves the illicit movement of funds

through international banking networks. Transaction Moni-

toring Systems (TMS) are employed to identify suspicious

activities, often supported by AI-driven risk models [24].

Fraudsters exploit mule accounts, forged documentation, and

regulatory loopholes to bypass oversight [25]. The centralized

structure of wire transfers allows regulatory bodies to flag

irregularities more efficiently than in decentralized systems

[26].

C. Cash-Based Fraud

Cash-based laundering schemes, such as structuring de-

posits below reporting thresholds, remain widespread in the

traditional financial ecosystem [21]. Cash-intensive businesses,

including casinos and retail outlets, are often exploited to

disguise illicit proceeds [27]. While effective reporting and

centralized oversight help counter such schemes, blockchain's

pseudonymous design eliminates these intermediaries, creating

a detection gap [28]. Comparison: While traditional financial

systems rely heavily on centralized oversight mechanisms

to combat fraud, blockchain's decentralized model reduces

accountability, increasing the difficulty of fraud detection and

regulatory enforcement [22], [29].

IV. CLASSICAL DETECTION APPROACHES

A. Graph-Based Methods

Blockchain transactions can be naturally represented as

graphs, with nodes representing addresses and edges repre-

senting transactions. Graph Convolutional Networks (GCNs)

have been widely used to capture relational structures in such

transaction graphs [23]. In the Elliptic dataset, for exam-

ple, GCNs have revealed patterns associated with fraudulent

clusters, including coordinated laundering operations [29].

These models excel in detecting community-based fraud but

are challenged by the dynamic and high-dimensional nature

of transaction networks [24]. Furthermore, explainability in

graph models remains limited, complicating their adoption in

compliance-driven industries [27].

B. Anomaly Detection Models

Anomaly detection leverages unsupervised and semi-

supervised methods to identify behaviors deviating from nor-

mal patterns. Algorithms like Isolation Forest, One-Class

SVM, and autoencoders have shown promise in flagging

unusual blockchain activity [24]. They are particularly effec-

tive in handling unlabeled datasets, which are common in

fraud detection scenarios where malicious activity is underre-

ported. However, their performance is often hindered by false

positives, especially in legitimate high-frequency trading or

arbitrage scenarios [26]. Integrating anomaly detection with

graph analysis improves precision but increases computational

demands [25].

C. Supervised Learning

Supervised learning models such as Random Forests, Gra-

dient Boosted Trees, and Neural Networks have achieved

competitive results when labeled data is available [25]. They

can learn from historical cases of fraud to detect similar future

transactions. For example, ensemble approaches combining

multiple classifiers have outperformed single models in terms

of accuracy and recall [28]. Nevertheless, they remain sen-

sitive to data imbalance, as fraudulent transactions typically

constitute less than 2% of total data [26]. This imbalance

skews predictions toward legitimate transactions, reducing the

effectiveness of fraud detection systems [27].

D. Limitations

While classical detection systems have evolved signifi-

cantly, they face three critical limitations. First, the severe

class imbalance in blockchain datasets often biases models

toward false negatives [26]. Second, the high dimensionality

of transaction data, especially in dynamic networks like DeFi,

creates scalability issues [27]. Third, interpretability remains

limited, especially in deep learning models, reducing their

applicability in regulated environments where explainability is

legally required [28]. Collectively, these challenges highlight

the need for quantum-enhanced approaches that can process

high-dimensional data more effectively and improve fraud

detection accuracy [29].

V. QUANTUM APPROACHES IN FRAUD DETECTION

A. Quantum Support Vector Machines (QSVMs)

QSVMs embed classical data into high-dimensional quan-

tum Hilbert spaces, enabling superior separation of over-

lapping classes compared to classical SVMs [10]. In fraud

detection, QSVMs have demonstrated improved performance

in scenarios where class imbalance is severe [29]. Their ability

to model complex non-linear decision boundaries makes them

ideal for identifying subtle laundering behaviors. Additionally,

QSVMs scale better than classical methods when data is repre-

sented in kernelized forms, offering computational advantages

in fraud detection tasks [31].

B. Quantum Neural Networks (QNNs)

Quantum Neural Networks (QNNs) leverage quantum gates

to encode data and perform classification. Continuous-variable

QNNs (CVQNNs) in particular are effective at handling

highly imbalanced data, which is common in blockchain fraud

datasets [7]. Unlike classical deep learning models, QNNs

exploit entanglement to capture complex correlations that span

across transaction graphs. Studies have shown that hybrid

CVQNN architectures can outperform both traditional neural

networks and QSVMs on fraud-related tasks [25]. However,

practical deployment is limited by hardware constraints in

today's Noisy Intermediate-Scale Quantum (NISQ) devices

[30].

C. Quantum Annealing

Quantum annealers, such as those developed by D-Wave,

specialize in solving combinatorial optimization problems.

Fraud detection can be formulated as an optimization prob-

lem, where the goal is to minimize misclassification while

accounting for complex network features [30]. For example,

support vector machine formulations can be translated into

Quadratic Unconstrained Binary Optimization (QUBO) prob-

lems solvable by quantum annealing [9]. This approach has

shown promise in achieving faster convergence than classical

optimization, particularly when dealing with large transaction

networks [31].

D. Unsupervised Quantum Methods

Beyond supervised models, unsupervised quantum algo-

rithms provide new avenues for detecting fraudulent activity.

Quantum Generative Adversarial Networks (QGANs) and

quantum autoencoders have been explored for anomaly de-

tection in unlabeled transaction datasets [25]. These models

learn compact quantum representations of legitimate activity,

enabling them to highlight irregularities in financial flows [31].

Semi-supervised quantum methods further enhance detection

by leveraging limited labeled data while exploiting large vol-

umes of unlabeled blockchain transactions [32]. This flexibility

makes unsupervised quantum approaches especially valuable

in crypto ecosystems where fraud labels are scarce.

E. Software Frameworks

The growth of quantum programming libraries has acceler-

ated experimentation in fraud detection research. Frameworks

like IBM's Qiskit [31] and Xanadu's PennyLane [32] provide

user-friendly interfaces for building and testing QML mod-

els. Qiskit supports hybrid workflows where classical pre-

processing is combined with quantum classification, while

PennyLane facilitates integration with popular deep learning

libraries such as TensorFlow and PyTorch. These tools reduce

the barrier to entry for researchers and practitioners, making it

possible to explore QML applications for fraud detection even

in the current NISQ era [32].

VI. HYBRID QUANTUM--CLASSICAL FRAUD DETECTION

FRAMEWORK

A. Stage 1: Classical Preprocessing

The first stage of the hybrid framework relies on classi-

cal methods for data cleaning, feature extraction, and graph

representation. Datasets like Elliptic contain millions of trans-

actions, requiring careful normalization and filtering to reduce

noise [23]. Classical graph analysis helps identify clusters,

degree centrality, and transaction frequency patterns, which

are essential for constructing features for downstream quantum

processing [29]. This stage ensures that the data fed into

quantum systems is both compact and informative [24].

B. Stage 2: Quantum Feature Selection

In the second stage, quantum kernels and embedding strate-

gies are applied to reduce dimensionality while preserving

critical correlations [13]. Quantum feature maps exploit en-

tanglement to capture subtle dependencies across multiple

transactions, which are often lost in classical dimensionality

reduction techniques [25]. By filtering irrelevant variables and

emphasizing high-risk correlations, quantum-enhanced feature

selection improves detection accuracy while reducing compu-

tational overhead [31]. This step acts as a bridge between raw

blockchain data and quantum classifiers.

C. Stage 3: Quantum Classification

The third stage involves applying quantum classifiers such

as QSVMs and CVQNNs to the preprocessed feature space

[7], [29]. These classifiers can distinguish legitimate from

fraudulent activity by exploiting high-dimensional quantum

kernels. Studies demonstrate that QSVMs achieve higher recall

rates in imbalanced fraud detection datasets compared to

classical SVMs [31]. By leveraging quantum entanglement,

CVQNNs further enhance classification accuracy and reduce

false negatives [25]. This stage provides the core decision-

making capability of the hybrid framework.

D. Stage 4: Hybrid Ensemble

Finally, predictions from quantum models are combined

with classical classifiers using ensemble learning techniques

[28]. The ensemble metaclassifier aggregates insights from

both paradigms, mitigating weaknesses such as quantum noise

and classical bias. For instance, Random Forests can be paired

with QSVM outputs to balance precision and recall [26].

This hybrid approach ensures robustness, interpretability, and

regulatory compliance while outperforming purely classical or

quantum systems [27].

VII. CHALLENGES AND FUTURE SCOPE

A. Hardware Constraints

Quantum hardware remains in the NISQ era, where de-

coherence, gate errors, and limited qubit counts restrict the

scalability of QML models [6]. Fraud detection tasks involving

millions of blockchain transactions often exceed the current

computational capacity of quantum devices [30]. Noise mitiga-

tion and error correction remain active research areas that must

advance significantly for real-world deployment [31]. Until

then, hybrid approaches are the most practical path forward.

B. Data Bottleneck

Loading large-scale blockchain data into quantum states

efficiently is another major bottleneck [16]. Current quantum

feature encoding methods are computationally expensive, re-

ducing the feasibility of real-time fraud detection [24]. Novel

quantum data loading schemes, such as amplitude encoding

and tensor networks, are being developed to address this issue

[25]. However, scalable quantum data pipelines are still in their

infancy, limiting the practical adoption of QML in production

systems [27].

C. Benchmarking Needs

A significant challenge in QML-based fraud detection is

the lack of standardized benchmarking. Comparisons be-

tween quantum and classical models often rely on small-scale

datasets or simulations [18]. Without consistent evaluation

frameworks, it is difficult to quantify the true advantage of

quantum approaches [26]. The development of open-source

benchmarks, shared datasets, and reproducible protocols is

essential for advancing research in this domain [19].

D. Post-Quantum Cryptography (PQC)

While QML provides tools for fraud detection, blockchain

security also requires upgrading to quantum-resistant cryp-

tography [11]. Algorithms such as CRYSTALS-Dilithium and

Kyber, standardized by NIST, are promising candidates for

PQC [12]. Integration of PQC with fraud detection ensures

not only improved monitoring but also protection against

quantum adversaries targeting cryptographic weaknesses [20].

Combining PQC with QML creates a holistic defense strategy

against both fraud and quantum attacks [21].

VIII. CONCLUSION

The rise of illicit transactions in cryptocurrency, enabled by

the pseudo-anonymous and decentralized nature of blockchain,

presents a formidable and evolving challenge to global finan-

cial security. While classical machine learning methods have

made significant progress in fraud detection, comprehensive

surveys show they are increasingly reaching their limits when

confronted with the complexity, scale, and adaptive nature of

modern financial crime. This research has outlined a concep-

tual framework for leveraging Quantum Machine Learning as

a next-generation tool for anomaly detection in this domain.

By proposing a hybrid architecture that combines classical

data processing with quantum feature selection and classifica-

tion, we envision a system capable of uncovering the subtle,

high-dimensional patterns of fraud that are currently unde-

tectable. Although significant technological hurdles related to

quantum hardware and data handling remain, this exploration

provides a crucial roadmap for future research. It reframes the

conversation around quantum computing from being solely a

threat to a potential solution, envisioning a future where the

same quantum principles that challenge blockchain's security

can be harnessed to become its most powerful and intelligent

defense.

ACKNOWLEDGMENT

The authors thank Mr. Allabaksh Shaik, Faculty Guide,

Department of ECE, Sri Venkateswara College of Engineering,

for guidance and support.

REFERENCES

[1] P. Thanalakshmi, A. Rishikhesh, J. M. Marceline, G. P. Joshi, and

W. Cho, "A Quantum-Resistant Blockchain System: A Comparative

Analysis," Mathematics, vol. 11, no. 3947, pp. 1--19, Sep. 2023. doi:

10.3390/math11183947.

[2] N. Fariha, M. N. M. Khan, M. I. Hossain, S. A. Reza, J. C. Bortty,

K. S. Sultana, M. S. I. Jawad, S. Safat, M. A. Ahad, and M. Begum,

"Advanced fraud detection using machine learning models: enhanc-

ing financial transaction security," International Journal of Account-

ing and Economics Studies, vol. 12, no. 2, pp. 85--104, 2025, doi:

10.14419/c73kcb17.

[3] M. B. Maneela, M. S. SaiHarsha, S. R. Saia, C. Viveka, M. Kavithaa,

D. Devarapalli, and D. Mythrayee, "Anomaly Detection in Transactions

Using Machine Learning," Edu-Tech Enterprise, vol. 3, p. 21, Jan. 2025.

doi: 10.71459/edutech202521.

[4] B. Dumitrescu, A. B˘alt,oiu, and S, . Budulan, "Anomaly detection in

graphs of bank transactions for anti money laundering applications,"

IEEE Access, vol. 10, pp. 47699--47712, 2022. doi: 10.1109/AC-

CESS.2022.3170467.

[5] P. Meena, "Artificial Intelligence: The Next Frontier for Assets Man-

agement," International Journal for Research in Applied Science &

Engineering Technology (IJRASET), vol. 12, no. 3, pp. 560--567, Mar.

2024\. doi: 10.22214/ijraset.2024.58875.

[6] Z. Yang, H. Alfauri, B. Farkiani, R. Jain, R. Di Pietro, and A. Erbad,

"A survey and comparison of post-quantum and quantum blockchains,"

IEEE Access, vol. 11, pp. 58321--58345, 2023. doi: 10.1109/AC-

CESS.2023.XXXXXXX.

[7] N. Killoran, T. R. Bromley, J. M. Arrazola, M. Schuld, N. Quesada,and S. Lloyd, "Continuous-variable quantum neural networks," Physical

Review Research, vol. 1, no. 3, p. 033063, 2019. doi: 10.1103/Phys-

RevResearch.1.033063.

[8] B. Narsimha, Ch. V. Raghavendran, P. Rajyalakshmi, G. K. Reddy, M.

Bhargavi, and P. Naresh, "Cyber Defense in the Age of Artificial Intelli-

gence and Machine Learning for Financial Fraud Detection Application,"

International Journal of Electrical and Electronics Research (IJEER),

vol. 10, no. 2, pp. 87--92, May 2022. doi: 10.37391/IJEER.100206.

[9] H. Wang, W. Wang, Y. Liu, and B. Alidaee, "Integrating Machine

Learning Algorithms With Quantum Annealing Solvers for Online Fraud

Detection," IEEE Access, vol. 10, pp. 75908--75921, Jul. 2022. doi:

10.1109/ACCESS.2022.3190897.

[10] A. Hussain, M. A. Khan, A. Iqbal, and I. Siddiqi, "Mixed Quantum-

Classical Method for Fraud Detection With Quantum Feature Selection,"

IEEE Access, vol. 11, pp. 70371--70381, Jun. 2023. doi: 10.1109/AC-

CESS.2023.3294102.

[11] P. Vanini, S. Rossi, E. Zvizdic, and T. Domenig, "Online payment fraud:

from anomaly detection to risk management," Financial Innovation, vol.

9, no. 66, 2023. doi: 10.1186/s40854-023-00470-w.

[12] A. Ganapathy, "Quantum computing in high frequency trading and fraud

detection," Engineering International, vol. 9, no. 2, pp. 61--72, 2021.

[13] Y. Lu and J. Yang, "Quantum financing system: A survey on quan-

tum algorithms, potential scenarios and open research issues," Journal

of Industrial Information Integration, vol. 41, p. 100663, 2024. doi:

10.1016/j.jii.2024.100663.

[14] M. Xu, X. Ren, D. Niyato, J. Kang, C. Qiu, Z. Xiong, X. Wang, and V. C.

M. Leung, "When quantum information technologies meet blockchain in

Web 3.0," IEEE Transactions on Emerging Topics in Computing, early

access, 2023.

[15] J. D. Mart'ın-Guerrero and L. Lamata, "Quantum Machine Learn-

ing: A Tutorial," Neurocomputing, vol. 470, pp. 457--461, 2022. doi:

10.1016/j.neucom.2021.02.102.

[16] S. Corli, L. Moro, D. Dragoni, M. Dispenza, and E. Prati, "Quan-

tum machine learning algorithms for anomaly detection: A review,"

Future Generation Computer Systems, vol. 166, p. 107632, 2025. doi:

10.1016/j.future.2024.107632.

[17] S. L. Phung and A. Bouzerdoum, "Quantum machine learning in finance:

Time series forecasting," Journal of Quantum Computing, vol. 4, no. 2,

pp. 115--130, Jun. 2022. doi: 10.1142/S2661339522500087.

[18] S. Sadeghi, V. Chouhan, M. Aldarwbi, A. Ghorbani, A. Chow, and R.

Burko, "Securing financial sector applications in the quantum era: a

comprehensive evaluation of NIST's recommended algorithms through

use-case analysis," Expert Systems With Applications, vol. 288, p.

128243, 2025. doi: 10.1016/j.eswa.2025.128243.

[19] S. Ounacer, H. A. E. Bour, Y. Oubrahim, M. Y. Ghoumari, and

M. Azzouazi, "Using Isolation Forest in anomaly detection: the case

of credit card transactions," Periodicals of Engineering and Natural

Sciences, vol. 6, no. 2, pp. 394--400, Dec. 2018.

[20] A. Abdallah, M. Maarof, and A. Zainal, "Fraud detection system: A

survey," Journal of Network and Computer Applications, vol. 68, pp.

90--113, 2016.

[21] C. Phua, V. Lee, K. Smith, and R. Gayler, "A comprehensive sur-

vey of data mining-based fraud detection research," arXiv preprint

arXiv:1009.6119, 2010.

[22] X. Li, Y. Ma, and L. Sun, "A survey of blockchain-based anomaly

detection," Future Generation Computer Systems, vol. 115, pp. 443--

456, 2021.

[23] E. Weber, A. Domeniconi, and C. Chen, "Anti-Money Laundering in

Bitcoin: Experiments with Graph Convolutional Networks," in Proc.

KDD, 2019, pp. 3564--3572.

[24] M. Schuld and N. Killoran, "Quantum Machine Learning in Finance,"

Frontiers in Artificial Intelligence, 2019.

[25] O. Kyriienko and M. Magnusson, "Unsupervised Quantum Machine

Learning for Fraud Detection," arXiv preprint arXiv:2208.01203, 2022.

[26] D. Tscharke et al., "Semi-supervised Anomaly Detection Using QSVR

with Quantum Kernels," arXiv preprint arXiv:2308.00583, 2023.

[27] J. Cultice et al., "Quantum Hybrid SVMs for Cyber-Physical Security,"

arXiv preprint arXiv:2409.04935, 2024.

[28] S. Lloyd, M. Mohseni, and P. Rebentrost, "Quantum algorithms

for supervised and unsupervised machine learning," arXiv preprint

arXiv:1307.0411, 2013.

[29] Elliptic Ltd., "Elliptic Data Set," 2019. [Online]. Available: https://www.kaggle.com/ellipticco/elliptic-data-set
[30] Mendeley Data, "Cryptocurrency Scam Dataset," 2021.

doi:10.17632/ffd5crf8mx.

[31] IBM Quantum, "Qiskit Textbook: Quantum Machine Learning," 2023.

[Online]. Available: https://qiskit.org/textbook

[32] Xanadu, "PennyLane Quantum Machine Learning Demos," 2023. [On-

line]. Available: https://pennylane.ai/qml

