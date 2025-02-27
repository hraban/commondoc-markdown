<a id="x-28COMMONDOC-MARKDOWN-DOCS-2FINDEX-3A-40README-2040ANTS-DOC-2FLOCATIVES-3ASECTION-29"></a>

# CommonDoc-Markdown

This is a wrapper around [3BMD][95d0] markdown parser which produces
documents in [CommonDoc][8f97] format. Also, it is able to render
CommonDoc documents into the Markdown.

It is a proof of the concept, but I'm already using it in the documentation builder
[40ANTS-DOC][778d].

> **Note**. This library is not compatible with [CommonMark][4117] yet.
> 
> 

<a id="x-28COMMONDOC-MARKDOWN-DOCS-2FINDEX-3A-3A-40INSTALLATION-2040ANTS-DOC-2FLOCATIVES-3ASECTION-29"></a>

## Installation

This library available only at Ultralisp.org now. To install it using Quicklisp client, do:

```lisp
(ql-dist:install-dist "http://dist.ultralisp.org/"
                      :prompt nil)

(ql:quickload :commondoc-markdown)
```
<a id="x-28COMMONDOC-MARKDOWN-DOCS-2FINDEX-3A-3A-40PARSING-2040ANTS-DOC-2FLOCATIVES-3ASECTION-29"></a>

## Parsing Markdown to CommonDoc

```
CL-USER> (common-doc.format:parse-document
          (make-instance 'commondoc-markdown:markdown)
          "
# Hello World

* First item
* Second item
")
#<COMMON-DOC:SECTION title: Hello World, ref: NIL>
```
<a id="x-28COMMONDOC-MARKDOWN-DOCS-2FINDEX-3A-3A-40FORMATTING-2040ANTS-DOC-2FLOCATIVES-3ASECTION-29"></a>

## Writing CommonDoc to Markdown

Now we can render our document back to Markdown:

```
CL-USER> (common-doc.format:emit-to-string
          (make-instance 'commondoc-markdown:markdown)
          *document*)
"# Hello World

* First item

* Second item


"
```
<a id="x-28COMMONDOC-MARKDOWN-DOCS-2FINDEX-3A-3A-40API-2040ANTS-DOC-2FLOCATIVES-3ASECTION-29"></a>

## API

<a id="x-28COMMONDOC-MARKDOWN-2FEMITTER-3A-2AGENERATE-SHORT-LINK-REFERENCES-2A-20-28VARIABLE-29-29"></a>

### [variable](ad9f) `commondoc-markdown/emitter:*generate-short-link-references*` t

By default it is `T`, but you can bind it to `NIL`,
to prevent short link references generation.

<a id="x-28COMMONDOC-MARKDOWN-2FEMITTER-3A-2AMIN-LINK-HASH-LENGTH-2A-20-28VARIABLE-29-29"></a>

### [variable](0f3e) `commondoc-markdown/emitter:*min-link-hash-length*` 4

Minumum length of the hash for generated markdown links.
This works only when [`*generate-short-link-references*`][651c] variable
is set to `T`.

<a id="x-28COMMONDOC-MARKDOWN-2FEMITTER-3A-2AEMIT-SECTION-ANCHORS-2A-20-28VARIABLE-29-29"></a>

### [variable](7f10) `commondoc-markdown/emitter:*emit-section-anchors*` t

When this variable is `T` (default), emitter outputs
a raw html `<a name="some-id"></a>` before each
Markdown section.

<a id="x-28COMMONDOC-MARKDOWN-DOCS-2FINDEX-3A-3A-40ROADMAP-2040ANTS-DOC-2FLOCATIVES-3ASECTION-29"></a>

## Roadmap

* Make commondoc-markdown compatible with [CommonMark][4117] syntax.


[8f97]: http://commondoc.github.io/
[651c]: https://40ants.com/commondoc-markdown/#x-28COMMONDOC-MARKDOWN-2FEMITTER-3A-2AGENERATE-SHORT-LINK-REFERENCES-2A-20-28VARIABLE-29-29
[778d]: https://40ants.com/doc/
[4117]: https://commonmark.org/
[95d0]: https://github.com/3b/3bmd
[7f10]: https://github.com/40ants/commondoc-markdown/blob/5120b3f23613cc4d06380a21ab48cf516fe862a7/src/emitter.lisp#L21
[ad9f]: https://github.com/40ants/commondoc-markdown/blob/5120b3f23613cc4d06380a21ab48cf516fe862a7/src/emitter.lisp#L26
[0f3e]: https://github.com/40ants/commondoc-markdown/blob/5120b3f23613cc4d06380a21ab48cf516fe862a7/src/emitter.lisp#L93

* * *
###### [generated by [40ANTS-DOC](https://40ants.com/doc/)]
