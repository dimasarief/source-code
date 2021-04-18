```
print("Score untuk sikap adalah 5-10")
sikap = float(input("masukan score Sikap: "))
print("Score untuk kecepatan pelayanan adalah 4-10")
kec_pelayanan = float(input("masukan score Kecepatan Pelayanan: "))

#Rules
sangat_sedikit = 300000
sedikit = 450000
normal = 600000
banyak = 800000
sangat_banyak = 1000000

# Variabel Linguistik untuk sikap
# kurang ramah, biasa, & sangat ramah

# Variabel Linguistik untuk kec.pelayanan
# lambat, standar, & cepat

if (sikap >= 5.0 and sikap <= 7.5):
    uB = (sikap - 5)/(7.5-5.0)
    uKR = (7.5 - sikap)/(7.5-5.0) 

elif (sikap >= 7.5 and sikap <= 10.0):
    uB = (10.0 - sikap)/(10-7.5) 
    uSR = (sikap - 7.5)/(10-7.5)

if (kec_pelayanan >= 4.0 and kec_pelayanan <= 7.0):
    uL = (7.0 - kec_pelayanan)/(7.0-4.0) 
    uS = (kec_pelayanan - 4.0)/(7.0-4.0)

elif (kec_pelayanan >= 7.0 and kec_pelayanan <= 10.0):
    uS = (10.0 - kec_pelayanan)/(10.0-7.0) 
    uC = (kec_pelayanan - 7)/(10.0-7.0)

############# Inference Systems ###########
if (sikap >= 5 and sikap <= 7.5) and (kec_pelayanan >= 4 and kec_pelayanan <= 7):
    uT1 = min(uKR, uL)*(sangat_sedikit)
    uT2 = min(uKR, uS)*(sedikit)
    uT3 = min(uB, uL)*(sedikit)
    uT4 = min(uB, uS)*(normal)
    a = (uT1+uT2+uT3+uT4)
    b = (min(uKR, uL)+min(uKR, uS)+min(uB, uL)+min(uB, uS))
    Z = a / b
    print("============ Result ============")
    print("uB:",uB, "uKR:", uKR, "uS:",uS, "uC:", uL)
    print("uT1:", uT1, "uT2:", uT2, "uT3:", uT3, "uT4:", uT4)
    print("a:", a)
    print("b:", b)

elif (sikap >= 5 and sikap <= 7.5) and (kec_pelayanan >= 7 and kec_pelayanan <= 10):
    uT1 = min(uKR, uS)*(sedikit)
    uT2 = min(uKR, uC)*(normal)
    uT3 = min(uB, uS)*(normal)
    uT4 = min(uB, uC)*(banyak)
    a = (uT1+uT2+uT3+uT4)
    b = (min(uKR, uS) + min(uKR, uC) + min(uB, uS) + min(uB, uC))
    Z = a / b
    print("============ Result ============")
    print("uB:",uB, "uKR:", uKR, "uS:",uS, "uC:", uC)
    print("uT1:", uT1, "uT2:", uT2, "uT3:", uT3, "uT4:", uT4)
    print("a:", a)
    print("b:", b)

elif (sikap >= 7.5 and sikap <= 10) and (kec_pelayanan >= 4 and kec_pelayanan <= 7):
    uT1 = min(uB, uL)*(sedikit)
    uT2 = min(uB, uS)*(normal)
    uT3 = min(uSR, uL)*(normal)
    uT4 = min(uSR, uS)*(banyak)
    a = (uT1+uT2+uT3+uT4)
    b = (min(uB, uL)+min(uB, uS)+min(uSR, uL)+min(uSR, uS))
    Z = a / b
    print("============ Result ============")
    print("uB:",uB, "uSR:", uSR, "uS:",uS, "uL:", uL)
    print("uT1:", uT1, "uT2:", uT2, "uT3:", uT3, "uT4:", uT4)
    print("a:", a)
    print("b:", b)

elif (sikap >= 7.5 and sikap <= 10) and (kec_pelayanan >= 7 and kec_pelayanan <= 10):
    uT1 = min(uB, uS)*(normal)
    uT2 = min(uB, uC)*(banyak)
    uT3 = min(uSR, uS)*(banyak)
    uT4 = min(uSR, uC)*(sangat_banyak)
    a = (uT1+uT2+uT3+uT4)
    b = (min(uB, uS)+min(uB, uC)+min(uSR, uS)+min(uSR, uC))
    Z = a / b
    print("============ Result ============")
    print("uB:",uB, "uSR:", uSR, "uS:",uS, "uC:", uC)
    print("uT1:", uT1, "uT2:", uT2, "uT3:", uT3, "uT4:", uT4)
    print("a:", a)
    print("b:", b)

print("=========================================")
print("Bonus bulan ini adalah sebesar:", Z)
print("=========================================")
```
