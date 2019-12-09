## Teaching Meaningful Explanations

Paper by Codella, Hind, Ramamurthy, Campbell, Dhurandhar, Varshney, Wei, and Mojsilovic
IBM Research

A paper proposing an approach to generate explanations.  This papers centers around assigned labels
and features.  A joint model is produced (via learning) to tailor labels and explanations from the
input data.

*Explanation* is defined as information provided to verify an output.  This is consistent with
other papers I've seen in medical applications, etc., where the explanation offers a justification
of the model output and so gives the practitioner a reason to trust or distrust the model.

### Requirements for Meaningful Information
- Complexity of the explanation matches the capability of the consumer. (i.e. it's understandable).
- The explanation needs to be tailored to the domain (i.e. it's set in the right context).

The paper goes on to describe how information consumers find meaningful explanations.  This is different
than a lot of explanation that depend on 'local' explanation finding.

### Candidate Approaches

With X as an input, Y as an output, and E as an explanation, the paper creates a tripe, X x Y x E.  This
is used as the basis for corresponding explanations e for the specific, (x,y) pair.  They used a multi-
pair network to predict Y and E as a output pair (y,e) from X (a given x).  This is the mathematical
basis for their TED (Teaching Explanations for Decisions) approach.

### Evaluation and Conclusions

They used four datasets to look at results, forgoing generality for later on.  The four datasets showed
some good results in these specifics but noted that their is an extra, somewhat laborious step, introduced
with this paradigm of approach.  So while it does look to provide meaningful results, it should be
weighed against how much work it is.  
