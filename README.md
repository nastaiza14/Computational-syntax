# Computational-syntax
Chapter 4

NOTES

I used universal dependencies as a reference to tag my sentences and make the rules, but didn't follow it completely.

A) Japanese Grammar summary

B) Problems encountered during assignment

- - - - - -
A)

On Japanese grammar (syntax):

# Basic morphology

Japanese doesn't have prepositions as such, it has some particles that determine case. The order is Subject-Object-Verb.

は (wa): topic of the sentence (nominative)
が (ga): subject of the sentence (nominative)
を (wo): direct object of the sentence (accusative)
に (ni): determines location/direction or indirect object (dative)
で (de): determines location of an action in progress (locative)
の (no): "of", possession and description (genitive)

wa and ga are similar in many contexts and are interchangeable in some, for the sentence to be grammatically correct, that is. We are not entering into detail.

There are other words that behave as prepositions too.

A noun may modify another without the need for the particle "no" (genitive).

Verb has polite and plain form.
Verb has negative and non-negative forms.
Verb tenses include: non-past(present & future), past, passive, causative, passive-causative.
Verb has progressive form in present or past.

To build the progressive the "te" form of the verb is used.

TO EAT: taberu

tabe-ru (eat) : in non-past.		Notice we find the stem by taking the "ru" (る) suffix. 
tabe-ta (ate) : past.
tabe-te-iru (-be- eating) : progressive.

The progressive uses something closer to our auxiliaries, the verb "to be": iru -> いる.

tabe-te-i-ta (-be eating-): past progressive.

Notice how the form of the "iru" verb is still present in the past progressive, but it only keeps the stem.

The copula is the verb "です" (desu) in polite form and "だ" (da) in plain form. 
Some adjectives can flex like verbs.

If the verb flexes, the copula is not necessary. If the speech is polite, the polite copula may be added after the flexed adjective. (the copula also flexes in past, but we are not going into much detail here)


- He is cold.
- kare	wa	samu-i	(desu)
- 彼		は	寒 い 	(です)
- he		(topic)	cold-is	(polite copula)

- He was a boy.
- kare	wa	shonen	datta
- 彼		は	少年	だった
- he		(topic)	boy	was


# Basic sentence structure

(Subject) wa (Object) wo VERB.

- I 	was 	just 	a 	boy 	with/wearing 	muddy	shoes.
- 僕 	は 	泥	 	だらけ 	の 	靴 	を 	履いた	少年	だけ	でした。
- boku wa doro darake no kutsu wo haita shonen dake deshita.	
- I	(topic)	mud	full of(genitive)	shoes	(object) wore boy only(particle) was.

Something like: I (shoes full of mud wearing)->boy only was).
There's a relative clause there.

- I 	will 	go 	to 	Italy.
- 私	は	イタリア	に	行く。
- watashi wa itaria ni iku.
- I (topic) Italy to(dative) go(non-past).

Other clauses (dative/locative) are typically added between the subject and object.
Adverbials as well, but also at the beginning.

(Subject) wa (dative) ni (locative) de (Object) wo VERB.

- I 	will	 give	 her	 a	 rose	 at	 the	 concert.
- 私	は	コンサート	で	彼女	に	薔薇	を	あげる。
- watashi wa consaato de kanojo ni bara wo ageru.
- I	(topic)	concert	in(loc)	she	to(dat)	rose	(object)	give.

Something like: I (in the concert) (to she) a rose give (will give).

- - - - - -

B)

A few problems I came across during the assignment:

1) 

For clause 5 ("It was conducted just off the Mexican from April to June"), I translated the sentence without a subject, because there is no equivalent expletive in Japanese. I could have added a demonstrative pronoun and something like "that was conducted", but since I didn't, the program cannot form a sentence with what I wrote. This type of sentence without a explicit subject is allowed in Japanese as far as I'm concerned.

If I wrote "あれ は ..." (are wa), "That (topic mark)", I would get a NP_nom, either before or after the adverbial "from April to June", and then we would have a sentence. 

2) 

Punctuation: "。" gets analyzed incorrectly in some instances, it gets labeled as "comma", which messes up the analysis in such cases. The code is U+3002 for both of the wrongly tagged and correctly tagged full-stop symbols. I also tried replacing "。" with ".", but the error persists.

3)

For progressive verb forms: "て いる" (te i-ru), "て い ます" (te i-masu), etc., where the "i" part translates to the verb "to be", the verb takes a "fixed" role to make that progressive tense. 
To specify this, I put the relevant words in the category "Predet", but this category is not recognised. 

In fact it is mismatched for sentence 17 ("Adam...", "アダムは永遠の命に連れて行かれたでしょう。"), where ("行か") is recognised as an item of said "Predet" category, even though it is not in there.

This may also affect other sentences.


4) 

If I add all the Adp objects (Adp_nom, Adp_acc, etc.) to the tag "ADP", the terminal takes a very long time to load the parsing. Even though this may affect the score, I decided to not put those categories in the ADP tag.

5) 

I can't seem to match categories nmod and compound. Either because I couldn't understand how it works in UD, which is the reference I used to analyze the Japanese sentences, or because I am writing wrong rules.

Overall I believe that describing the process of making this grammar could be a project in its own.
