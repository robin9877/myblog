# 1.交换两个变量的值
"""
x = input("输入x的值：")
y = input("输入yde值：")

x,y=y,x
print("交换后的x的值：{}".format(x))
print("交换后的y的值：{}".format(y))
"""

# 2.pyhton 九九乘法口诀表
"""
for i in range(1,10):
    for j in range(1,i+1):
        print("{}x{}={}\t".format(j,i,i*j),end="")

    print()
"""

# 3.计数排序
#计数排序的核心在于将输入的数据值转化为键存储在额外开辟的数组空间中。
#作为一种线性时间复杂度的排序，计数排序要求输入的数据必须是有确定范围的整数。
"""
def countSort(arr):
    output = [0 for i in range(256)]
    count = [0 for i in range(256)]

    ans = [""for _ in arr]

    for i in arr:
        count[ord(i)] += 1
    for i in range(256):
        count[i] += count[i-1]

    for i in range(len(arr)):
        output[count[ord(arr[i])]-1] =arr[i]
        count[ord(arr[i])] -= 1
    
    for i in range(len(arr)):
        ans[i] = output[i]
    return ans

arr = "wwwrobin9877"
ans = countSort(arr)
print("字符数组的排序 %s" %("".join(ans)))

"""
