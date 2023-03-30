# T-Rex-Tutorial
The term Regex stands for Regular expression. The regex or regexp or regular expression is a sequence of different characters which describe the particular search pattern. It is also referred/called as a Rational expression.
It is mainly used for searching and manipulating text strings. In simple words, you can easily search the pattern and replace them with the matching pattern with the help of regular expression.

This concept or tool is used in almost all the programming or scripting languages such as PHP, C, C++, Java, Perl, JavaScript, Python, Ruby, and many others. It is also used in word processors such as word which helps users for searching the text in a document, and also used in various IDEs.
The pattern defined by the regular expression is applied to the given string or a text from left to right.

## Summary
In summary, regular expressions (regex) are a powerful tool used for pattern matching and string manipulation. They consist of a combination of literal characters, metacharacters, quantifiers, and special characters that define a pattern to be matched against a string.

Some of the key components of regex include anchors, which specify the start and end of a line or word; character classes, which match sets of characters; quantifiers, which specify how many times a character or group should be repeated; and grouping and capturing, which allow you to capture and reuse parts of a matched pattern.

Other important features of regex include the or operator, bracket expressions, look ahead and look behind assertions, and backreferences. Regex can also be modified using flags, which affect how the pattern matching works (e.g. case sensitivity).

Learning regex can take some time and practice, but it can be a valuable tool for anyone working with text data or programming. Many programming languages support regex, and there are many online resources available for learning and practicing regex.

## Table of contents

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
Regex, or regular expressions, are composed of several components that define a search pattern. These components include:

Literal characters: These are the characters that make up the pattern you want to match, such as letters, digits, and special characters like @ or #.

Metacharacters: These are special characters that have a specific meaning in regex, such as the period (.), which matches any single character, or the asterisk (*), which matches zero or more occurrences of the previous character.

Quantifiers: These are symbols that indicate how many times a character or group of characters should be matched, such as the plus sign (+), which matches one or more occurrences of the previous character, or the question mark (?), which matches zero or one occurrence of the previous character.

Character classes: These are sets of characters that match any one character within the set. For example, the character class [abc] matches any one of the characters a, b, or c.

Anchors: These are symbols that specify the position of the match within the string, such as the caret (^), which matches the beginning of the string, or the dollar sign ($), which matches the end of the string.

Grouping constructs: These are symbols that group parts of the pattern together, such as parentheses (), which group characters together to form a subexpression.

Understanding these components and how they work together is essential for creating effective regex patterns. By combining these components in various ways, you can create powerful and flexible search patterns that can match a wide range of text inputs.

### Anchors
In regex, anchors are special characters that match a specific position within the text string, rather than a specific character. There are two main types of anchors:

The caret (^) anchor: This matches the beginning of a line or string. When used at the start of a pattern, it ensures that the pattern only matches at the beginning of the string. For example, the pattern "^hello" would match the string "hello world", but not the string "world hello".

The dollar sign ($) anchor: This matches the end of a line or string. When used at the end of a pattern, it ensures that the pattern only matches at the end of the string. For example, the pattern "world$" would match the string "hello world", but not the string "world hello".

In addition to these basic anchors, there are also some other specialized anchors that can be used to match specific positions in the text, such as:

The word boundary anchor (\b): This matches the boundary between a word character (as defined by regex) and a non-word character. For example, the pattern "\bcat\b" would match the string "cat", but not the string "catch".

The non-word boundary anchor (\B): This matches any position that is not a word boundary. For example, the pattern "o\B" would match the "o" in the string "hello", but not the "o" in the string "go".

Using anchors can be very useful for ensuring that a regex pattern matches only at specific positions within the text string. However, it's important to be careful when using anchors, as they can also limit the flexibility of your pattern and make it less useful in some cases.

### Quantifiers
In regex, quantifiers are special characters that specify how many times the preceding character or group of characters should be matched. They allow you to create more complex search patterns that can match multiple occurrences of a pattern, or patterns that occur in a specific sequence. Here are some common quantifiers:

The asterisk () quantifier: This matches zero or more occurrences of the preceding character or group. For example, the pattern "a" would match any number of "a" characters, including zero.

The plus sign (+) quantifier: This matches one or more occurrences of the preceding character or group. For example, the pattern "a+" would match one or more "a" characters.

