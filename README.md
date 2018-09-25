# StructExc6
Informatics Coursebook, Structure, p143

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
    cout<<"Indicated diagnose: ";
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
	for(int i=0;i<n;i++)
	{
		if(patients[i].days>max_days)
		{
			max_days=patients[i].days;
			cout<<"Name="<<patients[i].name<<endl;
			cout<<"Diagnose="<<patients[i].diagnose<<endl;
			cout<<"Days="<<patients[i].days<<endl;
		}
	}
	system("pause");
	return 0;
}
