# Goldman Sachs CoderPad

**Coderpad:**

1.) Find the minimum element in rotated array.
2.) https://leetcode.com/discuss/interview-question/356874/goldman-sachs-phone-screen-2019-shortest-path

Attened Round 1:
Question 1: FIle contains list of Ip Address. Get the IP address/s with highest frequency. If multiple Ip address available with higest freq, return sorted comma separeted.
Approch : Create TreeMap instead of Hashmap (for sorted IP address), get the min freq, get the Ip address with the min freq.

Ques2 : Trapping rain water
https://leetcode.com/problems/trapping-rain-water/
O(n)
Approch :
get the left wall,
get the right wall
if if left wall is smaller, check the left value and move the left pointer
if right wall is smaller, check the right value and move the right pointer

```
public int trap(int[] a) {
    
    int l = 0, r = a.length-1;
    int lMax = Integer.MIN_VALUE, rMax = Integer.MIN_VALUE;
    int total = 0;
    while(l < r){
       
        if(lMax < a[l]){
            lMax = a[l];
        }
        if(rMax < a[r]){
            rMax = a[r];
        }
        
        if(lMax <= rMax){    
            total = total + lMax-a[l];
            l++;
        }else{
            total = total + rMax-a[r];
            r--;
        }
    }
    
    return total;
}
```

**Coderpad:**
1. find the intersection elements in two arrays. Example:
Input: arr1: [1,1,2,2,2] arr2: [1,1,1,2,2,3,4,5]
Output: [1,1,2,2];

2.was exactly https://leetcode.com/problems/top-k-frequent-words/description/ , I applied the brute force of creating the hash, sort the hash and return the k elements.

**Coderpad:**
Following questions were asked in the coderpad round for goldman sachs

https://leetcode.com/discuss/interview-question/1396557/interview-question-police-and-thief
variation of this with max sum https://leetcode.com/problems/minimum-path-sum/description/

**Coderpad:**
Had Coderpad round with Goldman Sachs last week.
Q1 -- given a String like aaabbbcccaa need to return output like a3b3c3a2.
Q2 -- need to find max amount of gold in a given matrix, only allowed take steps up and right. Source point will be bottom-left

**Coderpad:**
CoderPad question of Goldman Sachs - 29th April 2022
Interviewer was very helpful, and question was also of easy level.
Q. Return the start index and length of the longest substring having identical characters in a given String.
i/p : S = "aabbbbbccddb"
o/p: [2,5]
explaination : As longest substring is 'bbbbb' of length 5 and start index as 2
i/p: S = "aabbb22rrrrr345571111111"
o/p: [17,7]
explaination : As '1111111' is the longest substring of length 7 and start index =17

I used sliding window to solve this. Please comment for the solution.

```
public class GSLongestSubString {
    public static void main(String[] args){
        String s1 = "aabbbbbccddb";
        String s2 = "aabbb22rrrrr345571111111";
        String s3 = "aaaabbeedddd";
        System.out.println("\n----------------"+"For Given String: "+s1+"----------------");
        callLongestSubstring(s1);
        System.out.println("\n----------------"+"For Given String: "+s2+"----------------");
        callLongestSubstring(s2);
        System.out.println("\n----------------"+"For Given String: "+s3+"----------------");
        callLongestSubstring(s3);
    }
    public static void callLongestSubstring(String s){
        int maxLen=0,start=0,end=0,len=0,startIndex=0;
        while(end+1!=s.length()){
            if(s.charAt(start)==s.charAt(end))
            {
                end++;
                len=end-start;
            }
            else
                start=end;
            if(maxLen<len)
            {
                if(end==s.length()-1)
                    maxLen=len+1;
                else
                    maxLen=len;
                startIndex=start;
            }
            System.out.println("start: "+start+" end: "+end+"  len: "+len+"  maxLen: "+
                    maxLen+"  startIndex: "+startIndex);
        }
        System.out.println("Start Index= "+startIndex+" Longest Length= "+maxLen);
    }
}
```

**Coderpad:**
I gave coderpad round for goldman sachs on october'20, 2 questions were asked
Time duration : 1hr

Q1. Min length of subarray exceeding the target sum
example:
[1,2,3,4], target = 6,
then answer = 2 since sum of all elements of subarray [3,4] has sum>=6 and its length is minimum
and if [1,2,3,4], target = 12, then return **-1 **, since no subarray has sum>=12

Solution:
Intially I gave O(n^2) approach , then explained 2 pointer approach
However faced some issue while coding it in coderpad.

Q2.optimal path to collect all rocks
Given a 2D array, with arr[i][j] representing the number of rock at that location.
Find optimal path from location A to location B in a multi dimensional array such that a person can collect maximum amount of rocks

