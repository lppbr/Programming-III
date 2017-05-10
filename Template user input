/*
 Name: Travis Neel
 Topic: Simplify user input with input function and function template
 */
#include <string>
#include <iostream>
#include <limits>
using std::string;
using std::cin;
using std::cout;
using std::endl;

template<class T, class T2, class T3>
inline T get_int(const T2 prompt, T2 const errmsg, T3 range_check, const T min=0, const T max=INT_MAX);

const char A='A'; // provides range checking for getting a char
const char Z='Z';

class Student {
private:
    
    string name="";
    int ID=0;
    double GPA=.0;
    char middle=' ';
    int birth_year=1900;
public:
    
    inline Student (
                    int ID=get_int("enter ID: ", "invalid ID, 1000 <= ID <= 999999, try again\n",false, 1000, 999999),
                    double GPA=get_int("enter GPA: ", "GPA must be 0 > 4.0 ", true, 0.0, 4.0),
                    char middle=get_int("Enter middle initial: ", "Must be a capital letter! ", true, A, Z)
                    ) {
        
        this->ID=ID;
        this->GPA=GPA;
        this->middle=middle;
    }
    
    void show() const;
    
};

void Student::show() const {
    cout<<"\n ID= "<<ID<<"\n GPA= "
        <<GPA<<"\n Middle initial= "<<middle<<"\n\n";
}

template<class T, class T2, class T3>
T get_int(const T2 prompt, T2 const errmsg, T3 range_check, const T min, const T max){
    T intI=0;
    
    while (true) {
        cout << prompt;
        // looking for bug. something to do with the datatype of intI and the cin>>intI statement?
        // type conversion or alternative method that doesn not rely on integer only input with cin.
        // either way the statment seems to work fine with minimal testing
        
        //if (((cin >> intI) and !range_check)
        //    or (range_check and intI >= min and intI <= max) ) break;
        
        if (((cin >> intI) and !range_check)
            or (range_check and intI >= min and intI <= max)) break;
        
        cout<<errmsg;
        cin.clear();
        cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
        
    }
    return intI;
}

int main (){
    
    string name1, name2="";
    
    cout<<"Enter Student1 name= "; cin>>name1;
    Student student1;
    cout<<"Enter Student2 name= "; cin>>name2;
    Student student2;
    cout<<"Name: "<<name1<<endl;
    student1.show();
    cout<<"Name: "<<name2<<endl;
    student2.show();

    return 0;
}
