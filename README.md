# Im_a_champion
no
# buoi 1
from cv2 import cv2
img = cv2.imread('3.PNG',1) 
img = cv2.resize(img,(0,0),fx = 0.3,fy=0.3)
img = cv2.rotate(img,cv2.ROTATE_90_CLOCKWISE)
img = cv2.imshow('cua so hien thi',img)
k = cv2.waitKey()
print(k)
if (k==ord('s')):
    cv2.imwrite("anhmoi.jpg",img)
    # chỗ này mình vẫn chưa fix lỗi đc, haha
#-----------------------------------------------------------
# buoi 2
import random
from cv2 import cv2
img = cv2.imread('3.PNG',1)
#print(img)
#print(type(img))
print(img.shape)
print(img[0][0])
'''for i in range(100):
      for j in range(img.shape[1]):
          img[i][j]=[random.randint(0,255),random.randint(0,255),random.randint(0,255)]
          # rgb là 3 thông số màu, thực ra có thể kèm thêm kênh apha(tức là 4 thông số màu) '''
vungchon = img[0:100,300:500] 
# sao chép ảnh 
img[400:500,200:400]=vungchon
# rồi gán vào 1 vị trí khác
cv2.imshow('ahaha', img)
cv2.waitKeyEx()

#---------------------------------------------------
# buoi 3
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while   True:
    ret,frame = cap.read()
    print(ret)
    # ret trả về true, false. true khi qtrinh  chạy cam ok và ngược lại
    cv2.imshow('haha', frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyWindow()
