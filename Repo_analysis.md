# Analysis of Identification of lincRNA as predictive biomarkers in breast cancer

Breast cancer is the most common malignant neoplasia in women ([WHO](https://www.who.int/cancer/prevention/diagnosis-screening/breast-cancer/en/)). For that reason, there are many clinical strategies diagnosis and treatment-decision tools based principally in detection of proteins by immunhistochemical techniques or by PCR analysis (to detect mRNA) (Patani, 2013).
However, less than %50 of the patients could respond to treatment in the clinical outcome, generating the necessity of better oncological management. In that sense, the development of better techniques is the new focus of traslational medicine (Alcaraz, 2017) and many of them are based in molecular biology techniques. One of this techniques is RNA Next Generation Sequencing
(RNA-Seq, Külahoglu, 2014), which provide us the information of all transcriptomic context of a given sample, like a breast tumor sample, and allowed us to make clinical decision (Berger, 2018).

In here, we analized 10 samples from 10 patients diagnosed with breast cancer which where candidates to receive neoadjuvant treatment. Samples were took before pharmacological administration and the RNA was extracted for RNA-Seq implementation (paired end, depth > 15 million reads). Then, clinical following was performed and we obtain 2 groups: No response patientes (8) and Response to neoadjuvant treatment patients (2).
With this information, we performed a differentiall expression analysis in order to identify lincRNA which could be candidates to be a biomarkers in response to treatment (Wang, 2018). For that, we used Bioconductor tools in R to align and count (QuasR) and to perform differential expression analysis (DESeq2).

In our results, we found that there is a set of lincRNA that are differentially over-expressed in No response patients (No_response group) (See heatmap.jpg and pca.jpg in /Graphs and differential expression results table in /results). For that, we selected only significant log2FoldChange values (p<0.05) and only genes that were over-expressed at a cutof > 1.5 of log2FoldChange value. Although there is mRNA differentially over-expressed
too, we notice that most of our differential expressed coding genes were already reported in other works, and this validate our results, but it didn't represent a real contribution. However, there is no information about the lincRNA in our results, which make it an opportunity to know more about breast cancer molecular processes. Although it is and opportunity, is a dissadvantage too, because 
we have problems to elucidate the significant value of the expression of this lincRNA and how they contribute to breast carcinogenesis, and because of that it is a perspective to validate experimentally our results.

![volcano_plot.JPG](https://github.com/LauraMCE/lncRNA_BC/blob/master/Transcriptome/Graphs/volcano_plot.JPG)

Figure 1: Volcano plot from differential expression analysis that shows only lincRNA differentially expressed in No response patients.

![heatmap.JPG](https://github.com/LauraMCE/lncRNA_BC/blob/master/Transcriptome/Graphs/heatmap.JPG)

Figure 2: Heatmap from differential expression analysis in which we is observed the set of top lincRNA which are related to No response to neadjuvant treatment.

![pca.JPG](https://github.com/LauraMCE/lncRNA_BC/blob/master/Transcriptome/Graphs/pca.JPG)

Figure 3: Principal component analysis plot in which is shown the similarityin lincRNA expression of No response patients group, respect to Response group.

Experimental validation has another problems, because of the lower expression levels of lincRNAs in tissues, which is important for the regulatory function that they have in physiological conditions (Quinn, 2016). However, many bioinformatic tools are available to make approximations of lincRNA properties and functions, which makes this perspective more plausible.

Another design problem is the fact that we only have 10 patients, and that had the consequence that we had troubles to perform Gene Set enrichment analysis, for example, and also we know that we have an stadistical bias in our differential expression analysis results. To solve that, we must use the metric Diff_of_Class as is specified in GSEA [documentation](http://software.broadinstitute.org/gsea/doc/GSEAUserGuideFrame.html?Consistent_Features), however, the statistical bias is still remaining. Another perspective is to take more samples to RNA-Seq processing, and analize if our lincRNA set is maintained.

We know that only one clinical parameter is not enough to determine clinical outcomes and response to treatment in breast cancer (Berger, 2018). For that reason, we also performed and exome next generation sequencing for some of our 10 samples (2 of No_response group and 2 of Response group), in order to analize the combination of lincRNA expression and exome variants as biomarkers
in breast cancer. Because of technical problems with sequencing processing, principally with the quality of the samples, we are waiting for that results, in order to analize the impact of these 2 parameters in the clinical routine. To this date, we couldn't have the exme sequencing results, so is a perspective for this work,  and this is the principal reason why ../Exome/data is not properly filled and the reason why the scripts in ../Exome/bin weren't proved yet (see [issue](https://github.com/LauraMCE/lncRNA_BC/issues/26#issue-517289033)).

Thus, we only have results from transcriptomic analysis, in which we can observe that there is a lincRNA set capable to describe molecularly No responsive breast cancer patients to neoadjuvant treatment. Bioinformatic approach allowed us to elucidate the lincRNA which are candidates to validation as possible clinical biomarkers in oncological management.
