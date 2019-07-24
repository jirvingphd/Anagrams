**Course**: Data Science   <br/>
**Mod**:    1                 <br/>
**Topic**:   Anagrams: Functions, strings, iteration, lists and or dictionaries <br/>
**Amount of time**: 45 minutes - 1 hour <br/>
**Author**: Matthew Mitchell matt.mitchell@flatironschool.com

## Teacher Notes

## Introduction

This problem only requires basic python programming knowledge but stands to be a moderately difficult problem solving exercise.
In an in person classroom, I recommend allocating 15-25 minutes for students to work on the problem, followed by 30 plus minutes for discussion. In an online or flipped classroom, student work time should be front loaded and then the entire classroom meeting time can be dedicated to reviewing student solutions. Start by asking students for their approaches, review places where students got stuck and have students articulate what their code does. Address any potential misconceptions that arise and check for student understanding by asking questions to other students regarding a specific code snippet that is presented. Then ask for alternative solutions (2 potential solutions are provided below.)

## Learning Goals

* Build students problem solving ability
* See that there are multiple valid solutions to a problem
* Master string slicing
* Iterate over strings
* Write functions

## Prerequisite Knowledge

Students should already have been exposed to and practice working with basic python data types.

## Paired Programming
                                                                                            
                                                                                      
Write a function to determine if two strings are anagrams. (Permutations of each other.)

## Teacher Notes

Hints / Kick-off Questions

* What is an anagram? (Simple reordering of letters)
* What data type would the inputs be?
* How would you go about checking if the characters from string 1 are also in string 2?
* 

* What is the problem we're trying to solve?
* How does this 

* Start with pseudocode / verbal explanations first.
    * If you were doing this yourself, how would you do this?



```python
## Teacher Notes

#Two potential solutions

def anagram(s1, s2):
    if len(s1) != len(s2):
        return False
    s1_letters = {}
    for l in s1:
        s1_letters[l] = s1_letters.get(l, 0) + 1 #Update previous entry by 1, if no entry start with 0
    s2_letters = {}
    for l in s2:
        s2_letters[l] = s2_letters.get(l, 0) + 1 #Same as above, could use subfunction
    for l in s1_letters.keys():
        if s1_letters[l] != s2_letters[l]:
            return False
    return True #If nothing has returned false, the two are anagrams!

def anagram2(s1, s2):
    s2 = list(s2)
    for l in s1:
        try:
            s2.remove(l)
        except:
            return False #s2 did not have the letter to remove
    if s2 == []:
        return True #their was a perfect correspondence and s2 is now an empty list
    return False
    
```

## Further Teacher Notes

Work through student solutions first. If students are unable to generate solutions independently, prompt them with follow up questions such as, how could we start checking letter by letter if the two matched? (This is apt to lead to a iterating over the strings similar to solution 2.) Alternatively, if you reference a "bag of letters" approach, you are more apt to produce solutions similar to the first solution above involving dictionaries and counts of letters. 

Once code is generated, be sure to have students go through the code line by line and explain verbally what is happening. Also be sure to explore edge cases which are important to consider. For example, "aabc" and "cba" are not anagrams because a occurs twice in the first string but only once in the second. 
