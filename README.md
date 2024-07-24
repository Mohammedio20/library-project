//# library-project
//library management
#include <iostream>
using namespace std;

//Global Consts
const int MAXBOOKS = 10;
const int MAXSTUDENTS = 7;

// Global Variables
int booksCount =0;
int studentsCount = 0;
string studentName[MAXSTUDENTS];
string title[MAXBOOKS];
string author[MAXBOOKS];
int isbn[MAXBOOKS];

// Function Protoype
void addBook();
void viewBooks();
void findBook(int);
int main()
{
		cout<<"########## ----Hello To Mohammed Library---- ############\n\n";
			// The Athentication 
			string password;
			string p = "Mohammed";
			int isAdmin;
			int option;
			cout<<"### If Admin choose ? - 1 \n### Student choose ? - 2 \n";
	cin>>isAdmin;
	//---------------------Admin---------------------------//
		if(isAdmin == 1) {
	    cout<<"### Hello Admin enter password ###\n";
	    cin>>password;
	    if(password != p) {
	        
	          cout<<"##### Incorrect password ######\n ";
	        return -1;
	    } else {
	        
 cout << "--- Admin options:\n--- 1. Add book\n---2. View books\n";
	       
	        cin>>option;
	        	        switch(option) {
	            case 1: 
	                addBook();
	                break;
	      
                    case 2: 
                        viewBooks();
                        break;
                        }
	 }
	 	//---------------------Student---------------------------//
		} else if (isAdmin==2){
		    	    cout<<"### Hello Student enter password ###\n";
	    cin>>password;
	    if(password != p) {
	        
	          cout<<"##### Incorrect password ######\n ";
	        return -1;
	    } else {
	        
 cout << "--- Student options:\n--- 1. view book\n---2. find books\n";
	       
	        cin>>option;
	        	        switch(option) {
	            case 1: 
	                viewBooks();
	                break;
	      
                    case 2: 
                    int is;
                    cout<<"### enter ISBN number ###\n";
                    cin>>is;
                        findBook(is);
                        break;
	        	        }
		}
		}
}


void addBook(){
    if(booksCount>=MAXBOOKS)
    {
        cout<<"### The Number of books has exceeded max limit###\n";
        return;
    } else {
        cout<<"-----  enter the  book title  -----\n";
        cin>>title[booksCount];
        
       cout<<"-----  enter the  book author  -----\n";           cin>>author[booksCount];
       
       cout<<"-----  enter the  book isbn  -----\n";
       cin>>isbn[booksCount];
    }
    booksCount++;
    int yes;
    cout<<"###wanna view Books -1###\n";
    cin>>yes;
    if(yes == 1){
    viewBooks();
    }
}

void viewBooks(){
    for(int i = 0; i< booksCount; i++)
    {
cout << "--- Title: " << title[i] << endl;
cout << "--- Author: " << author[i] << endl;
cout << "--- ISBN: " << isbn[i] << endl;
    }
    
    }
    
void findBook(int is){
    for(int i = 0; i< booksCount; i++){
        if(is == isbn[i]){
 cout << "--- Title: " << title[i] << endl;
cout << "--- Author: " << author[i] << endl;
cout << "--- ISBN: " << isbn[i] << endl;
return;
        } 
        else if(is != isbn[i]){
            cout<<"#### books is not Found #####\n";
        }
    }
}

