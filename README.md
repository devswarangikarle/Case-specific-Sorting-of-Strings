# Case-specific-Sorting-of-Strings

Given a string S consisting of only uppercase and lowercase characters. The task is to sort uppercase and lowercase letters separately such that if the ith place in the original string had an Uppercase character then it should not have a lowercase character after being sorted and vice versa.

Input
There is a single line of input containing a string of characters containing both uppercase and lowercase.

Constraints:
n == Length of string
1 ≤ n ≤ 105
Output
Print the string sorted according to the provided descriptiondef case_specific_sort(s):
    uppercase_chars = []
    lowercase_chars = []
    for c in s:
        if c.isupper():
            uppercase_chars.append(c)
        else:
            lowercase_chars.append(c)

    sorted_uppercase = sorted(uppercase_chars)
    sorted_lowercase = sorted(lowercase_chars)

    result = ''
    upper_index = lower_index = 0
    for c in s:
        if c.isupper():
            if sorted_uppercase:
                result += sorted_uppercase[upper_index]
                upper_index += 1
            else:
                result += c  
        else:
            if sorted_lowercase:
                result += sorted_lowercase[lower_index]
                lower_index += 1
            else:
                result += c  
    return result

s = input()

print(case_specific_sort(s)).


