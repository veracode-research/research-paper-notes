## Explainable Recommender Systems that Maximize Exploration

Author: Homanga Bharadhwaj
Indian Institute of Technology, Kanpur

This paper uses Gated Reccurent Unit (GRU) based RNN's (Recurrent Neural Networks) to model
the evolution of users' preference for a given choice.  They use this technique on Netflix and
IMDB datasets.

This is a short paper, just two pages, but it's interesting and has some concepts that I've
found worth considering.

#### Exploration

The paper defines exploration, for a user i, at a given time t as, e_(it), =
The sum of ratings for all movies rated by i that lie among the genres that fall in the
first quartile (this is because of the dataset).  The rating at the next time (t+1), will
contribute to the e_(i,t+1) if the corresponding to one of the genres in the quartile.

#### Mathematics

The math of the paper is interesting in that it sets up a series of matrices that project
evolution.  I really like this idea, even if this might be a bit outside the realm of
interest, because of the idea to explore how useful something is and how it then adds
to the rating.  Again, we're not really after ratings, but the idea of evolving utility
is interesting as I could see how mitigations or remediation advice, etc, could evolve
based on user (customer feedback).  Any collaborative system seems like this ought to
be similar to this, and the general process seems fairly thoughtful.

