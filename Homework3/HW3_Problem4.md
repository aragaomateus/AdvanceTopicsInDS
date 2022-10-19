# Problem 4 - Weakly and Semi-Supervised Learning for Image Classification

This problem is based on two papers, by Mahajan et al. on weakly supervised pretraining and by Yalinz et al. on semi-supervised learning for image classification. Both of these papers are from Facebook and used 1B images wiith hashtags. Read the two papers thoroughly and then answer the following questions. You can discuss these papers with your classmates if this helps in clarifying your doubts and improving your understanding. However no sharing of answers is permitted and all the questions should be answered individually in your own words.

References
• Yalniz et al. Billion-scale semi-supervised learning for image classification. Available at https://arxiv.org/pdf/1905.00546.pdf
• Mahajan et al. Exploring the Limits of Weakly Supervised Pretraining. Available at https://arxiv.org/pdf/1805.00932.pdf

1. Both the papers use the same 1B image dataset. However one does weakly supervised pretraining while the other does semi-supervised . What is the difference between weakly supervised and semi-supervised pretraining ? How do they use the same dataset to do two different types of pretraining ? Explain.




2. These questions are based on the paper by Mahajan et al.
(a) Are the model trained using hashtags robust against noise in the labels ? What experiments were done in the paper to study this and what was the finding ? Provide numbers from the paper to support your answer. (2)

(b) Why is resampling of hashtag distribution important during pretraining for transfer learning ?

3. These questions are based on the paper by Yalzin et al.

(a) Why are there two models, a teacher and a student, and how does the student model leverages the
teacher model ? Explain why teacher-student modeling is a type of distillation technique. (2+2)

(b) What are the parameters K and P in stage 2 of the approach where unlabeled images are assigned classes using teacher network ? What was the idea behind taking P > 1 ? Explain in your own words. (2+2)

(c) Explain how a new labeled dataset is created using unlabeled images ? Can an image in this new dataset belong to more than one class ? Explain. (2+2)

(d) Refer to Figure 5 in the paper. Why does the accuracy of the student model first improves as we increase the value of K and then decreases ? (2)
