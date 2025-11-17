# Number-of-Substrings-With-Only-1s

Given a binary string s, return the number of substrings with all characters 1's. Since the answer may be too large, return it modulo 109 + 7.

 class Solution:
    def numSub(self, s: str) -> int:
        mod = int(10 ** 9 + 7)
        ans = 0

        count = 0
        for i in range(len(s)):
            if(s[i] == "1"):
                count += 1
            else:
                ans += ((count * (count + 1)) // 2) % mod
                count = 0
        
        ans += ((count * (count + 1)) // 2) % mod
        
        return ans
