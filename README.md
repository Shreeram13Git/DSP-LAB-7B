# DSP-LAB-7B

#FIR   HIGH  PASS  FILTER USING  HAMMING  WINDOW

PROGRAM:

 clc; 
clear all; 
close all; 
N=input('enter the order of filter'); 
wc=(pi/2); 
a=(N-1)/2; 
for n=1:N 
if((n-1)==a) 
hd(n)=(pi-wc)/pi; 
else 
hd(n)=sin(pi*(n-1-a))-sin(wc*(n-1-a))/(pi*(n-1-a)); 
end; 
w(n)=0.54-(0.46*cos(2*pi*(n-1)/(N-1))); 
end; 
h=w.*hd; 
a=0:0.01:pi; 
b=freqz(h,1,a); 
mag=20*log(abs(b)); 
plot(a/pi,mag); 
grid; 
xlabel('normalized frequency\omega^pi'); 
ylabel('magnitude in db'); 
title('high pass filter');
