# Sprint Retro

## What went well
While this project was at times crunched and frustrating, there are a number of aspect that we were very proud of. First, doing a deep, archeological dive into the data led to a thorough understanding of the data. It was a complex set with twisting and repeating paths to information that was not always complete nor obvious nor even uniformly named. Learning the data set, while time consuming, made the organization into a relational form more profitable. I hope it is accurate to say that, it led to a relatively accurate relational model. There are still some issues with it concerning potential derived fields, skipped tables for the sake of time, and at least one instance of a transitive dependency due to running out of time (see `What you would do differently below for more explanation`), but in general, it feels like it is on it's way to being solidly 3rd normal form.

We are also very happy with the readability and modularity of the final code base. We feel that, by applying OOP principles to the code, it is easy to read, easy to understand, easy to reason about, easy to edit, and easy to extend. Having the master notebook simply run it's dependent notebooks has a wonderful aesthetic sense and makes finding the errors when they occurred easy to pinpoint. Additionally, using a temp view to share the read data across notebooks felt like a good solution to reading the file data once.

Finally, we feel our group dynamic was successful. We all expressed thankfulness for good communication -- with members all being patient and taking turns listening and talking. No one's ideas were shot down, and everyone felt comfortable sharing both agreement and disagreement without discord. No one tried to shirk work, and no one tried to bully others to have their own way. It was a more Muskateer, 'all for one, and one for all' mentality.

## What did not go well/hindered project
There were really two issues that hindered the project most and led to things that did not go as well as hoped.

The first is the time crunch. In class working time was limited, due to lectures and assignments, and especially for the first week, studying for the certification in Databricks and personal issues outside members' control led to issues of time management. This led to an uneven understanding of the data set and assignment as members' entry into dedicating time to the project was staggered. This led to a bulk of the work and full understanding of the data, process, and goal to be pushed closer to the due date than we would have preferred.

The second issue was the misunderstanding of project guidelines. With a misapprehension of expectations of normalization with the silver layer, we frantically pushed to get a full normalization, which is where the bulk of our attention and dedication was pushed. This in turn led to the lack of a gold layer during our presentation. However, I would note that, with the robust process toward normalization of the data set, the data should be wonderfully ordered for complex SQL joins to discover interesting patterns.

## What would you do differently
Given a similar task in the future, there are a number of ways we would approach this differently and a number of tweaks we would love to have made.

The most salient change we would make would be to communicate more openly and frequently with "the client". Had we been less apprehensive and more communicative, we may have cleared up the misunderstanding of assignment. So in future projects, assumptions will be checked at the door and an open line of communication will be kept.

Another obvious change is, given more time, we would have obviously included a gold layer -- a facsimile of which is to be included with the turned in copy of the assignment, though it was lacking in the presentation.

One change that was up for question early on was what to do with the URL fields. We understood that they appeared for the most part to be uniform in their construction, and even considered at one point having a reference table of url stems, from which we could derive urls from the stems combined with the login names. We determined, for fear of losing information readily available, to instead retain the urls. In retrospect, as derived fields, within a normalized system, it would have been best to remove them from their objects and use the reference tables instead. As well, we did not get to finish solving certain tables with issues, such as `mentions` which was a deeply nested array of user names and emails without ids, which we ended up adding as two fields in the object that technicallyt constituted a transitive dependency.

We would further modularize the code for ease of reading and removing certain coding repetition. For example, having a UDF that allows users to input partition size and file path, would save repetitious typing and make the code even more scannable.

For more minute changes, substituting a window function with row number rather than the potentially explosively large numbers achieved by `monotonically_increasing_id()` would be a better choice. 

## What was learned
This project single handedly made us all *far* more comfortable with Databricks and it's commands and techniques. We learned a lot with the hands on use of pyspark commands and how to apply them to the process of cleaning, organizing, and representing data. Additionally, we got comfortable with keeping our notebooks and workspace clean and easy to read and dive into, as we weaved into and out of one another's notebooks, ensuring whomever was reading at the time was able to grasp the nature of the work for that section. This led to some lovely discoveries in modular code in Databricks and how to pass information between notebooks making use of its shared temporary memory.

We learned a lot about what it takes to work collaboratively with a group in a data engineering setting: about assigning tasks, discovering strengths and weaknesses, working to help and be helped, and how to affectively make use of one another.

While it did not factor strongly into the project, we did get used to tying our project to a github repository and collaborating from different branches.

And finally, we learned about appropriate use of the cluster and better practice on saving money and compute when doing work both large and exploratory -- making sure to detach unused notebooks, using smaller datasets for exploratory tests, etc.
