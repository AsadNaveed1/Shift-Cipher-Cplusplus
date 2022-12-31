// Author : Muhammad Asad Naveed
// U.No : 3035957848
// Assignment 1 Question 3
// Description 1 :a C++ program which encrypts and decrypts a sequence of input characters using an algorithm adapted from the Vignѐre cipher  


#include <iostream>
#include <cctype> //to convert to lower and upper case

using namespace std;

const int MAXLEN = 50;  // max length for input sequence of characters
const int MAXKEY = 10;  // max length for key



void encryption(char alph, int number, char alphabetsmall[], char alphabetlarge[], int length)
{
  int c, y;
  char smaller, larger;

  if(isalpha(alph))                        //to ensure that alphabet is input
  {

    if(alph>='a' && alph<='z')             //if the input character by the user if lower case converted to upper case
    {

      char smaller= toupper(alph);
      for(int w=0; w<26; w++)
        if(alphabetlarge[w]==smaller)        //position of the input alphabet is found in the alphabet
        {

          int c= w;
          y= (c + number) % 26;            //formula to find the y which is the postion new character
          cout<<alphabetlarge[y];          //prints out the alphabter corresponding the new position
        break;
        }
    
    }


    else if(alph>='A' && alph<='Z')          //if the input character by the user if upper case converted to lower case
    {
    
      char larger= tolower(alph);
      for(int w=0; w<26; w++)
        if(alphabetsmall[w]==larger)          //position of the input alphabet is found in the alphabet
        {

          int c= w;
          y= (c + number) % 26;            //formula to find the y which is the postion new character
          cout<<alphabetsmall[y];           //prints out the alphabter corresponding the new position
        break;  
        }  
    } 

  }
  else
  {
    cout << alph;                           //prints those which are not alphabets


  } 
  
}  

void decryption(char alph, int number, char alphabetsmall[], char alphabetlarge[], int length)
{
  int c, y;
  char smaller, larger;

  if(isalpha(alph))                             //to ensure that alphabet is input
  {

    if(alph>='a' && alph<='z')                 //if the input character by the user if lower case converted to upper case
    {

      char smaller= toupper(alph);
      for(int w=0; w<26; w++)
        if(alphabetlarge[w]==smaller)          //position of the input alphabet is found in the alphabet
        {

          int c= w;
          y= ((c - number)+26) % 26;          //formula to find the y which is the postion new character
          cout<<alphabetlarge[y];             //prints out the alphabter corresponding the new position
        break;
        }
    
    }


    else if(alph>='A' && alph<='Z')           //if the input character by the user if upper case converted to lower case
    {
    
      char larger= tolower(alph);
      for(int w=0; w<26; w++)
        if(alphabetsmall[w]==larger)            //position of the input alphabet is found in the alphabet
        {

          int c= w;
          y= ((c - number)+26) % 26;           //formula to find the y which is the postion new character, plus 26 is done to avoid non negative number
          cout<<alphabetsmall[y];             //prints out the alphabter corresponding the new position
        break;  
        }  
    } 

  }
  else
  {
    cout << alph;


  } 
  
}  

/////////////////////////////////////MAIN FUNCTION/////////////////////////////////////////////
int main()
{
  // to store user inputs
  char s;             // 'e' for encryption, 'd' for decryption
  char text[MAXLEN];  // the sequence of characters to encrypt/decrypt
  char key[MAXKEY];   // the key

  int lenkey, j, x, e;

  char alphabetsmall[26]={'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'};
  char alphabetlarge[26]={'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'};
  int store[26];          //an array to store position of keys
  int counter;            //to keep check of the number of characters input by the user
  char let;               //stores the uppercase key

  counter=0;
  cin>>s;
  for(int i=0; i<=50; i++)     //a loop that continues until "!" is entered
  { 
    cin>>text[i];
    if(text[i]=='!')
    {
      break;
    }  

    else
    {
      counter++; 
    }  

  }
  cin>>lenkey;                        //user tells how many keys
  for(int j=0; j<lenkey; j++)
  {
    cin>>key[j];

  }  
  int checker=0;                       
  for(int e=0; e<=lenkey; e++)        //a loop to to take input of keys from the user which are all converted to uppercase
  {
    let= toupper(key[e]);

    for(int x=0; x<=25; x++)
    {
      if(alphabetlarge[x]==let)
      {
          store[checker]=x;          //store is an array which stores the position of each key in an array
  checker++;
  break;
      }
    }  

  }



  int checkingnumber=0;
  if(s=='e')
  {
    while(checkingnumber<counter)
    {

      for(int t=0; t<lenkey; t++)        //a loop for the position of keys so that each letter is encrypted accordingly
      {

        encryption(text[checkingnumber], store[t], alphabetsmall, alphabetlarge, counter);   //encryption function is called 

    checkingnumber++;

   if (checkingnumber >= counter)
	 {

	   cout << '!'<< endl;   // is displayed when all encrypted text is displayed
	   break;

	 }

      }

    }

  }
  

  else if(s=='d')
  {
    while(checkingnumber<counter)
    {

      for(int t=0; t<lenkey; t++)
      {

        decryption(text[checkingnumber], store[t], alphabetsmall, alphabetlarge, counter);  //decryption function is called 

    checkingnumber++;

   if (checkingnumber >= counter)
	 {

	   cout << '!'<< endl;   // is displayed when all decrypted text is displayed
	   break;

	 }

      }

    }

  }


  if (counter ==  0)
  {
    cout << "!" << endl;
    counter++;
  }

  return 0;
}
