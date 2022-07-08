#include <iostream>
#include <string.h>
#include <vector>
#include <stdio.h>
#include <conio.h>
#include <unistd.h>
#include <stdlib.h>
#include <fcntl.h>
#include <dirent.h>
#include <cstdlib>
#include <fstream>
#include <thread>

int handle;
typedef int8_t BYTE;
using namespace std;
typedef char PACKAGENAME;

long int get_module_base(int pid, const char *module_name)
{
	FILE *fp;
	long addr = 0;
	char *pch;
	char filename[32];
	char line[1024];
	snprintf(filename, sizeof(filename), "/proc/%d/maps", pid);
	fp = fopen(filename, "r");
	if (fp != NULL)
	{
		while (fgets(line, sizeof(line), fp))
		{
			if (strstr(line, module_name))
			{
				pch = strtok(line, "-");
				addr = strtoul(pch, NULL, 16);
				break;
			}
		}
		fclose(fp);
	}
	return addr;
}

int Xa_BaseAddress_FLOAT(long int addr, float value)
{
	pwrite64(handle, &value, 4, addr);
	return 0;
}

int Xa_BaseAddress_DWORD(long int addr, int value)
{
	pwrite64(handle, &value, 4, addr);
	return 0;
}

int Xa_BaseAddress_BYTE(long int addr, BYTE value)
{
	pwrite64(handle, &value, 4, addr);
	return 0;
}

int getPID(PACKAGENAME * PackageName)
{
	DIR *dir = NULL;
	struct dirent *ptr = NULL;
	FILE *fp = NULL;
	char filepath[256];
	char filetext[128];
	dir = opendir("/proc");
	if (NULL != dir)
	{
		while ((ptr = readdir(dir)) != NULL)
		{

			if ((strcmp(ptr->d_name, ".") == 0) || (strcmp(ptr->d_name, "..") == 0))
				continue;
			if (ptr->d_type != DT_DIR)
				continue;
			sprintf(filepath, "/proc/%s/cmdline", ptr->d_name);
			fp = fopen(filepath, "r");
			if (NULL != fp)
			{
				fgets(filetext, sizeof(filetext), fp);
				if (strcmp(filetext, PackageName) == 0)
				{

					break;
				}
				fclose(fp);
			}
		}
	}
	if (readdir(dir) == NULL)
	{
		return 0;
	}
	closedir(dir);
	return atoi(ptr->d_name);
}

string GetStdoutFromCommand(string cmd)
{
	string data;
	FILE *stream;
	const int max_buffer = 256;
	char buffer[max_buffer];
	cmd.append(" 2>&1");
	stream = popen(cmd.c_str(), "r");
	if (stream)
	{
		while (!feof(stream))
			if (fgets(buffer, max_buffer, stream) != NULL)
				data.append(buffer);
		pclose(stream);
	}
	return data;
}

int initPUBGM(){
int target_pid = getPID("com.tencent.ig");
		if (target_pid == 0)
		{
			target_pid = getPID("com.pubg.krmobile");
			if (target_pid == 0)
			{
				target_pid = getPID("com.rekoo.pubgm");
				if (target_pid == 0)
				{
				target_pid = getPID("com.vng.pubgmobile");
				if (target_pid == 0)
				{
					target_pid = getPID("com.pubg.imobile");
					if (target_pid == 0)
					{
						target_pid = getPID("com.tencent.iglite");
					if (target_pid == 0)
					{
						puts("PUBGM not running!");
						exit(1);
					}
				}
			}
		}
		}
		}
		
		char lj[64];
		sprintf(lj, "/proc/%d/mem", target_pid);
		handle = open(lj, O_RDWR);
		if (handle == -1)
		{
			puts("Failed to initialise memory!\n");
			exit(1);
		}
return 0;
}

int main( int argc,char **argv)
{
std::vector <std::string> sources; 
std::string destination;
std::string arg = argv[1];
int gs;
void *jg;

int target_pid = getPID("com.tencent.ig");
		if (target_pid == 0)
		{
			target_pid = getPID("com.pubg.krmobile");
			if (target_pid == 0)
			{
				target_pid = getPID("com.rekoo.pubgm");
				if (target_pid == 0)
				{
					target_pid = getPID("com.vng.pubgmobile");
				if (target_pid == 0)
				{
					target_pid = getPID("com.pubg.imobile");
					if (target_pid == 0)
					{
						target_pid = getPID("com.tencent.iglite");
					if (target_pid == 0)
					{
						puts("PUBGM not running!");
						exit(1);
				 }
 			}
 		}
 }
 }
 }
		
//Bypass
if(arg == "999"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39076C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390768,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390764,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390760,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39075C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39078C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390788,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390784,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390780,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390770,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907AC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907AC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907A8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390794,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390790,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907C0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907B8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907BC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907B4,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907B0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907F8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907DC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907D8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907D0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907D4,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390810,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390800,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39080C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3907FC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390804,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390838,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390834,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390830,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39082C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390824,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3908B4,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3908A0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39089C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390864,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39084C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390F30,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390F2C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390F1C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390F18,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3908B8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390FA4,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390FA0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390F84,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x390F80,0);
puts("@UMRANICHANNELS");
close(handle);
}

