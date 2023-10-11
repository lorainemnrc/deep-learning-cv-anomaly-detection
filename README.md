![title](https://github.com/lorainemnrc/deep-learning-cv-anomaly-detection/assets/23328647/dd7b365a-f3a4-4592-8262-e3cdac8a6bcd)

<h1 style="color: #1048CB"><b>Overview</b></h1>

In manufacturing industries, quality assurance and control is one of the most vital parts of the process. It ensures that the goods, products, and/or services that go into stock and are delivered/provided to customers achieve the highest level of quality possible. Such quality is achieved by ensuring these deliverables meet a certain level of standard, and never go below a certain threshold. However, for manufacturing industries, ensuring such quality can be a challenging task because of the defect's rarity, scale, sensitivity, and spectrum [(Zou, et. al., 2022)](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136900389.pdf).

These challenges pose a threat to the manufacturing industry, especially in the Philippines, where the industry is currently thriving. The semiconductor manufacturing industry in the Philippines has been silently dominating the country’s value of export. In 2022, 83% of the total export value from the country’s top commodity groups came from electronics products, beating out other minerals and other manufactured goods [(PSA, 2022)](https://psa.gov.ph/content/highlights-philippine-export-and-import-statistics-august-2022-preliminary). This was also a 40% jump in export value from the 2021 figures. Of these electronic products, 47.4% accounted for semiconductors, with an equivalent export value of 1.6 trillion pesos (or $28.7B) [(Statista, 2022)](https://www.statista.com/statistics/1264606/philippines-export-share-of-semiconductors). A simple miscalculation in quality equates to millions of pesos in losses which is not ideal for a business. Thus, it is imperative to create a system for early prediction and prevention of component defects in manufacturing processes.

<p align="justify"> &emsp;
The team believes that these challenges can be solved by leveraging the use of machine learning and the advancement in artificial intelligence (AI). The problems of rarity, scale, sensitivity, and spectrum can be answered by combining concepts of advanced data mining, deep learning techniques, and explainable AI which can be used in the quality management of manufacturing industries.
<p/>

<h1 style="color: #1048CB"><b>Data Source</b></h1>

The dataset used for this experiment is the Visual Anomaly (VisA) dataset, which was an original curation of [Zou et. al. (2022)](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136900389.pdf). VisA can also be retrieved from the [Registry of Open Data on Amazon Web Services (AWS)](https://registry.opendata.aws/visa/).

<p align="justify"> &emsp;
It is the largest visual anomaly detection dataset containing 12 classes in 3 domains, with around 10,821 images, 9,621 of which are normal images, and 1,200 anomalous. For this study, we selected six classes namely Cashew, Chewing Gum, Fryum, Macaroni (Macaroni 1), Printed Circuit Board (PCB) 1, and PCB 3 (which will be referred to hereinafter as PCB 2).
<p/>

<br>
<center style="font-size:12px;font-style:default;"><b>Table. Overview of the Selected VisA Subsets</b></center>
| Domain | Object | Normal | Anomalous | Anomaly Classes |
| :--: | :--: | :--: | :--: | :--: |
| Single Instance | Cashew | 500 | 100 | 9 |
|  | Chewing Gum | 503 | 100 | 6 |
|  | Fryum | 500 | 100 | 8 |
| Multiple Instances | Macaroni | 1,000 | 100 | 7 |
| Complex Structure | PCB1 | 1,004 | 100 | 4 |
|  | PCB2 | 1,006 | 100 | 4 |



<p align="justify"> &emsp;
The dataset has different images for normal, anomalous, and segmented anomalies for each of the 12 items or classes. The three domains of the subsets are single instance, multiple instances (both simple structures) and complex structure. The entire methodology from data preprocessing, feature extraction, model evaluation, and the inference was done for two deep learning models that combine image classification, object segmentation, and anomaly detection - the (1) Patch Distribution Model (PaDiM) and (2) Conditional Normalizing Flows for Anomaly Detection (CFLOW-AD).
<p/>

<h1 style="color: #1048CB"><b>Highlights</b></h1>

<p align="justify"> &emsp;
Our overall implementation of <strong><em>Padim<em/><strong/> and <strong><em>Cflow<em/><strong/> is an effective implementation of anomaly detection and localization. The model evaluation metric scores are comparable to our set benchmark, with <strong><em>Padim<em/><strong/> beating out every model in terms of sensitivity rate. Hence, our implementation is as effective as the implementation of our benchmark models.
</p>
  
<p align="justify"> &emsp;
Focusing on each of the subsets, the team states that there is no one-model-fits-all for this anomaly detection task. With our experiment involving six out of the twelve subsets of the VisA dataset, we see how <strong><em>Padim<em/><strong/> and <strong><em>Cflow<em/><strong/>'s performances change for each subset. If we were to be asked what the rule of thumb is in selecting the better model for a certain object, the team states that for simpler objects or components such as chewing gum and cashews, any of the models can be used and will provide fairly accurate results. For more complex objects, however, <strong><em>Padim<em/><strong/> is the better model to use as it exemplifies high sensitivity across all subsets while maintaining high accuracy in terms of classifying anomalous images.
</p>
