---
layout: post
title: "Hitchhiker's Guide to Clojure - Part 2"
date: 2014-02-02 21:20
comments: false
---

Amy and Frank were hurtled quite rapidly through time and space after
attaching themselves to a transaction headed through the
[Datomic Transactor](http://docs.datomic.com/transactions.html). From
there things slowed down a bit, then took a sharp left and
ricocheted off again with incredible speed until they landed in another
[Datomic Peer](http://docs.datomic.com/architecture.html), and finally
appeared in the same room.  Amy was quite startled by the
anti-climatic nature of the whole dematerializing and rematerializing
in the same exact spot, and didn't really know what to do next.  She
surveyed her office and found it exactly the same,
except for two distinct details.  For one, the pistachio shells had
disappeared, and for another, the date on the computer showed
yesterday at 8:00 am.  She tried to connect these facts rationally
with the pistachios in her pocket and finally said,

"I am about to come into work."

Frank, who was busily hunting through his blue zippered pack around
his waist, looked up briefly.

"Well, we better get out of here then, I only have a blue fanny pack."

{% img http://img.rakuten.com/PIC/37504308/0/1/500/37504308.jpg %}

_The Hitchhiker's Guide to Clojure explains that the "fanny pack", or
"bum bag", is the symbol of a licensed Chrono-agent.  The rank of the
Chrono-agent can be clearly determined by its color on the ROYGBIV
scale._

_The origins of this licensing method can be traced to an embarrassing
incident in human history known as "The Great Flood". A junior
Chrono-agent was trying to increase the yield of a tomato crop during
a dry spell and was trying to do the following recursive function in his evaluator:_

```clojure
(defn rain [days]
  (when (pos? days)
    (println (str "Rain: " days))
    (rain (dec days))))
    
(rain 5)
;;Output
;;  Rain: 5
;;  Rain: 4
;;  Rain: 3
;;  Rain: 2
;;  Rain: 1
```

_Unfortunately, he made the rookie mistake of forgetting to decrement
the days before passing it to the recursive function._

```clojure
(dec 5) ;=> 4
```

_The result of which was severely overwatered tomatoes._
```clojure
(defn rain [days]
  (when (pos? days)
    (println (str "Rain: " days))
    (rain days)))
 
(rain 5)
;;  Rain: 5
;;  Rain: 5
;;  Rain: 5
;;  Rain: 5
;;  Rain: 5
;;  ...(you get the idea)
```

_It is interesting to note that he could he written the same function with a
[recur](http://clojuredocs.org/clojure_core/clojure.core/recur) instead._

```clojure
(defn rain [days]
  (when (pos? days)
    (println (str "Rain: " days))
    (recur days)))
   
(rain 5)
;;Output
;;  Rain: 5
;;  Rain: 5
;;  Rain: 5
;;  Rain: 5
;;  Rain: 5
```

_That would have had the nice effect of not consuming the stack, (which
is fabulous for constructing those lovely fibonacci sea shells for beach
vacations), but without decrementing the parameter in the recursive
call, it wouldn't have really helped._

_A senior Chrono-agent was dispatched to sort out the mess.  By the
time he got there and stopped the rain, there was not much left to
work with. Thankfully, he was quite versed in lazy and infinite
aspects of Clojure. For instance, take this vector of 2 chickens:_

{% img http://farm4.staticflickr.com/3352/3556879530_089814192c_m.jpg %}

```clojure
[:hen :rooster]
```

_It can be transformed into an infinite lazy list of chickens by using
[cycle](http://clojuredocs.org/clojure_core/clojure.core/cycle)._

```clojure
(cycle [:hen :rooster])
```

_What really set the senior Chrono-agent apart from his junior
colleague, was that he did not put the infinite sequence in the
evaluator. If he had, there would have been another embarrassing
incident in human history, this time involving an over-abundance of poultry. Instead, he used
[take](http://clojuredocs.org/clojure_contrib/clojure.contrib.str-utils2/take)
to get the first n infinite chickens._

```clojure
(take 5 (cycle [:hen :rooster]))
;;=> (:hen :rooster :hen :rooster :hen)
(take 10 (cycle [:hen :rooster]))
;;=> (:hen :rooster :hen :rooster :hen :rooster :hen :rooster :hen
:rooster)
```

_After that, the council of Chrono-agents, decided to license evaluator
use. Low-level recursion requires the 2nd highest indigo level rank.
The highest violet rank, of course, belonging only to the
[Macro](http://clojure.org/macros) Masters. All lower levels are
required to stick to the safer, higher level abstractions like
[for](http://clojuredocs.org/clojure_core/clojure.core/for),
[map](http://clojuredocs.org/clojure_core/clojure.core/map), or
[reduce](http://clojuredocs.org/clojure_core/clojure.core/reduce)._

Amy was still watching Frank busily rumaging through his pack in the
office . Finally
he found what he
was looking for, his hand emerging triumphantly with a fistful of
mini-marshmallows.


"Got it. Come on, let's go! Someone is trying to destroy the world and
we need to see the otters."



