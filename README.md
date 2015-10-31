# -WSQ11-Yosoy196.2

#include iostream>

#include "BigIntegerLibrary.hh"

using namespace std;

int Upper;

int Lower;

BigInteger Rev;

BigInteger Number;

int Natural=0;

int NL=0;

int LN=0;


BigInteger Reverse(BigInteger val){

BigInteger inv= 0;

while (val != 0){

  inv= inv*10 + val % 10;
  
  val= val/10;
  
}
  return inv;
  
}

void Palindrome(BigInteger N, BigInteger R){

  if(N == R){
  
Natural = Natural+1;
}
else {

int Repetition= 0;

BigInteger X= N;

while (X!=R && Repetition < 30){

X=X+R;
R= Reverse(X);

Repetition= Repetition+1;

}
if (Repetition == 30){

  std::cout << "A Lynchrel number was found: " << N << std:: endl;
  
  LN= LN+1;
  
}
else {

  NL=NL+1;
}}}

int main (){

std::cout << "This is a Lychrel number detector. Please enter the lower bound: ";

std::cin >> Lower;


std::cout << "Enter the upper bound: ";

std::cin >> Upper;

Number = Lower;

while(Number <= Upper){

Rev= Reverse(Number);

Palindrome(Number, Rev);

Number = Number + 1;
}

std::cout << "The numbers analyzed were between: " << Lower << " and: " << Upper << std::endl;

std::cout <<  "Natural palindromes encountered: " << Natural << std::endl;

std::cout << "Non-Lycherels encountered: " << NL << std::endl;

std::cout << "Lycherel Numbers encountered: " << LN << std::endl;


return 0;
}
