# Awesome Temporal Action Segmentation

![Temporal Action Segmentation](./TAS.png)
A curated list of awesome temporal action segmentation resources. Inspired by [awesome-machine-learning-resources](https://github.com/ZhiningLiu1998/awesome-machine-learning-resources).
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

⭐ **Please leave a <font color='orange'>STAR</font> if you like this project!** ⭐

:fire: Huggingface Datasets for three common TAS benchmarks are now available and check them out here:

- 🤗 [gtea](https://huggingface.co/datasets/dinggd/gtea) 🤗
- 🤗 [50salads](https://huggingface.co/datasets/dinggd/50salads) 🤗
- 🤗 [breakfast](https://huggingface.co/datasets/dinggd/breakfast) 🤗

Do let us know if there is any IP issues regarding hosting these datasets on huggingface!

## Table of Contents

- [The Task](#the-task)
- [Datasets](#Datasets)
  - [Breakfast Actions](#breakfast)
  - [GTEA](#GTEA)
  - [50Salads](#50salads)
  - [YouTube Instructional](#youtube-instructional)
  - [Assembly101](#assembly101)
- [Evaluation](#evaluation-measures)
  - [Acc](#acc)
  - [F1](#f1-score)
  - [Edit](#edit-score)
- [Paper List](#paper-list)
  - [Fully-Supervised](#fully-supervised)
  - [Weakly-Supervised](#weakly-supervised)
  - [Unsupervsied](#unsupervised)
  - [Semi-Supervised](#semi-supervised)
  - [Online](#online)
  - [Continual](#continual)

## The Task

Temporal Action Segmentation takes as the input an untrimmed video sequence, segments it along the temporal dimension into clips and infers the semantics of actions in them.

![Task](./task.png)

## Surveys \& Overviews

- ATLAS tutorial in conjuction with ECCV2022. [[Tutorial]](https://nus-cvml.github.io/atlas-eccv22)
- Temporal Action Segmentation: An Analysis of Modern Techniques
  [[pdf]](https://arxiv.org/pdf/2210.10352.pdf)
  - Guodong Ding, Fadime Sener, and Angela Yao, _TPAMI 2023_.

## Datasets

There are multiple datasets that have been used to benchmark the perfomance of the temporal action segmentation approaches. The most commonly adopted datasets are the as follows:

### Breakfast

- The Language of Actions: Recovering the Syntax and Semantics of Goal-Directed Human Activities
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2014/papers/Kuehne_The_Language_of_2014_CVPR_paper.pdf)
  - Hilde Kuehne, Ali Arslan, and Thomas Serre, _CVPR 2014_.
  <details close>
    <summary>Read Abstract</summary>
    This paper describes a framework for modeling human activities as temporally structured processes. Our approach is motivated by the inherently hierarchical nature of human activities and the close correspondence between human actions and speech: We model action units using Hidden Markov Models, much like words in speech. These action units then form the building blocks to model complex human activities as sentences using an action grammar. To evaluate our approach, we collected a large dataset of daily cooking activities: The dataset includes a total of 52 participants, each performing a total of 10 cooking activities in multiple real-life kitchens, resulting in over 77 hours of video footage. We evaluate the HTK toolkit, a state-of-the-art speech recognition engine, in combination with multiple video feature descriptors, for both the recognition of cooking activities (e.g., making pancakes) as well as the semantic parsing of videos into action units (e.g., cracking eggs). Our results demonstrate the benefits of structured temporal generative approaches over existing discrimina-tive approaches in coping with the complexity of human daily life activities.
  </details>

targets recording videos ''in the wild'', in 18 different kitchens. The participants are not given any scrips and the recordings are unrehearsed and undirected. The dataset is composed of the 10 breakfast-related activities. This dataset is recorded with 52 participants with multiple cameras, varies from 3 to 5, all from a third-person point of view. There are 1712 videos, when accounting for the multi-camera views.

### GTEA

- Learning to Recognize Objects in Egocentric Activities
  [[pdf]](https://arxiv.org/pdf/2102.08065.pdf)
  - Alireza Fatih, Xiaofeng Ren, and M James Rehg, _CVPR 2011_.
  <details close>
    <summary>Read Abstract</summary>
    This paper addresses the problem of learning object models from egocentric video of household activities, us- ing extremely weak supervision. For each activity sequence, we know only the names of the objects which are present within it, and have no other knowledge regarding the ap- pearance or location of objects. The key to our approach is a robust, unsupervised bottom up segmentation method, which exploits the structure ofthe egocentric domain to par- tition each frame into hand, object, and background cat- egories. By using Multiple Instance Learning to match object instances across sequences, we discover and lo- calize object occurrences. Object representations are re- fined through transduction and object-level classifiers are trained. We demonstrate encouraging results in detecting novel object instances using models produced by weakly- supervised learning.
  </details>

contains 28 videos recorded in a single kitchen from seven procedural activities. The videos are recorded with a camera mounted on a cap, worn by four participants.

### 50Salads

- Combining Embedded Accelerometers with Computer Vision for Recognizing Food Preparation Activities
  [[pdf]](https://doi.org/10.1145/2493432.2493482)
  - Sebastian Stein, and Stephen J Mckenna, _UbiComp 2013_.

is composed of 50 recorded videos of 25 participants making two different mixed salads. The videos are captured by a camera with a top-down view onto the work-surface. The participants are provided with recipe steps which are randomly sampled from a statistical recipe model.

### YouTube Instructional

- Unsupervised Learning from Narrated Instruction Videos
  [[pdf]](https://doi.org/10.1109/CVPR.2016.495)
  - Jean-Baptiste Alayrac, Piotr Bojanowski, Nishant Agrawal, Josef Sivic, Ivan Laptev, and Simon Lacoste-Julien, _CVPR 2016_.

is a recently collected dataset where 53 participants were asked to dissemble and assemble take apart toys without given any instructions which resulted in realistic sequences with great variation in action ordering. The dataset is annotated with fine-grained, hand-object interactions, and coarse action labels which are composed of multiple fine-grained action segments related to the attaching or detaching of a vehicle part. The authors evaluated their dataset for temporal action segmentation using the coarse labels.

### Assembly101

- Assembly101: A Large-Scale Multi-View Video Dataset for Understanding Procedural Activities
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Sener_Assembly101_A_Large-Scale_Multi-View_Video_Dataset_for_Understanding_Procedural_Activities_CVPR_2022_paper.pdf)
  - Fadime Sener, Dibyadip Chatterjee, Daniel Shelepov, Kun He, Dipika Singhania, Robert Wang, and others, _CVPR 2022_.

is a recently collected dataset where 53 participants were asked to dissemble and assemble take apart toys without given any instructions which resulted in realistic sequences with great variation in action ordering. The dataset is annotated with fine-grained, hand-object interactions, and coarse action labels which are composed of multiple fine-grained action segments related to the attaching or detaching of a vehicle part. The authors evaluated their dataset for temporal action segmentation using the coarse labels.

## Evaluation Measures

### Acc

Accuracy or MoF (mean over frames) are an per-frame accuracy measure that calculates the ratio of frames that are correctly recognized by the temporal action model:

$\text{Acc}=\frac{\text{number of correct frames}}{\text{number of all frames}}$

### F1 score

The F1-score, or F1@$\tau$ compares the Intersection over Union (IoU) of each segment with respect to the corre- sponding ground truth based on some threshold $\tau/100$. $\tau$ are set to $\{10,25,50\}$. A segment is considered a true positive if its score with respect to the ground truth exceeds the threshold. If there is more than one correct segment within the span of a single ground truth action, then only one is marked as a true positive and the others are marked as false positives.

$\text{F1} = 2 \cdot \frac{\text{precision}\times \text{recall}}{\text{precision} +\text{recall}}$.

### Edit score

The Edit Score is computed using the Levenshtein distance $e$, which quantifies how similar two sequences are to each other by counting the minimum number of operations required to convert one (segment) string into another.

$\text{Edit} = \left(1-\frac{e(X,Y)}{\text{max}(|X|,|Y|)} \right)\cdot 100$

## Paper List

### Fully-Supervised

#### 2024

- FACT: Frame-Action Cross-Attention Temporal Modeling for Efficient Fully-Supervised Action Segmentation,
  [[code]](https://github.com/ZijiaLewisLu/CVPR2024-FACT)
  - Zijia Lu and Ehsan Elhamifar, _CVPR 2024_.

#### 2023

- Activity Grammars for Temporal Action Segmentation,
  [[pdf]](https://openreview.net/pdf?id=oOXZ5JEjPb)
  [[code]](http://cvlab.postech.ac.kr/research/KARI)
  - Dayoung Gong, Joonseok Lee, Deunsol Jung, Suha Kwak, and Minsu Cho, _NeurIPS 2023_.
- Diffusion Action Segmentation,
  [[pdf]](http://arxiv.org/pdf/2303.17959.pdf)
  [[code]](https://github.com/Finspire13/DiffAct)
  - Daochang Liu, Qiyue Li, AnhDung Dinh, Tingting Jiang, Mubarak Shah, and Chang Xu, _ICCV 2023_.
- How Much Temporal Long-Term Context is Needed for Action Segmentation?,
  [[pdf]](https://arxiv.org/pdf/2308.11358.pdf)
  [[code]](https://github.com/LTContext/LTContext)
  - Emad Bahrami, Gianpiero Francesca, and Juergen Gall, _ICCV 2023_.
- Streaming Video Temporal Action Segmentation In Real Time,
  [[pdf]](https://arxiv.org/pdf/2209.13808.pdf)
  [[code]](https://github.com/Thinksky5124/SVTAS)
  - Wujun Wen, Yunheng Li, Zhuben Dong, Lin Feng, Wanxiao Yang, and Shenlan Liu, _ISKE 2023_.

#### 2022

- Don't Pour Cereal into Coffee: Differentiable Temporal Logic for Temporal Action Segmentation,
  [[pdf]](https://openreview.net/pdf?id=PCQyUvAmKs)
  [[code]](https://diff-tl.github.io)
  - Ziwei Xu, Yogesh S Rawat, Yongkang Wong, Mohan S Kankanhalli, and Mubarak Shah, _NeurIPS 2022_.
- Maximization and Restoration: Action Segmentation through Dilation Passing and Temporal Reconstruction,
  [[pdf]](https://www.sciencedirect.com/science/article/abs/pii/S003132032200245X)
  - Junyong Park, Daekyum Kim, Sejoon Huh, and Sungho Jo, _PR 2022_.
- Mcfm: Mutual Cross Fusion Module for Intermediate Fusion-Based Action Segmentation,
  [[pdf]](https://ieeexplore.ieee.org/document/9897444)
  - Kenta Ishihara, Gaku Nakano, and Tetsuo Inoshita, _ICIP 2022_.
- Multistage temporal convolution transformer for action segmentation,
  [[pdf]](https://www.sciencedirect.com/science/article/abs/pii/S0262885622001962)
  - Nicolas Aziere and Sinisa Todorovic, _IVC 2022_.
- Semantic2Graph: Graph-based Multi-modal Feature Fusion for Action Segmentation in Videos,
  [[pdf]](https://arxiv.org/pdf/2209.05653v4.pdf)
  - Junbin Zhang, Pei-Hsuan Tsai, and Meng-Hsun Tsai, _Arxiv 2022_.
- Uncertainty-Aware Representation Learning for Action Segmentation,
  [[pdf]](https://www.ijcai.org/proceedings/2022/0115.pdf)
  - Lei Chen, Muheng Li, Yueqi Duan, Jie Zhou, and Jiwen Lu, _IJCAI 2022_.
- Unified Fully and Timestamp Supervised Temporal Action Segmentation via Sequence to Sequence Translation,
  [[pdf]](https://arxiv.org/pdf/2209.00638.pdf)
  - Nadine Behrmann, S. Alireza Golestaneh, Zico Kolter, Juergen Gall, and Mehdi Noroozi, _ECCV 2022_.

#### 2021

- ASFormer: Transformer for Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2110.08568.pdf)
  [[code]](https://github.com/ChinaYi/ASFormer)
  - Fangqiu Yi, Hongyu Wen, and Tingting Jiang, _BMVC 2021_.
- Alleviating Over-segmentation Errors by Detecting Action Boundaries,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2021/papers/Ishikawa_Alleviating_Over-Segmentation_Errors_by_Detecting_Action_Boundaries_WACV_2021_paper.pdf)
  [[code]](https://github.com/yiskw713/asrf)
  - Yuchi Ishikawa, Seito Kasai, Yoshimitsu Aoki, and Hirokatsu Kataoka, _WACV 2021_.
- Coarse to Fine Multi-Resolution Temporal Convolutional Network,
  [[pdf]](https://arxiv.org/pdf/2105.10859.pdf)
  [[code]](https://github.com/dipika-singhania/C2F-TCN)
  - Dipika Singhania, Rahul Rahaman, and Angela Yao, _Arxiv 2021_.
- FIFA: Fast Inference Approximation for Action Segmentation,
  [[pdf]](https://link.springer.com/chapter/10.1007/978-3-030-92659-5_18)
  - Yaser Souri, Yazan Abu Farha, Fabien Despinoy, Gianpiero Francesca, and Juergen Gall, _GCPR 2021_.
- Global2Local: Efficient Structure Search for Video Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Gao_Global2Local_Efficient_Structure_Search_for_Video_Action_Segmentation_CVPR_2021_paper.pdf)
  [[code]](http://mmcheng.net/G2LSearch)
  - Shang-Hua Gao, Qi Han, Zhong-Yu Li, Pai Peng, Liang Wang, and Ming-Ming Cheng, _CVPR 2021_.

#### 2020

- Action Segmentation with Mixed Temporal Domain Adaptation,
  [[pdf]](https://openaccess.thecvf.com/content_WACV_2020/papers/Chen_Action_Segmentation_with_Mixed_Temporal_Domain_Adaptation_WACV_2020_paper.pdf)
  - Min-Hung Chen, Baopu Li, Yingze Bao, and Ghassan Alregib, _WACV 2020_.
- Boundary-Aware Cascade Networks for Temporal Action Segmentation,
  [[pdf]](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123700035.pdf)
  [[code]](https://github.com/MCG-NJU/BCN)
  - Zhenzhi Wang, Ziteng Gao, Limin Wang, Zhifeng Li, and Gangshan Wu, _ECCV 2020_.
- Improving Action Segmentation via Graph Based Temporal Reasoning,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Huang_Improving_Action_Segmentation_via_Graph-Based_Temporal_Reasoning_CVPR_2020_paper.pdf)
  - Yifei Huang, Yusuke Sugano, and Yoichi Sato, _CVPR 2020_.
- Temporal Aggregate Representations for Long Term Video Understanding,
  [[pdf]](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123610154.pdf)
  - Fadime Sener, Dipika Singhania, and Angela Yao, _ECCV 2020_.

#### 2019

- MS-TCN: Multi-Stage Temporal Convolutional Network for Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2019/papers/Abu_Farha_MS-TCN_Multi-Stage_Temporal_Convolutional_Network_for_Action_Segmentation_CVPR_2019_paper.pdf)
  [[code]](https://github.com/yabufarha/ms-tcn)
  - Yazan Abu Farha and Juergen Gall, _CVPR 2019_.

#### 2018

- Temporal Deformable Residual Networks for Action Segmentation in Videos,
  [[pdf]](https://ieeexplore.ieee.org/document/8578803)
  - Peng Lei and Sinisa Todorovic, _CVPR 2018_.

#### 2017

- Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2017/papers/Carreira_Quo_Vadis_Action_CVPR_2017_paper.pdf)
  [[code]](https://github.com/ahsaniqbal/Kinetics-FeatureExtractor)
  - João Carreira and Andrew Zisserman, _CVPR 2017_.
- Temporal Convolutional Networks for Action Segmentation and Detection,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2017/papers/Lea_Temporal_Convolutional_Networks_CVPR_2017_paper.pdf)
  [[code]](https://github.com/colincsl/TemporalConvolutionalNetworks)
  - Colin Lea, Michael D Flynn Ren, Austin Reiter, and Gregory D Hager, _CVPR 2017_.

#### 2016

- An end-to-end generative framework for video segmentation and recognition,
  [[pdf]](https://arxiv.org/pdf/1509.01947.pdf)
  - Hilde Kuehne, Juergen Gall, and Thomas Serre, _WACV 2016_.
- Temporal Action Detection Using a Statistical Language Model,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2016/papers/Richard_Temporal_Action_Detection_CVPR_2016_paper.pdf)
  [[code]](https://github.com/alexanderrichard/squirrel)
  - Alexander Richard and Juergen Gall, _CVPR 2016_.

### Weakly-Supervised

#### 2024

- Efficient and Effective Weakly-Supervised Action Segmentation via Action-Transition-Aware Boundary Alignment,
  - Angchi Xu and Wei-Shi Zheng, _CVPR 2024_.

#### 2023

- Is Weakly-supervised Action Segmentation Ready For Human-Robot Interaction ? No , Let ’ s Improve It With Action-union Learning,
  [[pdf]](https://www.researchgate.net/profile/Fan-Yang-41/publication/372548891_Is_Weakly-supervised_Action_Segmentation_Ready_For_Human-Robot_Interaction_No_Let's_Improve_It_With_Action-union_Learning/links/64be18dab9ed6874a54076e7/Is-Weakly-supervised-Action-Seg)
  - Fan Yang, Shigeyuki Odashima, Shoichi Masui, and Shan Jiang, _IROS 2023_.
- Reducing the Label Bias for Timestamp Supervised Temporal Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2023/papers/Liu_Reducing_the_Label_Bias_for_Timestamp_Supervised_Temporal_Action_Segmentation_CVPR_2023_paper.pdf)
  - Kaiyuan Liu, Yunheng Li, Shenglan Liu, Chenwei Tan, and Zihang Shao, _CVPR 2023_.
- Timestamp-Supervised Action Segmentation in the Perspective of Clustering,
  [[pdf]](https://www.ijcai.org/proceedings/2023/0077.pdf)
  [[code]](https://github.com/ddz16/TSASPC)
  - Dazhao Du, Enhan Li, Lingyu Si, Fanjiang Xu, and Fuchun Sun, _IJCAI 2023_.

#### 2022

- A Generalized &amp; Robust Framework For Timestamp Supervision in Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2207.10137.pdf)
  [[code]](https://github.com/rahulrahaman/Timestamp-and-SkipTag)
  - Rahul Rahaman, Dipika Singhania, Alexandre Thiery, and Angela Yao, _ECCV 2022_.
- Hierarchical Modeling for Task Recognition and Action Segmentation in Weakly-Labeled Instructional Videos,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2022/papers/Ghoddoosian_Hierarchical_Modeling_for_Task_Recognition_and_Action_Segmentation_in_Weakly-Labeled_WACV_2022_paper.pdf)
  [[code]](https://github.com/rezaghoddoosian/Hierarchical-Task-Modeling)
  - Reza Ghoddoosian, Saif Sayed, and Vassilis Athitsos, _WACV 2022_.
- Robust Action Segmentation from Timestamp Supervision,
  [[pdf]](https://arxiv.org/pdf/2210.06501.pdf)
  - Yaser Souri, Yazan Abu Farha, Emad Bahrami, Gianpiero Francesca, and Juergen Gall, _BMVC 2022_.
- Semi-Weakly-Supervised Learning of Complex Actions from Instructional Task Videos,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Shen_Semi-Weakly-Supervised_Learning_of_Complex_Actions_From_Instructional_Task_Videos_CVPR_2022_paper.pdf)
  [[code]](https://github.com/Yuhan-Shen/SWSL)
  - Yuhan Shen and Ehsan Elhamifar, _CVPR 2022_.
- Set-Supervised Action Learning in Procedural Task Videos via Pairwise Order Consistency,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Lu_Set-Supervised_Action_Learning_in_Procedural_Task_Videos_via_Pairwise_Order_CVPR_2022_paper.pdf)
  [[code]](https://github.com/ZijiaLewisLu/CVPR22-POC)
  - Zijia Lu and Ehsan Elhamifar, _CVPR 2022_.
- Temporal Action Segmentation with High-level Complex Activity Labels,
  [[pdf]](https://arxiv.org/pdf/2108.06706.pdf)
  - Guodong Ding and Angela Yao, _TMM 2022_.
- Timestamp-Supervised Action Segmentation with Graph Convolutional Networks,
  [[pdf]](https://arxiv.org/pdf/2206.15031.pdf)
  - Hamza Khan, Sanjay Haresh, Awais Ahmed, Shakeeb Siddiqui, Andrey Konin, M Zeeshan, Zia Quoc, and Huy Tran, _IROS 2022_.
- Turning to a Teacher for Timestamp Supervised Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2207.00712.pdf)
  - Yang Zhao and Yan Song, _ICME 2022_.
- Unified Fully and Timestamp Supervised Temporal Action Segmentation via Sequence to Sequence Translation,
  [[pdf]](https://arxiv.org/pdf/2209.00638.pdf)
  - Nadine Behrmann, S. Alireza Golestaneh, Zico Kolter, Juergen Gall, and Mehdi Noroozi, _ECCV 2022_.
- Weakly-Supervised Online Action Segmentation in Multi-View Instructional Videos,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Ghoddoosian_Weakly-Supervised_Online_Action_Segmentation_in_Multi-View_Instructional_Videos_CVPR_2022_paper.pdf)
  [[code]](https://arxiv.org/pdf/2203.13309.pdf)
  - Reza Ghoddoosian, Isht Dwivedi, Nakul Agarwal, Chiho Choi, and Behzad Dariush, _CVPR 2022_.

#### 2021

- Anchor-Constrained Viterbi for Set-Supervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Li_Anchor-Constrained_Viterbi_for_Set-Supervised_Action_Segmentation_CVPR_2021_paper.pdf)
  - Jun Li and Sinisa Todorovic, _CVPR 2021_.
- Fast Weakly Supervised Action Segmentation Using Mutual Consistency,
  [[pdf]](https://arxiv.org/pdf/1904.03116.pdf)
  [[code]](https://github.com/yassersouri/MuCon)
  - Yaser Souri, Mohsen Fayyaz, Luca Minciullo, Gianpiero Francesca, and Juergen Gall, _TPAMI 2021_.
- Learning Discriminative Prototypes with Dynamic Time Warping,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Chang_Learning_Discriminative_Prototypes_With_Dynamic_Time_Warping_CVPR_2021_paper.pdf)
  - Xiaobin Chang, Frederick Tung, and Greg Mori, _CVPR 2021_.
- Temporal Action Segmentation from Timestamp Supervision,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Li_Temporal_Action_Segmentation_From_Timestamp_Supervision_CVPR_2021_paper.pdf)
  [[code]](https://github.com/ZheLi2020/TimestampActionSeg)
  - Zhe Li, Yazan Abu Farha, and Juergen Gall, _CVPR 2021_.
- Weakly-Supervised Action Segmentation and Alignment via Transcript-Aware Union-of-Subspaces Learning,
  [[pdf]](https://openaccess.thecvf.com/content/ICCV2021/papers/Lu_Weakly-Supervised_Action_Segmentation_and_Alignment_via_Transcript-Aware_Union-of-Subspaces_Learning_ICCV_2021_paper.pdf)
  [[code]](https://github.com/ZijiaLewisLu/ICCV21-TASL)
  - Zijia Lu and Ehsan Elhamifar, _ICCV 2021_.
- Weakly-supervised Temporal Action Localization by Uncertainty Modeling,
  [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/download/16280/16087)
  - Pilhyeon Lee, Jinglu Wang, Yan Lu, and Hyeran Byun, _AAAI 2021_.

#### 2020

- Fast Weakly Supervised Action Segmentation Using Mutual Consistency,
  [[pdf]](https://arxiv.org/pdf/1904.03116.pdf)
  - Yaser Souri, Mohsen Fayyaz, Luca Minciullo, Gianpiero Francesca, and Juergen Gall, _ECCV 2020_.
- Procedure Completion by Learning from Partial Summaries,
  [[pdf]](https://www.bmvc2020-conference.com/assets/papers/0130.pdf)
  - Zwe Naing and Ehsan Elhamifar, _BMVC 2020_.
- SCT: Set Constrained Temporal Transformer for Set Supervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Fayyaz_SCT_Set_Constrained_Temporal_Transformer_for_Set_Supervised_Action_Segmentation_CVPR_2020_paper.pdf)
  [[code]](https://github.com/MohsenFayyaz89/SCT)
  - Mohsen Fayyaz and Juergen Gall, _CVPR 2020_.
- Set-Constrained Viterbi for Set-Supervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Li_Set-Constrained_Viterbi_for_Set-Supervised_Action_Segmentation_CVPR_2020_paper.pdf)
  - Jun Li and Sinisa Todorovic, _CVPR 2020_.

#### 2019

- D3TW: Discriminative differentiable dynamic time warping for weakly supervised action alignment and segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2019/papers/Chang_D3TW_Discriminative_Differentiable_Dynamic_Time_Warping_for_Weakly_Supervised_Action_CVPR_2019_paper.pdf)
  [[code]](https://github.com/ld-ing/TCFPN-ISBA)
  - Chien Yi Chang, De An Huang, Yanan Sui, Fei-Fei Li, and Juan Carlos Niebles, _CVPR 2019_.
- Weakly Supervised Energy-Based Learning for Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Weakly_Supervised_Energy-Based_Learning_for_Action_Segmentation_ICCV_2019_paper.pdf)
  [[code]](https://github.com/JunLi-Galios/CDFL)
  - Jun Li, Peng Lei, and Sinisa Todorovic, _ICCV 2019_.

#### 2018

- A Hybrid RNN-HMM Approach for Weakly Supervised Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/1906.01028.pdf)
  - Hilde Kuehne, Alexander Richard, and Juergen Gall, _TPAMI 2018_.
- Action Sets: Weakly Supervised Action Segmentation Without Ordering Constraints,
  [[pdf]](https://alexanderrichard.github.io/publications/pdf/richard_action_sets.pdf)
  [[code]](https://github.com/alexanderrichard/action-sets)
  - Alexander Richard, Hilde Kuehne, and Juergen Gall, _CVPR 2018_.
- NeuralNetwork-Viterbi: A Framework for Weakly Supervised Video Learning,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2018/papers/Richard_NeuralNetwork-Viterbi_A_Framework_CVPR_2018_paper.pdf)
  [[code]](https://github.com/alexanderrichard/NeuralNetwork-Viterbi)
  - Alexander Richard, Hilde Kuehne, Ahsan Iqbal, and Juergen Gall, _CVPR 2018_.
- Weakly-Supervised Action Segmentation with Iterative Soft Boundary Assignment,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2018/CameraReady/1522.pdf)
  [[code]](https://github.com/ld-ing/TCFPN-ISBA)
  - Li Ding and Chenliang Xu, _CVPR 2018_.

#### 2017

- Weakly supervised action learning with RNN based fine-to-coarse modeling,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2017/papers/Richard_Weakly_Supervised_Action_CVPR_2017_paper.pdf)
  [[code]](https://github.com/alexanderrichard/weakly-sup-action-learning)
  - Alexander Richard, Hilde Kuehne, and Juergen Gall, _CVPR 2017_.
- Weakly supervised learning of actions from transcripts,
  [[pdf]](https://arxiv.org/pdf/1610.02237.pdf)
  - Hilde Kuehne, Alexander Richard, and Juergen Gall, _CVIU 2017_.

#### 2016

- Connectionist temporal modeling for weakly supervised action labeling,
  [[pdf]](https://arxiv.org/pdf/1607.08584.pdf)
  [[code]](https://github.com/daahuang/lasagne-ectc)
  - De An Huang, Fei-Fei Li, and Juan Carlos Niebles, _ECCV 2016_.

### Unsupervised

#### 2024

- Temporally Consistent Unbalanced Optimal Transport for Unsupervised Action Segmentation,
  - Ming Xu and Stephen Gould, _CVPR 2024_.
- OTAS: Unsupervised Boundary Detection for Object-Centric Temporal Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2024/papers/Li_OTAS_Unsupervised_Boundary_Detection_for_Object-Centric_Temporal_Action_Segmentation_WACV_2024_paper.pdf)
  [[code]](https://github.com/yl596/OTAS)
  - Yuerong Li, Zhengrong Xue and Huazhe Xu, _WACV 2024_.

#### 2023

- Leveraging triplet loss for unsupervised action segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2023W/L3D-IVU/papers/Bueno-Benito_Leveraging_Triplet_Loss_for_Unsupervised_Action_Segmentation_CVPRW_2023_paper.pdf)
  [[code]](https://github.com/elenabbbuenob/TSA-ActionSeg)
  - Elena Belen Bueno-Benito, Biel Tura Vecino, and Mariella Dimiccoli, _CVPRW 2023_.
- TAEC: Unsupervised action segmentation with temporal-Aware embedding and clustering,
  [[pdf]](https://arxiv.org/pdf/2303.05166.pdf)
  - Wei Lin, Anna Kukleva, Horst Possegger, Hilde Kuehne, and Horst Bischof, _CEURW 2023_.

#### 2022

- Fast and Unsupervised Action Boundary Detection for Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Du_Fast_and_Unsupervised_Action_Boundary_Detection_for_Action_Segmentation_CVPR_2022_paper.pdf)
  - Zexing Du, Xue Wang, Guoqing Zhou, and Qing Wang, _CVPR 2022_.
- My View is the Best View: Procedure Learning from Egocentric Videos,
  [[pdf]](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136730656.pdf)
  [[code]](https://sid2697.github.io/egoprocel)
  - Siddhant Bansal, Chetan Arora, and C V Jawahar, _ECCV 2022_.
- Temporal Action Segmentation with High-level Complex Activity Labels,
  [[pdf]](https://arxiv.org/pdf/2108.06706.pdf)
  - Guodong Ding and Angela Yao, _TMM 2022_.
- Unsupervised Action Segmentation by Joint Representation Learning and Online Clustering,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Kumar_Unsupervised_Action_Segmentation_by_Joint_Representation_Learning_and_Online_Clustering_CVPR_2022_paper.pdf)
  [[code]](https://bit.ly/3JKm0JP)
  - Sateesh Kumar, Sanjay Haresh, Awais Ahmed, Andrey Konin, M. Zeeshan Zia, and Quoc Huy Tran, _CVPR 2022_.

#### 2021

- Action Shuffle Alternating Learning for Unsupervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Li_Action_Shuffle_Alternating_Learning_for_Unsupervised_Action_Segmentation_CVPR_2021_paper.pdf)
  - Jun Li and Sinisa Todorovic, _CVPR 2021_.
- Joint Visual-Temporal Embedding for Unsupervised Learning of Actions in Untrimmed Sequences,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2021/papers/VidalMata_Joint_Visual-Temporal_Embedding_for_Unsupervised_Learning_of_Actions_in_Untrimmed_WACV_2021_paper.pdf)
  - Rosaura G Vidalmata, Walter J Scheirer, Anna Kukleva, David Cox, and Hilde Kuehne, _WACV 2021_.
- Temporally-Weighted Hierarchical Clustering for Unsupervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Sarfraz_Temporally-Weighted_Hierarchical_Clustering_for_Unsupervised_Action_Segmentation_CVPR_2021_paper.pdf)
  [[code]](https://github.com/ssarfraz/FINCH-Clustering/tree/master/TW-FINCH)
  - M Saquib Sarfraz, Naila Murray, Vivek Sharma, Ali Diba, Luc Van Gool, and Rainer Stiefelhagen, _CVPR 2021_.

#### 2020

- Action Segmentation with Joint Self-Supervised Temporal Domain Adaptation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Chen_Action_Segmentation_With_Joint_Self-Supervised_Temporal_Domain_Adaptation_CVPR_2020_paper.pdf)
  [[code]](https://github.com/cmhungsteve/SSTDA)
  - Min-Hung Chen, Baopu Li, Yingze Bao, Ghassan AlRegib, and Zsolt Kira, _CVPR 2020_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  Despite the recent progress of fully-supervised action segmentation techniques, the performance is still not fully satisfactory. One main challenge is the problem of spatiotemporal variations (e.g. different people may perform the same activity in various ways). Therefore, we exploit unlabeled videos to address this problem by reformulating the action segmentation task as a cross-domain problem with domain discrepancy caused by spatio-temporal variations. To reduce the discrepancy, we propose Self-Supervised Temporal Domain Adaptation (SSTDA), which contains two self-supervised auxiliary tasks (binary and sequential domain prediction) to jointly align cross-domain feature spaces embedded with local and global temporal dynamics, achieving better performance than other Domain Adaptation (DA) approaches. On three challenging benchmark datasets (GTEA, 50Salads, and Breakfast), SSTDA outperforms the current state-of-the-art method by large margins (e.g. for the F1@25 score, from 59.6% to 69.1% on Breakfast, from 73.4% to 81.5% on 50Salads, and from 83.6% to 89.1% on GTEA), and requires only 65% of the labeled training data for comparable performance, demonstrating the usefulness of adapting to unlabeled target videos across variations. The source code is available at https://github.com/cmhungsteve/SSTDA.
  </details>

#### 2019

- Unsupervised learning of action classes with continuous temporal embedding,
  [[pdf]](https://arxiv.org/pdf/1904.04189.pdf)
  [[code]](https://github.com/annusha/unsup_temp_embed)
  - Anna Kukleva, Hilde Kuehne, Fadime Sener, and Jurgen Gall, _CVPR 2019_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  The task of temporally detecting and segmenting actions in untrimmed videos has seen an increased attention recently. One problem in this context arises from the need to define and label action boundaries to create annotations for training which is very time and cost intensive. To address this issue, we propose an unsupervised approach for learning action classes from untrimmed video sequences. To this end, we use a continuous temporal embedding of framewise features to benefit from the sequential nature of activities. Based on the latent space created by the embedding, we identify clusters of temporal segments across all videos that correspond to semantic meaningful action classes. The approach is evaluated on three challenging datasets, namely the Breakfast dataset, YouTube Instructions, and the 50Salads dataset. While previous works assumed that the videos contain the same high level activity, we furthermore show that the proposed approach can also be applied to a more general setting where the content of the videos is unknown.
  </details>
- Unsupervised Procedure Learning via Joint Dynamic Summarization,
  [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Elhamifar_Unsupervised_Procedure_Learning_via_Joint_Dynamic_Summarization_ICCV_2019_paper.pdf)
  - Ehsan Elhamifar and Zwe Naing, _ICCV 2019_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  We address the problem of unsupervised procedure learning from unconstrained instructional videos. Our goal is to produce a summary of the procedure key-steps and their ordering needed to perform a given task, as well as localization of the key-steps in videos. We develop a collaborative sequential subset selection framework, where we build a dynamic model on videos by learning states and transitions between them, where states correspond to different subactivities, including background and procedure steps. To extract procedure key-steps, we develop an optimization framework that finds a sequence of a small number of states that well represents all videos and is compatible with the state transition model. Given that our proposed optimization is non-convex and NP-hard, we develop a fast greedy algorithm whose complexity is linear in the length of the videos and the number of states of the dynamic model, hence, scales to large datasets. Under appropriate conditions on the transition model, our proposed formulation is approximately submodular, hence, comes with performance guarantees. We also present ProceL, a new multimodal dataset of 47.3 hours of videos and their transcripts from diverse tasks, for procedure learning evaluation. By extensive experiments, we show that our framework significantly improves the state of the art performance.
  </details>

#### 2018

- Unsupervised Learning and Segmentation of Complex Activities from Video,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2018/papers/Sener_Unsupervised_Learning_and_CVPR_2018_paper.pdf)
  [[code]](https://github.com/Annusha/slim_mallow)
  - Fadime Sener and Angela Yao, _CVPR 2018_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  This paper presents a new method for unsupervised seg-mentation of complex activities from video into multiple steps, or sub-activities, without any textual input. We propose an iterative discriminative-generative approach which alternates between discriminatively learning the appearance of sub-activities from the videos' visual features to sub-activity labels and generatively modelling the temporal structure of sub-activities using a Generalized Mallows Model. In addition, we introduce a model for background to account for frames unrelated to the actual activities. Our approach is validated on the challenging Breakfast Actions and Inria Instructional Videos datasets and outperforms both unsupervised and weakly-supervised state of the art.
  </details>

#### 2016

- Unsupervised learning from narrated instruction videos,
  [[pdf]](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Alayrac_Unsupervised_Learning_From_CVPR_2016_paper.pdf)
  - Jean-Baptiste Alayrac, Piotr Bojanowski, Nishant Agrawal, Josef Sivic, Ivan Laptev, and Simon Lacoste-Julien, _CVPR 2016_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  We address the problem of automatically learning the main steps to complete a certain task, such as changing a car tire, from a set of narrated instruction videos. The contributions of this paper are three-fold. First, we develop a new unsupervised learning approach that takes advantage of the complementary nature of the input video and the associated narration. The method solves two clustering problems, one in text and one in video, applied one after each other and linked by joint constraints to obtain a single coherent sequence of steps in both modalities. Second, we collect and annotate a new challenging dataset of real-world instruction videos from the Internet. The dataset contains about 800,000 frames for five different tasks1 that include complex interactions between people and objects, and are captured in a variety of indoor and outdoor settings. Third, we experimentally demonstrate that the proposed method can automatically discover, in an unsupervised manner, the main steps to achieve the task and locate the steps in the input videos.
  </details>

#### 2015

- Unsupervised Semantic Parsing of Video Collections,
  [[pdf]](https://openaccess.thecvf.com/content_iccv_2015/papers/Sener_Unsupervised_Semantic_Parsing_ICCV_2015_paper.pdf)
  - Ozan Sener, Amir R. Zamir, Silvio Savarese, and Ashutosh Saxena, _ICCV 2015_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  Human communication typically has an underlying structure. This is reflected in the fact that in many user generated videos, a starting point, ending, and certain objective steps between these two can be identified. In this paper, we propose a method for parsing a video into such semantic steps in an unsupervised way. The proposed method is capable of providing a semantic "storyline" of the video composed of its objective steps. We accomplish this using both visual and language cues in a joint generative model. The proposed method can also provide a textual description for each of the identified semantic steps and video segments. We evaluate this method on a large number of complex YouTube videos and show results of unprecedented quality for this intricate and impactful problem.
  </details>

### Semi-Supervised

#### 2022

- Iterative Contrast-Classify for Semi-supervised Temporal Action Segmentation,
  [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/view/20124/19883)
  [[code]](https://github.com/dipika-singhania/ICC-Semi-Supervised-TAS)
  - Dipika Singhania, Rahul Rahaman, and Angela Yao, _AAAI 2022_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  Temporal action segmentation classifies the action of each frame in (long) video sequences. Due to the high cost of frame-wise labeling, we propose the first semi-supervised method for temporal action segmentation. Our method hinges on unsupervised representation learning, which, for temporal action segmentation, poses unique challenges. Actions in untrimmed videos vary in length and have unknown labels and start/end times. Ordering of actions across videos may also vary. We propose a novel way to learn frame-wise representations from temporal convolutional networks (TCNs) by clustering input features with added time-proximity conditions and multi-resolution similarity. By merging representation learning with conventional supervised learning, we develop an "Iterative Contrast-Classify (ICC)" semi-supervised learning scheme. With more labelled data, ICC progressively improves in performance; ICC semi-supervised learning, with 40% labelled videos, performs similarly to fully-supervised counterparts. Our ICC improves MoF by +1.8, +5.6, +2.5% on Breakfast, 50Salads, and GTEA respectively for 100% labelled videos.
  </details>
- Leveraging Action Affinity and Continuity for Semi-supervised Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2207.08653.pdf)
  [[code]](https://github.com/dinggd/semitas)
  - Guodong Ding and Angela Yao, _ECCV 2022_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  We present a semi-supervised learning approach to the temporal action segmentation task. The goal of the task is to temporally detect and segment actions in long, untrimmed procedural videos, where only a small set of videos are densely labelled, and a large collection of videos are unlabelled. To this end, we propose two novel loss functions for the unlabelled data: an action affinity loss and an action continuity loss. The action affinity loss guides the unlabelled samples learning by imposing the action priors induced from the labelled set. Action continuity loss enforces the temporal continuity of actions, which also provides frame-wise classification supervision. In addition, we propose an Adaptive Boundary Smoothing (ABS) approach to build coarser action boundaries for more robust and reliable learning. The proposed loss functions and ABS were evaluated on three benchmarks. Results show that they significantly improved action segmentation performance with a low amount (5% and 10%) of labelled data and achieved comparable results to full supervision with 50% labelled data. Furthermore, ABS succeeded in boosting performance when integrated into fully-supervised learning.
  </details>

### Online

#### 2024

- Progress-Aware Online Action Segmentation for Egocentric Procedural Task Videos,
  - Yuhan Shen and Ehsan Elhamifar, _CVPR 2024_.

### Continual

#### 2024

- Coherent Temporal Synthesis for Incremental Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2403.06102.pdf)
  - Guodong Ding, Hans Golong and Angela Yao, _CVPR 2024_.
  <details close>
  <summary><i>Read Abstract</i></summary>
  Data replay is a successful incremental learning technique for images. It prevents catastrophic forgetting by keeping a reservoir of previous data, original or synthesized, to ensure the model retains past knowledge while adapting to novel concepts. However, its application in the video domain is rudimentary, as it simply stores frame exemplars for action recognition. This paper presents the first exploration of video data replay techniques for incremental action segmentation, focusing on action temporal modeling. We propose a Temporally Coherent Action (TCA) model, which represents actions using a generative model instead of storing individual frames. The integration of a conditioning variable that captures temporal coherence allows our model to understand the evolution of action features over time. Therefore, action segments generated by TCA for replay are diverse and temporally coherent. In a 10-task incremental setup on the Breakfast dataset, our approach achieves significant increases in accuracy for up to 22% compared to the baselines.
  </details>

## Citation

If you find this repository helpful in your research, please consider citing our survey as:

```
@article{ding2023temporal,
  title={Temporal action segmentation: An analysis of modern techniques},
  author={Ding, Guodong and Sener, Fadime and Yao, Angela},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  year={2023},
  publisher={IEEE}
}
```

## Feedback

- [pull request](https://github.com/atlas-eccv22/awesome-temporal-action-segmentation/pulls)
