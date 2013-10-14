---
layout: default
title: Engineering Design Evaluation of the Team Formation Survey
permalink: /eval/teamsurvey.html
---

In Praxis (ESC101 for the uninitiated), all students are strongly encouraged
 to complete the Team Formation Survey, an anonymous survey that claims
to measure one's learning styles.

It had one major objective:
> to create as valuable a learning environment as possible for as many Praxis students as possible.

Which is broken down into four objectives:

> - being as unbiased as possible (e.g. avoiding arbitrary or subjective measures)
> - being as transparent as possible
> - being as quick and simple to complete as possible
> - providing as many students as possible with the opportunity to experience a diversity of team mates

Overall, I believe that, while the survey does meet its criteria sufficiently, there is still room for improvement.

In this evaluation, I will mainly look at simplicity and (perceived) length of the survey, as well as touch on the fairness objective.

### Quick
 - Objective: "being as quick and simple to complete as possible"
 - Metric: time to completion
 - Constraint: Four days (Friday to Tuesday)
 - Criteria: Shorter is better

The survey meets this simple criteria with flying colours. It took me only 16 minutes to complete the entire survey,
and I was writing down comments on the survey while I was doing it.

However, what if we frame it another way? How quick does it *feel*?

As I completed the survey, I was constantly wondering how much time I still need to spend on it. 

After seeing the
wall of questions, I felt discouraged. One idea for design for usability would be to split the survey up into more sections.
that way, as people complete one section of the survey, they can get a sense of accomplishment.

Another way to help users estimate the time remaining would be to post a "# of questions left" or even "# minutes left approximately" on a
corner of the page so people can keep track of progress, and again feel like they are succeeding. (Be reminded of the parable of the elevator)

Finally, the part of the survey which stated that it was in three parts was not clearly stated on the main page: it was coloured the same
as the other wall of text, which means it does not stand out very well. Perhaps changing the colour would help others estimate the time remaining.

### Simple
 - Objective: "being as quick and simple to complete as possible"
 - Metric: percentage of students who managed to complete survey and be matched into groups
 - Constraint: x less than 100% but more than zero (if no-one completes the survey, no point)
 - Criteria: more is better

While I found the survey straightforward enough, I believe improvements can be made in two areas.

One area which I foresee problems is people disposing of their tokens when they finish the survey.

The survey's ending page simply thanks us for participating. It neglicts to mention a key point
stated only on the card and the e-mail:

> Hang on to the card and bring it with you to studio next week

Since the ending page does not stress this, it's possible that people may forget this point and chuck the card
into the nearest trash can, making the survey useless.

(Yes, it may be common sense, but that's not very common. I, for one, do not have much common sense)

Adding a notice certainly wouldn't hurt, and it may very well raise the number of valid surveys.

I also found three parts of the survey itself confusing. 

First, because the survey isn't broken up into sections, if one leaves a question blank, it is very difficult to find it again by scrolling. 
Webassign, an online homework assignment site, partially solves this by adding a green checkmark around every completed question, allowing
users to find uncompleted questions. This may help people who wants to skip ahead in the survey.

Secondly, in the Language section, the checkbox system is plain dumb and/or confusing.

In the language spoken section, languages were presented thus:

> Do you speak a Romance language? Check all that apply.<br/>
> <label><input type="checkbox" value="None" checked=""/> None</label><br/>
> <label><input type="checkbox" value="sacre_bleu"/> French</label><br/>
> <label><input type="checkbox" value="mamma_mia"/> Italian</label><br/>
> <label><input type="checkbox" value="woof_woof"/> Pug Latin</label><br/>

Pop quiz: name two languages in the above list that aren't languages. (Hint: Pug Latin is one)

The answer is "None". (Sorry, all of you who hate French and Italian)

None isn't a language. So why not detect no language spoken by the lack of any checked boxes?
Then, the None box can be removed, and thus reduce the clicking when
someone do in-fact speak a language: they won't have to check their language and then uncheck "None".

Finally, again, in the language section, the definition of being able to speak a language is not very clear on the initial page.
Only on the next page does it finally say that "speaking" a language as defined on the survey is one where
the user can accomplish a certain list of tasks using said language. That would have been good clarification on the language page itself.

I personally checked French as I studied it in high school, but then had to go back once I read the requirements.

###Unbiased

(Is there a set of metrics for lack of bias? If there is, feel free to yell at me about it)

One area that may potentially introduce a bias is showing us the results of parts of the survey before we complete the next part.
For example, before the Bolton-Bolton survey, we are shown our Felder-Silverman Index. There might exist a possibility that
once we read the index, we would answer the following questions to match our existing index. A solution is to show the full results only
at the end.

Another area is exposure to experiences assumed by the survey. Some people may attend less parties than others, for example,
 and thus they may answer the question "If you meet someone at a party, do you remember their..." differently, 
not because of their learning style, but because of their lack of experience at parties.

Finally, one of the ways that the objective of unbiasedness is met is by using an anonymous survey. However, one set of questions
on the survey is identical to another survey that we took: that previous survey did record names. Since I do not expect people's answers to 
change significantly on the new survey, if I wanted to identify people in this survey, I simply have to compare the answers 
between this survey and the previous one to match people. While this seems challenging, it is feasible: 
Researchers at the University of Texas successfully 
[deanonymized data from the Netflix Challenge](http://www.cs.utexas.edu/~shmat/shmat_oak08netflix.pdf)
by correlating public IMDB reviews with private reviews found in the
anonymized database. Thus, this undermines the claim of anonymity.
