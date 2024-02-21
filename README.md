# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image


### Developed By:  V.S.Janani
### Register Number: 212222230050
### Program:

### i) Read and display the image

```
    import cv2
    image=cv2.imread('pic.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('flower',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```


## Output:

![ex1](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/539748bc-710e-47a5-bdde-c3a7485c9f44)


### ii)Write the image
```
    image=cv2.imread('pic.jpg',0)
    cv2.imwrite('a.jpeg',image)
```
## Output:

![ex1 1](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/d3241afe-a272-46a0-81f0-2a57a7c7b06e)


### iii)Shape of the Image
```
    import cv2
    image=cv2.imread('pic.jpg',1)
    print(image.shape)
```
## Output:

![ex1 2](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/5a5b0318-f914-49e7-bad9-c599cb03204f)


### iv)Access rows and columns
```
    import random
    import cv2
    image=cv2.imread('pic.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('car part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:
![ex1 3](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/53bfd58b-5133-47e8-8f53-b7844f4b0554)


### v)Cut and paste portion of image
```
  import cv2
  image=cv2.imread('pic.jpg',1)
  image=cv2.resize(image,(400,400))
  tag =image[130:200,110:190]
  image[110:180,120:200] = tag
  cv2.imshow('cut and paste',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()
```
## Output:
![ex1 4](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/eb5d7562-1913-4dc0-a9b0-b7e5879e964f)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('pic.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:

![ex1 5](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/309395cd-012c-4da7-a336-3ead1ae400c4)


### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('pic.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![ex1 6](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/8f861768-f14b-4036-b66d-f66e944e561d)


### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('pic.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![8](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/290306df-6b7d-4c10-b6ba-4c7b331c2de0)



### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('pic.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![9](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/c43a1338-debb-4615-8e84-f24c693616f3)


### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("pic.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![10](https://github.com/janani225/COLOR_CONVERSIONS_OF-IMAGE/assets/113497333/7aecd053-afa5-45cc-bcf4-582b9ccc9c5b)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







