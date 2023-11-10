# Matching an HTML Tag || Regex

Welcome, in this tutorial I will be breaking down the regular expression for matching an HTML Tag


/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/

I know this appears like a cryptic sequence to you, but fear not – we will demystify its components. However, if you're not interested in diving into the world of | Regular Expressions | (or regex), I'd advise clicking the X in the top right of the browser, as this exploration might either bewilder your mind or enhance your coding powers.

## Summary
These expressions stand as a sequence of characters that defines a search pattern.

Behind the comlex look this has `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` regular expressions serve as textual patterns used for either matching or replacing elements within strings of text. I'll break it down in a minute.
It's imperative to note that regex exhibits remarkable flexibility, operating across a spectrum of programming languages. While the showcased regex capably matches HTML tags, it's not the sole approach. The beauty of regex lies in its adaptability and customization.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)


## Regex Components
okay so lets break down /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/

we have '/' that open and close the expression, followed by an anchor '^' and an opening angle bracket '<'.
'([a-z]+)' Matches and captures one or more lowercase alphabetic characters

+ matches the previous token between one and unlimited times, as many times as possible, giving back as needed

In the second group '([^<]+)*'  * matches the previous token between zero and unlimited times, as many times as possible, giving back as needed

[^<] inside matches and captures any character that is not an opening angle bracket!

As you can see, things are not so bad when you break it down, lets keep going!
The next part were going to talk about is the Non-capturing group, the non-capturing group is comprised of 
(?:>(.*)<\/\1>|\s+\/>)  these are denoted by '(?:...)'

The regular expression pattern (?:>(.*)<\/\1>|\s+\/>) constitutes a non-capturing group. It contains two alternatives separated by | (OR operator)

So check it out, (?: >(.*)<\/\1> | \s+\/>)
does some tag matching. It's got two moves: one for the stuff between open and close HTML tags, and another for self-closing tags. The first part, >(.*)<\/\1>, goes between the > and </ for whatever's in there. The \1 thing at the end points back to the captured text between those tags. The other part, \s+\/>, is for those tags that close by themselves.

### Anchors
These expressions are opened and closed with /^ and $/
the ^ and $ represent Anchors. Anchors are crucial in defining the position of the pattern within the text. They ensure that the regex only matches patterns at the start or end of a string.

### Quantifiers

Within `([a-z]+)`, the '+' quantifier matches the previous token between one and unlimited times. Quantifiers specify the number of occurrences of the preceding element within the pattern.  + allows one or more occurrences of lowercase alphabetic characters, ensuring the matching of HTML tag names.
### OR Operator

The non-capturing group (?:...|...) contains two alternatives separated by | (OR operator). >(.*)<\/\1> captures content between open and close HTML tags. On the other hand, \s+\/> identifies self-closing tags

### Character Classes

[^<]+ inside the second capturing group matches any character that is not an opening angle bracket.

## Author
Zechiel Lozer(https://github.com/ZD0341)
