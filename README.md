# Indian-Stanadard-Atmosphere-model
//Variation of Temperature, Pressure, Density and Speed of sound along the altitude. This code will give you these four properties if you give the altitude as input
// temperature_varitaion.c.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"
#include "stdio.h"
#include "string.h"
#include "math.h"
#define SLOPE1 -6.5
#define SLOPE2 2.3
#define SLOPE3 -3.0
#define SLOPE4 29.6
#define height1 16
#define height2 46
#define height3 52
#define height4 75
#define Constant -34.1063 //-(g*1000/R)
#define Constant2 -0.0341 //-(g/R)


int _tmain(int argc, _TCHAR* argv[])
{
	double height, temperature1=303.15, temperature2=199.14,temperature3=268.15,temperature4=199.15, Temperature;
	double pressure,pressure1,pressure2,pressure3,pressure4,pressure5,pressure6,pressure7, pressure0=100500, temperaturep,SLOPEp;
	double density, density0=1.1549, density1, density2, density3,density4, density5, density6, density7;
	double speed_of_sound,P,r=1.4,R=287;
	printf("Enter the height Kilometers\n");
	scanf("%lf",&height);

	if(height<=16)
	{
		Temperature= temperature1+SLOPE1*height;
	}

	if(height>16 && height<=46)
	{
		Temperature= temperature2+SLOPE2*(height-height1);
	}

	if(height>46 && height<=52)
	{
		Temperature=temperature3;
	}

	if(height>52 && height<=75)
	{
		Temperature= temperature3+SLOPE3*(height-height3);
	}

	
	if(height>75 && height<=80)
	{
		Temperature= temperature4+SLOPE4*(height-height4);
	} 
	/*if(height>80)
	{
		printf("No data avilable\n");
		Temperature=00000000;
	} */
	//printf("The temprature is %lf kelvins\n",Temperature);
	/// pressure calculator
	/*if((height<=16)|| (height>16 && height<=46) || (height>52 && height<=75) || (height>75 && height<=80)) 
	{
			temperaturep=temperature1;
			SLOPEp=SLOPE1;

		pressure1= pressure0*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
		pressure=pressure1;
		if((height>16 && height<=46) || (height>52 && height<=75)|| (height>75 && height<=80))
		{
			temperaturep=temperature2;
			SLOPEp=SLOPE2;
			pressure2= pressure1*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
			pressure=pressure1;
		}
		if((height>52 && height<=75)|| (height>75 && height<=80))
		{
			temperaturep=temperature4;
			SLOPEp=SLOPE3;
			pressure3= pressure2*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
			pressure=pressure3;
		}
		if((height>75 && height<=80))
		{
			temperaturep=temperature4;
			SLOPEp=SLOPE3;
			pressure4= pressure3*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
			pressure=pressure4;
		}
	}*/
	if(height<=80)
	{
			temperaturep=temperature1;
			SLOPEp=SLOPE1;

		pressure1= pressure0*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
		pressure=pressure1;
		density1=density0*(pow((Temperature/temperaturep),((Constant/SLOPEp)-1)));
		density=density1;
		if(height>16)
		{
			pressure1= pressure0*(pow((199.15/temperaturep),(Constant/SLOPEp)));
		   pressure=pressure1;
		   density1=density0*(pow((199.15/temperaturep),((Constant/SLOPEp)-1)));
		   density=density1;
		}
		/*if((height>11 && height<=25) || (height>25 && height<=47) || (height>47 && height<=53)|| (height>53 && height<=79)|| (height>79 && height<=90)|| (height>90 && height<=105))
		if(height>11 && height<=105)
		{
			temperaturep=temperature2;
			pressure2= pressure1*(exp((Constant2/temperaturep)*(height-height1)*1000));
			pressure=pressure2;
			density2=density1*(exp((Constant2/temperaturep)*(height-height1)*1000));
			density=density2;
			if(height>25)
			{
				pressure2= pressure1*(exp((Constant2/temperaturep)*(25-height1)*1000));
				pressure=pressure2;
				density2=density1*(exp((Constant2/temperaturep)*(25-height1)*1000));
			 density=density2;
			}

		}*/
		//if((height>25 && height<=47) || (height>47 && height<=53)|| (height>53 && height<=79)|| (height>79 && height<=90)|| (height>90 && height<=105))
		if(height>16 && height<=80)
		{
			temperaturep=temperature2;
			SLOPEp=SLOPE2;
			pressure2= pressure1*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
			pressure=pressure2;
			density2=density1*(pow((Temperature/temperaturep),((Constant/SLOPEp)-1)));
		    density=density2;
		}
		if(height>46)
		{
			pressure2= pressure1*(pow((268.15/temperaturep),(Constant/SLOPEp)));
		   pressure=pressure2;
		   density2=density1*(pow((268.15/temperaturep),((Constant/SLOPEp)-1)));
		    density=density2;
		}
		//if((height>47 && height<=53)|| (height>53 && height<=79)|| (height>79 && height<=90)|| (height>90 && height<=105))
		if(height>46 && height<=80)
		{
			temperaturep=temperature3;
			pressure3= pressure2*(exp((Constant2/temperaturep)*(height-height2)*1000));
			pressure=pressure3;
			density3=density2*(exp((Constant2/temperaturep)*(height-height2)*1000));
			density=density3;

			if(height>52)
			{
				pressure3= pressure2*(exp((Constant2/temperaturep)*(52-height3)*1000));
				pressure=pressure3;
				density3=density2*(exp((Constant2/temperaturep)*(52-height3)*1000));
			    density=density3;

			}
		}
		//if((height>53 && height<=79)|| (height>79 && height<=90)|| (height>90 && height<=105))
		if(height>52 && height<=80)	
		{
			temperaturep=temperature3;
			SLOPEp=SLOPE3;
			pressure4= pressure3*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
			pressure=pressure4;
			density4=density3*(pow((Temperature/temperaturep),((Constant/SLOPEp)-1)));
		    density=density4;
		}
		/*if(height>79)
		{
			pressure5= pressure4*(pow((165.66/temperaturep),(Constant/SLOPEp)));
		   pressure=pressure5;
		   density5=density4*(pow((165.66/temperaturep),((Constant/SLOPEp)-1)));
		   density=density5;
		}
		//if((height>79 && height<=90)|| (height>90 && height<=105))
		if(height>79 && height<=105)
		{
			temperaturep=temperature4;
			pressure6= pressure5*(exp((Constant2/temperaturep)*(height-height5)*1000));
			pressure=pressure6;
			density6=density5*(exp((Constant2/temperaturep)*(height-height5)*1000));
			density=density6;
			if(height>90)
			{
				pressure6= pressure5*(exp((Constant2/temperaturep)*(90-height5)*1000));
				pressure=pressure6;
				density6=density5*(exp((Constant2/temperaturep)*(90-height5)*1000));
			    density=density6;
			}
		}*/
		if(height>75 && height<=80)
			{
			temperaturep=temperature4;
			SLOPEp=SLOPE4;
			pressure5= pressure4*(pow((Temperature/temperaturep),(Constant/SLOPEp)));
			pressure=pressure5;
			density5=density4*(pow((Temperature/temperaturep),((Constant/SLOPEp)-1)));
		    density=density5;
		}
	}
	if(height>80)
	{
		printf("No data is avilable\n");
	}
	if(height<=80)
	{
	speed_of_sound=sqrt(r*R*Temperature);
	//P=density*R*Temperature;
	printf("The temprature is T=%lf kelvins\n",Temperature);
	 printf("The pressure is P=%lf pascal\n",pressure);///
	 printf("The density is rho=%lf kg/m^3\n",density);
	 printf("The speed of sound is a=%lf m/s\n",speed_of_sound);


   printf("The pressure is %lf kilo pascal\n",pressure);
	}
	getchar();
    getchar(); 
	return 0;
}

