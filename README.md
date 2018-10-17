# StructExc6
Informatics Coursebook, Structure, p143

// Да се напише програма, която създава структура Hospital с полета name, diagnose и days, указващи името на пациент в болница, диагнозата му и брой дни, прекарани в болницата. Да се въведе цяло число n и след него n на брой данни от тип Hospital. Да се изведат имената на тези пациенти, чиято диагноза е предварително зададена от клавиатурата. Да се изведат данните на пациента с най-дълъг престой в болницата

#include<iostream>
#include<string>
using namespace std;
struct Hospital
{
  char name[20];
  char diagnose[30];
  int days;
};
int main()
{
	Hospital patients[100];
	int n;
	cout<<"Br patients=";
	cin>>n;
	for(int i=0;i<n;i++)
	{
		cout<<"Name=";
		cin.get();
        	cin.getline(patients[i].name,40);
		cout<<"Diagnose=";
		cin>>patients[i].diagnose;
		cout<<"Days=";
		cin>>patients[i].days;
	}
    
    string indicated_diagnose;
    cout<<"Enter diagnose: ";
    cin>>indicated_diagnose;
    cout<<"Patients by indicated diagnose:"<<endl;
	for(int i=0;i<n;i++)
	{
		if(patients[i].diagnose==indicated_diagnose) 
		{
			cout<<patients[i].name<<endl;
		}   
	
	}
	cout<<"Longest time in the hospital:"<<endl;
	int max_days=patients[0].days;
	int k=0;
	for(int i=1;i<n;i++)
	{
		if(patients[i].days>max_days)
		{
			max_days=patients[i].days;
			k=i;
			
		}
	}
			cout<<"Name="<<patients[k].name<<endl;
			cout<<"Diagnose="<<patients[k].diagnose<<endl;
			cout<<"Days="<<patients[k].days<<endl;
	system("pause");
	return 0;
}
