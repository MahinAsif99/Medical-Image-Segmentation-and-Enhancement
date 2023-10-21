Steps: 
1.	Read the colored image. 
2.	Convert it into a grayscale image. 
3.	Apply Median Filter to enhance the image plus,
4.	Apply Otsu’s thresholding function.
5.	“cv2.THRESH_BINARY”: If pixel intensity is greater than the set threshold, value set to 255, else set to 0 (black).
6.	Convert grayscale image into a binary image using a threshold. 
7.	Display the binary image. 
8.	Binarize the grayscale image using the local Otsu’s method. 
9.	Display the image.
10. Use google colab for quicker results. Google colab has all the directories available as compared to jupyter notebook or python etc.


Code:

Appendix (optional)
Write Simulation code etc…
import cv2
from PIL import ImageEnhance
from PIL import Image
from matplotlib import pyplot as plt
img = cv2.imread('/content/brain-ct2.jpeg',0)

# Apply global (simple) thresholding on image
ret1,th1 = cv2.threshold(img,127,255,cv2.THRESH_BINARY)

# Apply Otsu's thresholding on image
ret2,th2 = cv2.threshold(img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Apply Otsu's thresholding after Median filtering
blur = cv2.medianBlur(img,5)
ret3,th3 = cv2.threshold(blur,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

titles = ['Original Image','Global Thresholding (v=127)',"Otsu's Thresholding",'Median Filter + Otsu']
images = [img,th1,th2,th3]

for i in range(4):
   plt.subplot(2,2,i+1)
   plt.imshow(images[i], 'gray')
   plt.title(titles[i])
   plt.axis("off")

plt.show()
