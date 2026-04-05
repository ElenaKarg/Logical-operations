# Logical-operations
AND, OR and NOT

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load images
img1 = cv2.imread('C:/Users/elena/Desktop/mushroom.jpg', cv2.IMREAD_GRAYSCALE)
img2 = cv2.imread('C:/Users/elena/Desktop/butterfly.jpg', cv2.IMREAD_GRAYSCALE)

# Resize second image to match first
img2_resized = cv2.resize(img2, (img1.shape[1], img1.shape[0]))

# Logical operations
and_img = cv2.bitwise_and(img1, img2_resized)
or_img = cv2.bitwise_or(img1, img2_resized)
not_img1 = cv2.bitwise_not(img1)
not_img2 = cv2.bitwise_not(img2_resized)

# Visualize
plt.figure(figsize=(12, 6))

titles = ['Original 1', 'Original 2', 'AND', 'OR', 'NOT Image 1', 'NOT Image 2']
images = [img1, img2_resized, and_img, or_img, not_img1, not_img2]

for i in range(6):
    plt.subplot(2, 3, i+1)
    plt.imshow(images[i], cmap='gray')
    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()
