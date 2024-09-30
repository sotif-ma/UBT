# UBT：Uncertainty-based-Transformer-Model-for-Dangerous-Scenarios-Detection-in-Autonomous-Driving


# Abstract
The traditional target detection algorithm in the intelligent vehicle perception system cannot maintain stable recognition performance in the unknown and changing road environment. We find that uncertainty quantification is of great significance in detecting unknown complex environments and helps to improve the robustness and safety of autonomous driving systems. Therefore, this paper proposes a Transformer object detection algorithm based on uncertainty. Firstly, the double Gaussian feature map network (DGF) is designed to quantify and utilize the uncertainty of the features derived from the backbone network. Secondly, we propose a RBF-based query filtering model(RBQF), which takes uncertainty sum as the index of query vector screening. At the same time, this paper proposes an uncertainty detection head (UDH); the final model output results are quantitative uncertainty, improved detection performance and enhanced algorithm reliability. To further prove the detection performance of the proposed method in real driving scenes, we use COCO, Cityscapes, FoggyCityscapes, RainCityscapes and self-made traffic scene datasets for verification, which shows that our algorithm is well applicable to large datasets and complex road scenes. 
![fig1](https://github.com/user-attachments/assets/98ba0eef-035e-4e7e-8435-e477e7be73dc)
# Model frame
![fig2](https://github.com/user-attachments/assets/1d0195dc-0f5b-49f7-be78-9394f6eb53d6)

# Experimental Result
![tab1](https://github.com/user-attachments/assets/70e1b12c-01ea-48b6-978c-9063a51659f8)
![tab2](https://github.com/user-attachments/assets/3e996552-1797-4986-82f0-bc48305bba64)
![tab3](https://github.com/user-attachments/assets/cdf539ed-aa39-4056-b82e-440ef17e67fc)
![tab4](https://github.com/user-attachments/assets/7fff716f-583a-4298-87d6-17995ece7842)
![tab5](https://github.com/user-attachments/assets/6428a521-82a8-437c-94d5-99f78c1c0aa1)


To study the recognition of key objects in traffic scenes, we compare the calibration of the four categories of person, bus, car, and motorcycle. Compared with the original model, the confidence of each category model output by our method can have a minor error with the accuracy, and the average confidence is also close to the average accuracy, especially in the category of people, which achieves a good effect. In the category of bus, it can be seen from the confidence distribution map that the proportion of high confidence outputs of our method is high.
![fig7](https://github.com/user-attachments/assets/9b4192c4-5694-45cf-afe6-3fcf9cfa83f1)

In terms of calibration, on the left side of the plot, the ordinate is the confidence and accuracy, on the right is the ECE value, where higher values indicate less reliable model confidence, and the abscissa is the 0-1 value for x or y regression. From the analysis of the figure, it can be seen that the ECE curve of the proposed method is lower than that of the original model in all aspects. The error is the largest when y is 1 in the category of person, indicating that the position prediction reliability of the model at the edge of the picture is poor. ECE is relatively more prominent in the bus category, while the proposed method still has an inevitable reduction in all positions.
![fig8](https://github.com/user-attachments/assets/c4114acf-bf58-4185-9d77-4decfb0224d9)

The comparison plot of x-y reflects the ECE of different positions in the picture under a specific category. The comparison plot of w-h is related to the size of the model prediction box. The larger the ECE error, the redder the color, and the darker the color. The proposed method has lower ECE values and darker colors at any position and target box size. For the category of people, when w is 0.75 and h is about 0.4, our method has a smaller ECE value than baseline(DINO), indicating that it has a more reliable confidence level for larger prediction boxes. For the category of buses, baseline has a large error when the values of w and h are very small, indicating that its estimation of small targets far away is insufficient. Our method has some relief on this problem.
![fig9](https://github.com/user-attachments/assets/eaa69b1b-4ab1-4c70-b2e0-7ecb3969c2e9)

# Ablation experiment
![tab6](https://github.com/user-attachments/assets/fb7e9077-e216-4068-9fa7-c9e0c7bef45f)

# Visual Analysis
The first legend selects a traffic intensive scene with noticeable foreground and background. For the foreground object, the confidence values of the baseline and our method are 83.7% and 86.1%, respectively. For the controversial target behind the picture, such as the umbrella with only half of the edge exposed, the confidence of baseline and the proposed method are 52.2% and 47.0% respectively, indicating that the proposed method will have higher confidence for the obvious and more confident target, while it will be very cautious for the controversial target. The second and third legends select more complex traffic scenes. Compared with the baseline, our method can output higher confidence for some obvious large targets, has correct output box results for fuzzy small targets, and has more rational confidence judgment, which verifies that our method has better reliability in complex traffic scenes.
![fig6](https://github.com/user-attachments/assets/51ca4078-56ef-4c57-82b9-33fe6f972b84)


