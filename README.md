# Saree-border-design
#include<stdio.h>
#include<graphics.h>
#include<stdlib.h>
#include<windows.h>

//------  DDA line draw algorithm ------

void dda(int x1, int y1,int x2,int y2,int c)
{
	int x,y,length,i;
	float xinc,yinc;
	length=abs(y2-y1);
	if(abs(x2-x1)>length)
	length=abs(x2-x1);
	xinc=(x2-x1)/(float)length;
	yinc=(y2-y1)/(float)length;
	for(i=0;i<length;i++)
	{
		x=x1+(i*xinc)+0.5;
		y=y1+(i*yinc)+0.5;
		putpixel(x,y,c);
	}
}
void boarder(int a,int b)
{
	int j;
	

}

//------ Repeating one design for 1st saree -------

void v(int i)
{
	int d=RED,k=BLUE,p,l=GREEN,j;
	for(p=0;p<27;p++){dda(i+124,134+p,i+240,247+p,k);dda(i+240,247+p,i+360,p+130,l);}
	dda(i+120,131,i+240,245,d);
	dda(i+124,160,i+240,275,d);
	dda(i+240,275,i+360,155,d);
	dda(i+240,245,i+360,130,d);
	for(j=30;j<40;j++){setcolor(13);circle(i+360,230,j);}
	for(j=20;j<30;j++){setcolor(12);circle(i+360,230,j);}
	for(j=10;j<20;j++){setcolor(7);circle(i+360,230,j);}
	for(j=1;j<10;j++){setcolor(10);circle(i+360,230,j);}
	for(j=30;j<40;j++){setcolor(10);circle(i+240,180,j);}
	for(j=20;j<30;j++){setcolor(7);circle(i+240,180,j);}
	for(j=10;j<20;j++){setcolor(12);circle(i+240,180,j);}
	for(j=1;j<10;j++){setcolor(13);circle(i+240,180,j);}
	

}

//-------- 1st Saree --------

void saree1()
{
	int j,i=5,c=14,d=11;
	
	for(j=0;j<5;j++) dda(0,126+j,1500,126+j,c);
	for(j=0;j<5;j++) dda(0,j+110,1500,110+j,c);
	for(j=0;j<5;j++) dda(0,j+115,1500,115+j,c-2);
	for(j=0;j<6;j++) dda(0,j+120,1500,120+j,c-3);
	
	for(j=0;j<5;j++) dda(0,276+j,1500,276+j,c);
	for(j=0;j<5;j++) dda(0,j+292,1500,j+292,c);
	for(j=0;j<5;j++) dda(0,j+281,1500,281+j,c-2);
	for(j=0;j<6;j++) dda(0,j+286,1500,286+j,c-3);
	
	for(j=0;j<145;j++) dda(0,131+j,1500,131+j,d);
	v(i-235);
	v(i);
	v(i+235);
	v(i+470);
	v(i+705);
	v(i+940);
	v(i+1175);
	setcolor(9);
	settextstyle(3,0,6);
	outtextxy(500,30,"Saree border - 1");
}

//-------- Design for 2nd saree --------

rect(int a)
{
	int j,k=0;
	while(k<1500){
		for(j=0;j<=a;j++)
		{
			dda(k,231+j,k+a,231+j,3);
			dda(k+a,j+231+a,k+(a*2),j+231+a,3);
			dda(k,j+231+(a*2),k+a,j+231+(a*2),3);
			dda(k+a,j+231+(a*3),k+(a*2),j+231+(a*3),3);
			dda(k,j+231+(a*4),k+a,j+231+(a*4),3);
			dda(k+a,j+231+(a*5),k+(a*2),j+231+(a*5),3);
			dda(k,j+231+(a*6),k+a,j+231+(a*6),3);
		}
			k+=(a*2);
	}
}

//-------- 2nd Saree --------

void saree2()
{
	int j,c=13;
	for(j=0;j<145;j++) dda(0,231+j,1500,231+j,2);
	rect(20);
	for(j=0;j<5;j++) dda(0,j+210,1500,210+j,c);
	for(j=0;j<5;j++) dda(0,j+215,1500,215+j,c-2);
	for(j=0;j<6;j++) dda(0,j+220,1500,220+j,c-3);
	for(j=0;j<5;j++) dda(0,226+j,1500,226+j,c);
	
	for(j=0;j<5;j++) dda(0,376+j,1500,376+j,c);
	for(j=0;j<5;j++) dda(0,j+392,1500,j+392,c);
	for(j=0;j<5;j++) dda(0,j+381,1500,381+j,c-2);
	for(j=0;j<6;j++) dda(0,j+386,1500,386+j,c-3);
	
	setcolor(1);
	settextstyle(4,0,6);
	outtextxy(400,40,"Saree border - 2");
}

//-------- Design for 3rd saree --------

void bent(int a)
{
	int k=-100,j,c=3,i=5;
	while(k<1500)
	{
		for(j=0;j<5;j++)
		{
			dda(k,231+j,k+(a*5),376+j,c);
			dda(k,231+j,k-(a*5),376+j,c);
		}
		k=k+a;
	}
	
	while(i<1500)
	{
	for(j=30;j<40;j++){setcolor(13);circle(i+60,280,j);}
	for(j=20;j<30;j++){setcolor(12);circle(i+60,280,j);}
	for(j=10;j<20;j++){setcolor(7);circle(i+60,280,j);}
	for(j=1;j<10;j++){setcolor(10);circle(i+60,280,j);}
	for(j=30;j<40;j++){setcolor(5);circle(i+130,335,j);}
	for(j=20;j<30;j++){setcolor(7);circle(i+130,335,j);}
	for(j=10;j<20;j++){setcolor(12);circle(i+130,335,j);}
	for(j=1;j<10;j++){setcolor(13);circle(i+130,335,j);}
	i+=150;
	}
	
}

//-------- 2nd Saree --------

void saree3()
{
	int j,a=RED,b=9,d=1;
	for(j=0;j<150;j++) dda(0,231+j,1500,231+j,b);
	for(j=0;j<24;j++) dda(0,207+j,1500,207+j,a);
	for(j=0;j<20;j++) dda(0,380+j,1500,380+j,a);
	bent(20);
	setcolor(1);
	settextstyle(3,0,6);
	outtextxy(400,50,"Saree border - 3");
}

int main()
{
	int n,gd=DETECT,gmode;
	do
	{
		printf("1 . Saree 1\n2 . Saree 2\n3 . Saree 3\n4 . Exit\nEnter your choice : ");
		scanf("%d",&n);
		switch(n)
		{
			case 1:initgraph(&gd,&gmode,"");saree1();getch();closegraph();break;
			case 2:initgraph(&gd,&gmode,"");saree2();getch();closegraph();break;
			case 3:initgraph(&gd,&gmode,"");saree3();getch();closegraph();break;
			case 4:break;
		}
	}while(n<4);
return 0;
}
