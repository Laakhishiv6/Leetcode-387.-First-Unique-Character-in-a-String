# Leetcode-387.-First-Unique-Character-in-a-String
# Description
Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.
# Solution
In the given problem we have been given a string s , in which we have to find the first  character with unique occurrence.

# Algorithm
1. Initialize a frequency array of size 26 with all values 0 to store occurrences of each lowercase letter.
2. Loop through the string, for each character compute its index as ord(char) - ord('a'), and increment the count at that index.
3. Loop through the string again, and for each character check if its count in the frequency array is 1.
4. Return the index of the first such character.
5. If no unique character is found, return -1.
# Code
class Solution {
public:

    int firstUniqChar(string s) {
        int freq[26]={0};
        for(char c:s){
            freq[c-'a']++;
        }
        for(int i=0;i<s.size();i++){
            if(freq[s[i]-'a']==1){
                return i;
            }
        }
        return -1;
    }
    };
# Complexity
Time Complexity: 

First loop (for(char c:s)) → runs through all n characters once → O(n).

Second loop (for(int i=0; i<s.size(); i++)) → also runs through all n characters once → O(n).

Total: O(n + n) → O(n).

Space Complexity: 

The freq[26] array uses a fixed amount of space (26 integers) regardless of input size.

No extra space proportional to n is used.

So, O(1) auxiliary space.

