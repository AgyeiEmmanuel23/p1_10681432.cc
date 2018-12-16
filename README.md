# p1_10681432.cc
End of Semester Project
//Headers inclusion
#include <iostream>
#include <fstream>
#include <string>
#include <conio.h>
#include <windows.h>

using namespace std;


//For students
struct student
{
 string fname;
 string lname;
 string stud_id;
 string coursename;
};
 student studentData;
//For Staff
struct staff
{
 string fst_name; 
 string lst_name;
string stff_id;
 string addrs;
 };
 
 
staff tech[15];




int  main()
{

int i=0,j;
char choice;
string find;
string srch;

while(1)//outer loop
{ 
 system("cls");

//Level 1-Display process 
 cout<<"\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\";
 cout<<"\n\n\t\t\tSCHOOL MANAGEMENT PROGRAM\n\n";
 cout<<"\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\";
 cout<<"\n\n\t\t\tMAIN SCREEN\n\n";
 cout<<"1.Students information"<<endl;
 cout<<"2.Staff information"<<endl;
 cout<<"3.Exit program"<<endl;
 cout<<"Enter your choice: ";
 cin>>choice;

system("cls");//Clear screen


switch(choice)//First switch
{
 
case '1': //Student
 { 
while(1)//inner loop-1
{ 
system("cls");//Clear screen
//Level-2 display
cout<<"\t\t\tSTUDENTS INFORMATION SECTION\n\n\n";
cout<<"1.Create new entry\n";
cout<<"2.Find and display entry\n";
cout<<"3.Jump to main\n";
cout<<"Enter your choice: ";
cin>>choice;

switch (choice)//Second switch

{
case '1'://Insert data
{  ofstream f1("student.txt",ios::app);

for( i=0;choice!='n';i++)
{

if((choice=='y')||(choice=='Y')||(choice=='1'))
{
 cout<<"Enter First name: ";
 cin>>studentData.fname;
 cout<<"Enter Last name: ";
 cin>>studentData.lname;
 cout<<"Enter StudentID Number: ";
 cin>>studentData.stud_id;
 cout<<"Enter CourseName: ";
 cin>>studentData.coursename;
 
 f1<<studentData.fname<<endl<<studentData.lname<<endl<<studentData.stud_id <<endl<<studentData.coursename<<endl;
 cout<<"Do you want to enter data: ";
 cout<<"Press Y for Continue and N to Finish:  ";
 cin>>choice;
}
} 
f1.close();
}
continue;//control back to inner loop -1

case '2'://Display data
{  ifstream f2("student.txt"); 

cout<<"Enter First name to be displayed: ";
cin>>find;
cout<<endl;
int notFound = 0;
for( j=0;(j<i)||(!f2.eof());j++)
{ 

getline(f2,studentData.fname);

if(studentData.fname==find)
{
 notFound = 1;
 cout<<"First Name: "<<studentData.fname <<endl;
 cout<<"Last Name: "<<studentData.lname <<endl;

 getline(f2,studentData.stud_id);
 cout<<"StudentID number: "<<studentData.stud_id <<endl;

 getline(f2,studentData.coursename);
 cout<<"course offered: "<<studentData.coursename<<endl<<endl;
}

}

if(notFound == 0){

cout<<"No Record Found"<<endl;
}
f2.close();
cout<<"Press any key two times to proceed";
getch();//To hold data on screen
getch();//To hold data on screen

}
continue;//control back to inner loop -1

case '3'://Jump to main
{
break;//inner switch breaking
}
}

break;//inner loop-1 breaking
}
continue;//Control pass to 1st loop    
}

case '2'://Teachers biodata
{ 
while(1)//inner loop-2
{ 
system("cls");//Clear screen
//Level-2 Display process
cout<<"\t\t\tSTAFF INFORMATION  SECTION\n\n\n";
cout<<"1.Create new entry\n";
cout<<"2.Find and display\n";
cout<<"3.Jump to main\n";
cout<<"Enter your choice: ";
cin>>choice;

switch (choice)//Third switch
{
case '1'://Insert data
{ 
ofstream t1("teacher.txt",ios::app);

for(i=0;choice!='n'&& choice!='N';i++)
{
 
 if((choice=='y')||(choice=='Y')||(choice=='1'))
 {
  cout<<"Enter First name: ";
  cin>>tech[i].fst_name;
  cout<<"Enter Last name: ";
  cin>>tech[i].lst_name;
  cout<<"Enter your StaffID: ";
  cin>>tech[i].stff_id;
  cout<<"Enter Your Address: ";
  cin>>tech[i].addrs;
 
  t1<<tech[i].fst_name<<endl<<tech[i].lst_name<<endl 
   <<tech[i].stff_id<<endl<<tech[i].addrs<<endl;
   
  cout<<"Do you want to enter data: ";
  cin>>choice;
 }
}

system("cls");



t1.close();
}//case 1

continue;//Control pass to inner loop-2

case '2'://Display data
{ 
ifstream t2("teacher.txt"); 

cout<<"Enter name to be displayed: ";
cin>>find;

cout<<endl;
int notFound = 0;
for( j=0;((j<i)||(!t2.eof()));j++)
{ 
 
 getline(t2,tech[j].fst_name);
 
 if(tech[j].fst_name==find)
 {
  notFound = 1;
  cout<<"First name: "<<tech[j].fst_name <<endl;
  getline(t2,tech[j].lst_name);
  cout<<"Last name: "<<tech[j].lst_name <<endl;
  getline(t2,tech[j].stff_id);
  cout<<"StaffID : "<<tech[j].stff_id <<endl;
  getline(t2,tech[j].addrs);
  cout<<"Address: "<<tech[j].addrs <<endl;

  
 }//if
 
}//for loop
t2.close();
if(notFound == 0){

 cout<<"No Record Found"<<endl;
}
cout<<"Press any key two times to proceed";
getch();
getch();
}//case 2

continue;//Control pass to inner loop-2

case '3'://Jump to main 
{
break;//inner switch
}//case 3

}//inner switch

break;//inner while
}//inner loop

continue;//control pass to 1st loop
}//outer case 2


case '3':
{
break;//outer case 3
}//outer case 3
}   
break;//outer loop
}

return 0;
}
																																																																																																																																																																																																																																																																																																																																																																																																																																																																																						
