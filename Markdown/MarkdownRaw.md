# Markdown Cheatsheet
https://www.markdown-cheatsheet.com/

## Headings
# Heading level 1
## Heading level 2
### Heading level 3
#### Heading level 4
##### Heading level 5 
###### Heading level 6

## Basic / Emphasis
**bold text**  
__bold text__  
*italic text*  
_italic text_  
***bold + italic text***  
___bold + italic text___  
_**bold + italic text**_  
~~strikethrough text~~

> Blockquote
>
> > Nested Blockquote

## Lists
Numbered list
1. First item
2. Second item
   1. Indented item
   2. Indented item
3. Third item

Unordered list
- First item
- Second item
  - Indented item
  - Indented item
- Third item

Alt Unordered list
* Also a list
+ And this too  
  Paragraph under list item
  ```
  Code block too
  ```

Checkbox list
- [ ] Checkbox 1
- [x] Checkbox 2
- [ ] Checkbox 3

## Line breaks & paragraphs
This first line ends with two trailing spaces.  
This is the second line.

This is the first line.

This second line has a single blank line before it.


## Links & images
[Link](https://www.google.com)

[Link with title](https://www.google.com "Title goes here.")

Direct link: <https://google.com>

[Reference style link][Arbitrary case-insensitive reference text]

[Relative reference to a repository file](../Markdown/Markdown.md)

[Numbered reference style link][1]

[reference text link].

[arbitrary case-insensitive reference text]: https://google.com
[1]: https://google.com
[reference text link]: https://google.com

![Markdown image](markdown.png)  
[![Markdown clickable image](markdown.png "Click me!")](https://google.com)

## Code
Inline `code`
```java
// Multiline code
const message = "Hi!";
```
 
Inline code ``with `backticks` escaped``

## Horizontal rules

___
***
---

## Tables
<https://tableconvert.com/csv-to-markdown>

| Table | Headers |
|---    |---      |
| three | or      |
| more  | hyphens |

| Colons | are | used  |
|:-------|:---:|------:|
| to     |align|columns|

## Escaping characters
Without *escaping*  
With \*escaping\*


## Inline HTML
<html>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>

  <div align="center">
    Centered
  </div>
</html>
