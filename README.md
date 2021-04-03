# String_In_C-
All Important Questions Along with c++ solution in c++

Qustion no 3.
=========================
 Check Anagram :
 
 Iterative Solution:
 --------------------------
 Logic :
 
 Anagram  :: Number of character and type of character must be same 
 Step 1: First compare the length of the String if not equal then return false;
 Step 2: Sort the both String .
 Step 3: Compare the the both String , if Both the string  are same the these are Anagram else not Anagram.
 
 Time Compleity =O(nlogn);
 
  Functions code:
  C++ Implementation:
  -------------------------------------------------------------------------------------------------------------------------
  bool AreAnagram(string &s1,string &s2)
  {
     if(s1.length()!=s2.length())
     return false;
     sort(s1.begin(), s1.end());
     sort(s2.begin(), s2.end());
     if(s1==s2)
     {
     return true;
     }
     else
     {
     return false;
     }
     
     
   }
  ---------------------------------------------------------------------------------------------------------------------------------
  Efficent Approach :C++ Implementation :
  
  ==================================================================================================================================
#include <bits/stdc++.h>
using namespace std;
int CHARS=256;
bool areAnagram(string &s1, string &s2)
{
    if(s1.length()!=s2.length())
       return false;
       int count[CHARS]={0};
       for(int i=0;i<s1.length();i++)
       {
           count[s1[i]]++;
           count[s2[i]]--;
       }
       for(int i=0;i<CHARS;i++)
       {
           if(count[i]!=0)
           return false;
       }
       return true;
}
int main() {
	string s1="aabbcc";
	string s2="ababcc";
	if(areAnagram(s1,s2)==1)
	{
	cout<<"Given String is Anagram";
	}
	else
	{
	    cout<<"Not Anagram ";
	}
	

	
	return 0;
}
 
