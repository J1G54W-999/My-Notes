- ### Glossary:
- `.` wildcard → Matches any single character (except a newline)
- `[]` → Character Classes (Mini list of possible characters)
- `|` → Alterations (match an 'alternative pattern' within the same expression)
- `+` and `*` → Repetitions (match characters or groups that appear multiple times)
- `\` → Escape sequence (`\` followed by a character will escape the characters special attribute)
- `(?i)`→Add to start of regex to make it case insensitive 
- `Greedy quantifiers` → Will match as many characters as possible that match the expression
- `Non-greedy quantifiers` → Matches the smallest possible number of characters that match the expression
- `Capture Groups` → Allow parts of regex to be extracted or referenced separately with `()` 
- `Named Capture Groups` → You can assign names to the capture groups for readability
- `Negation` → Specify characters you DON'T want to match
- `Back References` → Used to refer back to previously captured group within the same regex pattern
- `Word Boundaries` → Marks the transition between a word character and a non-word character, or the start/end of a string
------
- ### The `.` Wildcard Examples: 
- Regex `a.c` matches `"abc"`, `"a1c",` `"a-c"` etc. Any character can appear between `"a"` and `"c"` 
- Regex `...` matches any three-character sequence, like `"cat"`, `"dog"`, `"123"`, or `"!!!"` 
- Regex `'b.t'` will match `"bat"`, `"bit"`, `"bot"`, `"but"`, etc. 
------ 
- ### `[]` Character Class:
- `[aeiou]` matches any single lowercase vowel
- `[0-9]` matches any single digit from 0 to 9 
- `[a-z]` matches any single lowercase character 
- `[A-Z]` matches any single uppercase character 
- `[a-zA-Z]` matches any single uppercase or lowercase character 
- `"cat"`, `"cot"`, `"cut"` with the regex `c[aeiou]t` will match `"cat"`, `"cot"`, and `"cut"` 
-------
- ### Custom Character Sets:
- You can create your own character classes and add only what you want `[-\s]` or `[-_.*]` etc
- 
- Example: Matching Letters Sha256 Hashes `[a-fA-F0-9]{64}` 
- `fa690b82061edfd2852629aeba8a8977b57e40fcb77d1a7a28b26cba62591204` 
- Matches all of the letters in a SHA256 hash
-------
- ### Negation in Custom Character Classes:
- Negation allows you to specify characters you DON'T want to match by placing a `^` at the beginning of a character class `[]` (inside the square brackets)

#### Syntax: `[^abc]` match any character that is NOT a, b, or c

- Example: Excluding path from a URL `https?:\/\/[^\/]+` 
- `https://www.youtube.com/watch?v=FAB9KpZtnZs` = Matches http until the TLD and negates the path
- 
- Example: Excluding Specific Symbols `[^.,!?]` 
- `What's his power level?. It's over 9000!` = Matches any character that is not `.` `,` `!` or `?` 
-------
- ### Lookahead: 
- Checks if a certain pattern follows the current position in the string. (Doesn't consume characters, only checks for the presence of a pattern)  
#### Syntax: `(?=pattern)` 
- #### Examples: 
- Detecting Usernames Before Domain:
- `\w+(?=@domain\.com)` 
- 
- Looking for credit card numbers:
- `\d{4}(?=\d{4})` 
- 
- Validating Secure Password:
- `.{8,}(?=.*[A-Z])(?=.*\d)` 
- Matches if there are 8 characters, an uppercase letter and a digit
-------
- ### Lookbehind: 
- Checks if a certain pattern precedes the current position in the string. (Doesn't consume characters, only checks for the presence of a pattern)
#### Syntax: `(?<=pattern)` 

- #### Examples: 
- Finding Suspicious Downloads:
- `(?<=downloaded\s)file_\w+\.zip` 
- 
- Matching File Extensions:
- `(?<=\.)[a-z]{3,4}` 
- 
- Detecting Numbers Preceded by Specific Words:
- `(?<=Amount: )\d+` 
-------
- ### Negative Lookahead:
#### Syntax: `(?!...)`  
- #### Examples:
- `malware(?! threat)` = Matches `malware` if NOT followed by the word `threat`
- Will Match: "There is malware confirmed on the system"
- Won't Match: "There is a malware threat on the system"
-------
- ### Negative Lookbehind:
#### Syntax: `(?<!...)` 
- Example: `(?<!DDoS )attack` = Matches 'attack' if NOT preceded by the word 'DDoS'
- Will Match: "There is a MITM attack on the system"
- Won't Match: "There is a DDoS attack on the system"
-------
- ### `|` Alteration Examples:
- `cat|dog` matches either `“cat”` or `“dog”` 
- `(http|https)://` matches `“http://”` or `“https://”` 
- The pattern `error|warning|alert` will match any of these words individually
-------
- ### `*` and `+` Repetitions:
- `*`: Matches zero or more occurrences of the preceding character or group.
- `+`: Matches one or more occurrences of the preceding character or group.
- 
- `a*` matches `"", "a", "aa", "aaa"` etc.
- `x+` matches `"x", "xx", "xxx",` etc. 
- `[0-9]+` matches `"123"` or `"45678"` any sequence of digits from 0-9 
-------
- ### `\` Escape Sequences:
- `\.`matches a literal dot `.` instead of acting as a wildcard.
- `\*` matches a literal asterisk `*` instead of the repetition operator.
- `\\` matches a literal backslash `\` 
- 
- The regex pattern `192.168.1.2` will create false positives because `.` characters have not been escaped 
- Correct pattern = `192\.168\.1\.2` 
- 
- The regex pattern `http://www.google.com` will create a syntax error because the `/` character denotes the beginning and end of a regular expression. 
- Correct pattern `http:\/\/www\.google\.com` 
-------
- ### Meta-characters:
- Meta-characters are like aliases of literals making it easier to write patterns without having to specify every individual character

#### Examples: 
- `\d+` will match any digit character of one or more digits 
- `\d`→Matches any digit The same as [0-9]
- `\D`→Matches any non-digit 
- `\w`→Matches any alphanumeric word character and underscores. The same as [a-zA-Z0-9_]
- `\W`→Matches any non-word character like symbols or spaces 
- `\s`→Matches any whitespace like spaces, tabs and new lines
- `\S`→Matches any non-whitespace 
- `\b`→Matches a word boundary. `/bsaw/b` matches `saw` but not jigsaw (matches a position instead of a character) 
-------
- ### Word Boundaries: 
- Marks a position between a word character and non-word character
- Helps match whole words without matching parts of longer  
- #### Examples: 
- The word `saw` 
- `\bsaw\b` 
- Matches the standalone word `saw` and not `jigsaw` or `sawyer` 
- 
- Detecting Suspicious Commands:
- `\brm\b` 
- Matches `rm -rf` and not `farm` or `form` 
- 
- Identifying Specific File Types:
- `\.exe\b` 
- 
- Extracting a standalone IP Address from text:
- `\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b` 
-------
- ### Meta-characters and Literals together:
- Matching an email address: (Simple version)
- `\w+@\w+\.\w+` 
- 
- Matching Dates: YYYY-MM-DD format (2024-11-02)
- `\d{4}-\d{2}-\d{2}` 
- 
- Matching URL Protocols:
- `https?:\/\/` 
- 
- Matching Basic Passwords:
- `\w{8,}` 
-------
- ### Anchors:
- `^`→Asserts that the match must start at the beginning of the line or string 
- Example: `^Love`will match "Love" only if it appears at the beginning of a line 
- 
- `$`→Asserts that the match must occur at the end of the line or string 
- Example: `Anime$` will match "Anime" only if it’s at the end of a line 
-------
- ### Quantifiers:
- `*` → Matches zero or more of the preceding element
- `+` → Matches one or more of the preceding element
- `?` → Matches zero or one of the preceding element
- `{}` braces → Specifies the number of times the preceding element should match
 
#### Examples:
- `ab*c` → Matches "ac", "abc", "abbc", etc.
- `ab+c` → Matches "abc", "abbc", but not "ac"
- `colou?r` → Matches "color" and "colour"
- 
- Matching Optional Country Codes:
- `(\+1\s?)?\d{3}-\d{3}-\d{4}` 

#### Examples: `{}` 
- `{x}` → Matches exactly x occurrences.
- `{x,}` → Matches at least x occurrences (no upper limit).
- `{,y}` → Matches at most y occurrences (no lower limit).
- `{x,y}` → Matches between x and y occurrences (inclusive)
- `a{2,4}` → Matches "aa", "aaa", or "aaaa"
-------
- ### Greedy Quantifiers:  
#### Append `*`, `+`, `{x,y}` without any additional symbols

- Example: Greedy `<.*>` 
- `<div><span>Hello</span></div>`  = will match everything from the first `<` to the last `>` 
- ### Non-Greedy Quantifiers:  
#### Append `?` after the quantifier `*?`, `+?`, `{x,y}?` to make it non-greedy.

- Example: Non-greedy `<.?>` 
- `<div><span>Hello</span></div>`  = will match every `<` and `>` but stop each time. So rather than one big match we get 4 matches here `<div>` `<span>` etc.
-------
- ### Capture Groups:
- Each group is numbered based on the order of the opening parenthesis

#### Examples: 
- Basic Capture Group `(\w+)\s(\w+)` 
- `Naruto Uzumaki` = will capture 2 separate groups (group 1) `Naruto` and (group 2) `Uzumaki` 
- 
- Using Capture Groups for Rearranging (Replacement)
- `this makes sense` = `\1` `\2` `\3` chronological order by default
- `sense this makes` = `/3` `/1` `/2` rearranged (specify in python)
- 
- Capture Groups in Repeated Patterns `(\d{2})-(\d{2})-(\d{4})` 
- 21-06-25 = Each part of the date is captured separately
- `(Group 1 = Day)` - `(Group 2 = Month)` - `(Group 3 = Year)`
- ------
- ### Named Capture Groups:
#### Syntax: 
- `(?P<name>pattern)` = Python for named capture groups (?P for Python)
- `(?<name>pattern)` = .NET languages (C# and JavaScript) for named capture groups

#### Examples: 
- Named Groups in Matching a Full Name: 
- `(?P<first>\w+)\s(?P<last>\w+)` 
- Naruto Uzumaki 
- `Group 1 "first" = Naruto` `Group 2 "last" = Uzumaki` 
- 
- Named groups in Date Matching: 
- `(?<day>\d{2})-(?<month>\d{2})-(?<year>\d{4})`
- 21-06-2025  
- `Group 1 "day" = 21` `Group 2 "month" = 06` `Group 3 "year" = 2025` 
- 
- URL Parsing with Named Groups: 
- `(?<protocol>https?)://(?<domain>[\w.-])(?<path>.*)?`     
- https://domain.com/path/to/page 
- `Group 1 "protocol" = http(s)` `Group 2 "domain" = example` `Group 3 "path" = rest of path` 
-------
- ### Back References:
- Used to refer back to previously captured group within the same regex pattern (refers back to the value captured and not the pattern used to capture it)

- ### Numbered Back References: 
#### Syntax: `\number` 
- Example: `(\d{2})-(\d{2})-\1` 
- matches a pattern like `12-06-12` = `\1` captures the result of capture group 1 and references the result
- ### Named Back References:
- Refers to the text matched by a capturing group and matches the same text
#### Syntax: `\k<name>` 
#### Examples: 
- `(?<phrase>\w+)\s+\k<phrase>` 
- Matches `pika pika` and `gum gum` 
- because the first word is captured as 'phrase' and then repeated as a reference 
- Both words have to be the same to match
-------
- ### Non Capturing Groups:
- Allow you to group parts of a regex pattern without storing the matched portion in memory for back referencing
- 
#### Syntax: `(?:pattern)` 

- Simple Non-capturing Group:
- `(?:abc|def)\d+` 
- 
- Capturing URL without the protocol:
- Syntax: `(?:https?):\/\/[^\s/$.?#].[^\s]*` 
- 
- Capture a URL without `www.` if present:
- `(?:https?):\/\/(?:www\.)?(\w+\.\w{2,})[\/\w?&=\d]*` 
-------
- ### Regex Example Searches: 
- Matching an IPv4 address 
- `[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+`
- 
- Starts with `http` and ends with `robots.txt`
- `http://.*robots\.txt`
- 
- Identify URLs beginning with `http` or `https`:  
- `(http|https)://` 
- 
- Find all instances of the chrome browser and its `version number`:
- `(?i)chrome.*[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+` 
- 
- Find email addresses and specify TLD match of at least 2 characters (case insensitive):
- `(?i)[a-z0-9.-_]+\@[a-z0-9.-_]+\.[a-z]{2,}` 