The question mark (?) quantifier: This matches zero or one occurrence of the preceding character or group. For example, the pattern "colou?r" would match both "color" and "colour".

The curly braces ({}) quantifier: This allows you to specify the exact number of occurrences of the preceding character or group. For example, the pattern "a{3}" would match exactly three "a" characters.

The curly braces with range ({m,n}) quantifier: This allows you to specify a range of occurrences of the preceding character or group, from m to n. For example, the pattern "a{2,4}" would match between two and four "a" characters.

The lazy quantifier (?, ?, +?, {m,n}?) : These are similar to their greedy counterparts, but they match the minimum number of times possible, allowing for a shorter match. For example, the pattern ".?" would match the shortest possible sequence of characters, whereas ".*" would match the longest possible sequence of characters.

Using quantifiers can make your regex patterns more flexible and powerful, allowing you to match a wide range of text inputs. However, it's important to use them carefully, as overusing or misusing quantifiers can result in unexpected matches or poor performance.

### OR Operator
In regex, the "or" operator is represented by the vertical bar symbol (|). It allows you to specify multiple alternatives for a given pattern, so that the pattern will match any of the alternatives. Here's an example:

Suppose you want to match a string that contains either the word "hot" or the word "dog". You could use the following regex pattern:

hot|dog

This pattern would match any string that contains either "hot" or "dog", regardless of what comes before or after the word. For example, it would match "the cat in the hat" and "my dog has fleas".

You can also use the "or" operator to match alternative characters. For example, the pattern:

gr[ae]y

would match either "gray" or "grey", but not "grxy" or "grvy".

Note that the "or" operator has a lower precedence than most other regex operators, so you may need to use parentheses to group the alternatives properly. For example, the pattern:

penguin|doge loves me

would match either "penguin" or "doge loves me", but not "penguin loves me" or "doge". To match the full phrases "cat loves me" and "dog loves me", you would need to use parentheses:

(penguin|doge) loves me

### Character Classes
In regex, character classes allow you to match a specific set of characters. They are enclosed in square brackets and can be used to match any single character that is included in the set. Here are some examples of character classes:

The dot (.) character class: This matches any single character except for a newline. For example, the pattern "c.t" would match "cat", "cot", "cut", etc.

The bracketed character class: This matches any single character that is included in the bracketed set. For example, the pattern "[aeiou]" would match any single vowel character.

The negated bracketed character class: This matches any single character that is not included in the bracketed set. It is denoted by a caret (^) character at the beginning of the bracketed set. For example, the pattern "[^aeiou]" would match any single non-vowel character.

The range character class: This matches any single character that falls within a specified range of characters. It is denoted by a hyphen (-) between two characters. For example, the pattern "[a-z]" would match any lowercase letter from "a" to "z".

The predefined character classes: These match common sets of characters, such as digits (\d), whitespace (\s), and word characters (\w). For example, the pattern "\d{3}-\d{2}-\d{4}" would match a social security number in the format "123-45-6789".

Using character classes can make your regex patterns more flexible and powerful, allowing you to match specific sets of characters within a text input. However, it's important to use them carefully, as overusing or misusing character classes can result in unexpected matches or poor performance.

### Flags
Regex flags are special modifiers that can be added to the end of a regular expression to modify how the pattern is matched. They change the behavior of the regex engine and can affect how case sensitivity, multi-line matching, and other features are handled. Here are some common regex flags:

The case-insensitive flag (i): This makes the regex pattern match characters regardless of their case. For example, the pattern "/cat/i" would match "cat", "Cat", and "CAT".

The global flag (g): This causes the regex pattern to match all occurrences in the input string, rather than just the first occurrence. For example, the pattern "/dog/g" would match "dog" in the input string "my dog has fleas" multiple times.

The multi-line flag (m): This changes how the ^ and $ anchor characters are interpreted. When the multi-line flag is set, ^ and $ match the start and end of a line in the input string, rather than the start and end of the entire string. For example, the pattern "/^cat/m" would match "cat" at the beginning of a line in a multi-line input string.

The dot-all flag (s): This makes the dot (.) character class match any character, including newline characters. By default, the dot character does not match newline characters. For example, the pattern "/c.t/s" would match "cat", "cot", "cut", as well as "c\nt".

