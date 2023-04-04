# Markdown Cheatsheet
https://www.markdown-cheatsheet.com/

## Headings
<table>
<tr>
<td>

# Heading level 1
## Heading level 2
### Heading level 3
#### Heading level 4
##### Heading level 5 
###### Heading level 6
</td>
<td>

```markdown
# Heading level 1
## Heading level 2
### Heading level 3
#### Heading level 4
##### Heading level 5 
###### Heading level 6
```
</td>
</tr>
</table>

## Basic / Emphasis
<table>
<tr>
<td>

**bold text**  
__bold text__  
*italic text*  
_italic text_  
***bold + italic text***  
___bold + italic text___  
_**bold + italic text**_  
~~strikethrough text~~
</td>
<td>

```markdown
**bold text**  
__bold text__  
*italic text*  
_italic text_  
***bold + italic text***  
___bold + italic text___  
_**bold + italic text**_  
~~strikethrough text~~
```
</td>
</tr>
<tr>
<td>

> Blockquote
>
> > Nested Blockquote
</td>
<td>

```markdown
> Blockquote
>
> > Nested Blockquote
```
</td>
</tr>
</table>

## Lists

Numbered list
<table>
<tr>
<td>

1. First item
2. Second item
   1. Indented item
   2. Indented item
3. Third item
</td>
<td>

```markdown

1. First item
2. Second item
   1. Indented item
   2. Indented item
3. Third item
```
</td>
</tr>
<table>

Unordered list
<table>
<tr>
<td>

- First item
- Second item
  - Indented item
  - Indented item
- Third item
</td>
<td>

```markdown
- First item
- Second item
  - Indented item
  - Indented item
- Third item
```
</td>
</tr>
<table>

Alt Unordered list
<table>
<tr>
<td>

* Also a list
+ And this too  
  Paragraph under list item
  ```
  Code block too
  ```
</td>
<td>

````markdown
* Also a list
+ And this too  
  Paragraph under list item
  ```
  Code block too
  ```
````
</td>
</tr>
<table>

Checkbox list
<table>
<tr>
<td>

- [ ] Checkbox 1
- [x] Checkbox 2
- [ ] Checkbox 3
</td>
<td>

```markdown
- [ ] Checkbox 1
- [x] Checkbox 2
- [ ] Checkbox 3
```
</td>
</tr>
<table>

## Line breaks & paragraphs
<table>
<tr>
<td>

This first line ends with two trailing spaces.  
This is the second line.

This is the first line.

This second line has a single blank line before it.
</td>
<td>

```markdown
This first line ends with two trailing spaces.  
This is the second line.

This is the first line.

This second line has a single blank line before it.
```
</td>
</tr>
</table>

## Links & images
<table>
<tr>
<td>

[Link](https://www.google.com)

[Link with title](https://www.google.com "Title goes here.")

Direct link: <https://google.com>

[Reference style link][Arbitrary case-insensitive reference text]

[Relative reference to a repository file](../Markdown/Markdown.md)

[Numbered reference style link][1]

[reference text link].
</td>
<td>

```markdown
[Link](https://www.google.com)

[Link with title](https://www.google.com "Title goes here.")

Direct link: <https://google.com>

[Reference style link][Arbitrary case-insensitive reference text]

[Relative reference to a repository file](../Markdown/MarkdownRaw.md)

[Numbered reference style link][1]

[reference text link].
```
</td>
</tr>
</table>


[arbitrary case-insensitive reference text]: https://google.com
[1]: https://google.com
[reference text link]: https://google.com
<table>
<tr>
<td>

![Markdown image](markdown.png)  
[![Markdown clickable image](markdown.png "Click me!")](https://google.com)
</td>
<td>

```markdown
![Markdown image](markdown.png)  
[![Markdown clickable image](markdown.png "Click me!")](https://google.com)
```
</td>
</tr>
</table>

## Code
<table>
<tr>
<td>

Inline `code`
```java
// Multiline code
const message = "Hi!";
```
 
Inline code ``with `backticks` escaped``
</td>
<td>

````markdown
Inline `code`
```java
// Multiline code
const message = "Hi!";
```
 
Inline code ``with `backticks` escaped``
````
</td>
</tr>
</table>

## Horizontal rules
`___`
___
`***`
***
`---`
---

## Tables
<https://tableconvert.com/csv-to-markdown>

<table>
<tr>
<td>

| Table | Headers |
|---    |---      |
| three | or      |
| more  | hyphens |
</td>
<td>

```markdown
| Table | Headers |
|---    |---      |
| three | or      |
| more  | hyphens |
```
</td>
</tr>
</table>

<table>
<tr>
<td>

| Colons | are | used  |
|:-------|:---:|------:|
| to     |align|columns|
</td>
<td>

```markdown
| Colons | are | used  |
|:-------|:---:|------:|
| to     |align|columns|
```
</td>
</tr>
</table>

## Escaping characters
<table>
<tr>
<td>

Without *escaping*  
With \*escaping\*
</td>
<td>

```markdown
Without *escaping*  
With \*escaping\*
```
</td>
</tr>
</table>

## Inline HTML
<table>
<tr>
<td>

<html>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>

  <div align="center">
    Centered
  </div>
</html>
</td>
<td>

```markdown
<html>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>
  
  <div align="center">
    Centered
  </div>
</html>
```
</td>
</tr>
</table>