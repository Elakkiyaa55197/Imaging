import cv2

# Load an image from file
image = cv2.imread('example.jpg')

# Resize the image to 300x300
resized_image = cv2.resize(image, (300, 300))

# Convert the image to grayscale
gray_image = cv2.cvtColor(resized_image, cv2.COLOR_BGR2GRAY)

# Apply Gaussian blur
blurred_image = cv2.GaussianBlur(gray_image, (5, 5), 0)

# Perform edge detection using Canny
edges = cv2.Canny(blurred_image, 50, 150)

# Display the images
cv2.imshow('Original', image)
cv2.imshow('Gray', gray_image)
cv2.imshow('Edges', edges)

# Wait for a key press and close windows
cv2.waitKey(0)
cv2.destroyAllWindows()
