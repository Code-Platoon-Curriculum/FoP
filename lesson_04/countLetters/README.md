Assignment: Count Letters Function

Write a function named `countLetters` that takes as a parameter a string and returns an object that tabulates how many of each letter is in that string. The string can contain characters other than letters, but only the letters should be counted. The string could even be the empty string (just ""). Lower-case and upper-case versions of a letter should be part of the same count. The keys of the object should be upper-case letters. If a letter does not appear in the string, then it would not get added to the object. 

For example, if the string is:

"AaBb"


then the object that is returned should contain these key-value pairs:
{A: 2, B: 2}


**Note:** Don't use any built-in letter-checking methods. Use character comparison instead (e.g., `char >= 'A' && char <= 'Z'`).