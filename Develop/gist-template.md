# Regex Tutorial

Introductory paragraph (replace this with your text)

## Summary

This tutorial is devoted to teaching the various aspects of Regex and how it can be used to create patterns that help match, locate and manage text.

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

The OR operator in regular expressions is represented by the pipe symbol |. It is used to specify more than one pattern to match within the same position of a string.

Here's how it works:

* a|b - This pattern matches either 'a' or 'b'. It will first try to match 'a'. If 'a' is not found, it will then try to match 'b'.
The OR operator can be used with characters, groups, and character classes. For example:

* (abc|def) - This pattern matches either 'abc' or 'def'.

### Character Classes

Character classes in regular expressions allow you to match any symbol from a defined set of characters. Here are the most common character classes:

* `[abc]` - This pattern matches any single character that is either 'a', 'b', or 'c'. It's equivalent to a|b|c.

* `[a-z]` - This pattern matches any single lowercase letter. The hyphen - is used to specify a range of characters.

* `[A-Z]` - This pattern matches any single uppercase letter.

* `[0-9]` - This pattern matches any single digit.

* `[a-zA-Z]` - This pattern matches any single letter, regardless of case.

* `[^abc]` - This pattern matches any single character that is not 'a', 'b', or 'c'. The caret ^ at the start of the character class negates the set.

There are also some special character classes:

* `\d` - This is equivalent to [0-9], it matches any single digit.

* `\D` - This is equivalent to [^0-9], it matches any single character that is not a digit.

* `\w` - This matches any word character, equivalent to [a-zA-Z0-9_].

* `\W` - This matches any non-word character, equivalent to [^a-zA-Z0-9_].

* `\s` - This matches any whitespace character (spaces, tabs, line breaks).

* `\S` - This matches any non-whitespace character.

### Flags

Flags in regular expressions are used to change the search pattern. Here are the most common flags:

* `g` - Global search. Without this flag, the search stops after the first match. With this flag, the search continues to find all matches.

* `i` - Case-insensitive search. Without this flag, the search is case-sensitive. With this flag, the search ignores case.

* `m` - Multiline search. Without this flag, the ^ and $ metacharacters match the start and end of the entire string. With this flag, they match the start and end of each line.

* `s` - Allows . to match newline characters. Without this flag, the . metacharacter matches any character except newline characters. With this flag, it matches any character including newline characters.

* `u` - Unicode mode. It makes the regex engine treat the pattern as a sequence of Unicode code points. This is necessary for using Unicode property escapes \p{...} and named captures (?<name>...).

* `y` - Sticky mode. It makes the regex engine start the search not from the start of the string, but from the position indicated in lastIndex property of the regex object.

### Grouping and Capturing

Grouping and capturing are powerful features in regular expressions that allow you to not only match complex patterns but also extract and use parts of the string that match the pattern.

Here's how they work:

* Grouping

Grouping is done using parentheses (). The part of the pattern enclosed in parentheses is treated as a single unit by the regex engine. This is useful when you want to apply a quantifier to a group of characters, or when you want to group alternatives.

For example, (abc)+ matches one or more occurrences of 'abc'. Without the parentheses, abc+ would match 'ab' followed by one or more 'c' characters.

* Capturing

When you use parentheses for grouping, you're also creating a "capture group". The regex engine will "capture" the part of the string that matches the pattern inside the parentheses, and you can use this captured text later.

Capture groups are numbered by counting their opening parentheses from the left to the right. The first capture group is 1, the second is 2, and so on. You can refer to these groups in three ways:

In the pattern itself, using a backreference (\1, \2, etc.). This matches the same text that was matched by the capture group. For example, (abc)\1 matches 'abcabc'.

In the replacement part of a replace function, using a dollar sign ($1, $2, etc.). This inserts the text that was matched by the capture group.

In the result of the match or exec function, which returns an array where each capture group has its own element.

There's also a special kind of parentheses (?:...) that creates a non-capturing group. This is useful when you want to group parts of the pattern, but you're not interested in reusing the matched text. Non-capturing groups are not numbered, and you can't refer to them using backreferences or in the replacement string.

### Bracket Expressions

Bracket expressions, also known as character classes, are a feature of regular expressions that allow you to match any one character from a set of characters.

Here's how they work:

* `[abc]` - This pattern matches any single character that is either 'a', 'b', or 'c'. It's equivalent to a|b|c.

* `[a-z]` - This pattern matches any single lowercase letter. The hyphen - is used to specify a range of characters.

* `[A-Z]` - This pattern matches any single uppercase letter.

* `[0-9]` - This pattern matches any single digit.

* `[a-zA-Z]` - This pattern matches any single letter, regardless of case.

* `[^abc]` - This pattern matches any single character that is not 'a', 'b', or 'c'. The caret ^ at the start of the character class negates the set.

Bracket expressions only match a single character. To match multiple characters from a set, you would combine a bracket expression with a quantifier. For example, [a-z]+ matches one or more lowercase letters.

Note: Inside a bracket expression, most special characters lose their special meaning and represent themselves. For example, [abc$] matches 'a', 'b', 'c', or '$'. The exceptions are the backslash \, the caret ^ (only at the start), the hyphen - (except at the start or end), and the closing bracket ] (except at the start).

