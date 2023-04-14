## Google Cloud Log RE2 Regular Expressions Cheatsheet
[RE2 Syntax](https://github.com/google/re2/wiki/Syntax)

| kinds of single-character expressions | examples |
|---|---|
| any character, possibly including newline (s=true) | `.` |
| character class | `[xyz]` |
| negated character class | `[^xyz]` |
| Perl character class (link) | `\d` |
| negated Perl character class | `\D` |
| ASCII character class (link) | `[[:alpha:]]` |
| negated ASCII character class | `[[:^alpha:]]` |
| Unicode character class (one-letter name) | `\pN` |
| Unicode character class | `\p{Greek}` |
| negated Unicode character class (one-letter name) | `\PN` |
| negated Unicode character class | `\P{Greek}` |

| | Composites |
|---|---|
| `xy` | x followed by y |
| `x|y` | x or y (prefer x) |

| | Repetitions |
|---|---|
| `x*` | zero or more x, prefer more |
| `x+` | one or more x, prefer more |
| `x?` | zero or one x, prefer one |
| `x{n,m}` | n or n+1 or ... or m x, prefer more |
| `x{n,}` | n or more x, prefer more |
| `x{n}` | exactly n x |
| `x*?` | zero or more x, prefer fewer |
| `x+?` | one or more x, prefer fewer |
| `x??` | zero or one x, prefer zero |
| `x{n,m}?` | n or n+1 or ... or m x, prefer fewer |
| `x{n,}?` | n or more x, prefer fewer |
| `x{n}?` | exactly n x |

| | Grouping |
|---|---|
| `(re)` | numbered capturing group (submatch) |
| `(?P<name>re)` | named & numbered capturing group (submatch) |
| `(?:re)` | non-capturing group |
| `(?flags)` | set flags within current group; non-capturing |
| `(?flags:re)` | set flags during re; non-capturing |

| | Flags |
|---|---|
| `i` | case-insensitive (default false) |
| `m` | multi-line mode: ^ and $ match begin/end line in addition to begin/end text (default ` |false) |
| `s` | let . match \n (default false) |
| `U` | ungreedy: swap meaning of x* and x*?, x+ and x+?, etc (default false) |

| | Empty strings |
|---|---|
| `^` | at beginning of text or line (m=true) |
| `$` | at end of text (like \z not \Z) or line (m=true) |
| `\A` | at beginning of text |
| `\b` | at ASCII word boundary (\w on one side and \W, \A, or \z on the other) |
| `\B` | not at ASCII word boundary |
| `\z` | at end of text |

| | Escape sequences |
|---|---|
| `\t` | horizontal tab (≡ \011) |
| `\n` | newline (≡ \012) |
| `\r` | carriage return (≡ \015) |
| `\*` | literal *, for any punctuation character * |
| `\123` | octal character code (up to three digits) |
| `\x7F` | hex character code (exactly two digits) |
| `\x{10FFFF}` | hex character code |

| | Character class elements |
|---|---|
| `x` | single character |
| `A-Z` | character range (inclusive) |
| `\d` | Perl character class |
| `[:foo:]` | ASCII character class foo |
| `\p{Foo}` | Unicode character class Foo |
| `\pF` | Unicode character class F (one-letter name) |

| | Named character classes as character class elements |
|---|---|
| `[\d]` | digits (≡ \d) |
| `[^\d]` | not digits (≡ \D) |
| `[\D]` | not digits (≡ \D) |
| `[^\D]` | not not digits (≡ \d) |