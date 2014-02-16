---
layout: post
title: "Hitchhiker's Guide to Clojure"
date: 2014-02-03 19:33
---
{% img http://farm6.staticflickr.com/5480/12258585125_36e8fdee1e.jpg %}

_The following is a cautionary example of the unpredictable
combination of Clojure, a marathon viewing of the BBC's series "The
Hitchhiker's Guide to the Galaxy", and a questionable amount of
cheese._

There have been many tourism guides to the
[Clojure](http://clojure.org/) programming language.  Some that easily
come to mind for their intellectual erudition and prose are "The Joy
of Touring Clojure", "Touring Clojure", "Clojure Touring", and the
newest edition of "Touring Clojure Touring".  However, none has
surpassed the wild popularity of "The Hitchhiker's Guide to Clojure".
It has sold over 500 million copies and has been on the "BigInt's
Board of Programming Language Tourism" for the past 15 years. While,
arguably, it
lacked the in-depth coverage of the other guides, it made up for it in
useful practical tips, such as what to do if you find a nil in your
pistachio.  Most of all, the cover had the following words printed in
very large letters: **Don't Worry About the Parens**.

To tell the story of the book, it is best to tell the story of two
people whose lives were affected by it: Amy Denn, one of the last
remaining [Pascal](http://en.wikipedia.org/wiki/Pascal_(programming_language) developers in Cincinnati, and Frank Pecan, a time
traveler, guidebook reseacher, and friend of Amy.

Amy, at this moment, was completely unaware of the chronological
advantages of her friend, being preoccupied with the stark fact that
she was about to be fired.  She had been given a direct order from her
CEO to deploy the code at 3:05pm.  It was now 3:00pm and she had
realized that if she did so, all the data painstaking collected about
the effects of
[Throat Singing](http://en.wikipedia.org/wiki/Tuvan_throat_singing) on
the growth rate of tomatoes would be erased. Unfortunately, the CEO
did not really understand or trust anything having to do with
technology or programming.  In truth, the only two things that he
seemed to care about were tomatoes and checklists of unreasonable
things. The fact that no course of action available to her in the next
5 minutes would help her employment situation, agitated Amy so much
that she was violently shelling and eating pistachio nuts.

{% img http://farm4.staticflickr.com/3331/3659226924_fbf336379e_n.jpg %}

The "Hitchhiker's Guide to Clojure" says that
_pistachios are Nature's
most perfect [s-expression](http://en.wikipedia.org/wiki/S-expression). An
s-expression is recursively composed of s-expressions or an atom.
In the case of the humble pistachio, the atom is the nut inside. The
atom simply evaluates to itself.  This is best seen is an example
where the following expressions are evaluated in the Clojure
[REPL](http://tryclj.com/)_

```clojure
"hi" ;;=> "hi"
1 ;;=> 1
true ;;=> true
nil ;;=> nil
````

_Which leads to the very practical tip of what to do if you find a nil
in your pistachio.  The answer, of course, is to be thankful that you
have a value that represents the absence of a value - and to get
another pistachio._

_In Clojure, a s-expression is written with parens.  The first element
within the parens is an operator or function and the rest of the
elements are treated as data, some of which can be s-expression
themselves._

```clojure
(+ 1 2) ;;=> 3
(+ 1 (+ 2 2)) ;;=> 5
```
_Considering the pistachio again, we can think of the nut in the shell
as an s-expression, (providing we also imagine an operator or function
right in front of the nut)._

_Here we define a function that will turn the nut red, by appending the
string "red" to the nut-name._

```clojure
(defn red [nut]
  (str "red " nut))

(red "nut1") ;;=> "red nut1"
```

_Notice that if we put a quote in front of the expression, it will no
longer be evaluated._

```clojure
'(red "nut1") ;;=> (red "nut1")
```
_quoting the expression turns it into a list, which we can then
manipulate with other s-expressions (code as data)._

```clojure
(first '(red "nut1")) ;;=> red

(last '(red "nut1")) ;;=> "nut1"
```

_If we try to evaluate the s-expression with just the nut name in the
parens, we get an error because there is no function in
the first slot._

```clojure
("nut1")
;;=> ClassCastException java.lang.String cannot be cast to clojure.lang.IFn
```

_The whole thing of having to have a function in front of the nut in
the pistachio has invited much heated debate on the suitability of
pistachios being held up as the paragon of an s-expression.  But
critics have failed to explain the corroborating evidence of red
pistachio nuts, or find a more suitable nut._

Amy's time traveling friend, Frank, is due to appear on the scene
momentarily to reveal that the whole world is really made of Clojure
[Datomic](http://www.datomic.com/) datoms.  Furthermore, a transaction
is going to be evaluated soon, which will retract all the facts on
EVERYTHING. The practical effect of this will be that nothing will
have an attributes. A world without any attributes at all would be
quite boring and, for all purposes, be non-existent. Luckily for Amy, Frank is a Datomic Time
Traveller and has a hand-held "evaluator" which will save them. Also
luckily, the readers will be spared dialog, since the author
can never figure out where to put the punctuation and is really
rubbish at it.  Only one phrase will be illustrated.  This is the
rather important one, having been uttered by Amy after it was explained to her
that she, and the entire world around her, was entirely composed of
Clojure:

"Isn't that the language with a lot of parens?"

To which, Frank handed her the "Hitchhiker's Guide to Clojure" and
pointed to the words on the front cover,  **"Don't Worry About the
Parens."**, and turned to the first page.

*"There is absolutely no need to worry about the parens. It is known
 today that the first really important discovery of humankind was not
 fire, but [Paredit](http://www.emacswiki.org/emacs/ParEdit).  Paredit
 mode magically acts to insert and balance the right parens to the
 point where they actually can no longer be seen.  This is evident by
 just looking around you. The world is made of Clojure and there are
 millions, billions, and trillions of parens all around you and your
 tea cup right now.  Yet, you don't see them.  Paredit mode."*

At the urging of Frank, Amy quickly stuffed the remaining pistachios
in her pockets while he readied his evaluator. The display showed
some large integer value, that decreased as he pushed the buttons on
the console.  Finally, he pushed the large red button and two parens
started glowing on either side of them ... and they disappeared.


