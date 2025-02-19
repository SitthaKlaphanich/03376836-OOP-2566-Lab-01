# 65030258 สิทธา กล้าพานิช 
# Lab-01 การตั้งชื่อตัวแปรและชนิดข้อมูลในภาษา C\#


 ให้นักศึกษาพิจารณาชื่อตัวแปรตามตารางต่อไปนี้ ว่าสามารถใช้ได้หรือไม่ พร้อมบอกเหตุผล

| ชื่อตัวแปร | ใช้ได้/ไม่ได้ | เหตุผล|
|--|--|--|
| `xxx`     | ใช้ได้ | ไม่มีตัวอักษรที่ละเมิดกฎการตั้งชื่อ            |
| `null`    | ไม่ได้ | ไม่เป็นการตั้งชื่อตัวแปรที่ถูกต้อง             |
| `_value`  | ใช้ได้ | อนุญาตให้ใช้ underscore (_) ในชื่อตัวแปร  |
| `First-name`| ไม่ได้ | มีตัวอักษรพิเศษ (-) ที่ไม่ได้รับอนุญาตในชื่อตัวแปร |
| `Hello!` |    ไม่ได้ | มีตัวอักษรพิเศษ (!) ที่ไม่ได้รับอนุญาตในชื่อตัวแปร |
| `w*h` |    ไม่ได้    | มีการใช้เครื่องหมาย * ที่ไม่ได้รับอนุญาตในชื่อตัวแปร |
| `time` |   ใช้ได้    | ไม่มีปัญหา     |
| `do` |    ใช้ได้   | ไม่มีปัญหา       |
| `Do` |  ใช้ได้     | ไม่มีปัญหา แต่ควรระมัดระวังเนื่องจากภาษาโปรแกรมบางภาษาอาจจะแยกตัวพิมพ์ใหญ่/เล็ก |
| `21November`| 	ใช้ได้ | ไม่มีปัญหา   |
| `ladkrabang`| ใช้ได้   | ไม่มีปัญหา |
| `Student ID`| ไม่ได้   | มีช่องว่างที่ไม่ได้รับอนุญาตในชื่อตัวแปร |


---ผลการทดลอง


## ชนิดข้อมูลภายในภาษา C\#

Property ของชนิดข้อมูล ในภาษา C# มีชนิดข้อมูลต่างๆ ได้แก่ `byte`, `char`, `bool`, `sbyte`, `short`, `ushort`, `int` , `uint`, `float`, `double`, `decimal`, `long`, `ulong` โดยแต่ละชนิด มีคุณสมบัติที่สำคัญได้แก่ ขนาด (เป็นไบต์) ค่าต่ำสุด ค่าสูงสุด ที่เก็บในตัวแปรชนิดนั้นๆ ได้ ซึ่งมีฟังก์ชันในภาษา C# ที่ช่วยให้เราทราบคุณสมบัติเหล่านั้น ได้แก่คำสั่ง `sizeof()`, `MinValue()` และ `MaxValue()` การแสดงค่าคุณสมบัติต่างๆ ของตัวแปร สามารถทำได้โดยใช้ฟังก์ชั่นเหล่านั้น ดังตัวอย่าง

## 13. โปรแกรมแสดงคุณสมบัติ size, MinValue และ MaxValue ของชนิดข้อมูล

```csharp
Console.WriteLine("Data type : int");
Console.WriteLine("Size :" + sizeof(int));
Console.WriteLine("Minimum Value :" + int.MinValue);
Console.WriteLine("Maximum Value :" + int.MaxValue);
```

### ผลที่ได้จากโปรแกรม

```text
Data type : int
Size :4
Minimum Value :-2147483648
Maximum Value :2147483647
```

👉 คำสั่งสำหรับการทดลอง  

ให้นักศึกษา เขียนโปรแกรมคล้ายกับตัวอย่างในข้อ 13 โดยมีชนิดข้อมูลเป็น `byte`, `char`, `bool`, `sbyte`, `short`, `ushort`, `uint`, `float`, `double`, `decimal`, `long` `และ ulong`  

