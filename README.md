# byufons-needle
円周率の近似。それほどうまく行ってない


import numpy as np
from numpy.random import * 
import math
import matplotlib.pyplot as plt

#投げる針の本数が「面積に対して」それほど多くないほうが良い。
#十分に投げる範囲の面積が「「充分に」」大きい必要がある。
N=100
a=np.zeros((N,2,2))
#a[1,1]=1

#長さ0.5の針をN本、ばらまく。
#針の両先端の座標を決定した。
num=0
for i in range (N):
    r1=10000*(rand())
    r2=10000*(rand())
    r3=(rand())*0.5
    a[i,0]=(r1,r2)
    a[i,1,0]=a[i,0,0]+r3
    r4=math.sqrt((0.25)-((r3)*(r3)))
    a[i,1,1]=r4+a[i,0,1]
   #print(int(a[i,1,1]))
#    plt.plot(r1,r2)
#重なっているか判定
   # print(int(a[i,1,1]))
   #針の両端のｙ座標の整数部分が等しい場合、平行線と重なっていない。
    if int(a[i,0,1])==int(a[i,1,1]):
    
        num=1+num
        #numは平行線線が重なっていない針の本数。
#print(r1,r2,"yo")        
#print(a)
print(num)
ok=N-num
# print(ok)
# print(N/num)
print(N/ok)
