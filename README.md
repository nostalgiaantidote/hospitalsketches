# hospitalsketches

# Hospital Sketches: A TEI Edition in Progress

This is an in-prograss TEI edition of Hospital Sketches by Louisa May Alcott, published by James Redpath, Boston, 1863.

This text is drawn from [a print edition digitized by Duke University Libraries and housed at the Internet Archive](https://archive.org/details/hospitalsketches01alco). I have OCR'd the text and cleaned it up manually for my own practice (although this text is already available on [Project Gutenberg](https://www.gutenberg.org/ebooks/3837)).  


## Purpose
The primary purpose of this project is for my own learning as I play around with TEI and its possibilities. This project is an opportunity to practice creating and publishing a digital edition, using XSLT and web publishing tools, and performing text analysis. It is also an opportunity for me to more fully enjoy the practices of close reading and annotating with a text I admire. The more I re-read and mark up, the more I appreciate LMA's influences, style, and wit.


This edition is a work in progress, but if this markup as-is is useful for you for text analysis or other purposes, you are welcome to use it. Please let me know if you do!


So far, my markup focuses on names of fictional and real people and places; historical events; speech; and literary, religious, and classical references.  

## Brief Guide to the Mark-up

### People
#### Fictional characters created by Alcott
- Named fictional characters created by Alcott (even ones who are thinly disguised real people) are tagged with `<persName>` with `@ref` to their entry in the Person List for fictional people.
-  Non-name references to people, are tagged with `<rs type="person">` with `@ref` to their entry in the Person List.
- The very few minor unnamed fictional characters mentioned in the text but who do not speak or are spoken to are not tagged.

#### Real people
- Named real people, (e.g. Charles Dickens or Abraham Lincoln, are tagged with `<persName>` with `@ref` to their entry in the Person List for real people.
- Non-name references to people (e.g. "the father of our country" for "George Washington") are tagged with `<rs type="person">` with `@ref` to their entry in the Person List.

#### Fictional characters Alcott mentions
- Named fictional characters created by other authors (e.g. "Sairy Gamp") are not tagged as people but as literary references -- see section [References, Quotations, and Allusions](#references-quotations-and-allusions).

### Events
- I have tagged references to historical events (such as "the Burnside Blunder") with `<rs type="event">`.

### Places
I have followed a similar method for places as for people:
#### Fictional places created by Alcott
- Named fictional places created by Alcott (even ones who are thinly disguised real places, e.g. "Hurly-burly House") are tagged with `<placeName>` with `@ref` to their entry in the Place List for real places.

#### Real places
- Named real places (e.g. "Washington, D.C." or "Willards") are tagged with `<placeName>` with `@ref` to their entry in the Place List for real places.
- Coordinate location of real places are stored in the Place List for real places.

#### Fictional places Alcott mentions
Named fictional places created by other authors (e.g. "the Slough of Despond") are not tagged as places but as literary references -- see section [References, Quotations, and Allusions](#references-quotations-and-allusions).

### References, Quotations, and Allusions
I have tagged direct and indirect references to literary works, authors, songs, etc. using `<seg>` tag with the following attributes and children:
#### `@type`
- **literary** - references to published works, such as novels (Note that, for now, in cases like "We talked about Emerson," I have tagged Emerson as a person not as a reference to his work.)
- **biblical**- references to the biblical people, events, and stories
- **religious** - non-biblical religious references ("The Seven Sleepers"). I'm considering other ways to categorize these few references.
- **classical** - references to classical authors or mythology ("Cato," "Gen. Mars" )
- **hymn** - references to religious songs ("Blow Ye Trumpet Blow")
- **fairytale** - references to folk tales, etc. ("Blue Beard")

- **historicalPerson** - references to historical people not contemporary to Alcott's time of writing. So, at least for now, Pocahontas is tagged as `<seg type="historicalPerson">` but Abraham Lincoln is tagged as `<persName>`.


#### `<bibl>`
- `<seg>` references with authors, titles, or Wikipedia links include a <bibl> entry as a child to <seg>. Where applicable, childen of `<bibl>` are:
-- `<author>` Name of author (e.g. Dickens), or, for Biblical references, Hebrew Scriptures or New Testament
-- `<title`> Name of title of work (e.g. The Pickwick Papers) or, for Biblical references, book of the Bible (e.g. Proverbs).
-- `<ref>`: relevant Wikipedia or other link



While this category of mark-up is the one that's most interesting to me, it's become the slippiest and the most frequently overhauled. The current mark-up scheme is a bit cumbersome. I settled on this system because I wanted to strictly follow TEI schema, include hyperlinks that may be useful to the reader, and also allow for answers to questions such as, "Which author's works does Alcott most refer to?" (answer: Dickens) and "Which of Dickens's novels does Alcott reference most?" (answer: *Martin Chuzzlewit*).  


## To-Do / Currently working on...
- Continued clean-up of text
- XSLT for web reading
- Track down remaining references
- Think more on how to best mark up names of historical people ("Pocahontas," "Cato," "Columbus")
- Add a few biographical notes
- Consider moving Wikipedia links out of in-line text