Solution:
I used recursive approach using a list to keep track of the visited nodes.

Since I got stuck in 1st problem for 40 min, had only 20 mins to code 2nd solution, didn't complete this problem also.

I don't know whether they give some points for the approach , or they want the exact results to be returned.

Anyways good experience, and I would advise all other people to manage their time efficiently here.

Having been reading posts, thank everyone for posting their experience. It is quite helpful :-)

I just had my CoderPad round, and got three problems. No talking at all at the beginning, straightly dive into CoderPad (not sure if the interviewer was not in a good mood lol)...

Question 2 in this post https://leetcode.com/discuss/interview-question/896616/Goldman-Sachs-October-2020-coderpad-round
I solved it using dynamic programing.

**Coderpad:**
A variant of https://leetcode.com/problems/knight-probability-in-chessboard/solution/
Again, another dynamic programing question, which makes me wonder if the interviewer was deliberately giving me a hard time lol.

Solved both questions in like 40 mins, thinking I should be done for the day. Then the interviewer mentioned we still had time and gave me a thrid question... (so make sure you control your time lol)

Question like https://leetcode.com/discuss/interview-question/1481760/Goldman-Sachs-or-Coder-Pad-or-Initial-Round
Solved using binary search and hashmap.
Got a few BQs afterwards and briefly chatted for like 3 mins at the end about my research and CV.

Hope this is helpful and good luck everyone.

**Coderpad:**
I had just completed the first round with Goldman Sach's which is Coderpad Interview. This was for an opening in their Engineering Division.
Location: Salt Lake CIty
My Exp: 6 YOE
The interviewer introduced themselves and mentioned how they will conduct the interview followed by my introduction.
I was asked two situation based behavioral questions, these are random. They will describe an imaginery scenario and ask how you would deal the sutuation.
Then we moved to the technical part on coderpad.
First Coding question: https://leetcode.com/problems/find-the-winner-of-the-circular-game/description/
I was kinda stuck with a bug for a very long time but the interviewer was really patient and I was able to fix it and tests passed. Although this could've been solved in many ways I was just stuck, things these interviews do to my brain.
Second Coding Question: https://leetcode.com/problems/trapping-rain-water/
I only had 15 min left but I managed to code it up on time and all Test cases passed.
I practiced the Goldman Sachs tagged questions for this round.

**Coderpad:**
Today I had my coderpad round. I was asked two questions:

Median of two sorted arrays
Find a cycle in an array: You are given an integer array of size N.
Every element of the array is greater than or equal to 0.
Starting from arr[startIndex], follow each element to the index it points to. Continue to do this until you find a cycle.
Return the length of the cycle. If no cycle is found return -1
Examples:
countLengthOfCycle([1, 0], 1) == 2 ,
countLengthOfCycle([1, 2, 0], 0) == 3

Today I had my coderpad round with GS. We dived straight into the code. This was the first question:

A string was given. I needed to find the first non-repeating counter. If there is no such character, return 0.

Input:
asubsebusapd

Output:
e

Input:
aabbcc

Output:
0

Pretty straight-forward.

Used a hashmap to count the frequency.
Traverse the array to find the first element with frequency = 1 and return it.
If there is no such element, return 0.
The interviewer did not ask me to optimize it. If anyone has any idea, please comment.

Second question:
https://leetcode.com/discuss/interview-question/1837465/Goldman-Sachs-or-Coderpad-or-Find-the-maximum-gold-that-can-be-collected

Third question:
https://leetcode.com/discuss/interview-question/1837497/Goldman-Sachs-or-Coderpad-or-Find-the-largest-tree

**Coderpad:**
Today I had my coderpad round with GS. We dived straight into the code. This was the First question: https://leetcode.com/discuss/interview-question/1837422/Goldman-Sachs-or-Coderpad-or-First-non-repeating-character

Second question:
https://leetcode.com/discuss/interview-question/1837465/Goldman-Sachs-or-Coderpad-or-Find-the-maximum-gold-that-can-be-collected

I had solved two questions within 30 minutes so the interviewer asked me this third question:

A forest is represented with a hashmap. This hashmap has this key -> value relationship: child -> parent.
Every node has a unique integer element. I needed to find out the largest tree's root node. If there is a tie, return the smallest root.

The tree with the highest number of nodes, is the largest one. The edges are directed from parent to child.

Input:
{{1 -> 2}, {3 -> 4}}

Output:

**Coderpad:**

I first found out the roots present in the forest. Then created an adjacency list and applied BFS to count the nodes. Maintained the maximum count and root with the largest tree in two variables.

ad a coderpad interview sometimes this week. One easy and one medium. Q1. Exactly the same as https://leetcode.com/problems/minimum-size-subarray-sum/

