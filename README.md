# Medical-Image-Segmentation-and-Enhancement

1.Introduction
Brain Tumor is caused by the uncontrolled magnification of tissue in the brain or central spine that can disrupt proper brain function. Primary brain tumors originate from cells within the brain and secondary (metastatic) brain tumors begin in another part of the body and then spread to the brain. Brain tumors can be cancerous (malignant) or non-cancerous (benign). There are over 120 brain tumor relegations defined by the WHO, predicated on the tumor cell type and location. They are graded based on the cells where they arise, and a number ranging from I-IV. Grades I and II are considered as lower grade tumors, and III and IV are considered as higher grade tumors. Brain tumors can be life-threatening and thus precise diagnosis and necessary treatment is vital for a patient. In the pathology lab, tumor tissue analysis is carried out by utilizing Microscopic analysis such as biopsy ⎯ Electronic modalities such as CT, Ultrasound, MRI etc. Among all electronic modalities Magnetic Resonance Imaging (MRI) is one of the most used and popular for brain tumor diagnosis. It takes a high resolution and high contrast images of the brain in the axial, coronal and sagittal orientation providing a three-dimensional assessment of the lesion. 
In this project, we will be performing some approaches where MRI gray-scale images were incorporated for brain tumor detection. Brain tumor images were taken as input and medical image processing techniques such as pre-processing and post-processing were incorporated to identify the tumor region only. The pre-processing includes enhancement, filter operation, and segmentation and post-processing includes feature extraction and identification. 

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/8de2c46f-c784-4e79-a514-35936e21af9d)

2.Objectives
Brain cancer is a destructive and life-threatening disease that imposes immense negative effects on patients' lives. Therefore, the aim of the project is to detection of brain tumors at an early stage improves the impact of treatments and increases the patient’s survival rates. However, detecting brain tumors in their initial stages is a demanding task and an unmet need. [3]

2.1	Features
Our project has some features that are:
2.1.1	Image Enhancement:
Image enhancement refers to the process of highlighting certain information of an image, as well as weakening or removing any unnecessary information according to specific needs. For example, eliminating noise, revealing blurred details, and adjusting levels to highlight features of an image.
Image enhancement techniques can be divided into two broad categories:

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/b1952771-82ba-48c0-9f9c-8ada6ef0bc70)

•	Spatial domain — enhancement of the image space that divides an image into uniform pixels according to the spatial coordinates with a particular resolution. The spatial domain methods perform operations on pixels directly.
•	Frequency domain — enhancement obtained by applying the Fourier Transform to the spatial domain. In the frequency domain, pixels are operated in groups as well as indirectly.

2.2.2	Noise removal using median filter:
The median filter is a non-linear digital filtering technique, often used to remove noise from an image or signal. Such noise reduction is a typical pre-processing step to improve the results of later processing (for example, edge detection on an image). Median filtering is very widely used in digital image processing because, under certain conditions, it preserves edges while removing noise (but see the discussion below), also having applications in signal processing.
The main idea of the median filter is to run through the signal entry by entry, replacing each entry with the median of neighboring entries. The pattern of neighbors is called the "window", which slides, entry by entry, over the entire signal. For one-dimensional signals, the most obvious window is just the first few preceding and following entries, whereas for two-dimensional (or higher-dimensional) data the window must include all entries within a given radius or ellipsoidal region (i.e. the median filter is not a separable filter).

2.2.3	Image Segmentation using OTSU method:
The process of separating the foreground pixels from the background is called thresholding. There are many ways of achieving optimal thresholding and one of the ways is called the Otsu’s method, proposed by Nobuyuki Otsu. Otsu’s method is a variance-based technique to find the threshold value where the weighted variance between the foreground and background pixels is the least. The key idea here is to iterate through all the possible values of threshold and measure the spread of background and foreground pixels. Then find the threshold where the spread is least.
Segmentation divides the image into regions based on the similar attributes. Basically, segmentation was performed to extract important features from the image for further analysis. Thresholding based Otsu’s method is used of its wide uses to segment an image for further processing like feature analysis as well as to do the binary transformation of an image. It also takes less time to compute the threshold value than other techniques as the mathematical expression is simple. During research, it has been found that in RGB gray scale image only green and blue channels are required to detect brain tumor. As a result, the threshold based Otsu’s segmentation was performed only on the resultant image of green and blue channels and the red channel was discarded.  In this study, the resultant image was generated by adding the green and blue channels and then computed the complement of the resultant image. The Otsu’s method was applied on the complemented image and transformed the image into a binary image containing only values 0 and 1 where 0 shows black and 1 shows white color. 

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/c7b48a47-8a45-4ae9-92f1-be4c2bbed83f)

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/86b508fe-dbff-43f5-a6bd-73647fb0051d)

3.PROPOSED METHADOLOGY
BLOCK DIAGRAM:
                                                   ![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/7d5b3f73-56ef-4c2a-b68f-a5f0de45cd37)

4	Simulation Results
4.1	software simulation results
We have simple thresholding where we manually supply parameters to segment the image — this works extremely well in controlled lighting conditions where we can ensure high contrast between the foreground and background of the image. 
Methods like as Otsu’s thresholding that attempt to be more dynamic and automatically compute the optimal threshold value based on the input image. 
And finally we have adaptive thresholding which, instead of trying to threshold an image globally using a single value, instead breaks the image down into smaller pieces, and thresholds each of these pieces separately and individually.[14]

Otsu’s thresholding:
Which automatically determines the threshold value. The benefit of Otsu’s thresholding technique is that we don’t have to fiddle with manually setting the threshold cutoff — Otsu’s method will do that automatically for us.

CT scan of brain show Ischemic Stroke or Hemorrhagic Stroke:
                                                                               
![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/93dd751b-e22b-4a3c-9bd2-a068bc1821cd)

Output:
![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/3822595c-122f-4f39-ad18-b89c60eb7a5c)

Let us set the threshold value to v=220 

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/683dcc15-282f-4efd-a945-03a2d5ee4935)

CT scan of brain showing Meningioma:

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/8fad85cd-fdc6-4ec0-b4e7-b0b95bd7eae1)

![image](https://github.com/MahinAsif99/Medical-Image-Segmentation-and-Enhancement/assets/148430248/28c750c3-3d8a-41c1-9a86-0abdee6ece7a)

Description
Otsu’s algorithms simply assume that a grayscale image consists of two types of pixels. Foreground and background pixels. It divides all the pixels into two clusters. It minimizes the intra-cluster variation by maximizing the inter-cluster variance. Finally, it returns a single intensity value which is called a threshold value. This threshold value divides the two clusters of pixels. All pixels of one cluster are assigned intensity value 0 and pixels of the second cluster are assigned value 1. Thus, it binaries the grayscale image.

5.Conclusion
The image segmentation is a relevant technique in image processing. Numerous and varied methods exist for many applications. Now that we have described the algorithms, we can compare the outputs and check which type of segmentation technique is better for a particular format. It is believed that there are two key factors which allow for the use of a segmentation algorithm in a larger object detection system: correctness and stability.

Manual detection of brain tumor is not only a tedious process but also time consuming whereas an automated approach takes less time. This study proposed approach reduces time and provides higher accuracy compared to other existing approaches. As early detection of tumor is very important for a brain tumor patient, this research will assist the pathologists to detect brain tumor more quickly with higher accuracy. But it is still possible to increase the accuracy rate. If experts intra and inters observation variability issues can be minimized, then in future it will be possible to increase the accuracy rate.







                                                    


                                              


