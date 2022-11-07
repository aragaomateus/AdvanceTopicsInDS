# Problem 4 - Weakly and Semi-Supervised Learning for Image Classification

This problem is based on two papers, by Mahajan et al. on weakly supervised pretraining and by Yalinz et al. on semi-supervised learning for image classification. Both of these papers are from Facebook and used 1B images wiith hashtags. Read the two papers thoroughly and then answer the following questions. You can discuss these papers with your classmates if this helps in clarifying your doubts and improving your understanding. However no sharing of answers is permitted and all the questions should be answered individually in your own words.

References
• Yalniz et al. Billion-scale semi-supervised learning for image classification. Available at https://arxiv.org/pdf/1905.00546.pdf
• Mahajan et al. Exploring the Limits of Weakly Supervised Pretraining. Available at https://arxiv.org/pdf/1805.00932.pdf

1. Both the papers use the same 1B image dataset. However one does weakly supervised pretraining while the other does semi-supervised . What is the difference between weakly supervised and semi-supervised pretraining ? How do they use the same dataset to do two different types of pretraining ? Explain.

***Answer:***

Weakly supervisision is using supervision with noisy labels. The mahajan paper accomplishes this by using hashtags to label the data. Semi-supervised is when some of the data is labeled but other data isn't. The Yalinz does this by seperating the dataset into D, a dataset with only labeled data, and U a dataset with only unlabeled data.



2. These questions are based on the paper by Mahajan et al.
(a) Are the model trained using hashtags robust against noise in the labels ? What experiments were done in the paper to study this and what was the finding ? Provide numbers from the paper to support your answer. (2)
***Answer:***
The Mahajan paper claims that the model trained using hashtags are robust against noise in the labels. The authors randomly replaced p% of the hashtags in the Instagrams dataset with other hashtags. They found that a noise level of p = 10% leads to a loss of less than 1% in classification accuracy, and at p = 25% label noise, the reduction in accuracy is around 2%. These results suggest that label noise may be a limited issue if networks are 

(b) Why is resampling of hashtag distribution important during pretraining for transfer learning ?

***Answer:***

hashtags are governed by a Zipfian distribution. Prior studies in language modeling found that resampling Zipfian distributions reduces
the impact of the head of the word distribution on the overall training loss. resampling from the distribution is important to obtain good transfer to ImageNet image-classification tasks. using uniform or square-root sampling leads to an accuracy improvement of 5 to 6% irrespective of the number of ImageNet classes in the transfer task

3. These questions are based on the paper by Yalzin et al.

(a) Why are there two models, a teacher and a student, and how does the student model leverages the
teacher model ? Explain why teacher-student modeling is a type of distillation technique. (2+2)

***Answer:***

We use a teacher-student model since it produces a better model when we have fixed complexity. The student model leverages the teacher model by be trained on the output of the teacher model. The process of distalation is to compress a large model into a smaller once. A teacher-student model is a form of distallation because the teacher model is training on unlabeled data, and our student model is then trained on the teacher's predictions in order to mimic the teacher model. So we get the same effect with much less need time and computational power.

(b) What are the parameters K and P in stage 2 of the approach where unlabeled images are assigned classes using teacher network ? What was the idea behind taking P > 1 ? Explain in your own words. (2+2)

***Answer:***

K is how many examples we should be selecting from U for each label.

P is how many classes we want to save for each image.

The reason for choosing P > 1 is that it is difficult to properly identify our tail classes, so we need to ensure P > 1 so that they appear in our new dataset. 


(c) Explain how a new labeled dataset is created using unlabeled images ? Can an image in this new dataset belong to more than one class ? Explain. (2+2)

***Answer:***

We train the teacher model using the initial unlabeled data. Then the outputs from this model are used to create a new labeled dataset. There can be multiple labels if a image belongs to the top K images for multiple classes. 

(d) Refer to Figure 5 in the paper. Why does the accuracy of the student model first improves as we increase the value of K and then decreases ? (2)

***Answer:***

Accuracy first increases k due to increase in diversity as well as hardness of examples. But after a certain point these is too much noise and our performance drops.  
