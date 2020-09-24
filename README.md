<div align="center">

## ^A5\*Calculator


</div>

### Description

A complete GUI scientific calculator for engineering applications.
 
### More Info
 
Inputs r made through mouse.

Angles r in radians


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Wasim Haque](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/wasim-haque.md)
**Level**          |Advanced
**User Rating**    |4.0 (24 globes from 6 users)
**Compatibility**  |C, C\+\+ \(general\)
**Category**       |[Math](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/math__3-12.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/wasim-haque-a5-calculator__3-5812/archive/master.zip)





### Source Code

```
#include<stdio.h>
#include<conio.h>
#include<string.h>
#include<math.h>
#include<graphics.h>
#include<dos.h>
union REGS i,o;
char numc[]={'1','2','3','4','5','6','7','8','9','0','=','-','+','*','/'};
int optr[]={48,61,45,43,42,246},sq[]={251,253,227};
int button,xx,yy;
int xco[15],k=-1,x=210;
int xcor,ycor;
int yco[15],num=0;
int prevx,prevy;
int xx1=210,yy1=328,up=0;//xx1=210,yy1=181;
int numascii[]={49,50,51,52,53,54,55,56,57,48,61,45,43,42,246};
char numstring[14];
void main()
{
int i,c=4,x1,y1=377,x2,n=0,k=0;//x=210;
int gd=DETECT,gm;
int key;
//struct stack exp;
char numcod[5];
initgraph(&gd,&gm," ");
//hidemouseptr();
cleardevice();
setcolor(14);
settextstyle(4,HORIZ_DIR,4);outtextxy(185,7,"C a l c u l a t o r");
setlinestyle(0,0,3);
setcolor(8); settextstyle(0,HORIZ_DIR,0);
rectangle(200,60,440,345);
line(200,95,440,95); setfillstyle(1,4);setcolor(15);
bar(380,130,437,103);outtextxy(388,114,"On/Off");
setfillstyle(1,1);setcolor(14);
for(i=0;i<3;i++)
 {
 y1=y1-49;x1=210;
 for(c=0;c<3;c++)
 {
 xco[num]=x1;yco[num]=y1;
 num++;itoa(num,numcod,10);
 bar(x1,y1,x1+12,y1+12);outtextxy(x1+4,y1+4,numcod);x1=x1+52;
 }
 }
 y1=377;
for(i=0;i<3;i++)
 {
 y1=y1-49;x2=x1;
 for(c=0;c<2;c++)
 {
 xco[num]=x2;yco[num]=y1;
 bar(x2,y1,x2+12,y1+12);outtextxy(x2+4,y1+4,&optr[n]);n++;
 x2=x2+52;num++;
}
 }
setfillstyle(1,10);setcolor(6);
bar(290,207,340,220);outtextxy(297,210,"RESET");
bar(210,181,238,193);outtextxy(214,183,"exp");
bar(248,179,278,195);outtextxy(256,184,"y");outtextxy(264,180,"x");
bar(288,181,298,193);outtextxy(290,185,&sq[0]);
bar(308,179,334,195);outtextxy(316,184,"x");outtextxy(324,180,"2");
bar(344,179,374,195);outtextxy(360,185,"y");outtextxy(352,185,&sq[0]); outtextxy(348,180,"x");
bar(380,179,408,195);outtextxy(384,183,"1/x");
bar(416,181,430,193);outtextxy(417,183,"n!");
bar(210,140,228,152);outtextxy(213,144,"ln");
bar(238,138,268,156);outtextxy(246,143,"e");outtextxy(254,139,"x");
bar(276,140,300,152);outtextxy(277,143,"log");
bar(308,138,338,156);outtextxy(316,145,"10");outtextxy(329,138,"x");
bar(346,140,370,152);outtextxy(347,143,"Sin");
bar(378,140,402,152);outtextxy(379,143,"Cos");
bar(410,140,434,152);outtextxy(411,143,"Tan");
bar(210,99,250,112);outtextxy(213,103,"Tan");outtextxy(238,99,"-1");
bar(260,99,300,112);outtextxy(261,103,"Cos");outtextxy(286,99,"-1");
bar(308,99,348,112);outtextxy(309,103,"Sin");outtextxy(334,99,"-1");
bar(356,104,366,114);outtextxy(358,105,".");setfillstyle(1,7);
//bar(210,328,222,340);
bar(203,63,437,93);
initmouse();
showmouseptr();
while(1)
{
mouse_ctrl();
}
}
calculate()
{
 int len=0,f1=0,f2=0,k,rp=0,st;
 int rest[4],nop=0;
 double res;
 float resd;
 char numstr1[7],numstr2[7],op,strres[14];
 outtextxy(280,450,"calculating...");
 for(rp=0;rp<strlen(numstr1);rp++)
 {
 numstr1[rp]='\0';
 }
 for(rp=0;rp<strlen(numstr2);rp++)
 {
 numstr2[rp]='\0';
 }
 numstring[strlen(numstring)]='\0';
 len=strlen(numstring);puts(numstring);puts("hit a key");getch();
 for(rp=0;rp<len;rp++)
 {
 if(numstring[rp]=='+' || numstring[rp]=='-' || numstring[rp]=='*' || numstring[rp]=='/')
 {
  op=numstring[rp];st=rp;
  for(f2=rp+1;f2<len;f2++)
  {
  numstr2[f1]=numstring[f2];++f1;
  }
 }
 }
 for(rp=0;rp<st;rp++)
 {
  numstr1[rp]=numstring[rp];
 }
 numstr1[rp]='\0';numstr2[f1]='\0';
 //puts(numstr1);puts(numstr2);printf("%c",op); getch();
 switch(op)
 {
 case '+': res=atof(numstr1)+atof(numstr2);break;
 case '*': res=atof(numstr1)*atof(numstr2);break;
 case '/': res=atof(numstr1)/atof(numstr2);break;
 case '-': res=atof(numstr1)-atof(numstr2);break;
 }
 gcvt(res,6,strres); //puts(strres);
 outtextxy(x+16,74,strres);x=x+16;
 for(rp=0;rp<len;rp++)
 {
 numstring[rp]='\0';
 }
 for(rp=0;rp<strlen(strres);rp++)
 {
 numstring[rp]=strres[rp];
 }
 numstring[rp]='\0';
 for(rp=0;rp<strlen(strres);rp++)
 {
 strres[rp]='\0';
 }
 for(rp=0;rp<strlen(numstr1);rp++)
 {
 numstr1[rp]='\0';
 }
 for(rp=0;rp<strlen(numstr2);rp++)
 {
 numstr2[rp]='\0';
 }
 k=strlen(numstring)-1;op='\0'; setfillstyle(1,7);//puts(numstring);
 bar(203,63,437,93);x=210;outtextxy(x,72,numstring);x=x+8*(k);
 return;
}
mouse_ctrl()
{
int rp=0,sq,i=0;
double sqf,ctof,xtof;
char ntoc[5];
char symb[1];
char xstr[4];
//cleardevice();
fflush(stdin);
initmouse();
showmouseptr();
outtextxy(280,450,"mouse activated...");
while(1)
{
 getmousepos(&button,&xcor,&ycor);
 if((button & 1)==1)
 {
 if(xcor>308 && xcor<334 && ycor>179 && ycor<195)
 {
  sqf=atof(numstring)*atof(numstring);
  gcvt(sqf,5,ntoc);
  goto fun_call;
 }
 if(xcor>290 && xcor<340 && ycor>210 && ycor<220)
 {
  //reset(ntoc);
  gcvt(0.0,5,ntoc);goto fun_call;
 }
 if(xcor>380 && xcor<408 && ycor>179 && ycor<195)
 {
 ctof= atof(numstring);
 sqf=1/ctof;gcvt(sqf,5,ntoc);goto fun_call;
 }
 if(xcor>210 && xcor<228 && ycor>140 && ycor<152)
 {
 ctof=log((atof(numstring)));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>276 && xcor<300 && ycor>140 && ycor<152)
 {
 ctof=log(atof(numstring))/log(10);
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>288 && xcor<298 && ycor>181 && ycor<193)
 {
 ctof=sqrt(atof(numstring));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>238 && xcor<268 && ycor>138 && ycor<156)
 {
 ctof=exp(atof(numstring));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>416 && xcor<430 && ycor>181 && ycor<193)
 {
 ctof=atof(numstring);sqf=1.0;
 for(rp=1;rp<=ctof;rp++)
 {
  sqf=sqf*rp;
 }
 gcvt(sqf,5,ntoc);goto fun_call;
 }
 if(xcor>308 && xcor<338 && ycor>138 && ycor<156)
 {
 ctof=pow(10,atof(numstring));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>346 && xcor<370 && ycor>140 && ycor<152)
 {
 ctof=sin(atof(numstring));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>378 && xcor<402 && ycor>140 && ycor<152)
 {
 ctof=cos(atof(numstring));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>410 && xcor<434 && ycor>140 && ycor<152)
 {
 ctof=tan(atof(numstring));
 gcvt(ctof,5,ntoc);goto fun_call;
 }
 if(xcor>210 && xcor<250 && ycor>99 && ycor<112)
 {
 ctof=atan(atof(numstring));
 gcvt(ctof,6,ntoc);goto fun_call;
 }
 if(xcor>260 && xcor<300 && ycor>99 && ycor<112)
 {
 ctof=acos(atof(numstring));
 gcvt(ctof,6,ntoc);goto fun_call;
 }
 if(xcor>308 && xcor<348 && ycor>99 && ycor<112)
 {
 ctof=asin(atof(numstring));
 gcvt(ctof,6,ntoc);goto fun_call;
 }
 if(xcor>248 && xcor<278 && ycor>179 && ycor<195)
 {
 setfillstyle(1,7);bar(203,63,437,93);x=210;
 xstr[i]=symb[0];outtextxy(x,72,xstr);++i;symb[0]='\0';puts(numstring);
 getmousepos(&button,&xcor,&ycor);
 if(xcor>418 && xcor<430 && ycor>328 && ycor<340)
 {
 ctof=atof(numstring);xtof=atof(xstr);puts(xstr);
 sqf=pow(ctof,xtof); printf("\n%d",sqf);
 gcvt(sqf,6,ntoc);goto fun_call;
 }
 else return;
 }
 if(xcor>210 && xcor<222 && ycor>328 && ycor<340)
 {
 symb[0]='1';
 goto fun;
 }
 if(xcor>262 && xcor<274 && ycor>328 && ycor<340)
 {
 symb[0]='2';
 goto fun;
 }
 if(xcor>314 && xcor<326 && ycor>328 && ycor<340)
 {
  symb[0]='3';
 goto fun;
 }
 if(xcor>366 && xcor<378 && ycor>328 && ycor<340)
 {
  symb[0]='0';
 goto fun;
 }
 if(xcor>418 && xcor<430 && ycor>328 && ycor<340)
 {
  calculate();
 }
 if(xcor>210 && xcor<222 && ycor>279 && ycor<291)
 {
  symb[0]='4';
 goto fun;
 }
 if(xcor>262 && xcor<278 && ycor>279 && ycor<291)
 {
  symb[0]='5';
 goto fun;
 }
  if(xcor>314 && xcor<326 && ycor>279 && ycor<291)
 {
  symb[0]='6';
 goto fun;
 }
 if(xcor>366 && xcor<378 && ycor>279 && ycor<291)
 {
  symb[0]='-';
 goto fun;
 }
 if(xcor>418 && xcor<430 && ycor>279 && ycor<291)
 {
  symb[0]='+';
 goto fun;
 }
 if(xcor>210 && xcor<222 && ycor>230 && ycor<242)
 {
  symb[0]='7';
 goto fun;
 }
 if(xcor>262 && xcor<274 && ycor>230 && ycor<242)
 {
  symb[0]='8';
 goto fun;
 }
 if(xcor>314 && xcor<326 && ycor>230 && ycor<240)
 {
  symb[0]='9';
 goto fun;
 }
 if(xcor>366 && xcor<378 && ycor>230 && ycor<242)
 {
  symb[0]='*';
 goto fun;
 }
 if(xcor>418 && xcor<430 && ycor>230 && ycor<242)
 {
  symb[0]='/';
 goto fun;
 }
 if(xcor>356 && xcor<366 && ycor>104 && ycor<114)
 {
 symb[0]='.';
 goto fun;
 }
 if(xcor>380 && xcor<437 && ycor>103 && ycor<130)
 {
 closegraph();exit(1);
 //main();
 }
 }
}
fun_call:
rel_print(ntoc);
return;
fun:
store(symb);
return;
}
store(char sym[])
{
numstring[strlen(numstring)]=sym[0];
setfillstyle(1,7);setcolor(0);
k=strlen(numstring);
bar(203,63,437,93);x=210;outtextxy(x,72,numstring);x=x+8*(k-1);
sym[0]='\0';
return;
}
rel_print(char ntoc[])
{
int rp=0;
for(rp=0;rp<strlen(numstring);rp++)
{
numstring[rp]='\0';
}
for(rp=0;rp<strlen(ntoc);rp++)
{
  numstring[rp]=ntoc[rp];
}
numstring[rp]='\0';
numstring[rp+1]='\0';
for(rp=0;rp<strlen(ntoc);rp++)
{
ntoc[rp]='\0';
}
ntoc[rp+1]='\0';
setfillstyle(1,7);setcolor(0);
k=strlen(numstring);
bar(203,63,437,93);x=210;outtextxy(x,72,numstring);x=x+8*(k-1);
fflush(stdin);
return;
}
initmouse()
   {
   i.x.ax=0;
   int86(0x33,&i,&o);return;
   }
  showmouseptr()
   {
   i.x.ax=1;
   int86(0x33,&i,&o);return;
   }
  /*changecursor(int *cursor)
   {
   i.x.ax=9;
   i.x.bx=0;
   i.x.cx=0;
   i.x.dx=(unsigned)cursor;
   segread(&s);
   s.es=s.ds;
   int86x(0x33,&i,&i,&s);return;
   }*/
 getmousepos(int *button,int *x,int *y)
{
	i.x.ax=3;
	int86(0x33,&i,&o);
	*button=o.x.bx;
	*x=o.x.cx;
	*y=o.x.dx;
	return;
}
hidemouseptr()
{
	i.x.ax=2;
	int86(0x33,&i,&o);
	return;
}
```