The Unicode flag (u): This enables full Unicode support for the regex engine, allowing it to correctly handle characters from any Unicode character set. This can be useful when working with non-ASCII text.

Using regex flags can make your patterns more powerful and flexible, allowing you to match more complex text inputs. However, it's important to use them carefully and appropriately, as they can also make your patterns more complex and harder to debug.

### Grouping and Capturing
In regex, grouping and capturing are used to extract specific parts of a matched pattern. Grouping is used to define a subexpression within a larger regex pattern, while capturing is used to extract the matched substring of a particular group.

To group a subexpression in a regex pattern, you can enclose it in parentheses. For example, the pattern "(\w+)-(\d+)" would match a string containing a word followed by a hyphen and a number. The two subexpressions, the word and the number, are grouped separately by the parentheses.

To capture the matched substring of a particular group, you can use a backreference. Backreferences are denoted by the backslash character () followed by the group number. For example, if you wanted to capture the word and number separately from the previous example, you could use the backreferences \1 and \2, respectively. The pattern "(\w+)-(\d+)" would match the string "foo-42" and capture "foo" and "42" separately.

Example:
import re
text = "headaches@hotmail.com"
pattern = r"(\w+@\w+\.\w+)"
matches = re.findall(pattern, text)
print(matches)

This pattern would match any email address in the text and capture the full email address as a group. The re.findall() function would return a list of all matched email addresses.

### Bracket Expressions
Regex bracket expressions, also called character classes, are a way to define a set of characters that a regex pattern can match. They allow you to match a single character from a group of characters, rather than just a specific character.

Bracket expressions are enclosed in square brackets [] and can include a range of characters or character classes. Here are some examples of bracket expressions:

[abc]: matches any single character that is either a, b, or c.
[a-z]: matches any single lowercase letter from a to z.
[A-Z]: matches any single uppercase letter from A to Z.
[0-9]: matches any single digit from 0 to 9.
[^abc]: matches any single character that is not a, b, or c.
You can also use pre-defined character classes within bracket expressions. Here are some common ones:

\d: matches any digit character (same as [0-9]).
\w: matches any word character (letters, digits, and underscores).
\s: matches any whitespace character (spaces, tabs, newlines).
You can combine multiple bracket expressions by using the pipe symbol | as an "or" operator. For example, the pattern [0-9a-fA-F] matches any hexadecimal digit (0-9, a-f, or A-F).

Bracket expressions are a powerful tool in regex, allowing you to define complex character sets with just a few characters. They can also make your patterns more readable and concise.

### Greedy and Lazy Match
In regex, greedy and lazy matching refer to how the regex engine tries to match a pattern within a string. Greedy matching is the default behavior, and it tries to match as much of the input string as possible while still satisfying the pattern. On the other hand, lazy matching tries to match as little of the input string as possible while still satisfying the pattern.

Greedy matching is denoted by the * or + quantifiers, which match zero or more and one or more occurrences of the preceding pattern, respectively. For example, the pattern a.*b would match the string "aabbbba" by greedily matching as much of the input string as possible between the 'a' and the 'b', resulting in the entire string being matched.

Lazy matching is denoted by adding a question mark ? after the quantifier. For example, the pattern a.*?b would match the same string "aabbbba" as before, but lazily, matching as little as possible between the 'a' and the 'b', resulting in just "aab" being matched.

Example:
import re

text = "<html><head><title>Title</title></head><body>Body</body></html>"

greedy_pattern = r"<.*>"
lazy_pattern = r"<.*?>"

greedy_match = re.search(greedy_pattern, text)
lazy_match = re.search(lazy_pattern, text)

print("Greedy match:", greedy_match.group())
print("Lazy match:", lazy_match.group())

In this example, both patterns match the entire HTML string, but the greedy pattern matches all the text between the first "<" and the last ">", while the lazy pattern only matches the first tag. This demonstrates how the lazy pattern matches as little as possible while still satisfying the pattern.

### Boundaries
In regex, boundaries are used to match patterns at specific positions in the input string. There are several boundary patterns that can be used in regex:

^: Matches the start of the string. For example, the pattern ^whats would match the string "whats good", but not "good whats".
$: Matches the end of the string. For example, the pattern good$ would match the string "whats good", but not "good whats".
\b: Matches a word boundary, which is the position between a word character (as defined by \w) and a non-word character. For example, the pattern \bcat\b would match the word "cat" in the string "The cat is black", but not in "The category is mammals".
\B: Matches a non-word boundary, which is the position between two word characters or two non-word characters. For example, the pattern \Bcat\B would match the word "cat" in the string "scathe" (between two non-word characters).

