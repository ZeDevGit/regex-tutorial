# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors are a unique component in Regex in that they work a bit differently with how they deal with strings. Anchors provide a method to limit how regex matches a string by telling the regex engine where matches can being or end. They can be used to ensure that a regex matches a string at a specific place: either at the beginning or end of a string, at the end of a line, or on a word or non-word boundary.

* `^` Used to find matches at the beginning of a string, or at the beginning of a line if the multiline flag is enabled.
* `$` Used to find matches at the end of a string, or end of a line if the multiline flag is enabled. 

### Quantifiers

Quantifiers in regular expressions define how many instances of a character, group, or character class must be present in the input for a match to be found. Here are the most common quantifiers:

* `*` - The asterisk indicates zero or more of the preceding element. For example, a* matches any number of 'a' characters, including none.

* `+` - The plus sign indicates one or more of the preceding element. For example, a+ matches one or more 'a' characters.

* `?` - The question mark indicates zero or one of the preceding element. It makes the preceding element optional. For example, a? matches zero or one 'a' character.

* `{n}` - Curly brackets with a number inside specify exactly 'n' occurrences of the preceding element. For example, a{3} matches exactly three 'a' characters.

* `{n,}` - Curly brackets with a number followed by a comma specify 'n' or more occurrences of the preceding element. For example, a{2,} matches two or more 'a' characters.

* `{n,m}` - Curly brackets with two numbers separated by a comma specify between 'n' and 'm' occurrences of the preceding element. For example, a{2,3} matches either two or three 'a' characters.

### OR Operator



### Character Classes



### Flags



### Grouping and Capturing



### Bracket Expressions



### Greedy and Lazy Match



### Boundaries



### Back-references



### Look-ahead and Look-behind



## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
