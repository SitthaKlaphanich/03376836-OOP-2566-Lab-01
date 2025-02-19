# 65030258 สิทธา กล้าพานิช
# Lab-01 การเขียนโปรแกรมด้วยตัวดำเนินการทางตรรกะ

ตัวแปรชนิด boolean มักจะถูกใช้เป็นที่เก็บผลที่เกิดจากการดำเนินการทางตรรกะ เช่น AND, OR, NOT เป็นต้น ซึ่งการดำเนินการทางตรรกะจะมีตารางความจริง เป็นตัวบอกผลในการดำเนินการของตัวดำเนินการต่างๆ ดังตัวย่าง

### ตัวดำเนินการ AND

Y = A AND B

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### ตัวดำเนินการ OR

Y = A OR B

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### ตัวดำเนินการ NOT

Y = NOT A

| A | Y |
|--|--|
| 0 | 1 |
| 1 | 0 |

ตัวดำเนินการในภาษา C#
ใช้เครื่องหมายต่างๆ ดังต่อไปนี้

| การดำเนินการ | เครื่องหมาย |
|------------|-----------|
| Logical AND | & |
| Logical XOR | ^ |
| Logical OR | \| |

## 14. การเขียนโปรแกรมด้วยตัวดำเนินการทางตรรกะ

ตัวอย่างภาษา C# ต่อไปนี้เป็นการพิมพ์ตารางความจริงออกทางหน้าจอ
👉 ให้เขียนโปรแกรมต่อไปนี้

```csharp
bool A, B,Y;
Console.WriteLine("      Y = A AND B");
Console.WriteLine("-----------------------");
Console.WriteLine("   A      B\t|  Y");
Console.WriteLine("-----------------------");
A = false; B = false; Y = A & B;
Console.WriteLine(" {0}\t{1}\t| {2}", A,B,Y);
A = false; B = true; Y = A & B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = false; Y = A & B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = true; Y = A & B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
Console.WriteLine("-----------------------");
```

➢ รันโปรแกรมและบันทึกผล

 
👷 จากจ้อ 14 ให้เขียนโปรแกรมเพื่อสร้างตารางความจริงของลอจิกดังต่อไปนี้

1. `AND`
```csharp
bool A, B, Y;
Console.WriteLine("      Y = A AND B");
Console.WriteLine("-----------------------");
Console.WriteLine("   A      B\t|  Y");
Console.WriteLine("-----------------------");
A = false; B = false; Y =  A&B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = false; B = true; Y =   A&B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = false; Y =   A&B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = true; Y =    A&B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
Console.WriteLine("-----------------------");

#Sittha Klaphanich
```
![](./LAB_Images/AND.png)

2. `OR`
```csharp
bool A, B, Y;
Console.WriteLine("      Y = A or B");
Console.WriteLine("-----------------------");
Console.WriteLine("   A      B\t|  Y");
Console.WriteLine("-----------------------");
A = false; B = false; Y = A || B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = false; B = true; Y =  A || B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = false; Y =  A || B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = true; Y =   A || B;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
Console.WriteLine("-----------------------");

#Sittha Klaphanich
```
![](./LAB_Images/OR.png)

3. `NOT`
```csharp
bool A, Y;
Console.WriteLine("   Y = NOT A    ");
Console.WriteLine("-----------------------");
Console.WriteLine("   A    |  Y");
Console.WriteLine("-----------------------");
A = false;  Y = !A  ;
Console.WriteLine(" {0}\t| {1}", A,  Y);
A = true;  Y = !A  ;
Console.WriteLine(" {0}\t| {1}", A,  Y);
Console.WriteLine("-----------------------");

#Sittha Klaphanich
```
![](./LAB_Images/NOT.png)
 
5. `NAND`
```csharp
bool A, B, Y;
Console.WriteLine("   Y = A NAND B    ");
Console.WriteLine("-----------------------");
Console.WriteLine("   A    B\t|  Y");
Console.WriteLine("-----------------------");
A = false; B = false; Y =  !(A&B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B,  Y);
A = false; B = true;   Y = !(A&B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B,  Y);
A = true; B = false;  Y =  !(A&B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = true;   Y =  !(A&B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
Console.WriteLine("-----------------------");

#Sittha Klaphanich
```
![](./LAB_Images/NAND.png)

7. `NOR`
```csharp
bool A, B, Y;
Console.WriteLine("   Y = A NOR B    ");
Console.WriteLine("-----------------------");
Console.WriteLine("   A    B\t|  Y");
Console.WriteLine("-----------------------");
A = false; B = false; Y =  !(A||B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B,  Y);
A = false; B = true;   Y = !(A||B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B,  Y);
A = true; B = false;  Y =  !(A||B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = true;   Y =  !(A||B)  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
Console.WriteLine("-----------------------");

#Sittha Klaphanich
```
![](./LAB_Images/NOR.png)

9. `Exclusive OR`
```csharp
bool A, B, Y;
Console.WriteLine("   Y = A XOR B    ");
Console.WriteLine("-----------------------");
Console.WriteLine("   A    B\t|  Y");
Console.WriteLine("-----------------------");
A = false; B = false; Y = A^B  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B,  Y);
A = false; B = true;  Y = A^B  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B,  Y);
A = true; B = false;  Y = A^B  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
A = true; B = true;   Y = A^B  ;
Console.WriteLine(" {0}\t{1}\t| {2}", A, B, Y);
Console.WriteLine("-----------------------");

#Sittha Klaphanich
```

![](./LAB_Images/XOR.png)

## [ชนิดข้อมูลตัวเลขจำนวนเต็ม (Integer Types)](./Lab-01-part-15.md)