### Greedy and Lazy Match

In regular expressions, "greedy" and "lazy" are terms used to describe the matching behavior of quantifiers.

* Greedy Quantifiers

By default, quantifiers in regular expressions are greedy. This means they will match as much as possible. For example, given the string <em>hello</em><em>world</em> and the pattern <em>.*</em>, the match will be the entire string <em>hello</em><em>world</em>. This is because the .* pattern is greedy and consumes as much as it can, including the </em><em> in the middle.

* Lazy Quantifiers

Lazy quantifiers, also known as non-greedy or reluctant quantifiers, will match as little as possible. You can make a quantifier lazy by following it with a question mark ?. For example, given the same string <em>hello</em><em>world</em> and the pattern <em>.*?</em>, there will be two matches: <em>hello</em> and <em>world</em>. This is because the .*? pattern is lazy and stops consuming as soon as it can form a valid match.

Here's how you can make the common quantifiers lazy:

* `*?` - Zero or more, lazy. This will match as few characters as possible to form a valid match.

* `+?` - One or more, lazy. This will match as few characters as possible, but there must be at least one.

* `??` - Zero or one, lazy. This will prefer to match zero characters if that forms a valid match.

* `{n,m}?` - Between n and m, lazy. This will match as few characters as possible to form a valid match, but there must be at least n.

### Boundaries

Boundaries in regular expressions are positions between characters, rather than actual characters. Here are the most common boundary types:

* `^` - Matches the start of the string, or the start of a line if the multiline flag m is set.

* `$` - Matches the end of the string, or the end of a line if the multiline flag m is set.

* `\b` - Matches a word boundary. This is the position where a word character (\w) is followed or preceded by a non-word character (\W), or at the start or end of the string if the first or last character is a word character.

* `\B` - Matches a non-word boundary. This is the position where two word characters or two non-word characters are adjacent, or at the start or end of the string if the first or last character is a non-word character.

These boundary types are often used to ensure that a pattern matches a whole word and not a part of a word. For example, the pattern \bword\b matches 'word' in 'word is a word', but not 'word' in 'password'.

### Back-references

Boundaries in regular expressions are positions between characters, rather than actual characters. Here are the most common boundary types:

* `^` - Matches the start of the string, or the start of a line if the multiline flag m is set.

* `$` - Matches the end of the string, or the end of a line if the multiline flag m is set.

* `\b` - Matches a word boundary. This is the position where a word character (\w) is followed or preceded by a non-word character (\W), or at the start or end of the string if the first or last character is a word character.

* `\B` - Matches a non-word boundary. This is the position where two word characters or two non-word characters are adjacent, or at the start or end of the string if the first or last character is a non-word character.

These boundary types are often used to ensure that a pattern matches a whole word and not a part of a word. For example, the pattern \bword\b matches 'word' in 'word is a word', but not 'word' in 'password'.

Back-references in regular expressions are a way to refer back to capture groups that have already been matched. They allow you to reuse part of the regex match within the same regex.

Here's how they work:

* \1, \2, \3, etc. - These patterns refer back to the first, second, third, etc. capture group in the regex. For example, in the regex (a)b\1, the \1 refers back to the first capture group (a). This regex would match 'aba', but not 'abb', because the \1 has to match the same text that was matched by (a).
Back-references are useful for finding repeated patterns in a string. For example, the regex (\w+)\s+\1 matches repeated words, like 'the the' or 'to to'. The (\w+) captures a word, the \s+ matches one or more spaces, and the \1 matches the same word again.

* Note: Back-references in JavaScript are written with a $ instead of a \ in the replacement string of the replace method. For example, 'abc'.replace(/(a)(b)(c)/, '$2$3$1') would return 'bca'.

### Look-ahead and Look-behind

Look-ahead and look-behind are types of assertions in regular expressions that allow you to match a pattern only if it's followed or preceded by another pattern, without including that other pattern in the match.

* Look-ahead

Look-ahead is written as (?=...) for positive look-ahead and (?!...) for negative look-ahead.

Positive look-ahead (?=...) matches if the pattern inside the parentheses is ahead. For example, \d(?=px) matches a digit only if it's followed by 'px', but 'px' is not part of the match.

Negative look-ahead (?!...) matches if the pattern inside the parentheses is not ahead. For example, \d(?!px) matches a digit only if it's not followed by 'px'.

* Look-behind

Look-behind is written as (?<=...) for positive look-behind and (?<!...) for negative look-behind. Note that not all regex engines support look-behind.

Positive look-behind (?<=...) matches if the pattern inside the parentheses is behind. For example, (?<=px)\d matches a digit only if it's preceded by 'px', but 'px' is not part of the match.

Negative look-behind (?<!...) matches if the pattern inside the parentheses is not behind. For example, (?<!px)\d matches a digit only if it's not preceded by 'px'.

These assertions are called "look-ahead" and "look-behind" because they look ahead or look behind the current position in the string to check if the pattern matches, but they don't consume any characters or move the position. This is why the 'px' in the examples above is not part of the match.

## Author

 [ZeDevGit](https://github.com/ZeDevGit)