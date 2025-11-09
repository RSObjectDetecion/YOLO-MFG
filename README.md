# YOLO-MFG
This repository contains the average result of multiple runs(including confidence intervals) and ablation experiments results for our paper:

multiple runs:

To ensure the reliability of the experimental results, we have selected five random seeds (42, 2025, 3047, 2003, 2024) and conducted two runs for each seed. As shown, the proposed model achieved an average mAP₅₀ of 81.69 ± 0.13, with the best result reaching 81.9.
<p align="center">
<img width="325" height="455" alt="multi runs" src="https://github.com/user-attachments/assets/5187230e-f911-4223-8577-75f73ffe9739" />
</p>


Ablation experiments:

The reason for the 4-way split in MGSA is optimal: Our design initially followed the typical three-scale distribution in remote sensing imagery, namely small, medium, and large objects, motivating a three-way channel split. However, since the number of channels in backbone is generally a power of two (2^n), a strict three-way equal division is infeasible. Therefore, we adopt a four-way split as a principled compromise. We evaluated three configurations: C/4+C/4+C/2, C/4+C/2+C/4, and C/2+C/4+C/4, C denotes the number of input channels. The first configuration achieved the best performance. 
<p align="center">
<img width="1151" height="132" alt="Split Config" src="https://github.com/user-attachments/assets/99b6f38c-8c81-48fa-8089-1d6d6575d760" />
</p>


The theoretical basis for the gating parameter initialization at 0.5 in GEA: It ensures a balanced start between global and local pathways, avoiding early dominance of either attention or convolutional features. We have added experiments with 0, 1, 0.25, and 0.75 and found 0.5 yields more stable optimization and better final accuracy.
<p align="center">
<img width="826" height="138" alt="Gating Parameter" src="https://github.com/user-attachments/assets/5a2b77a0-e1e4-47ad-9aa0-c040ae4bc9f2" />
</p>



attention range L in Equation 2: We conducted experiments on four moderate values (5, 7, 9, 11) on the SIMD dataset. The best performance was achieved when L=7. The experimental results are as follows.
<p align="center">
<img width="782" height="142" alt="Attention Range L" src="https://github.com/user-attachments/assets/c0a35e82-5e60-4959-b6c6-9f20512eeeb9" />
</p>


We conducted experiments on four common large kernel size (5, 7, 9, 11) on the SIMD dataset. The best performance was achieved when K=7. The experimental results are as follows.
<p align="center">
<img width="718" height="135" alt="Kernel size K" src="https://github.com/user-attachments/assets/4fcc9028-9fe1-4c92-b1b2-54d7bc902c94" />
</p>

