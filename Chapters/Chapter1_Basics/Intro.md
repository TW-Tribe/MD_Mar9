<button data-help-id="chapter:intro" class="help-btn">Help about this lesson</button>

```markdown
# MD_Mar9
This is my new file.

- [MD\_Mar9](#md_mar9)
- [Markdown](#markdown)
- [Lesson 1: Introduction](#lesson-1-introduction)
- [Lesson 2: Creating a Sample Document](#lesson-2-creating-a-sample-document)


# Markdown
Learning Markdown together with other participants.


# Lesson 1: Introduction
The document contains rules about how to use short codes to author a Markdown file and create repository in GitHub. 

The magical short codes:   
#, *, _, `, -   
Tabs   
Spaces   

Click on the following to learn:
1. [Headings](UG/Getting_started/heading.md)
2. [Inline](Working_with_markdown/../UG/Working_with_markdown/inline.md)
3. [Lists](lists.md)
4. [Tables](table.md)
5. [Codes](codes.md)
6. [Images or Videos](image.md)
7. [Hyperlinks](hyperlinks.md)
8. Adding for test
9. Again testing
- [MD\_Mar9](#md_mar9)
- [Markdown](#markdown)
- [Lesson 1: Introduction](#lesson-1-introduction)
- [Lesson 2: Creating a Sample Document](#lesson-2-creating-a-sample-document)

# Lesson 2: Creating a Sample Document

WhatsApp
What is WhatsApp?
WhatsApp (officially WhatsApp Messenger) is a free communication app which allows you to send messages, make voice and video calls, and share images and documents, user locations, and other content. Two former Yahoo! developers launched WhatsApp in January 2009.  Later in January 2018, WhatsApp released a standalone business app called WhatsApp Business which can communicate with the standard WhatsApp client. With more than two and a half billion users worldwide, WhatsApp is one of the most successful apps ever made. 



<img src="../../Images/Guj_Jun_14.png" width="300" height="200" />

<img src="../../Images/Guj_Jun_14.png" width="400" height="250" />


> Note: This is a warning.




![](/Images/Guj_Jun_14.png)


<table class="table table-striped">
<caption>Caption for this Table</caption>
<button data-help-id="chapter:intro" class="help-btn">Help about this lesson</button>

# Introduction to Markdown

Main message
--------------

Markdown is a lightweight syntax for writing formatted text in plain files. This lesson shows the core elements you need to create readable, maintainable documentation.

Situation
---------

Many writers create documentation directly in Markdown for websites and static sites (for example, Jekyll). This file explains the essentials and gives examples you can copy.

Tasks (what to do)
-------------------

1. Create a new `.md` file and add a short title.
2. Use headings for structure: one `#` for the page title, `##` for sections.
3. Use lists for steps and bullets, and code fences for examples.
4. Add images using relative paths (see example).

Practical examples
------------------

Headings

```markdown
# Lesson title
## Section title
```

Lists

```markdown
- Bullet item
1. Numbered step
```

Code block

```markdown
```html
<img src="../../Images/Guj_Jun_14.png" alt="sample image"/>
```
```

Image (rendered)

<img src="../../Images/Guj_Jun_14.png" width="300" alt="sample image" />

Table (use simple Markdown table where possible)

```markdown
| Property | Description |
|---|---|
| Topic1 | Short description |
```

Best practices (concise, clear)
-------------------------------

- Use active voice and second person where appropriate (for instructions).
- Keep paragraphs short (1–3 sentences).
- Use consistent sentence-style capitalization for headings.

Next steps
----------

- Add topic pages under `Chapters/` and link them from `index.md`.
- Use `data-help-id` attributes to connect UI help to these topics.
