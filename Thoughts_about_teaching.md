Thoughts on Teaching with Applied Statistics with R: A Practical Guide
for the Life Sciences
================
Justin Touchon
8/3/2021

The book I’ve written and which you have either bought or are maybe
thinking about buying — Applied Statistics with R: A Practical Guide for
the Life Sciences — grew out of my efforts to teach undergraduate and
graduate students statistics. This page talks a little about how I use
the book in my teaching.

As I describe in the book, I am not a statistician but an ecologist. I
study behavior and evolution of animals in the real world, where data
are often messy and imperfect. Over the years, I got pretty good at
analyzing and visualizing my data, good enough where I started getting
asked to teach other people how to analyze and visualize their data.

The materials in my book began as lectures in a week-long workshop I
would teach with my friends Andy Jones and Stu Dennis at the Smithsonian
Tropical Research Institute. Now that I am an Associate Professor of
Biology at Vassar College, I teach a 0.5 credit Applied Biostatistics
course each spring to a small group (generally 10–11) of senior
students.

## Course structure

At Vassar, our semester is usually 13–14 weeks long. We usually meet
once per week for 2 hours and during that time we partially work through
the material in a given chapter. There are 10 “meaty” chapters in the
book, which therefore provides time for 10 weeks where I cover 1 chapter
each week, plus I usually build in 1 week in the middle as a
“mid-semester recap” to just go over code again and answer questions and
make sure everyone is up to speed and on the same page. With the
remaining weeks of the semester I give students free time to work on an
independent project where they analyze data on their own, with
consultation from me as necessary. The course ends with a final
presentation or paper describing 1) what question or questions they were
trying to answer with their independent project, 2) what the nature of
the data were, 3) how they went about analyzing the data and 4) what
they found. I try to keep the focus less on the results they found and
more about the process by which they got there.

## What things look like in the classroom

When I teach Applied Biostatistics, I try to do as little lecturing as
possible. Instead, I try to code along with the students. I have my
laptop hooked up to a projector and have R open. Then, we just go
through the book page by page, with some elaboration or tangents here
and there as necessary and appropriate. Sometimes the best teaching is
when a student will ask “why do you code it that way?” or “what does
that bit of code do?” and we can explore from there. I don’t try to work
through all of each chapter with my students, but I do try to get
through some of the material to help them get started. I find coding
along with them provides a nice medium for explaining what the code is
doing and why we type this thing or that thing. It also creates a slow
enough pace where most students can keep up and digest the material as
we go. I like to have a chalkboard or dry erase board next to the
projector screen so that when, for example, we are starting to code our
first Linear Models, I can draw out a Normal distribution or make a
quick drawing to explain what residuals are. I find it very useful to
have non-computer space where I can write and draw things out as
necessary.

In any class there are a few students that struggle to wrap their heads
around the code. Like learning any language, some folks pick it up very
naturally and others do not. I try to be patient and make sure they get
the help they need, but I also am careful to not let one or two students
totally derail the day and occupy all of my time. If we have a two hour
class period, I usually stop coding with 30 minutes or more left, so
that I can have time to help struggling students one-on-one. I also
encourage students to work in groups outside of our actual class time
when they are finishing a chapter or working on the weeks homework
assignment, since they might be able to help one another in a way that
is more intuitive than how I might help them. Plus, we all know that
figuring out your own solution is the best way to learn something!
Lastly, I also create a forum on our course management software (Vassar
uses Moodle) where students can post questions if they get stuck.
Students are then encouraged to respond if they can help their
classmates get unstuck!

## Weekly homework assignments

In the first week of the semester, in addition to starting to go over
the basics of what R is and how to use it, I teach the students the
basics of using RMarkdown in RStudio. The reason for this is so they can
then use RMarkdown to create their homework assignments. RMarkdown
beautifully integrates code and output and text, so provides an
excellent medium for this sort of work. That said, there is a potential
downside. Some students have trouble distinguishing RMarkdown from just
having a script file to code into and so will do *everything* in
RMarkdown. I think this is the wrong approach, and strongly discourage
them from doing this. My approach is that they should use an R script
for working through the chapter and maybe even working the kinks out for
a homework assignment, then move to RMarkdown when it is time to craft
the final version of their homework assignment.

Homework assignments are turned in as .html files (easily knitted out of
RStudio) at least a day before our next class period. This gives me
enough time to look through them and figure out any mistakes students
might have made, or better yet to figure out interesting or clever
solutions they have come up with. Each class then starts with a run
through of everyone’s homework, highlighting any of the cool things they
have come up with. I find this is one of the best teaching times because
I get to give positive feedback to students that have found interesting
things on the internet about how to modify their color palette or add
text here or there or just somehow dress up a figure or some code. There
are often common mistakes made by multiple students, so I try to address
these in a way that doesn’t spotlight particular students but instead I
show the code (without names) and discuss why the mistake was made and
how it could have been corrected.

## The independent project

As mentioned above, the course ends with each student analyzing some
dataset of their choosing. Ideally the data are the student’s own,
perhaps from their senior thesis, but in the event they do not have data
of their own students are encouraged to download publicly available data
from Data Dryad or other repositories. Students that get public health
data or survey data often have a more difficult time translating the
lessons of the book to the types of analyses they might want to or need
to conduct. Thus, I try to steer students to choose data associated with
published papers in ecology or similar fields. I will tell them to look
through recent issues of journals they might be interested in (e.g.,
Behavioral Ecology or New Phytologist or Evolution) and that have
available data associated with them. The students spend the final 2–3
weeks of the semester working on their projects on their own and I make
myself available for consultation each week. In the final class period
students present their analyses to the class.

I hope you find this information useful. If you plan to teach with the
book, please feel free to reach out at jutouchon-at-vassar-dot-edu. I
would love to hear from you and am happy to answer any questions if you
have them! I’m also just happy to have your feedback in general.

¡Saludos!

-Justin
