%byte stuffing
clc;
clear all;
close all;
startflag={'ESC STX'};
endflag={'ESC ETX'};
msg={'G','ESC','A','ESC', 'ESC','U', 'R', 'ESC','I'};
temp={'ESC'};
len=length(msg);
j=1;
for i=1:len
 if(strcmp(msg(i),temp))
 stufmsg(j)=temp;
 j=j+1;
 end
 stufmsg(j)=msg(i);
 j=j+1;
end
finalmsg=[startflag stufmsg endflag];
sprintf('The original message is %s',sprintf(' S%s',msg{:}))
sprintf('The framed message is %s', sprintf(' %s', finalmsg{:}))
%byte destuffing 
i=1;
j=1;
while(i<=length(stufmsg))
 if(strcmp(stufmsg(i),temp))
 i=i+1;
 end
 destufmsg(j)=stufmsg(i);
 j=j+1;
 i=i+1;
end
sprintf ('The Framed message is %s', sprintf (' %s',finalmsg{:}))
sprintf ('The byte destuffed message is %s', sprintf(' %s', destufmsg{:}))
![image](https://github.com/AshishBhosle17/Mern-Stack-Ecommerce-Platform/assets/140106733/0b1caec7-8a8e-4e66-a920-07fddf6199cd)
![WhatsApp Image 2024-04-29 at 00 06 02_91586d41](https://github.com/AshishBhosle17/Mern-Stack-Ecommerce-Platform/assets/140106733/98d4b99c-c30a-41c8-91ea-6aa6aab026e4)


