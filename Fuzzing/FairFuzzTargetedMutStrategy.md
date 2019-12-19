
## FairFuzz: A Targeted Mutation Strategy for Increasing Greybox Fuzz Testing Coverage

**Authors:** Caroline Lemieux, Koushik Sen


- **Reviewer:** Andrew R. Reiter
- **Review Date:** Dec 19 2019

Paper github: [https://github.com/carolemieux/afl-rb](https://github.com/carolemieux/afl-rb)

Their goal is to increase code coverage in greybox setting. They aim
to do this by discovering rare branches and then by employing a
mutation strategy that uses mutation experiments to determine the
parts of the input that relate to those rare branches. The strategy
is capable of being combined with the magic byte approaches by
Driller and Steelix and the customization of power schedules seen in the
AFLFast work from Bohme, et al..

They observe that only using the notion of *n* least-hit branches
can fail to work across applications, so they define a cut-off based on
rarity. Essentially, they find the branch with least hits and define 
the cutoff as the next power of 2 greater than that branch's number
of hits. 

They define the notion of a mutation tuple and keep track of mutations
that lead to target branches in the code. In particular, they focus on
deterministic mutations, insert, updates, and deletes.
They define a "mutation mask"
function that determines whether the input generated from a given mutation
on a location will likely reach a target rare branch. Using this, they can determine
whether or not various mutations will likely continue to reach a target
and thus whether to allow mutations to occur and test them as new inputs.

They discuss whether their definition of mutation mask is actually any good
and also why their approach may not work on other targets.


They made use of 9 benchmarks:

- djpeg from libjpeg-turbo-1.5.1
- readpng from libpng1.6.29
- tcpdump -nr from tcpdump-4.9.0
- nm from GNU binutils-2.28
- objdump -d from GNU binutils-2.28
- readelf -a from GNU binutils-2.28
- c++filt from GNU binutils-2.28
- mutool draw from mupdf-1.9
- xmllint from libxml2-2.94

No dictionaries used. The seeds are found [seeds](https://github.com/carolemieux/afl-rb/tree/master/testcases)
and `c++filt` was seeded with "_Z1fv\n". They do 20 runs of 24 hours
each on a single core, selecting this by referencing other papers. For
analysis, they use *branch coverage* despite the order dependent nature
of the path coverage in AFL. I would have been interested in also understanding
the path probabilities as a point of comparison. They also include 
some discussion about the various findings for each of the 9 applications they
put under test.


