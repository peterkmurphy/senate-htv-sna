# Senate How-To-Vote Social Network Analysis

## Voting to avoid the clusterfück

### Introduction

This is a project that I threw together one Friday night - in between reading my daughter a bedtime story and tucking her in to bed. I generated an image - kind of like below - for Queensland, shared it on Facebook - and then went to bed. The next morning, I had a few shares - and the morning after that, 10s of shares. (As of writing, it now has 140). I didn't expect it to be so popular.

I got two requests. One: do it for every state (not just Queensland), and secondly, put the code on GitHub.

### The Gist

How does one not vote for a horrible micro-party in the Australia senate? In 2019, you have to number at least 6 parties above the line or 12 candidates below it. It's not like earlier years, where you can just vote "1" above the line. Now you need to choose. What if you vote for the *wrong* microparty? 

My idea: look at the Senate "How to Vote" cards on [Antony Green's 2019 Election Site](https://www.abc.net.au/news/elections/federal/2019/guide/preview) (initially, just for Queensland; now for all eight states and territories). The [How to Vote Card for the WA Nationals](http://nationals.org.au/wp-content/uploads/2019/04/HTV-2019-Senate-Nick-Fardell-NO-PRINTER-NO-BLEEDS.pdf) had to be sourced elsewhere, but otherwise, Antony Green's site had a comprehensive list of the HTVs for the senate.

By writing down which parties preference each other, and entering the data into [Graphviz](https://www.graphviz.org/) (an open source graphing tool), you can see which parties cluster together. Parties that cluster together are the ones that preference each other, which means at least a minimum of ideological affinity.

### The results

When you run Graphviz, you generally end up with one humungous cluster of parties on the right (and the Right): PHON, FACNP, Rise Up, LNP, and of course UAP. Then you've got a far looser cluster of parties around the Greens, the ALP and the Animal Justice Party. However, that's when you have a lot of parties there.

For the ACT and NT, you end up with a big mess, because almost everybody preferences everybody else. That's because the AEC forces everyone to vote 1 to 6 above the line, even though the territories only elect two senators each.

### Running things yourself.

Anybody is free to clone or download the source, and trying to generating images themselves. From the commnad line, for an input file 'state.dot' (containing the graph data for a state) I ran:


`neato -Tpng -Gstart=rand state.dot -o state.png`

Where 'neato' is a tool bundled with GraphViz that makes undirected network graphs. There is some randomness; running this command multiple times may give you different results - all saved to 'state.png'. I generally ran it several times until "The Greens" were on the left, ahd Fraser Anning's mob were on the right. It seems the best thing to do. 

### Acknowledgments

Thanks to Chewie Smith for the subtitle "Voting to avoid the clusterfück". Thanks also for Chakae D'Ellencourt for inspiring this post. 