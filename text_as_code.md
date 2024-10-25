---
marp: true
theme: uncover
class: invert
paginate: true
size: 16:9

---

<style>
section {
  font-size: 30px;
}
ul, ol {
  margin-left: 0;
  margin-right: 0;
}
</style>

# Text As Code
Alex Schumacher

<!-- Or why old computer nerds are angry at emoji. 

Not talking about learning a computer language, 
but how the words that you write end up in front of people 
on the internet, how to present them exactly how you want to, 
and how to do that with a team of people in a workplace. 
-->
---

# Outline
1. Character Encoding
2. Markup Languages
3. Publishing
4. Working With `git`

---
<!---  
Why does this matter? Many in the tech field assume you are familiar with 
markup languages, git, and how (at a rough level), web publishing works. 

Getting familiar with these concepts can give you a leg up when looking for 
technical writing jobs. 
--->

# Why does this matter? 

- Foundational knowledge for many tech-related jobs.

- Useful in many areas, not just writing code. 

- Lets you edit Wikipedia to say whatever you want. 

---
<!---  
Computers store data in binary. Each character must be represented by some binary string.

Character encoding lets the computer translate this to something we can read --->

## Character Encoding

- How each letter, symbol, or other piece of text is stored on a computer. 
  
- Translates binary into human. 

---

## Definitions

- *Character*:  Individual symbols or letters - `A` `!` `+` `Ö`

---

## Definitions

- *Character*:  Individual symbols or letters - `A` `!` `+` `Ö`

- *Binary*:   Code that represents all characters as sets of `0` or `1` 
            (ex. `A` is `01000001`)

---

## Definitions

- *Character*:  Individual symbols or letters - `A` `!` `+` `Ö`

- *Binary*:   Code that represents all characters as sets of `0` or `1` 
            (ex. `A` is `01000001`)

- *Encoding*: Translating characters into binary according to a set of rules. 

---

## How it works:
<!--- How did we get here? 

Computer scientists long ago had to assign characters to binary numbers. What they chose affected
computer development for generations. 

If you're writing a program, you have to know what kind of characters are going to be used. 

The process goes back and forth - when you type a letter, the character set determines what binary number 
to save it as. When the computer reads that binary number in the future, it can then determine what
character to show you. 
--->


- Someone had to decide what set of binary numbers represent what character, creating a `character set`. 

- Every computer program references this `character set` to determine what characters to show when you read a file. 


---

## Examples
<!---
ASCII only has 128 possible characters, very simple. Imagine trying to type in another language using ASCII!
UTF-8 has 1,112,064. 
Unicode is a non-profit in California that keeps up with our changing language. 
Over 90% of the internet uses Unicode encoding. 

Ascii star wars: run `nc towel.blinkenlights.nl 23` in terminal
--->

  - ASCII (American Standard Code for Information Interchange)  
  
  - UTF-8 (Unicode Transformation Format – 8)
  
---
<!-- ASCII table - the html name, the BIN relating to binary 

The good news is, you're never going to have to look at this again, just understand the concept that a computer is doing this in the background. 
-->
## Examples

![w:1000 h:600](ascii_table.png)

---
<!-- 
Real-world examples: emoji, strictly-defined publishing
Apple/Android/Samsung all show the same emoji code differently. 

This is the same with fonts. The character is separate from the font used to display it. If one program reads the file and says to use Times New Roman, another program may use Helvetica. Same text, different font. 

Understanding what encoding type you’re using can affect what characters you can and can’t display, how something is communicated, or why something looks differently to one person or another.

Story from work - copying something that uses a different character encoding makes it show up differently where you paste it, since all it's "copying" is the binary numbers, and its up to the program to interpret what character to show. 
-->
## Examples

![](emoji_diff.jpeg)

---
<!--- 
Now that we know how each letter is stored. What about sentences, paragraphs, more complex things.
You will use this much more often than you'll use character encoding, but you can give specific 
character encoding directives via markup languages. 

I'm not teaching you a specific language tonight, just concepts that you will run into when 
creating online documentation. 

Markdown is the behind-the-scenes way that documents are formatted for print, publication, or web. 
--->

## Markup Languages

- Combines the character encoding and all the other formatting of a document (font, spacing, margins, etc). 
  
- Interpreted by a program to display or print. 
  
---
<!--- 
Markup languages allow programs to display rich text.
--->

## Definitions

- *Plain Text*: Text without any formatting directives - the raw characters saved in a file. 
  
- *Rich Text*: The text you see after the markup language has been rendered (ex. MS Word document)

