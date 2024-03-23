# Awesome Temporal Action Segmentation

![Temporal Action Segmentation](./TAS.png)
A curated list of awesome temporal action segmentation resources. Inspired by [awesome-machine-learning-resources](https://github.com/ZhiningLiu1998/awesome-machine-learning-resources).
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) 

⭐ **Please leave a <font color='orange'>STAR</font> if you like this project!** ⭐
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
  - Guodong Ding, Fadime Sener, and Angela Yao, *TPAMI 2023*.

## Datasets
There are multiple datasets that have been used to benchmark the perfomance of the temporal action segmentation approaches. The most commonly adopted datasets are the as follows:

### Breakfast
- The Language of Actions: Recovering the Syntax and Semantics of Goal-Directed Human Activities 
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2014/papers/Kuehne_The_Language_of_2014_CVPR_paper.pdf) 
  - Hilde Kuehne, Ali Arslan, and Thomas Serre, *CVPR 2014*.

targets recording videos ''in the wild'', in 18 different kitchens. The participants are not given any scrips and the recordings are unrehearsed and undirected. The dataset is composed of the 10 breakfast-related activities. This dataset is recorded with 52 participants with multiple cameras, varies from 3 to 5, all from a third-person point of view. There are 1712 videos, when accounting for the multi-camera views.

