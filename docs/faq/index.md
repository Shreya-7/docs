# Frequently Asked Questions

*This should be a crowd curated list that could apply to people curious about the production of codethesaur.us on the front or back end. Questions that might be overlooked in guides or maybe have not found their way to guides yet.*

## What does "Not implemented in this language" mean exactly?
This means that this concept is a thing you can look up on Code Thesaurus, but doesn't necessarily mean the language can do it. So not all languages can do all things other languages can, so this is a way of marking in the file "we're looked at this in the file, and this language can't do it." 
In the code for a language, contributors would identify this concept with a `"not-implemented": true`

## If I'm editing a language, but I don't know how to implement a concept, what do I do?
You can leave it blank. For example, 

```json
"some_concept_i_dont_know": {
    "name":"some concept I don't know"
        },
```
## What kinds of languages and structures are / can be included?
This is detailed in [Architecture](project_architecture.md)

## How can a concept be represented for a language? How does that look in the code?

1. concept exists (and has example code)

```json
"some_concept": {
    "name":"some concept name",
    "code": ["this language code interpretation of concept"],
    "comment": "optional comment",
        },
```
2. concept doesn't exist (therefore can't have code)

```json
"some_concept": {
    "name":"some concept name",
    "comment": "optional comment",
    "not-implemented": true
        },
```
3. unknown state (the ID got added but wasn't added to the file)

```json
"some_concept": {
    "name":"some concept name"
        },
```
4. concept exists (but no example code)

```json
"some_concept": {
    "name":"some concept name",
    "comment": "optional comment",
        },
```

## What if a developer could implement a workaround with code in the language to represent a concept? 
Code Thesaurus is a language reference tool. It should explain how the language works and exists. This is not to invent functionality or to be an algorithm reference. If the concepts don't exist natively, they are not implemented in the language. For our purposes, they should all have "code" deleted and replaced with `"not-implemented": true`.

## What should I put in the comments on a concept for the language? What are comments for?
Comments provide additional detail on the implementation of a concept in a language. They are optional and important. For example, in the concept "String as an array of Characters" in Swift is implemented with String. At the time of this FAQ writing, the comment on this is "String in Swift bridges to Foundation's NSString class, so developers have a wide variety of string methods available to them." The comment provides a helpful commentary to point developers new to Swift to key information about the implementation.

## Why do the concepts for maths not only show the operator, like **+**?
For maths, the order of the operators may matter. Most languages usually use something along the lines of the operator in between two operands (i.e. a + b). Not all languages do, notably something like LISP does (+ a b).
There are also prefix and postfix operators that might get confusing if people don't understand what prefix and postfix are. (As in what's the difference between ++ and ++ when we really mean ++a and a++?).

Therefore, the concepts need to show that even though we use the same operator, like **+**, it is between or before or after the operands so that a developer reader could use the information to implement the concept in their own code.

## What if I am assigned an Issue, but I can't finish it (as a contributor)?
If you've started, do a PR for whatever you have accomplished. If you have not started, that's ok. In both instances, it helps to communicate. Make a comment on the Issue that you are no longer available, so someone else can get the assignment and the work can still be accomplished. More info at the [Code of Conduct](https://github.com/codethesaurus/codethesaur.us/blob/main/CODE_OF_CONDUCT.md).
