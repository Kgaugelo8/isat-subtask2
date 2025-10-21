Initial commit: Create main C++ file for Sub-task 2
#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>
using namespace std;

// --- Conversion Functions ---
string decToBin(int n){string s="";while(n){s=to_string(n%2)+s;n/=2;} return s==""?"0":s;}
int binToDec(string b){int d=0;for(char c:b)d=d*2+(c-'0'); return d;}
string decToHex(int n){string s="";char h[]="0123456789ABCDEF";while(n){s=h[n%16]+s;n/=16;} return s==""?"0":s;}
int hexToDec(string h){int d=0;for(char c:h){c=toupper(c);d=d*16+((c<='9')?c-'0':c-'A'+10);} return d;}
 Implement menu-driven interface for all conversion options
int main(){
    srand(time(0));
    int choice;
    do{
        cout<<"\n======= NUMBER CONVERTER MENU =======\n";
        cout<<"1. Convert Decimal -> Binary\n";
        cout<<"2. Convert Binary -> Decimal\n";
        cout<<"3. Convert Decimal -> Hexadecimal\n";
        cout<<"4. Convert Hexadecimal -> Decimal\n";
     Add Demo option to generate and convert random integers to binary
        cout<<"5. Demo (Generate and convert random integers to binary)\n";
        cout<<"6. Exit\n";
        cout<<"Enter your choice (1-6): ";
        cin>>choice;
Add Decimal to Binary and Binary to Decimal functions
        if(choice==1){
            int n; cout<<"Enter Decimal: "; cin>>n;
            cout<<"Binary: "<<decToBin(n)<<endl;
        }
        else if(choice==2){
            string b; cout<<"Enter Binary: "; cin>>b;
            cout<<"Decimal: "<<binToDec(b)<<endl;
   Add Decimal to Hexadecimal and Hexadecimal to Decimal functions         
        }
        else if(choice==3){
            int n; cout<<"Enter Decimal: "; cin>>n;
            cout<<"Hexadecimal: "<<decToHex(n)<<endl;
        }
        else if(choice==4){
            string h; cout<<"Enter Hexadecimal: "; cin>>h;
            cout<<"Decimal: "<<hexToDec(h)<<endl;
        }
        else if(choice==5){
            int n = rand()%100;
            cout<<"Random Decimal: "<<n<<" -> Binary: "<<decToBin(n)<<endl;
        }
        else if(choice!=6){
            cout<<"Invalid choice! Please enter 1-6.\n";
        }
    }while(choice!=6);

    cout<<"Exiting program... Goodbye!\n";
}