### GTEA
- Learning to Recognize Objects in Egocentric Activities 
  [[pdf]](https://arxiv.org/pdf/2102.08065.pdf) 
  - Alireza Fatih, Xiaofeng Ren, and M James Rehg, *CVPR 2011*.

contains 28 videos recorded in a single kitchen from seven procedural activities. 
The videos are recorded with a camera mounted on a cap, worn by four participants. 


### 50Salads

- Combining Embedded Accelerometers with Computer Vision for Recognizing Food Preparation Activities 
  [[pdf]](https://doi.org/10.1145/2493432.2493482) 
  - Sebastian Stein, and Stephen J Mckenna, *UbiComp 2013*.

is composed of 50 recorded videos of 25 participants making two different mixed salads. The videos are captured by a camera with a top-down view onto the work-surface. The participants are provided with recipe steps which are randomly sampled from a statistical recipe model.


### YouTube Instructional
- Unsupervised Learning from Narrated Instruction Videos 
  [[pdf]](https://doi.org/10.1109/CVPR.2016.495) 
  - Jean-Baptiste Alayrac, Piotr Bojanowski, Nishant Agrawal, Josef Sivic, Ivan Laptev, and Simon Lacoste-Julien, *CVPR 2016*.

is a recently collected dataset where 53 participants were asked to dissemble and assemble take apart toys without given any instructions which resulted in  realistic sequences with great variation in action ordering. The dataset is annotated with fine-grained, hand-object interactions, and coarse action labels which are composed of multiple fine-grained action segments related to the attaching or detaching of a vehicle part. The authors evaluated their dataset for temporal action segmentation using the coarse labels. 

### Assembly101
- Assembly101: A Large-Scale Multi-View Video Dataset for Understanding Procedural Activities 
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Sener_Assembly101_A_Large-Scale_Multi-View_Video_Dataset_for_Understanding_Procedural_Activities_CVPR_2022_paper.pdf) 
  - Fadime Sener, Dibyadip Chatterjee, Daniel Shelepov, Kun He, Dipika Singhania, Robert Wang, and others, *CVPR 2022*.

is a recently collected dataset where 53 participants were asked to dissemble and assemble take apart toys without given any instructions which resulted in  realistic sequences with great variation in action ordering. The dataset is annotated with fine-grained, hand-object interactions, and coarse action labels which are composed of multiple fine-grained action segments related to the attaching or detaching of a vehicle part. The authors evaluated their dataset for temporal action segmentation using the coarse labels. 

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
## Paper List
### Fully-Supervised
#### 2024
- FACT: Frame-Action Cross-Attention Temporal Modeling for Efficient Fully-Supervised Action Segmentation,
  [[code]](https://github.com/ZijiaLewisLu/CVPR2024-FACT)
    - Zijia Lu and Ehsan Elhamifar, *CVPR2024*.
#### 2023
- Activity Grammars for Temporal Action Segmentation,
  [[pdf]](https://openreview.net/pdf?id=oOXZ5JEjPb)
  [[code]](http://cvlab.postech.ac.kr/research/KARI)
    - Dayoung Gong, Joonseok Lee, Deunsol Jung, Suha Kwak, and Minsu Cho, *NeurIPS 2023*.
- Diffusion Action Segmentation,
  [[pdf]](http://arxiv.org/pdf/2303.17959.pdf)
  [[code]](https://github.com/Finspire13/DiffAct)
    - Daochang Liu, Qiyue Li, AnhDung Dinh, Tingting Jiang, Mubarak Shah, and Chang Xu, *ICCV 2023*.
- How Much Temporal Long-Term Context is Needed for Action Segmentation?,
  [[pdf]](https://arxiv.org/pdf/2308.11358.pdf)
  [[code]](https://github.com/LTContext/LTContext)
    - Emad Bahrami, Gianpiero Francesca, and Juergen Gall, *ICCV 2023*.
- Streaming Video Temporal Action Segmentation In Real Time,
  [[pdf]](https://arxiv.org/pdf/2209.13808.pdf)
  [[code]](https://github.com/Thinksky5124/SVTAS)
    - Wujun Wen, Yunheng Li, Zhuben Dong, Lin Feng, Wanxiao Yang, and Shenlan Liu, *ISKE 2023*.
#### 2022
- Don't Pour Cereal into Coffee: Differentiable Temporal Logic for Temporal Action Segmentation,
  [[pdf]](https://openreview.net/pdf?id=PCQyUvAmKs)
  [[code]](https://diff-tl.github.io)
    - Ziwei Xu, Yogesh S Rawat, Yongkang Wong, Mohan S Kankanhalli, and Mubarak Shah, *NeurIPS 2022*.
- Maximization and Restoration: Action Segmentation through Dilation Passing and Temporal Reconstruction,
  [[pdf]](https://www.sciencedirect.com/science/article/abs/pii/S003132032200245X)
    - Junyong Park, Daekyum Kim, Sejoon Huh, and Sungho Jo, *PR 2022*.
- Mcfm: Mutual Cross Fusion Module for Intermediate Fusion-Based Action Segmentation,
  [[pdf]](https://ieeexplore.ieee.org/document/9897444)
    - Kenta Ishihara, Gaku Nakano, and Tetsuo Inoshita, *ICIP 2022*.
- Multistage temporal convolution transformer for action segmentation,
  [[pdf]](https://www.sciencedirect.com/science/article/abs/pii/S0262885622001962)
    - Nicolas Aziere and Sinisa Todorovic, *IVC 2022*.
- Semantic2Graph: Graph-based Multi-modal Feature Fusion for Action Segmentation in Videos,
  [[pdf]](https://arxiv.org/pdf/2209.05653v4.pdf)
    - Junbin Zhang, Pei-Hsuan Tsai, and Meng-Hsun Tsai, *Arxiv 2022*.
- Uncertainty-Aware Representation Learning for Action Segmentation,
  [[pdf]](https://www.ijcai.org/proceedings/2022/0115.pdf)
    - Lei Chen, Muheng Li, Yueqi Duan, Jie Zhou, and Jiwen Lu, *IJCAI 2022*.
- Unified Fully and Timestamp Supervised Temporal Action Segmentation via Sequence to Sequence Translation,
  [[pdf]](https://arxiv.org/pdf/2209.00638.pdf)
    - Nadine Behrmann, S. Alireza Golestaneh, Zico Kolter, Juergen Gall, and Mehdi Noroozi, *ECCV 2022*.
#### 2021
- ASFormer: Transformer for Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2110.08568.pdf)
  [[code]](https://github.com/ChinaYi/ASFormer)
    - Fangqiu Yi, Hongyu Wen, and Tingting Jiang, *BMVC 2021*.
- Alleviating Over-segmentation Errors by Detecting Action Boundaries,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2021/papers/Ishikawa_Alleviating_Over-Segmentation_Errors_by_Detecting_Action_Boundaries_WACV_2021_paper.pdf)
  [[code]](https://github.com/yiskw713/asrf)
    - Yuchi Ishikawa, Seito Kasai, Yoshimitsu Aoki, and Hirokatsu Kataoka, *WACV 2021*.
- Coarse to Fine Multi-Resolution Temporal Convolutional Network,
  [[pdf]](https://arxiv.org/pdf/2105.10859.pdf)
  [[code]](https://github.com/dipika-singhania/C2F-TCN)
    - Dipika Singhania, Rahul Rahaman, and Angela Yao, *Arxiv 2021*.
- FIFA: Fast Inference Approximation for Action Segmentation,
  [[pdf]](https://link.springer.com/chapter/10.1007/978-3-030-92659-5_18)
    - Yaser Souri, Yazan Abu Farha, Fabien Despinoy, Gianpiero Francesca, and Juergen Gall, *GCPR 2021*.
- Global2Local: Efficient Structure Search for Video Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Gao_Global2Local_Efficient_Structure_Search_for_Video_Action_Segmentation_CVPR_2021_paper.pdf)
  [[code]](http://mmcheng.net/G2LSearch)
    - Shang-Hua Gao, Qi Han, Zhong-Yu Li, Pai Peng, Liang Wang, and Ming-Ming Cheng, *CVPR 2021*.
#### 2020
- Action Segmentation with Mixed Temporal Domain Adaptation,
  [[pdf]](https://openaccess.thecvf.com/content_WACV_2020/papers/Chen_Action_Segmentation_with_Mixed_Temporal_Domain_Adaptation_WACV_2020_paper.pdf)
    - Min-Hung Chen, Baopu Li, Yingze Bao, and Ghassan Alregib, *WACV 2020*.
- Boundary-Aware Cascade Networks for Temporal Action Segmentation,
  [[pdf]](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123700035.pdf)
  [[code]](https://github.com/MCG-NJU/BCN)
    - Zhenzhi Wang, Ziteng Gao, Limin Wang, Zhifeng Li, and Gangshan Wu, *ECCV 2020*.
- Improving Action Segmentation via Graph Based Temporal Reasoning,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Huang_Improving_Action_Segmentation_via_Graph-Based_Temporal_Reasoning_CVPR_2020_paper.pdf)
    - Yifei Huang, Yusuke Sugano, and Yoichi Sato, *CVPR 2020*.
- Temporal Aggregate Representations for Long Term Video Understanding,
  [[pdf]](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123610154.pdf)
    - Fadime Sener, Dipika Singhania, and Angela Yao, *ECCV 2020*.
#### 2019
- MS-TCN: Multi-Stage Temporal Convolutional Network for Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2019/papers/Abu_Farha_MS-TCN_Multi-Stage_Temporal_Convolutional_Network_for_Action_Segmentation_CVPR_2019_paper.pdf)
  [[code]](https://github.com/yabufarha/ms-tcn)
    - Yazan Abu Farha and Juergen Gall, *CVPR 2019*.
#### 2018
- Temporal Deformable Residual Networks for Action Segmentation in Videos,
  [[pdf]](https://ieeexplore.ieee.org/document/8578803)
    - Peng Lei and Sinisa Todorovic, *CVPR 2018*.
#### 2017
- Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2017/papers/Carreira_Quo_Vadis_Action_CVPR_2017_paper.pdf)
  [[code]](https://github.com/ahsaniqbal/Kinetics-FeatureExtractor)
    - João Carreira and Andrew Zisserman, *CVPR 2017*.
- Temporal Convolutional Networks for Action Segmentation and Detection,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2017/papers/Lea_Temporal_Convolutional_Networks_CVPR_2017_paper.pdf)
  [[code]](https://github.com/colincsl/TemporalConvolutionalNetworks)
    - Colin Lea, Michael D Flynn Ren, Austin Reiter, and Gregory D Hager, *CVPR 2017*.
#### 2016
- An end-to-end generative framework for video segmentation and recognition,
  [[pdf]](https://arxiv.org/pdf/1509.01947.pdf)
    - Hilde Kuehne, Juergen Gall, and Thomas Serre, *WACV 2016*.
- Temporal Action Detection Using a Statistical Language Model,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2016/papers/Richard_Temporal_Action_Detection_CVPR_2016_paper.pdf)
  [[code]](https://github.com/alexanderrichard/squirrel)
    - Alexander Richard and Juergen Gall, *CVPR 2016*.
### Weakly-Supervised
#### 2024
- Efficient and Effective Weakly-Supervised Action Segmentation via Action-Transition-Aware Boundary Alignment,
    - Angchi Xu and Wei-Shi Zheng, *CVPR2024*.
#### 2023
- Is Weakly-supervised Action Segmentation Ready For Human-Robot Interaction ? No , Let ’ s Improve It With Action-union Learning,
  [[pdf]](https://www.researchgate.net/profile/Fan-Yang-41/publication/372548891_Is_Weakly-supervised_Action_Segmentation_Ready_For_Human-Robot_Interaction_No_Let's_Improve_It_With_Action-union_Learning/links/64be18dab9ed6874a54076e7/Is-Weakly-supervised-Action-Seg)
    - Fan Yang, Shigeyuki Odashima, Shoichi Masui, and Shan Jiang, *IROS 2023*.
- Reducing the Label Bias for Timestamp Supervised Temporal Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2023/papers/Liu_Reducing_the_Label_Bias_for_Timestamp_Supervised_Temporal_Action_Segmentation_CVPR_2023_paper.pdf)
    - Kaiyuan Liu, Yunheng Li, Shenglan Liu, Chenwei Tan, and Zihang Shao, *CVPR 2023*.
- Timestamp-Supervised Action Segmentation in the Perspective of Clustering,
  [[pdf]](https://www.ijcai.org/proceedings/2023/0077.pdf)
  [[code]](https://github.com/ddz16/TSASPC)
    - Dazhao Du, Enhan Li, Lingyu Si, Fanjiang Xu, and Fuchun Sun, *IJCAI 2023*.
#### 2022
- A Generalized &amp; Robust Framework For Timestamp Supervision in Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2207.10137.pdf)
  [[code]](https://github.com/rahulrahaman/Timestamp-and-SkipTag)
    - Rahul Rahaman, Dipika Singhania, Alexandre Thiery, and Angela Yao, *ECCV 2022*.
- Hierarchical Modeling for Task Recognition and Action Segmentation in Weakly-Labeled Instructional Videos,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2022/papers/Ghoddoosian_Hierarchical_Modeling_for_Task_Recognition_and_Action_Segmentation_in_Weakly-Labeled_WACV_2022_paper.pdf)
  [[code]](https://github.com/rezaghoddoosian/Hierarchical-Task-Modeling)
    - Reza Ghoddoosian, Saif Sayed, and Vassilis Athitsos, *WACV 2022*.
- Robust Action Segmentation from Timestamp Supervision,
  [[pdf]](https://arxiv.org/pdf/2210.06501.pdf)
    - Yaser Souri, Yazan Abu Farha, Emad Bahrami, Gianpiero Francesca, and Juergen Gall, *BMVC 2022*.
- Semi-Weakly-Supervised Learning of Complex Actions from Instructional Task Videos,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Shen_Semi-Weakly-Supervised_Learning_of_Complex_Actions_From_Instructional_Task_Videos_CVPR_2022_paper.pdf)
  [[code]](https://github.com/Yuhan-Shen/SWSL)
    - Yuhan Shen and Ehsan Elhamifar, *CVPR 2022*.
- Set-Supervised Action Learning in Procedural Task Videos via Pairwise Order Consistency,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Lu_Set-Supervised_Action_Learning_in_Procedural_Task_Videos_via_Pairwise_Order_CVPR_2022_paper.pdf)
  [[code]](https://github.com/ZijiaLewisLu/CVPR22-POC)
    - Zijia Lu and Ehsan Elhamifar, *CVPR 2022*.
- Temporal Action Segmentation with High-level Complex Activity Labels,
  [[pdf]](https://arxiv.org/pdf/2108.06706.pdf)
    - Guodong Ding and Angela Yao, *TMM 2022*.
- Timestamp-Supervised Action Segmentation with Graph Convolutional Networks,
  [[pdf]](https://arxiv.org/pdf/2206.15031.pdf)
    - Hamza Khan, Sanjay Haresh, Awais Ahmed, Shakeeb Siddiqui, Andrey Konin, M Zeeshan, Zia Quoc, and Huy Tran, *IROS 2022*.
- Turning to a Teacher for Timestamp Supervised Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2207.00712.pdf)
    - Yang Zhao and Yan Song, *ICME 2022*.
- Unified Fully and Timestamp Supervised Temporal Action Segmentation via Sequence to Sequence Translation,
  [[pdf]](https://arxiv.org/pdf/2209.00638.pdf)
    - Nadine Behrmann, S. Alireza Golestaneh, Zico Kolter, Juergen Gall, and Mehdi Noroozi, *ECCV 2022*.
- Weakly-Supervised Online Action Segmentation in Multi-View Instructional Videos,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Ghoddoosian_Weakly-Supervised_Online_Action_Segmentation_in_Multi-View_Instructional_Videos_CVPR_2022_paper.pdf)
  [[code]](https://arxiv.org/pdf/2203.13309.pdf)
    - Reza Ghoddoosian, Isht Dwivedi, Nakul Agarwal, Chiho Choi, and Behzad Dariush, *CVPR 2022*.
#### 2021
- Anchor-Constrained Viterbi for Set-Supervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Li_Anchor-Constrained_Viterbi_for_Set-Supervised_Action_Segmentation_CVPR_2021_paper.pdf)
    - Jun Li and Sinisa Todorovic, *CVPR 2021*.
- Fast Weakly Supervised Action Segmentation Using Mutual Consistency,
  [[pdf]](https://arxiv.org/pdf/1904.03116.pdf)
  [[code]](https://github.com/yassersouri/MuCon)
    - Yaser Souri, Mohsen Fayyaz, Luca Minciullo, Gianpiero Francesca, and Juergen Gall, *TPAMI 2021*.
- Learning Discriminative Prototypes with Dynamic Time Warping,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Chang_Learning_Discriminative_Prototypes_With_Dynamic_Time_Warping_CVPR_2021_paper.pdf)
    - Xiaobin Chang, Frederick Tung, and Greg Mori, *CVPR 2021*.
- Temporal Action Segmentation from Timestamp Supervision,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Li_Temporal_Action_Segmentation_From_Timestamp_Supervision_CVPR_2021_paper.pdf)
  [[code]](https://github.com/ZheLi2020/TimestampActionSeg)
    - Zhe Li, Yazan Abu Farha, and Juergen Gall, *CVPR 2021*.
- Weakly-Supervised Action Segmentation and Alignment via Transcript-Aware Union-of-Subspaces Learning,
  [[pdf]](https://openaccess.thecvf.com/content/ICCV2021/papers/Lu_Weakly-Supervised_Action_Segmentation_and_Alignment_via_Transcript-Aware_Union-of-Subspaces_Learning_ICCV_2021_paper.pdf)
  [[code]](https://github.com/ZijiaLewisLu/ICCV21-TASL)
    - Zijia Lu and Ehsan Elhamifar, *ICCV 2021*.
- Weakly-supervised Temporal Action Localization by Uncertainty Modeling,
  [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/download/16280/16087)
    - Pilhyeon Lee, Jinglu Wang, Yan Lu, and Hyeran Byun, *AAAI 2021*.
#### 2020
- Fast Weakly Supervised Action Segmentation Using Mutual Consistency,
  [[pdf]](https://arxiv.org/pdf/1904.03116.pdf)
    - Yaser Souri, Mohsen Fayyaz, Luca Minciullo, Gianpiero Francesca, and Juergen Gall, *ECCV 2020*.
- Procedure Completion by Learning from Partial Summaries,
  [[pdf]](https://www.bmvc2020-conference.com/assets/papers/0130.pdf)
    - Zwe Naing and Ehsan Elhamifar, *BMVC 2020*.
- SCT: Set Constrained Temporal Transformer for Set Supervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Fayyaz_SCT_Set_Constrained_Temporal_Transformer_for_Set_Supervised_Action_Segmentation_CVPR_2020_paper.pdf)
  [[code]](https://github.com/MohsenFayyaz89/SCT)
    - Mohsen Fayyaz and Juergen Gall, *CVPR 2020*.
- Set-Constrained Viterbi for Set-Supervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Li_Set-Constrained_Viterbi_for_Set-Supervised_Action_Segmentation_CVPR_2020_paper.pdf)
    - Jun Li and Sinisa Todorovic, *CVPR 2020*.
#### 2019
- D3TW: Discriminative differentiable dynamic time warping for weakly supervised action alignment and segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2019/papers/Chang_D3TW_Discriminative_Differentiable_Dynamic_Time_Warping_for_Weakly_Supervised_Action_CVPR_2019_paper.pdf)
  [[code]](https://github.com/ld-ing/TCFPN-ISBA)
    - Chien Yi Chang, De An Huang, Yanan Sui, Fei-Fei Li, and Juan Carlos Niebles, *CVPR 2019*.
- Weakly Supervised Energy-Based Learning for Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Weakly_Supervised_Energy-Based_Learning_for_Action_Segmentation_ICCV_2019_paper.pdf)
  [[code]](https://github.com/JunLi-Galios/CDFL)
    - Jun Li, Peng Lei, and Sinisa Todorovic, *ICCV 2019*.
#### 2018
- A Hybrid RNN-HMM Approach for Weakly Supervised Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/1906.01028.pdf)
    - Hilde Kuehne, Alexander Richard, and Juergen Gall, *TPAMI 2018*.
- Action Sets: Weakly Supervised Action Segmentation Without Ordering Constraints,
  [[pdf]](https://alexanderrichard.github.io/publications/pdf/richard_action_sets.pdf)
  [[code]](https://github.com/alexanderrichard/action-sets)
    - Alexander Richard, Hilde Kuehne, and Juergen Gall, *CVPR 2018*.
- NeuralNetwork-Viterbi: A Framework for Weakly Supervised Video Learning,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2018/papers/Richard_NeuralNetwork-Viterbi_A_Framework_CVPR_2018_paper.pdf)
  [[code]](https://github.com/alexanderrichard/NeuralNetwork-Viterbi)
    - Alexander Richard, Hilde Kuehne, Ahsan Iqbal, and Juergen Gall, *CVPR 2018*.
- Weakly-Supervised Action Segmentation with Iterative Soft Boundary Assignment,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2018/CameraReady/1522.pdf)
  [[code]](https://github.com/ld-ing/TCFPN-ISBA)
    - Li Ding and Chenliang Xu, *CVPR 2018*.
#### 2017
- Weakly supervised action learning with RNN based fine-to-coarse modeling,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2017/papers/Richard_Weakly_Supervised_Action_CVPR_2017_paper.pdf)
  [[code]](https://github.com/alexanderrichard/weakly-sup-action-learning)
    - Alexander Richard, Hilde Kuehne, and Juergen Gall, *CVPR 2017*.
- Weakly supervised learning of actions from transcripts,
  [[pdf]](https://arxiv.org/pdf/1610.02237.pdf)
    - Hilde Kuehne, Alexander Richard, and Juergen Gall, *CVIU 2017*.
#### 2016
- Connectionist temporal modeling for weakly supervised action labeling,
  [[pdf]](https://arxiv.org/pdf/1607.08584.pdf)
  [[code]](https://github.com/daahuang/lasagne-ectc)
    - De An Huang, Fei-Fei Li, and Juan Carlos Niebles, *ECCV 2016*.
### Unsupervised
#### 2024
- Temporally Consistent Unbalanced Optimal Transport for Unsupervised Action Segmentation,
     - Ming Xu and Stephen Gould, *CVPR2024*.
- OTAS: Unsupervised Boundary Detection for Object-Centric Temporal Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2024/papers/Li_OTAS_Unsupervised_Boundary_Detection_for_Object-Centric_Temporal_Action_Segmentation_WACV_2024_paper.pdf)
  [[code]](https://github.com/yl596/OTAS)
     - Yuerong Li, Zhengrong Xue and Huazhe Xu, *WACV2024*.
#### 2023
- Leveraging triplet loss for unsupervised action segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2023W/L3D-IVU/papers/Bueno-Benito_Leveraging_Triplet_Loss_for_Unsupervised_Action_Segmentation_CVPRW_2023_paper.pdf)
  [[code]](https://github.com/elenabbbuenob/TSA-ActionSeg)
    - Elena Belen Bueno-Benito, Biel Tura Vecino, and Mariella Dimiccoli, *CVPRW 2023*.
- TAEC: Unsupervised action segmentation with temporal-Aware embedding and clustering,
  [[pdf]](https://arxiv.org/pdf/2303.05166.pdf)
    - Wei Lin, Anna Kukleva, Horst Possegger, Hilde Kuehne, and Horst Bischof, *CEURW 2023*.
#### 2022
- Fast and Unsupervised Action Boundary Detection for Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Du_Fast_and_Unsupervised_Action_Boundary_Detection_for_Action_Segmentation_CVPR_2022_paper.pdf)
    - Zexing Du, Xue Wang, Guoqing Zhou, and Qing Wang, *CVPR 2022*.
- My View is the Best View: Procedure Learning from Egocentric Videos,
  [[pdf]](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136730656.pdf)
  [[code]](https://sid2697.github.io/egoprocel)
    - Siddhant Bansal, Chetan Arora, and C V Jawahar, *ECCV 2022*.
- Temporal Action Segmentation with High-level Complex Activity Labels,
  [[pdf]](https://arxiv.org/pdf/2108.06706.pdf)
    - Guodong Ding and Angela Yao, *TMM 2022*.
- Unsupervised Action Segmentation by Joint Representation Learning and Online Clustering,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2022/papers/Kumar_Unsupervised_Action_Segmentation_by_Joint_Representation_Learning_and_Online_Clustering_CVPR_2022_paper.pdf)
  [[code]](https://bit.ly/3JKm0JP)
    - Sateesh Kumar, Sanjay Haresh, Awais Ahmed, Andrey Konin, M. Zeeshan Zia, and Quoc Huy Tran, *CVPR 2022*.
#### 2021
- Action Shuffle Alternating Learning for Unsupervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Li_Action_Shuffle_Alternating_Learning_for_Unsupervised_Action_Segmentation_CVPR_2021_paper.pdf)
    - Jun Li and Sinisa Todorovic, *CVPR 2021*.
- Joint Visual-Temporal Embedding for Unsupervised Learning of Actions in Untrimmed Sequences,
  [[pdf]](https://openaccess.thecvf.com/content/WACV2021/papers/VidalMata_Joint_Visual-Temporal_Embedding_for_Unsupervised_Learning_of_Actions_in_Untrimmed_WACV_2021_paper.pdf)
    - Rosaura G Vidalmata, Walter J Scheirer, Anna Kukleva, David Cox, and Hilde Kuehne, *WACV 2021*.
- Temporally-Weighted Hierarchical Clustering for Unsupervised Action Segmentation,
  [[pdf]](https://openaccess.thecvf.com/content/CVPR2021/papers/Sarfraz_Temporally-Weighted_Hierarchical_Clustering_for_Unsupervised_Action_Segmentation_CVPR_2021_paper.pdf)
  [[code]](https://github.com/ssarfraz/FINCH-Clustering/tree/master/TW-FINCH)
    - M Saquib Sarfraz, Naila Murray, Vivek Sharma, Ali Diba, Luc Van Gool, and Rainer Stiefelhagen, *CVPR 2021*.
#### 2020
- Action Segmentation with Joint Self-Supervised Temporal Domain Adaptation,
  [[pdf]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Chen_Action_Segmentation_With_Joint_Self-Supervised_Temporal_Domain_Adaptation_CVPR_2020_paper.pdf)
  [[code]](https://github.com/cmhungsteve/SSTDA)
    - Min-Hung Chen, Baopu Li, Yingze Bao, Ghassan AlRegib, and Zsolt Kira, *CVPR 2020*.
#### 2019
- Unsupervised learning of action classes with continuous temporal embedding,
  [[pdf]](https://arxiv.org/pdf/1904.04189.pdf)
  [[code]](https://github.com/annusha/unsup_temp_embed)
    - Anna Kukleva, Hilde Kuehne, Fadime Sener, and Jurgen Gall, *CVPR 2019*.
- Unsupervised procedure learning via joint dynamic summarization,
  [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Elhamifar_Unsupervised_Procedure_Learning_via_Joint_Dynamic_Summarization_ICCV_2019_paper.pdf)
    - Ehsan Elhamifar and Zwe Naing, *ICCV 2019*.
#### 2018
- Unsupervised Learning and Segmentation of Complex Activities from Video,
  [[pdf]](https://openaccess.thecvf.com/content_cvpr_2018/papers/Sener_Unsupervised_Learning_and_CVPR_2018_paper.pdf)
  [[code]](https://github.com/Annusha/slim_mallow)
    - Fadime Sener and Angela Yao, *CVPR 2018*.
#### 2016
- Unsupervised learning from narrated instruction videos,
  [[pdf]](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Alayrac_Unsupervised_Learning_From_CVPR_2016_paper.pdf)
    - Jean-Baptiste Alayrac, Piotr Bojanowski, Nishant Agrawal, Josef Sivic, Ivan Laptev, and Simon Lacoste-Julien, *CVPR 2016*.
#### 2015
- Unsupervised Semantic Parsing of Video Collections,
  [[pdf]](https://openaccess.thecvf.com/content_iccv_2015/papers/Sener_Unsupervised_Semantic_Parsing_ICCV_2015_paper.pdf)
    - Ozan Sener, Amir R. Zamir, Silvio Savarese, and Ashutosh Saxena, *ICCV 2015*.
### Semi-Supervised
#### 2022
- Iterative Contrast-Classify for Semi-supervised Temporal Action Segmentation,
  [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/view/20124/19883)
  [[code]](https://github.com/dipika-singhania/ICC-Semi-Supervised-TAS)
    - Dipika Singhania, Rahul Rahaman, and Angela Yao, *AAAI 2022*.
- Leveraging Action Affinity and Continuity for Semi-supervised Temporal Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2207.08653.pdf)
  [[code]](https://github.com/dinggd/semitas)
    - Guodong Ding and Angela Yao, *ECCV 2022*.
### Online
#### 2024
- Progress-Aware Online Action Segmentation for Egocentric Procedural Task Videos,
    - Yuhan Shen and Ehsan Elhamifar, *CVPR2024*.
### Continual
#### 2024
- Coherent Temporal Synthesis for Incremental Action Segmentation,
  [[pdf]](https://arxiv.org/pdf/2403.06102.pdf)
    - Guodong Ding, Hans Golong and Angela Yao, *CVPR2024*.







## Citation
If you find this repository helpful in your research, please consider citing our survey as:
```
@article{ding2022temporal,
    title={Temporal Action Segmentation: An Analysis of Modern Techniques},
    author={Ding, Guodong and Sener, Fadime and Yao, Angela},
    journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
    year={2023}
}
```

## Feedback
- [pull request](https://github.com/atlas-eccv22/awesome-temporal-action-segmentation/pulls)