# Monte-Carlo-Ensemble-Neural-Network (MCENN)
Software:
        Python 3.7.3
        Tensorflow 1.13.1

Usage Guide:

This package include the MCENN code and 10 datasets for testing.

1) Download all the zip files and extract all. 

2) Extract features from 2D image by ResNet50.

        #ResNet/MCENN_demo_eval_transfer.py
                Input data: 
                        2D images data/MCENN_demo_ADNI_2Ddata
                Output data:
                        data/MCENN_demo_renset_result_test.mat
3) MCENN classification

        #MCENN/MCENN_demo_eval.py
                Input data:
                        data/MCENN_demo_renset_result_test.mat
                Output data:
                        results/MCENN_demo_cn_ad_r0_SP4_FP1_.mat
4) results format  

        MCENN_demo_cn_ad_r0_SP4_FP1_.mat 
                500(100 times dropout, 5 trained models)*10(subjects)
        .Actual 500*10: original labels
        .Predicted 500*10: Predicted labels
        .Logits0/Logits1: probability predicted as lable=1 is 1./(1+exp(Logits0(1,:)-Logits1(1,:)))
        .P_Vote : Accuray, fscore, gmean, sensitivity and specificity  