Example:
import re

text = "The cat is black and white, but not the category is mammals."

start_pattern = r"^The"
end_pattern = r"mammals\.$"
word_boundary_pattern = r"\bcat\b"
non_word_boundary_pattern = r"\Bcat\B"

print("Start pattern match:", re.search(start_pattern, text).group())
print("End pattern match:", re.search(end_pattern, text).group())
print("Word boundary pattern match:", re.findall(word_boundary_pattern, text))
print("Non-word boundary pattern match:", re.findall(non_word_boundary_pattern, text))

In this example, the start pattern matches the "The" at the beginning of the string, the end pattern matches the "mammals." at the end of the string, the word boundary pattern matches the word "cat" once in the string, and the non-word boundary pattern matches the word "cat" once in the string (in the middle of the word "scathe").

### Back-references
In regex, backreferences allow you to refer back to previously captured groups within the pattern. They are denoted by a backslash followed by the group number, where the group number is the order in which the groups appear in the pattern.

For example, the pattern (\w+)\s+\1 would match any word followed by one or more whitespace characters and then the same word again. Here, the \1 refers back to the first captured group (i.e., (\w+)), so the pattern would match strings like "like like" or "us us".

Example:
import re

text = "like like us us"

pattern = r"(\w+)\s+\1"

matches = re.findall(pattern, text)

print(matches)

In this example, the pattern matches the first two words ("like like") and the last two words ("us us"), because they are followed by one or more whitespace characters and then the same word again. The re.findall() function returns a list of all the matches found in the input string.

Note that backreferences can only be used to refer to groups that have already been matched in the pattern. If you try to refer to a group that hasn't been matched yet, or a group that is inside a nested group that hasn't been matched yet, you will get an error.

### Look-ahead and Look-behind
In regex, look ahead and look behind assertions allow you to match patterns based on what comes before or after a particular position in the input string, without including that part of the string in the match.

Positive look ahead assertions are denoted by (?=...), where ... is the pattern to match. For example, the pattern foo(?=bar) would match the string "foo" only if it is immediately followed by "bar". The "bar" part of the string is not included in the match.

Negative look ahead assertions are denoted by (?!...), where ... is the pattern to not match. For example, the pattern foo(?!bar) would match the string "foo" only if it is not immediately followed by "bar".

Positive look behind assertions are denoted by (?<=...), where ... is the pattern to match. For example, the pattern (?<=foo)bar would match the string "bar" only if it is immediately preceded by "foo". The "foo" part of the string is not included in the match.

Negative look behind assertions are denoted by (?<!...), where ... is the pattern to not match. For example, the pattern (?<!foo)bar would match the string "bar" only if it is not immediately preceded by "foo".

Example:
import re

text = "foobar foobaz fooqux barfoo"

positive_lookahead_pattern = r"foo(?=bar)"
negative_lookahead_pattern = r"foo(?!bar)"
positive_lookbehind_pattern = r"(?<=foo)bar"
negative_lookbehind_pattern = r"(?<!foo)bar"

print("Positive lookahead matches:", re.findall(positive_lookahead_pattern, text))
print("Negative lookahead matches:", re.findall(negative_lookahead_pattern, text))
print("Positive lookbehind matches:", re.findall(positive_lookbehind_pattern, text))
print("Negative lookbehind matches:", re.findall(negative_lookbehind_pattern, text))

In this example, the positive lookahead pattern matches the first "foo" in "foobar", but not the second "foo" in "foobaz", because it is not followed by "bar". The negative lookahead pattern matches the second "foo" in "foobaz", but not the first "foo" in "foobar", because it is followed by "bar". The positive lookbehind pattern matches the "bar" in "foobar" and "barfoo", but not the "bar" in "fooqux", because it is not preceded by "foo". The negative lookbehind pattern matches the "bar" in "fooqux", but not the "bar" in "foobar" or "barfoo", because they are preceded by "foo".

## Author
Hello, my name is Elmer Herrera and this is tutorial for Regex. I hope this can help anyone looking for imformation on the subject. https://github.com/elmerherrera