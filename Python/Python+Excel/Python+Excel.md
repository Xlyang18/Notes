# Python+Excel

## 目录

*   [专有名词](#专有名词)

*   [操控Excel读取操作](#操控excel读取操作)

    *   [打开Excel表格](#打开excel表格)

    *   [打印表单、指定单元格信息](#打印表单指定单元格信息)

    *   [打印指定行列位置单元格的信息](#打印指定行列位置单元格的信息)

    *   [通过固定列对象来取出单元格信息](#通过固定列对象来取出单元格信息)

    *   [通过切片来获取区间内的所有信息](#通过切片来获取区间内的所有信息)

    *   [通过划分区间来答应输出表格信息](#通过划分区间来答应输出表格信息)

    *   [通过确定首尾单元格来遍历该区间内的所有单元格元素信息](#通过确定首尾单元格来遍历该区间内的所有单元格元素信息)

    *   [打印表单的长度，即几行几列](#打印表单的长度即几行几列)

*   [统计表单文件当中出现的相同元素次数](#统计表单文件当中出现的相同元素次数)

## 专有名词

*   工作簿-（workbook）

*   表单-（worksheet）

*   行、列、单元格-（row、column、cell）

***

*   运用到的模块：openpyxl

## 操控Excel读取操作

### 打开Excel表格

```python
wb = openpyxl.load_workbook("同级目录下的.xlsx格式文件")  # 范例： one.xlsx

# 选取表格中的活跃表单（一般情况下，活跃表单为顺序第一个表单）
ws = wb.active
```

*   **随后的操作对象皆是以 ‘ws’进行的。**

***

打印表格内所有表单的操作

*   直接打印为数组信息：  <操作表格对象>.sheetnames

*   通过遍历元素，打印为字符串信息： for循环后使用   <接受循环的参数>.title

```python
 # 打印为数组
 print(wb.sheetnames)
 
 # 遍历元素，打印为字符串
 for date in wb:
     print(date.title)
```

### 打印表单、指定单元格信息

| .row       | 单元格行属性                  |
| ---------- | ----------------------- |
| .column    | 单元格列属性                  |
| .coordinat | 单元格名称信息属性    （例如：A1、C5） |
| .value     | 单元格内容信息                 |

```python
print(ws). # 答应表单对象信息
#--输出结果为 <Worksheet "标准集">
# 此处的“标准集”为对应操作表单的名字


print(ws['A2']). #打印对应表单内指定单元格的信息
#--输出结果为 <Cell '标准集'.A2>


print("行：{}、列：{}、信息：{}、内容：{}".format(ws['A2'].row, ws['A2'].column, ws['A2'].coordinat, ws['A2'].value)) 
# 打印指定单元格全部信息
#--输出结果为 行：2、列：1、信息：A2、内容：xxxxxx
```

### 打印指定行列位置单元格的信息

*   <操作表单对象>.cell()

```python
print(ws.cell(row=2,column=1).value)

# 打印第二行第一列的单元格内容
```

*   打印固定行多列信息（遍历列信息实现）

    > 使用for循环，遍历列信息，不改变行信息，输出需要的固定列多行信息。

```python
for i in range(1, 9):
    print(ws.cell(row=i column=2).value)

# 打印固定第二列，1到9行的单元格内容
```

### 通过固定列对象来取出单元格信息

column\_date = <操作表格对象>\['<指定的列信息>']

```python
column_date = ws['C']
```

***

固定列信息后，给出一个行信息来确定一个唯一的单元格元素，打印信息

```python
column_date = ws['C']
print(column_date[2].value)
# 此处为打印单元格C2元素的内容
```

固定列信息后，通过遍历行信息来打印固定列多行信息

```python
column_date = ws['C']
for i in range(1,9):
    print(colume_date[i].value)
# 此处为打印C1～C9的单元格内容
```

### 通过切片来获取区间内的所有信息

*   打印列信息为B～C的所有单元格元素的内容

```python
col_range = ws['B:C']

for col in col_range:
    for call_col in col:
        print(cell_col.value)
# 打印列信息为B、C的所有单元格元素内容

```

*   打印行信息为2～4的所有单元格元素的内容

```python
row_range = ws['2:4']

for row in row_range:
    for call_row in row:
        print(call_row.value)
# 打印行信息为2～4的所有单元格元素内容
```

### 通过划分区间来答应输出表格信息

<操作表单对象>.iter\_rows()

```python
for row in ws.iter_rows(min_row=1,max_row=2,max_col=3)
    for cell in row:
        print(cell)
# 划分一个区间：1～2行，1～3列的单元格，打印信息
```

### 通过确定首尾单元格来遍历该区间内的所有单元格元素信息

```python
cell_range = ws["A1:C3"]
for one in cell_range:
    for cell in one:
        print(cell.coordinate,cell.value)
    print("-----End of Row-----")

# 打印A1～C3单元格内所有单元格元素的内容
```

### 打印表单的长度，即几行几列

<操作表单对象>.max\_row        <操作表单对象>.max\_column

```python
 print("{}*{}".format(ws.max_row,ws.max_column))
```

## 统计表单文件当中出现的相同元素次数

*   创建一个值使其初始值设置为0，用于后续累加

*   检测元素的value属性（内容属性），如果该属性的值是目标值，这累加1 初始创建的值的参数

*   随后输出该初始值的最后结果确定元素重复出现次数

```python
num = 0
column_date = ws["A1:D5"]
    # 循环ws[]标记区间内的表单范围
    for one in column_date:
        # 每当获取一次ws[]内的值，就将该值循环放入cell参数当中，作为数据呈现
        for cell in one:
            # 输出该值的信息属性和内容属性
            print(cell.coordinate, cell.value)
            # 将数据类型转为字符串型，用作后续的比对
            cell_value = str(cell.value)
            # 核对数据，通过则累加num计数参数，此处的“111”为，作为比对值的内容。
            if cell_value == "111":
                num = num + 1

        print(num)
        print("-----End of Row-----")

```

column\_date = ws\["A1:D{}".format(n)]

for one in column\_date:

for cell in one:

print(cell.coordinate, cell.value)

cell\_value = str(cell.value)

if cell\_value == "111":

num = num + 1

print(num)

print("-----End of Row-----")
