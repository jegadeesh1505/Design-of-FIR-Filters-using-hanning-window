
# Design-of-FIR-Filters-using-hanning-window

#DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
# LPF
```py
clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc = input("Enter cutoff frequency (0 to %pi) = ");

alpha = (N-1)/2;

for n = 0:N-1

    if n == alpha then
        hd(n+1) = Wc/%pi;
    else
        hd(n+1) = sin(Wc*(n-alpha))/(%pi*(n-alpha));
    end

    // Hanning window
    w(n+1) = 0.5 - 0.5*cos((2*%pi*n)/(N-1));

    h(n+1) = hd(n+1)*w(n+1);

end

[H,f] = frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("Magnitude Response LPF (Hanning Window)")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("Magnitude Response in dB")

```
# HPF
```py
clc;
clear;
close;

N=input("Enter filter length = ");
Wc=input("Enter cutoff frequency = ");

alpha=(N-1)/2;

for n=0:N-1
    
    if n==alpha then
        hd(n+1)=1-Wc/%pi;
    else
        hd(n+1)=-sin(Wc*(n-alpha))/(%pi*(n-alpha));
    end
    
    w(n+1)=0.5-0.5*cos((2*%pi*n)/(N-1));
    h(n+1)=hd(n+1)*w(n+1);

end

[H,f]=frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("HPF Magnitude Response")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("HPF Magnitude in dB")

```
# BPF
```py
clc;
clear;
close;

N=input("Enter filter length = ");
Wc1=input("Enter lower cutoff frequency = ");
Wc2=input("Enter upper cutoff frequency = ");

alpha=(N-1)/2;

for n=0:N-1
    
    if n==alpha then
        hd(n+1)=(Wc2-Wc1)/%pi;
    else
        hd(n+1)=(sin(Wc2*(n-alpha))-sin(Wc1*(n-alpha)))/(%pi*(n-alpha));
    end
    
    w(n+1)=0.5-0.5*cos((2*%pi*n)/(N-1));
    h(n+1)=hd(n+1)*w(n+1);

end

[H,f]=frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("BPF Magnitude Response")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("BPF Magnitude in dB")

```
# BSF
```py

clc;
clear;
close;

N=input("Enter filter length = ");
Wc1=input("Enter lower cutoff frequency = ");
Wc2=input("Enter upper cutoff frequency = ");

alpha=(N-1)/2;

for n=0:N-1
    
    if n==alpha then
        hd(n+1)=1-(Wc2-Wc1)/%pi;
    else
        hd(n+1)=(sin(Wc1*(n-alpha))-sin(Wc2*(n-alpha)))/(%pi*(n-alpha));
    end
    
    w(n+1)=0.5-0.5*cos((2*%pi*n)/(N-1));
    h(n+1)=hd(n+1)*w(n+1);

end

[H,f]=frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("BSF Magnitude Response")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("BSF Magnitude in dB")

```


# OUTPUT
<img width="607" height="133" alt="image" src="https://github.com/user-attachments/assets/0de849c1-d7ba-4322-8dd3-90b6a8b17ca9" />
<img width="920" height="481" alt="image" src="https://github.com/user-attachments/assets/e8e5078e-89e2-42d6-bbd2-9be3ab58b6b7" />
<img width="607" height="133" alt="image" src="https://github.com/user-attachments/assets/530739c2-4ec2-45bd-b678-b129183b8c9d" />
<img width="1011" height="585" alt="image" src="https://github.com/user-attachments/assets/b5146598-4d6a-45ed-a2ef-6f0484bd2da7" />
<img width="394" height="145" alt="image" src="https://github.com/user-attachments/assets/ec1a57ab-64a7-48f1-ac40-7ea176c2b891" />
<img width="1013" height="554" alt="image" src="https://github.com/user-attachments/assets/7245c8f6-6344-4e91-bb0e-138257be105f" />
<img width="406" height="157" alt="image" src="https://github.com/user-attachments/assets/8a2e97a2-9de7-43f6-97ff-4a9d6faf44d6" />
<img width="1017" height="550" alt="image" src="https://github.com/user-attachments/assets/23da0a09-d63d-4cbc-a231-29a7a0479e38" />








# RESULT
