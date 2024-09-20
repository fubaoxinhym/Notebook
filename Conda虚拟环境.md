## 创建、激活Conda虚拟环境以及安装包的步骤如下：

### 创建Conda虚拟环境：
conda create -n 自己输入名称 python=版本号
   ```bash
   conda create -n myenv python=3.8
   ```
   这里`myenv`是你创建的虚拟环境的名称，`python=3.8`指定了Python的版本。

### 激活Conda虚拟环境：
conda activate 环境名称
   ```bash
   conda activate myenv
   ```
   激活名为`myenv`的虚拟环境。

###  用Conda安装包：
   ```bash
   conda install numpy
   ```
   这里`numpy`是你想要安装的包的名称。

### 用pip安装包：
   ```bash
   pip install pandas
   ```
   这里`pandas`是你想要安装的包的名称。

### 在虚拟环境运行Python代码
法一：在cmd中输入`cd 目录位置`转到python文件对应的位置下
法二：直接在python文件所在目录输入cmd然后回车,然后弹出的命令符就是直接转至这个位置之中
随后我们还要在输入`conda activate 环境名称`打开虚拟环境,记住每次打开cmd都要输入打开这个哦.
```bash
python 文件名.py
```

归并排序算法的Python代码：

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]

        merge_sort(L)
        merge_sort(R)

        i = j = k = 0

        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1

        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1

        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1

# 测试归并排序
if __name__ == "__main__":
    test_array = [38, 27, 43, 3, 9, 82, 10]
    merge_sort(test_array)
    print("Sorted array is:", test_array)
```

要在不同的虚拟环境中运行这段代码，你需要：

1. 创建两个不同的虚拟环境，例如`myenv1`和`myenv2`。
2. 在每个环境中激活并安装Python。
3. 将上述归并排序的代码保存到一个Python文件中，比如`merge_sort.py`。
4. 在每个环境中，使用`python merge_sort.py`命令来运行这个脚本。

注意，不能在同一个终端会话中同时激活多个环境。需要为每个环境分别打开新的终端会话，或者在同一个会话中先退出当前环境再激活另一个环境。

### 退出虚拟环境
输入
```bash
conda deactivate
```
即可退出当前所在的虚拟环境

### 环境重命名
```bash
conda rename -n text text1
```
前一个text为旧名字,后一个text为新名字,注意要在base环境中运行此代码,更名后按新名字启动环境(`conda activate text1`)

### 查找所有创建过的环境
输入此代码可查找到你创建过的所有环境
```bash
conda env list
```

### 查看当前环境下安装的包
```bash
conda list
```

### 删除虚拟环境
```bash
conda env remove --name 名称 -y
```
### 不用重新安装，找回消失的Anaconda Prompt
1. win+R 输入cmd 进入命令行，进入到Anaconda的安装目录，语句：cd/d Anaconda的安装目录。例如
```
cd /d D:\anaconda3
```
2.进入到Anaconda的安装目录后，输入：
```
python .\Lib\_nsis.py mkmenus
```
3. 在电脑开始菜单，点击所有程序，就可以看到重新出现了Anaconda3所有快捷文件 