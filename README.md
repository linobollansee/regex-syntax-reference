# Regular Expression (RegEx) Syntax Reference (Sorted by Frequency)

| Syntax / Keyword | Description | Freq | Example |
|------------------|-------------|------|----------|
| `.` | Matches any single character except newline | VC | `a.c` → matches `abc`, `axc` |
| `^` | Matches the start of a string | VC | `^Hello` → matches `"Hello world"` |
| `$` | Matches the end of a string | VC | `world$` → matches `"Hello world"` |
| `*` | Matches 0 or more repetitions of the preceding pattern | VC | `ab*` → matches `a`, `ab`, `abb` |
| `+` | Matches 1 or more repetitions of the preceding pattern | VC | `ab+` → matches `ab`, `abb`, but not `a` |
| `?` | Makes preceding token optional (0 or 1 occurrence) | VC | `colou?r` → matches `color` or `colour` |
| `[]` | Character class — matches any one character inside brackets | VC | `[aeiou]` → matches any vowel |
| `[^...]` | Negated character class — matches anything *not* inside brackets | VC | `[^0-9]` → matches non-digits |
| `|` | Alternation — acts as logical OR | VC | `cat|dog` → matches `cat` or `dog` |
| `()` | Capturing group — groups subpatterns and captures text | VC | `(ab)+` → matches `ab`, `abab` |
| `(?:...)` | Non-capturing group — groups without capturing | VC | `(?:foo|bar)` → matches `foo` or `bar` |
| `\` | Escape character — allows matching special symbols literally | VC | `\.` → matches a literal `.` |
| `\d` | Matches any digit (0–9) | C | `\d+` → matches `123`, `42` |
| `\D` | Matches any non-digit | C | `\D+` → matches `abc`, `--` |
| `\w` | Matches any word character (letters, digits, underscore) | C | `\w+` → matches `hello_123` |
| `\W` | Matches any non-word character | C | `\W+` → matches `!!!`, ` ` |
| `\s` | Matches any whitespace character | C | `\s+` → matches spaces, tabs, newlines |
| `\S` | Matches any non-whitespace character | C | `\S+` → matches words without spaces |
| `{n}` | Matches exactly *n* occurrences of the preceding token | C | `\d{4}` → matches `2025` |
| `{n,}` | Matches *n* or more occurrences | C | `\d{2,}` → matches `12`, `1234` |
| `{n,m}` | Matches between *n* and *m* occurrences | C | `a{2,4}` → matches `aa`, `aaa`, `aaaa` |
| `(?P<name>...)` | Named capturing group | C | `(?P<year>\d{4})` → captures `"year": "2025"` |
| `(?=...)` | Positive lookahead — ensures a pattern is followed by another | LC | `\d(?=px)` → matches `5` in `5px` |
| `(?!...)` | Negative lookahead — ensures a pattern is *not* followed by another | LC | `foo(?!bar)` → matches `foo` not followed by `bar` |
| `(?<=...)` | Positive lookbehind — ensures a pattern is preceded by another | LC | `(?<=USD)\d+` → matches `100` in `USD100` |
| `(?<!...)` | Negative lookbehind — ensures a pattern is *not* preceded by another | LC | `(?<!@)\w+` → matches `name` in `@user name` |
| `\b` | Word boundary | LC | `\bword\b` → matches `word` as a standalone |
| `\B` | Non-word boundary | LC | `\Bword` → matches `sword` but not `word` |
| `(?i)` | Enables case-insensitive matching | LC | `(?i)hello` → matches `HELLO` or `hello` |
| `(?m)` | Multiline mode (`^` and `$` match line start/end) | LC | `(?m)^#` → matches comment lines |
| `(?s)` | Dotall mode — makes `.` match newlines too | LC | `(?s)a.*b` → matches across lines |
| `(?x)` | Verbose mode — allows comments and whitespace in regex | R | `(?x) \d{4} - \d{2} - \d{2}  # date` |
| `(?P=name)` | Backreference to a named group | R | `(?P<quote>['"]).*?(?P=quote)` |
| `\1`, `\2`, etc. | Numeric backreference to captured groups | R | `(a|b)\1` → matches `aa`, `bb` |
| `(?# comment )` | Inline comment (ignored in verbose mode) | R | `(?# This part matches dates )` |
| `(?R)` | Recursion — re-invokes entire pattern (advanced) | R | `(?R)` used in nested structures like parentheses |
