# Palindrome_Checker
JavaScript

Return true if the given string is a palindrome. Otherwise, return false.  

A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.  

Note: You'll need to remove all non-alphanumeric characters (punctuation, spaces and symbols) and turn everything into the same case (lower or upper case) in order to check for palindromes.  

We'll pass strings with varying formats, such as racecar, RaceCar, and race CAR among others.  

We'll also pass strings with special symbols, such as 2A3*3a2, 2A3 3a2, and 2_A3*3#A2.  

Provided test cases:  
palindrome("eye") should return true.  
palindrome(“race car”) should return true.  
palindrome(“not a palindrome”) should return false.  
palindrome(“A man, a plan, a canal. Panama”) should return true.  
palindrome(“never odd or even”) should return true.  
palindrome(“nope”) should return false.  

  
#### For this solution, I'll use 5 methods:  

(1) The toLowerCase() method to return the calling string value converted to lowercase.  
(2) The replace() method to return a new string with some or all matches of a pattern replaced by a replacement. We will use one of the RegExp we just created earlier.  
(3) The split() method splits a String object into an array of strings by separating the string into sub strings.  
(4) The reverse() method reverses an array in place. The first array element becomes the last and the last becomes the first.  
(5) The join() method joins all elements of an array into a string.  
  
### Solution:  

function palindrome(str) {  
  // Step 1. Lowercase the string and use the RegExp to remove unwanted characters from it  
    
  &ensp; var re = /[\W_]/g;  
  &ensp; // or var re = /[^A-Za-z0-9]/g;  
    
  &ensp; var lowRegStr = str.toLowerCase().replace(re, '');  
  &ensp; // str.toLowerCase() = "A man, a plan, a canal. Panama".toLowerCase() = "a man, a plan, a canal. panama"  
  &ensp; // str.replace(/[\W_]/g, '') = "a man, a plan, a canal. panama".replace(/[\W_]/g, '') = "amanaplanacanalpanama"  
  &ensp; // var lowRegStr = "amanaplanacanalpanama";  
    
  &ensp; // Step 2. Use the same chaining methods with built-in functions  
    
  &ensp; var reverseStr = lowRegStr.split('').reverse().join('');   
  &ensp; // lowRegStr.split('') = "amanaplanacanalpanama".split('') = ["a", "m", "a", "n", "a", "p", "l", "a", "n", "a", "c", "a", "n", "a", "l", "p", "a", "n", "a", "m", "a"]  
  &ensp; // ["a", "m", "a", "n", "a", "p", "l", "a", "n", "a", "c", "a", "n", "a", "l", "p", "a", "n", "a", "m", "a"].reverse() = ["a", "m", "a", "n", "a", "p", "l", "a", "n", "a", "c", "a", "n", "a", "l", "p", "a", "n", "a", "m", "a"]  
  &ensp; // ["a", "m", "a", "n", "a", "p", "l", "a", "n", "a", "c", "a", "n", "a", "l", "p", "a", "n", "a", "m", "a"].join('') = "amanaplanacanalpanama"  
  &ensp; // So, "amanaplanacanalpanama".split('').reverse().join('') = "amanaplanacanalpanama";  
  &ensp; // And, var reverseStr = "amanaplanacanalpanama";  
     
  &ensp; // Step 3. Check if reverseStr is strictly equals to lowRegStr and return a Boolean  
    
  &ensp; return reverseStr === lowRegStr; // "amanaplanacanalpanama" === "amanaplanacanalpanama"? => true  
}  
  
palindrome("A man, a plan, a canal. Panama");  
  
console.log(palindrome==palindrome);  
  
### Output: true
