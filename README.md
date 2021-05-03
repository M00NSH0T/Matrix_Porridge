![Matrix Porridge](https://github.com/M00NSH0T/Matrix_Porridge/blob/main/matrix.jpg?raw=true)


# Matrix Porridge: Optimizing the Human Diet. 
For Everything, but Taste.

Many COVID-19 survivors report losing their sense of smell and / or taste. While for most this returns over time, others continue to struggle with this issue months later. This problem made me remember an old project I worked on over a decade ago, way back in 2010 using Matlab. At the time, I was in my final days running my first company, right before Conservation Services Group recruited me. I was working long hours and had very little time to eat regular meals. A friend of mine and I were joking at the time that sometimes it'd be nice to just have an actually healthy meal to just eat in a hurry... one that didn't care at all about taste. 

I immediately thought back to the movie, "The Matrix" and the famous ["tasty wheat scene"](https://www.youtube.com/watch?v=v1EcrD5IyxM). Basically, in this dystopian future where the atmosphere had been ruined and nothing grew above ground, food had to be synthesized. The result was a gelatinous goop... "a single cell protein combined with synthetic aminos, vitamins, and minerals. Everything the body needs." (The Matrix, 1999)

Now there are a million products out there that claim to be healthy meals on the go for you, but looking at the nutrition labels on these, I never really found anything that quite delivered what I wanted. All focused too much on making something "edible." But those days, I was looking for something you'd down like a shot of bad whiskey. Something that got the job done, but didn't necessarily taste good. Not a bar filled with chocolate and peanut butter.

So back to these COVID-19 survivors. Losing their sense of taste is clearly not something anyone would ask for. But perhaps there's some lemonade they can make from these lemons. 

This project aims to find the optimal list of ingredients necessary to create the perfect meal for people who can't taste. It doesn't matter if the ingredients make sense to a chef, just as long as they solve the equation and meet the dietary constraints of a typical adult.

Check out the Jupyter Notebooks and recipe files. I recommend reviewing these in order, as certain sections get removed, added, or replaced from one notebook to the next as I evolve / refine the process. The first notebook had a lot more general discussion / background than the subsequent ones. Also, notebookes 1 and 2 used my original dataset from 2010 when I first attempted this problem in Matlab. I got around to rebuilding this using the most recent USDA data in notebook 3, but it still needed work. The solution from that notebook included a rather long recipe with some odd ingredients. I displayed that output in a word cloud for convenience, as shown below:

![recipe](https://github.com/M00NSH0T/Matrix_Porridge/blob/main/stylecloud.png?raw=true)


In the 4th notebook, I took a first pass at manually culling the massive ingredients list... removing high salt / salt added items as well as anything that obviously wasn't going to make it into a healthy, optimal food, such as fried foods. I also removed compound ingredients, such as salads and other prepared foods. And then I added hard constraints for the first time around the sodium requirements instead of the soft bounds built into the objective function, as well as added a constraint for the weight of the final meal. This last part proved necessary after some initial runs with the culled ingredients list yielded recipes that would weigh 5-10 pounds, including mostly raw watercress, which is far more than most non-competitive eaters could realistically take down in one sitting. Then, I modified the objective function to round down any inputs below a given threshold prior to calculating value, which was done to trim down the number of ingredients in the end product. I wanted to move away from solutions that were so complex they needed a word cloud to display. Finally, I used a differential evolution global optimizer to derive the final ingredients list. 

The result is a simple list of three ingredients: 
1.  reduced sodium whole milk,
1.  boiled lobster,
1.  raw, ripe plantains.

Sounds pretty gross, but other than being a bit high in saturated fat, it meets all the constraints for a healthy meal; at least those I included in my objective function and constraints. In future notebooks, I may need revisit those...