---
<!--- 
Each character here, including the spaces, commas, etc are all simply stored as characters. Not very exciting. 
--->
## Example

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
sed do eiusmod tempor incididunt ut labore et dolore magna aliqua
```

---

<style scoped>section{font-size:40px;font-family: 'Roboto';text-align: right}</style>
**Lorem** 
<span>
~~ipsum dolor sit amet~~, *consectetur adipiscing elit*, 
<span style="color:green;">sed do eiusmod tempor</span> <span style="font-size:20px">incididunt ut labore </span><span style="font-size:40px">et dolore magna aliqua</span>
</span>

---
<!--- 
Here we see how to add formatting. 

In MS Word you just select the text and click a button to change formatting. 

In Markup languages, you give "directives" (sometimes called tags) telling text how it should  be displayed. 
--->
## Example

Markup directives add formatting: 
- `abcd` from `` `abcd` `` as surrounded backticks
- *italic* from `*italic*`
- **bold** from `**bold**`
- ~~strikethrough~~ from `~~strikethrough~~`
- > blockquote from `>`
- [source link](https://www.website.com) from `[source link](http://www.website.com)`
- and some fancy emojis :smile: from `:smile:` using words surrounded by colons

---
<!--- 
Languages you may have heard of
--->
## Markup Language Examples

- HTML
- XML
- Markdown
- Wikicode
- reStructured Text

---
<!--- 
VSCode is very common across the industry. 

Notepad is the most basic editor on Windows. 

LaTex is a very academic-focused editing system that combines markup and its own formatting for advanced typesetting.
--->
## Text Editors

- Plain text editors: 
  - VSCode
  - Notepad (Windows)
  - LaTeX
- Rich Text editors (aka, "what you see is what you get")
  - MS Word
  - Google Docs

---
<!--- 
Point out the UTF-8 headers in the XML, as well as in VS Code. 

Talk about work examples - every piece of documentation I've ever seen or worked on professionally has been stored as some sort of markup language
--->
## Example

Microsoft Word Documents uncompressed

---
<!--- 
If I gave this presentation 200 years ago, it’d be about the movable type printing press. 

Giving a high-level overview.
--->

## Publishing

- Software to render the markup language into the end-product - how text is made readable. 

- Web, print, PDF, and everything else goes through this process. 

---
<!--- 
Do live demo here of web publishing using my laptop as the server.

docker run -it --rm -d -p 8080:80 --name web nginx
--->

## Web Publishing

- Files are stored on a server. 
- Someone visits the webpage, initiating a connection to the server. 
- The server provides the text and markup directives as code. 
- The browser (Chrome, Firefox, etc) interprets the code according to the markup directives and renders it so you can read it. 

---
<!--- 
Brief overview of style sheets. 

A main style sheet that every individual web page references. 

The server figures it all out and provides the end resulting code to your browser. 
--->
## Real World
<!---
You don't need to know everything. 

Usually you just create the text you're working on, the style framework takes care of the rest. 

Sometimes you'll have a limited number of markdown directives you can work with for a specific publishing framework. 
--->

- Text stored in a markup language gives the browser a place to start. 
- Style sheets and frameworks provide all the rest. 
- Images, video, and other files are also told how to display with directives in the markup language. 

---
<!--- 
In the real world, what does this look like? 

The syntax for html and markdown are almost assumed knowledge in a lot of tech fields. 

--->
## Working with text as code

- Likely you won't need to master a markup language, but you should be familiar with the concepts when working in tech.

- A common collaboration tool is `git` which allows multiple people to work on the same project together. 

---
<!--- 
Working in plain text is important, as you don't want any directive hidden or interpreted. 

You render the text as you're working to see what it will look like, but you save it in git pre-rendered. 
--->
## Git

- `git` allows people to work on different parts of the same project at the same time, then combine them into the final product. 

- Work on plain text files in an editor, then save them to a central location so everyone on the team can see them. 

---
<!--- 
Why git? 

git log --graph --oneline --decorate --all

git blame

git history

--->
## Why use git?

- Organizes a large number of shared text files. 

- Everyone can see and use the same character encoding, styles, and framework.

- Allows for input and revision before publishing a final version. 

---
<!--- 
--->
## GitHub vs `git`


- `git` is a free software
- GitHub is a version of `git` that Microsoft owns and runs. Easy and mostly free to use. 

---
<!--- 
"fork and pull" model for clear collaboration. 

Changes to branches must be approved by other collaborators before being saved. 

Make sure the content meets the standards of the organization before publication. 
--->

## GitHub Process


- Create a `repository`
- Create a `branch`
- Add/edit files and `commit` them
- Submit the changes for a `pull request` 
- `Merge` the changes into the `main` branch


---
<!--- 
web publishing, software publishing, etc

This is why it can be powerful - as soon as you merge something, it can be live on the internet ready for people to read. 
--->

## GitHub Publishing

- `git` and GitHub are often used as the source for publishing. 

- Can be setup to automatically send changes to the `main` branch to a web publishing system. 

---

<!--- 
Demo and homework
--->
## Homework

1. Create a free GitHub account
2. Create a public repo with a `README.md` file. 
3. Create a new branch
4. Update the `README.md` file with anything you want. 
   1. At least three sections with headers
   2. At least two lists
   3. At least five text enhancements (bold, italic, strikethrough, underline, subscript, superscript, etc)
   4. Bonus points:
      1. Pictures
      2. Tables
      3. Links
      4. Table of Contents
5. Merge the branch into the `main` branch


---

# Thanks!

Full presentation available at:
https://github.com/mrhollywoodgates/text_as_code


---
# Homework Walkthrough

1. Create a repository ![](01_create_repo.png)
---
2. Repository Details:
   
   ![h:600](02_create_repo_details.png)
---
3. Commit and create branch
   
   ![h:600](03_commit_and_branch.png)
---
4. Create pull request

![](04_create_pr.png)

---
5. Pull request details

![h:600](05_create_pr_2.png)

---

![](git.png)