////////////////////////////////////////
//////// Memory hacks////////
////////////////////////////////////////

//no recoil on
if(arg == "1"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1440D98,0);
puts("@UMRANICHANNELS");
close(handle);
}
//no recoil off
if(arg == "2"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//no recoil V2 on
if(arg == "3"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3DB0778,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3E7F310,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1440D98,0);
puts("@UMRANICHANNELS");
close(handle);
}
//no recoil V2 off
if(arg == "4"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//no shake on
if(arg == "5"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29F70AC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29F71E0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//no shake off
if(arg == "6"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//stand scope on
if(arg == "7"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE38C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//stand cope off
if(arg == "8"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//sit scope on
if(arg == "9"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE390,0);
puts("@UMRANICHANNELS");
close(handle);
}
//sit cope off
if(arg == "10"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//croshair on
if(arg == "11"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x144153C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//croshair off
if(arg == "12"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//headshot on
if(arg == "13"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29C6460,0);
puts("@UMRANICHANNELS");
close(handle);
}
//headshot off
if(arg == "14"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//headshot v2 on
if(arg == "15"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4B45F98,0);
puts("@UMRANICHANNELS");
close(handle);
}
//headshot v2 off
if(arg == "16"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//headshot v3 on
if(arg == "17"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x426D8B8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x426D8BC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//headshot v3 off
if(arg == "18"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet on
if(arg == "19"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x42CA8D0,85);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet off
if(arg == "20"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet v1 on
if(arg == "21"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x2B36700,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet v1 off
if(arg == "22"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet v2 on
if(arg == "23"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0X427FC98,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet v2 off
if(arg == "24"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet v3 on
if(arg == "25"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x426D8C4,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Megicbullet v3 off
if(arg == "26"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//WallLoot on
if(arg == "27"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4B510E4,0);
puts("@UMRANICHANNELS");
close(handle);
}
//WallLoot off
if(arg == "28"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//AutoDrive on
if(arg == "29"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x57C7E34,0);
puts("@UMRANICHANNELS");
close(handle);
}
//AutoDrive off
if(arg == "30"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//XhitEffect on
if(arg == "31"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1C46924,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1C46924,0);
puts("@UMRANICHANNELS");
close(handle);
}
//XhitEffect off
if(arg == "32"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//LongHand on
if(arg == "33"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE38C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//LongHand off
if(arg == "34"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}

////////////////////////////////////////
//////// Aimbot hacks//////////
////////////////////////////////////////

//Aimbot 360 on
if(arg == "35"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CE91C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CE91C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CE91C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CE91C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot 360 off
if(arg == "36"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot 100m on
if(arg == "37"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CE91C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CEA50,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot 100m off
if(arg == "38"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot 500m on
if(arg == "39"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29CE91C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29F71E0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot 500m off
if(arg == "40"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot tdm on
if(arg == "41"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29F70AC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot tdm off
if(arg == "42"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot Touch Simulation on
if(arg == "43"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0xF9C14C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x132EBB8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0xFFC074,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0xFFC0F4,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0xFFD6D8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x14EC30C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1E80248,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29C5188,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x2FF9020,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3A99630,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3DC0250,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3DD32F0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x533D11C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3D14130,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x536E590,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Aimbot Touch Simulation off
if(arg == "44"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}


////////////////////////////////////////
//////// Burtual hacks//////////
////////////////////////////////////////

//Bullet Tracking on
if(arg == "45"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x42CA8D0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3F1AFB8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29C5B4C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE390,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE394,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Bullet Tracking off
if(arg == "46"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Bullet Tracking on
if(arg == "47"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x41ED350,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3E4C194,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE38C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE390,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE394,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Bullet Tracking off
if(arg == "48"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Auto Bullet on
if(arg == "49"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x41ED350,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3E4C194,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE38C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Auto Bullet off
if(arg == "50"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Sky Shoot on
if(arg == "51"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x41ED350,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3E4C194,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE38C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE390,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29EE394,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1152178,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x14BF76C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x11B2D98,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x11B2E18,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x11B3E60,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1650C68,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1F55E58,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29ED9C0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29F70AC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29F71E0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x2F525D0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x39EC570,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3D01090,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3D14130,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x536E590,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Sky Shoot off
if(arg == "52"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Fast Bullet on
if(arg == "43"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x41ED350,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3E4C194,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Fats Bullet off
if(arg == "54"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//WallSoot on
if(arg == "55"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29C5B4C,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29C5B50,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x29C5B54,0);
puts("@UMRANICHANNELS");
close(handle);
}
//WallShoot off
if(arg == "56"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}



////////////////////////////////////////
//////// Visual hacks////////////
////////////////////////////////////////

//Ipad on
if(arg == "57"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3E825E4,0);
puts("@UMRANICHANNELS");
close(handle);
}
//ipad off
if(arg == "58"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//No Grass on
if(arg == "59"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x2999B98,0);
puts("@UMRANICHANNELS");
close(handle);
}
//No Grass off
if(arg == "60"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//No Tree on
if(arg == "61"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x408DAA4,0);
puts("@UMRANICHANNELS");
close(handle);
}
//No Tree off
if(arg == "62"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//No Fog on
if(arg == "63"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x45F21BC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//No Fog off
if(arg == "64"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//No Homes on
if(arg == "65"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4C8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3EB54EC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//No Homes off
if(arg == "66"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//Desert map on
if(arg == "67"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3815FC0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Desert Map off
if(arg == "68"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//Black map on
if(arg == "69"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4143F00,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Black Map off
if(arg == "70"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//Red Fog on
if(arg == "71"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31c534c,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4D8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Red Fog off
if(arg == "72"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//black Fog on
if(arg == "73"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4BC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4CC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4D8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//balck Fog off
if(arg == "74"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//green Fog on
if(arg == "75"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31c5358,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4D8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//green Fog off
if(arg == "76"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//dark bule Fog on
if(arg == "77"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4BC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4CC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//dark blue Fog off
if(arg == "78"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//cyan Fog on
if(arg == "79"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4BC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//cyan Fog off
if(arg == "80"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//purple Fog on
if(arg == "81"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4CC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//purple Fog off
if(arg == "82"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//light green Fog on
if(arg == "83"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31C5448,0);
puts("@UMRANICHANNELS");
close(handle);
}
//light green Fog off
if(arg == "84"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//yellow Fog on
if(arg == "85"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4D8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4BC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//yellow Fog off
if(arg == "86"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//pink Fog on
if(arg == "87"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4D8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4BC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//pink Fog off
if(arg == "88"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//white body on
if(arg == "89"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//white body off
if(arg == "90"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//black body on
if(arg == "91"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3251218,0);
puts("@UMRANICHANNELS");
close(handle);
}
//black body off
if(arg == "92"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//green body on
if(arg == "93"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//green body off
if(arg == "94"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//blue body on
if(arg == "95"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//blue body off
if(arg == "96"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//white sky on
if(arg == "97"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//white sky off
if(arg == "98"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//Black sky on
if(arg == "99"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4143FF0,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Black sky off
if(arg == "100"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//ranbow sky on
if(arg == "101"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3286EA8,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3586ECC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3386EA8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//ranbow sky off
if(arg == "102"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//Blue sky on
if(arg == "103"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4BC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x31FC4CC,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3286EA8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//Blue sky off
if(arg == "104"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}



////////////////////////////////////////
//////// Speed hacks////////////
////////////////////////////////////////

//speed flash on
if(arg == "105"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x451CC94,0);
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x1541460,0);
puts("@UMRANICHANNELS");
close(handle);
}
//speed flash off
if(arg == "106"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//speed flash v2 on
if(arg == "107"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3EDDE04,0);
puts("@UMRANICHANNELS");
close(handle);
}
//speed flash v2 off
if(arg == "108"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//speed flash v3 on
if(arg == "109"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x3ED02DC,0);
puts("@UMRANICHANNELS");
close(handle);
}
//speed flash v3 off
if(arg == "110"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//speed knock on
if(arg == "111"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x121B21C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//speed knock off
if(arg == "112"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//speed bikes on
if(arg == "113"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4D7628C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//speed bikes off
if(arg == "114"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//speed vichels on
if(arg == "115"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4D7628C,0);
puts("@UMRANICHANNELS");
close(handle);
}
//speed vichels off
if(arg == "116"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}




////////////////////////////////////////
//////// fly hacks////////////
////////////////////////////////////////

//long jump on
if(arg == "117"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x121B328,0);
puts("@UMRANICHANNELS");
close(handle);
}
//long jump off
if(arg == "118"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//sky jump on
if(arg == "119"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x13B9B20,0);
puts("@UMRANICHANNELS");
close(handle);
}
//sky jump off
if(arg == "120"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//high jump on
if(arg == "121"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x121B238,0);
puts("@UMRANICHANNELS");
close(handle);
}
//high jump off
if(arg == "122"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//dacia jump on
if(arg == "123"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4D7ECE8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//dacia jump off
if(arg == "124"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//uaz jump on
if(arg == "125"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4D7ECE8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//uaz jump off
if(arg == "126"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
//bugy jump on
if(arg == "127"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0x4D7ECE8,0);
puts("@UMRANICHANNELS");
close(handle);
}
//bugy jump off
if(arg == "128"){
initPUBGM();
Xa_BaseAddress_FLOAT(get_module_base(target_pid,"libUE4.so") + 0,0); 
puts("@UMRANICHANNELS");
close(handle);
}
	
}