Q2. Find the second smallest element in an array. Important to take note of the word element
For example, [4,8, 9, 2, 1, 1] should return 1, not 2. Also, if array.length is less than 2, just immediately return zero.

**Coderpad:**
Hi,

I had my GS Coderpad round today.
Had 2 questions;

Pascal's triangle
Find Median of 2 Sorted arrays, also asked me to not use Arrays.sort()
The interviewer was kind of encouraging, so, that was nice since I fumbled a bit in Pascal question, idk why, just got blank, but in the end it passed all cases

Best of luck to everyone else giving this round.

**Coderpad:**
Q1. Find the second smallest element in the array (use O(n) time)
Q2. Same as Q1 here

**Coderpad:**
Power of 10
https://leetcode.com/problems/power-of-three/
Given an integer, find out whether it is a power of 10 or not.
Train Map : Similar to the link post
https://leetcode.com/discuss/interview-question/1639541/goldman-sachs-coderpad-iplist-train-map

**Coderpad:**
I appear for the coderpad interview today,

Two Behavioral question

you submitted report to manager with minor error that neglected while submitting, how you approach on this situation
you and your co-worker working on assignment where you work 90% and co-worker did 10% of the work, you co-worker gets the credit for the entire project, after knowing this what's your point of view about this situation and how you treat your co-worker after this?
Two coding questions

implement deque
find out max tree node, if two or more nodes with similar length then return smaller node
eg: {4:6, 7:6, 3:4, 5:4, 13:15, 16:15, 12:13, 14:13} so for both 6 and 15 parent node with total 5 tree node, but output is 6 as it is smaller

**Coderpad:**

I appear for the coderpad interview today,

Two Behavioral question

you submitted report to manager with minor error that neglected while submitting, how you approach on this situation
you and your co-worker working on assignment where you work 90% and co-worker did 10% of the work, you co-worker gets the credit for the entire project, after knowing this what's your point of view about this situation and how you treat your co-worker after this?
Two coding questions

implement deque
find out max tree node, if two or more nodes with similar length then return smaller node
eg: {4:6, 7:6, 3:4, 5:4, 13:15, 16:15, 12:13, 14:13} so for both 6 and 15 parent node with total 5 tree node, but output is 6 as it is smaller

**Coderpad:**
I had a codepad round for Goldman. Brief intro followed by the 2 questions as below. Need to run as per custom test cases that's provided

https://leetcode.com/problems/trapping-rain-water/
Give a string, return the character & count of each character till it's repeating
Test case 1: "aabbccc" -> return "a2b2c3"
Test case2 :"ccc" -> return "c3"



15 minutes of background and a couple of behavioral questions.
followed by 60 minutes of coding 2 questions.

Behavioral:
Question 1: If a remote coworker dumps a task that is irrelevant to your project and signs off, how would you deal with it?
Question 2: If your manager asks confidential information from a different project you are working on, how would you deal with it?

**Coderpad:**
Coding:
Question 1: String compression problem
Question 2: Max Average of students

Questions same as https://leetcode.com/discuss/interview-question/5129061/Goldman-Sachs-or-Coderpad-or-String-Compression-and-Max-Average


**Coderpad:**
Coderpad round - interviewer seemed distracted most of the time and not very talkative.

First question: encode input string "aaaabbcccd" -> "a4b2c3d1"

My first ever coderpad interview, nervous and struggled with this one more than I should have. Passed all tests after ~25 mins. Interviewer asked if I could think of additional test cases. I said nope, just wanted to get to the next question.

Second questions: Median of two sorted arrays: https://leetcode.com/problems/median-of-two-sorted-arrays/

I have seen this question but never attempted to solve it. Went back and forth with interviewer about the best approach, decided on two pointers traversing each array (1 for each). Got all tests to pass but told the interviewer I could think of a test case to make my code fail. Had about 3 minutes to try and find a solution but could not. Interviewer abruptly ended interview when time was up.

Interview was four weeks ago and haven't heard back. Followed up with recruiter last who said she was still waiting for info. Thoughts?


Early careers Software Engineer - US
Asked Some behavioral questions and jumped to coderpad

**Coderpad:**
Find the second smallest number in the array
Given a list of lists of students and scores, return student with highest average


Coderpad round: 2 questions to be completed in 1 hr

**Coderpad:**
Ques 1: Group all anagrams and return as set of list
Ques 2: Find max sum of rocks in 2d matrix from source to destination

**Coderpad:**

Hello Guys need help in preparing for the virtual onsite of Goldman Sachs.
I have done with coderpad round (phone screen)
1 - find longest substring with unique character.
2- find minimum subarray with sum greater than or equal to K.
