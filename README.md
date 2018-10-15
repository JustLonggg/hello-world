# Second Homework



# coding: utf-8

# In[1]:


while True:
    try:
        a = int(input('请输入一个整数：'))
        break
    except:
        print('格式不正确！请重新输入。')
        
if a%2:
    print('奇数')
else:
    print('偶数')
    


# In[17]:


import numpy as np
def fun1():
    a = [i for i in range(100,1000) if not i%17]
    a = np.array(a)
    print(a)
    return
fun1()


# In[18]:


import math
def fun2():
    while True:
        try:
            a = int(input('请输入二次项的值：'))
            b = int(input('请输入一次项的值：'))
            c = int(input('请输入常数项的值：'))
            break
        except:
            print('输入错误，请重新输入！')
    d = b**2 - 4*a*c
    if d<0:
        print('方程无解')
    elif d==0:
        e = -b/(2*a)
        print('方程有唯一解：',e)
    else:
        f = (-b+math.sqrt(d))/(2*a)
        g = (-b-math.sqrt(d))/(2*a)
        print('方程的两个解为%.2f和%.2f' % (f,g))
        
    return

fun2()


# In[22]:


book_dict = {'book':['python','djang','data'],'author':'laoqi','publisher':'phei'}
new_dict = {}
for each in book_dict.items():
    if type(each[1])==type([1]):
        new_dict[tuple(each[1])] = each[0]
    else:
        new_dict[each[1]] = each[0]
print(new_dict)


# In[34]:


def trans(n):
    a = []
    while n:
        if n%2==0:
            a.append('0')
        else:
            a.append('1')
        n=n//2
    a.reverse()
    print(a)
    return
trans(10)


# In[38]:


price_index = {'北京':102.9,'天津':102.2,'河北':120.9,'山西':101.8,'内蒙古':101.8,'辽宁':130.4}
count = 0
for each in price_index:
    count += price_index[each]
    
ave = count/len(price_index)
print(ave)
for each in price_index:
    if price_index[each]>ave:
        print(each,'-->',price_index[each])
        


# In[3]:


def judge(n):
    a = str(n)
    for i in range(5):
        if a[i]!=a[4-i]:
            print('不是回文数')
            break
        if a[i]==a[4-i] and i==4:
            print('是回文数')
    return
judge(12321)
        


# In[5]:


a = [2,4,-7,19,-2,-1,45]
b = [i for i in a if i<0]
print(b)


# In[7]:


dict1 = {'python':89,'java':58,'physics':65,'math':87,'chinese':74,'english':60}
a = [each for each in dict1 if dict1[each]>(89+58+65+87+74+60)/6]
print(a)


# In[8]:


a = [i**2 for i in range(1,101)]
b = sum(a)
print(b)


# In[12]:


def judge(n):
    count=0
    for i in range(2,n):
        if n%i==0:
            count+=1
    if count==0:
        print('%d是素数'% n)
    
    return
for i in range(2,100):
    judge(i)


# In[13]:


def search(a,b):
    result = []
    for i in range(b,100):
        if i%a==0 and i%b==0:
            result.append(i)
    return result
search(5,9)
            


# In[19]:


import math
def ave(a):
    count = 0
    for i in range(len(a)):
        count += a[i]
    return count/len(a)

def sigma(b):
    count = 0
    for i in range(len(b)):
        count += (b[i]-ave(b))**2
    
    return math.sqrt(count/(len(b)-1))

dict1 = {}
while True:
    try:
        a = input('请输入姓名：(输入q结束)')
        if a == 'q':
            break
        else:
            dict1[a] = int(input('请输入分数：'))
    except:
        print('输入有误，请重新输入！')
        
a = sorted(dict1.items(),key = lambda x:x[1],reverse=True)
print(a)
b = []
for each in dict1:
    b.append(dict1[each])
print(b)

print('平均数为：',ave(b))
print('标准差为：',sigma(b))
    


# In[20]:


def factorial(n):
    if n == 1:
        return 1
    else:
        return n*factorial(n-1)
factorial(5)


# In[23]:


def sum_seq(n):
    return (n[0]+n[-1])*len(n)/2
a=range(1,10,2)
sum_seq(a)


# In[26]:


def get_list(a,n):
    b = len(a)
    if n<b:
        return a[n]
    else:
        print('None')
        return
a = [1,2,3]
get_list(a,3)
    

