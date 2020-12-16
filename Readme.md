# Open Closed Principle

## 1. Penjelasan CouponWithout OCP
Didalam program ini semua logic untuk mengatur diskon baik nominal, persen dan cashback terdapat dalam satu class yang sama yaitu `Coupon.cs`
```csharp
          if(discNominal == 0 && discPercentage > 0)
          {
              net = (100 - discPercentage) * originPrice / 100;
          }
          else if (discNominal > 0 && discPercentage == 0)
          {
              net = originPrice - discNominal;
          }
          else if(discNominal > 0 && discPercentage > 0)
          {
              if(discNominal >= 3000 && discPercentage >= 30)
              {
                  net = originPrice - discNominal;
              }
              else if(discNominal < 3000 && discPercentage < 30)
              {
                  double hargadiscPersen;
                  hargadiscPersen =  (100 - discPercentage)  * originPrice/ 100;
                  net = hargadiscPersen - discNominal;
              }
          }
          return net;         
```

## 3. Class Diagram 
### Coupon With OCP
![alt text](https://github.com/MTYU-Luki/CouponWithoutOCP/blob/master/ClassDiagram1.png)



