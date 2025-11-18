
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'A' 
WAIT:JNB TI, WAIT
CLR TI 
END


```
### (ii) Serial Port to Transfer a Message

```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="SHRI LEKSHMAN RIKHESH R";
unsigned char i;
TMOD=0X20;
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<23;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}




```

### OUTPUT:
<img width="1912" height="867" alt="image" src="https://github.com/user-attachments/assets/9a5c459f-b389-4ff3-8fd3-e28e1bd1728f" />

<img width="1919" height="842" alt="image" src="https://github.com/user-attachments/assets/123fd4b3-8a88-4012-b33d-8bce03834b28" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
