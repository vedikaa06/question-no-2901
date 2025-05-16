# question-no-2901
Solution to question no 2901 on LeetCode 

2901. Longest Unequal Adjacent Groups Subsequence II

You are given a string array of words and array groups, both arrays with length n.

The hamming distance between two strings of equal length is the number of positions at which the corresponding characters are different.

You need to select the longest subsequence from an array of indices [0, 1, ..., n - 1], such that for the subsequence denoted as [i0, i1, ..., ik-1] having length k, the following holds:

For adjacent indices in the subsequence, their corresponding groups are unequal, i.e., groups[ij] != groups[ij+1], for each j where 0 < j + 1 < k.
words[ij] and words[ij+1] are equal in length, and the hamming distance between them is 1, where 0 < j + 1 < k, for all indices in the subsequence.
Return a string array containing the words corresponding to the indices (in order) in the selected subsequence. If there are multiple answers, return any of them.

Note: strings in words may be unequal in length.

solution:
Each pair of consecutive words in the sequence:

Belong to different groups, and

Differ by exactly one character (checked using the check() method).

How it works:
dp[i] stores the length of the longest valid subsequence ending at i.

prev[i] helps reconstruct the path (sequence) by storing the previous word index.

For each word i, it checks all previous words j:

If words[i] and words[j] differ by one character and are from different groups, update dp[i].

After filling dp[], it backtracks from the index with the maximum length (maxIndex) using prev[] to build the final sequence.

check() method:
Returns true if two strings of the same length differ by exactly one character.

Result:
Returns the longest valid list of words following the above two conditions.