### หมายเหตุ

ชนิดข้อมูล bool เก็บข้อมูลได้เฉพาะ true และ false ไม่ต้องหา MinValue และ MaxValue

ชนิดข้อมูล char จะต้องมีการ cast ค่า MinValue และ MaxValue ไปยัง int ก่อน ดังนี้

```csharp
Console.WriteLine("Minimum Value :" + (int) char.MinValue);
Console.WriteLine("Maximum Value :" + (int) char.MaxValue);
```
### ---ผลการทดลอง `char`
```csharp
Console.WriteLine("Data type : char");
Console.WriteLine("Size :" + sizeof(char));
Console.WriteLine("Minimum Value :" + (int) char.MinValue);
Console.WriteLine("Maximum Value :" + (int) char.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `char`
```text
Data type : char
Size :2
Minimum Value :0
Maximum Value :65535

#Sittha Klaphanich
```
### ---ผลการทดลอง `byte`
```csharp
Console.WriteLine("Data type : byte");
Console.WriteLine("Size :" + sizeof(byte));
Console.WriteLine("Minimum Value :" + byte.MinValue);
Console.WriteLine("Maximum Value :" + byte.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `byte`
```text
Data type : byte
Size :1
Minimum Value :0
Maximum Value :255

#Sittha Klaphanich
```
### ---ผลการทดลอง `short`
```csharp
Console.WriteLine("Data type : short");
Console.WriteLine("Size :" + sizeof(short));
Console.WriteLine("Minimum Value :" + short.MinValue);
Console.WriteLine("Maximum Value :" + short.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `short`
```text
Data type : short
Size :2
Minimum Value :-32768
Maximum Value :32767

#Sittha Klaphanich
```
### ---ผลการทดลอง `ushort`
```csharp
Console.WriteLine("Data type : ushort");
Console.WriteLine("Size :" + sizeof(ushort));
Console.WriteLine("Minimum Value :" + ushort.MinValue);
Console.WriteLine("Maximum Value :" + ushort.MaxValue);

#Sittha Klaphanich
 ```
### ผลที่ได้จากโปรแกรม `ushort`
```text
Data type : ushort
Size :2
Minimum Value :0
Maximum Value :65535

#Sittha Klaphanich
```
### ---ผลการทดลอง `uint`
```csharp
Console.WriteLine("Data type : uint");
Console.WriteLine("Size :" + sizeof(uint));
Console.WriteLine("Minimum Value :" + uint.MinValue);
Console.WriteLine("Maximum Value :" + uint.MaxValue);

#Sittha Klaphanich
 ```
### ผลที่ได้จากโปรแกรม `uint`
```text
Data type : uint
Size :4
Minimum Value :0
Maximum Value :4294967295

#Sittha Klaphanich
```
### ---ผลการทดลอง `float`
```csharp
Console.WriteLine("Data type : float");
Console.WriteLine("Size :" + sizeof(float));
Console.WriteLine("Minimum Value :" + float.MinValue);
Console.WriteLine("Maximum Value :" + float.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `float`
```text
Data type : float
Size :4
Minimum Value :-3.4028235E+38
Maximum Value :3.4028235E+38

#Sittha Klaphanich
```

### ---ผลการทดลอง `double`
```csharp
Console.WriteLine("Data type : double");
Console.WriteLine("Size :" + sizeof(double));
Console.WriteLine("Minimum Value :" + double.MinValue);
Console.WriteLine("Maximum Value :" + double.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `double`
```text
Data type : double
Size :8
Minimum Value :-1.7976931348623157E+308
Maximum Value :1.7976931348623157E+308

#Sittha Klaphanich
```
### ---ผลการทดลอง `decimal`
```csharp
Console.WriteLine("Data type : decimal");
Console.WriteLine("Size :" + sizeof(decimal));
Console.WriteLine("Minimum Value :" + decimal.MinValue);
Console.WriteLine("Maximum Value :" + decimal.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `decimal`
```text
Data type : decimal
Size :16
Minimum Value :-79228162514264337593543950335
Maximum Value :79228162514264337593543950335

#Sittha Klaphanich
```
### ---ผลการทดลอง `long`
```csharp
Console.WriteLine("Data type : long");
Console.WriteLine("Size :" + sizeof(long));
Console.WriteLine("Minimum Value :" + long.MinValue);
Console.WriteLine("Maximum Value :" + long.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `long`
```text
Data type : long
Size :8
Minimum Value :-9223372036854775808
Maximum Value :9223372036854775807

#Sittha Klaphanich
```
### ---ผลการทดลอง `ulong`
```csharp
Console.WriteLine("Data type : ulong");
Console.WriteLine("Size :" + sizeof(ulong));
Console.WriteLine("Minimum Value :" + ulong.MinValue);
Console.WriteLine("Maximum Value :" + ulong.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `ulong`
```text
Data type : ulong
Size :8
Minimum Value :0
Maximum Value :18446744073709551615

#Sittha Klaphanich
```
### ---ผลการทดลอง `bool`
```csharp
Console.WriteLine("Data type : bool");
Console.WriteLine("Size :" + sizeof(bool));

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `bool`
```text
Data type : bool
Size :1

#Sittha Klaphanich
```
### ---ผลการทดลอง `sbyte`
```csharp
Console.WriteLine("Data type : sbyte");
Console.WriteLine("Size :" + sizeof(sbyte));
Console.WriteLine("Minimum Value :" + sbyte.MinValue);
Console.WriteLine("Maximum Value :" + sbyte.MaxValue);

#Sittha Klaphanich
```
### ผลที่ได้จากโปรแกรม `sbyte`
```text
Data type : sbyte
Size :1
Minimum Value :-128
Maximum Value :127

#Sittha Klaphanich
```

## การใช้งานข้อมูลชนิดต่างๆ

ข้อมูลชนิดตรรกะ The Boolean Type
ข้อมูลชนิดตรรกะ (boolean) มีค่าที่เป็นไปได้เพียง 2 ค่าเท่านั้นคือ true และ false ในภาษา C# จะไม่สามารถกำหนดค่าตัวเลขลงไปในตัวแปร boolean ได้ ส่วนใหญ่ตัวแปร boolean มักใช้เพื่อการตัดสินใจและมีที่มาจากการประเมินค่าสมการต่างๆ ตัวอย่างต่อไปนี้เป็นการใช้ตัวแปร boolean กับการเปรียบเทียบด้วยตัวดำเนินการ “>”
ตัวอย่าง

```csharp
bool a = 4 > 5;
Console.WriteLine("4 > 5 is {0}", a);
```

## สนุกกับการสร้างตัวเลขสุ่ม

ในภาษา C# มีวิธีการสร้างตัวเลขสุ่ม (random number) โดยใช้คลาส Random มาสร้างเป็นตัวแปรโดยมีรูปแบบดังนี้

```csharp
Random random = new Random();
```

เมื่อสร้างแล้ว เราสามารถนำมาหาค่าตัวเลขสุ่มจากตัวแปรดังกล่าว ซึ่งมักจะกำหนดค่าสูงสุดและต่ำสุดในการสุ่มลงไปด้วย ดังนี้

```csharp
int randomNumber = random.Next(0, 100);
```

โปรแกรมด้านล่างนี้เป็นตัวอย่างการสุ่มเลข 0 – 100

```csharp
Random random = new Random();
int randomNumber = random.Next(0, 100);
Console.WriteLine(randomNumber);
```
 
ให้รัน 10 ครั้งแล้วบันทึกค่าที่ได้จากการรัน

![](./LAB_Images/random.png)

![](./LAB_Images/random2.png)

![](./LAB_Images/random3.png)

![](./LAB_Images/random4.png)

![](./LAB_Images/random5.png)

![](./LAB_Images/random6.png)

![](./LAB_Images/random7.png)

![](./LAB_Images/random8.png)

![](./LAB_Images/random9.png)

![](./LAB_Images/random10.png)


## [การเขียนโปรแกรมด้วยตัวดำเนินการทางตรรกะ](./Lab-01-part-14.md)
