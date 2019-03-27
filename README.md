# Vehicle-Re-ID
'Viewpoint-aware Attentive Multi-view Inference for Vehicle Re-identification'

Accepted by 2018 IEEE/CVF Conference on Computer Vision and Pattern Recognition

[Abstract]

Vehicle re-identification (re-ID) has the huge potential to contribute to the intelligent video surveillance. However, it
suffers from challenges that different vehicle identities with a similar appearance have little inter-instance discrepancy
while one vehicle usually has large intra-instance differences under viewpoint and illumination variations. Previous
methods address vehicle re-ID by simply using visual features from originally captured views and usually exploit
the spatial-temporal information of the vehicles to refine the results. In this paper, we propose a Viewpoint-aware
Attentive Multi-view Inference (VAMI) model that only requires visual information to solve the multi-view vehicle re-
ID problem. Given vehicle images of arbitrary viewpoints, the VAMI extracts the single-view feature for each input image
and aims to transform the features into a global multiview feature representation so that pairwise distance metric
learning can be better optimized in such a viewpointinvariant feature space. The VAMI adopts a viewpoint-aware
attention model to select core regions at different viewpoints and implement effective multi-view feature inference
by an adversarial training architecture. Extensive experiments validate the effectiveness of each proposed component
and illustrate that our approach achieves consistent improvements over state-of-the-art vehicle re-ID methods
on two public datasets: VeRi and VehicleID.

[Method Overview]

![Image text](https://raw.github.com/csyizhou/Vehicle-Re-ID/edit/master/img/VAMI.png)

An overview of the architecture of VAMI. The F Net is for learning single-view features containing vehicles’ intrinsic information such as model, color and type. Moreover, viewpoint features can be also learned so that the central point feature of each viewpoint cluster over the whole training set can be obtained and used for attention learning. The attention model aims to output viewpoint-aware attention maps from the input view image targeting at different viewpoints. To infer multi-view features from the obtained attentive single-view features, we design a conditional generative network trained by an adversarial architecture. The network of the real multi-view data branch is only available in the training phase. Auxiliary vehicle classifiers are configured at the end of D to help match the inferred multi-view features with correct input vehicles’ identities. Finally, given positive and negative vehicle pairs, a contrastive loss is designed to optimize the network for distance metric learning. (Best viewed in color.)
