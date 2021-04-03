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


Best Efficient 
=========================================================================
#include <bits/stdc++.h> 
using namespace std; 

const int CHAR=256;
int leftMost(string &str) 
{
    bool visited[CHAR];
    fill(visited,visited+CHAR,false);
    int res=-1;
    for(int i=str.length()-1;i>=0;i--){
        if(visited[str[i]])
        res=i;
        else
        visited[str[i]]=true;
    }
    
    return res;
}
 
int main() 
{ 
    string str = "geeksforgeeks";
    cout<<"Index of leftmost repeating character:"<<endl;
    cout<<leftMost(str)<<endl;  
    
    return 0; 
} 
==================================================================================
 
 QUESTION 4;
 ============================================
 Create LeftMostRepeatingCharacter

Naive Approach::
--------------------------
Step 1: take one character of the string and iterate over the string ,if you find the same character , then return it's index.
Step 2: If not repeat the same Step  again , If not found return -1 .



Efficient Approach 
===========================================
Step 1:  Take  a count array of size 256 and initialize it to 0 .
Step 2: Iterate it over the string , and store it's count in the count array .
Step 3: Scan the count array , if count[str[i]]>1 then print that index.
Step 4: Of not , then return , -1;
=====================================================
Thank you
