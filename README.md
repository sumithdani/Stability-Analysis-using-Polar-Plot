# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-16 at 14 20 42_cfac6d2d](https://github.com/user-attachments/assets/811bf111-eb12-4607-9ffe-4168bfd4edd5)
![WhatsApp Image 2025-11-16 at 14 20 43_f59416b4](https://github.com/user-attachments/assets/39b64e59-406b-47c5-b998-219b8f41414a)



## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
~~~
num=[1]
den = conv([1 0], conv([0.5 1], [0.2 1]));
sys=tf(num,den)
w=logspace(-1,2,1000);
[mag phase]=bode(sys,w);
mag=squeeze(mag);
phase=squeeze(phase);
theta=deg2rad(phase);
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
~~~

## Output:
<img width="1210" height="997" alt="Screenshot 2025-11-19 142220" src="https://github.com/user-attachments/assets/26a96e84-1640-4a36-a0d4-17c9cbb63029" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin =  7.0000 rad/s <br>
Phase Margin = 55.6412 degree <br>
Gain crossover frequency =  0.8979 rad/s <br>
Phase crossover frequency = 3.1623 rad/s <br>
The system is  Stable
