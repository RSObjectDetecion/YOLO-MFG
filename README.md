# YOLO-MFG

The reason for the 4-way split in MGSA is optimal: Our design initially followed the typical three-scale distribution in remote sensing imagery, namely small, medium, and large objects, motivating a three-way channel split. However, since the number of channels in backbone is generally a power of two (2^n), a strict three-way equal division is infeasible. Therefore, we adopt a four-way split as a principled compromise. We evaluated three configurations: C/4+C/4+C/2, C/4+C/2+C/4, and C/2+C/4+C/4, C denotes the number of input channels. The first configuration achieved the best performance. 


The theoretical basis for the gating parameter initialization at 0.5 in GEA: It ensures a balanced start between global and local pathways, avoiding early dominance of either attention or convolutional features. We have added experiments with 0, 1, 0.25, and 0.75 and found 0.5 yields more stable optimization and better final accuracy.


attention range L in Equation 2: We conducted experiments on four moderate values (5, 7, 9, 11) on the SIMD dataset. The best performance was achieved when L=7. The experimental results are as follows.


We conducted experiments on four common large kernel size (5, 7, 9, 11) on the SIMD dataset. The best performance was achieved when K=7. The experimental results are as follows.
