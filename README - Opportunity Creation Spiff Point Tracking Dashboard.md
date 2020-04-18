# Opportunity-Creation-Spiff-Point-Tracking-Dashboard
This is a dashboard I created for my Sales to be able to track activities and opportunities created for individuals and the team pairings for an April sales spiff.

The goal of the spiff is to encourage account executives to prospect into their target accounts, and to work with their account development representative (indiviuals focused solely on prospect into accounts generally) to work the account executive's target accounts specifically. 

Account executives were split up into teams of two (for a total of 7 teams). Each account executive and their team were awarded points based on opportunities created on their target accounts and upsell accounts (existing customers they were trying to sell more product to). Opportunities became more valuable as they went further in the sales cycle, with each of several stage categories up to "Closed Won" counting for increasing numbers of points, up to a maximum of 4 points for a won deal.

There was also a qualification requirement for the spiff. Each account executive on a team was required to complete a total of 500 prospecting activities (emails, calls, Linkedin messages) and 150 calls on their target accounts within the month of the spiff. Each AE had to complete achieve both metrics for the team to be eligible to win the spiff.

Dashboard Process:
My manager asked me to help with it after he tried to create a Salesforce report, but found it insufficient for what he hoped to see to track the points and activities of the teams throughout the month. I worked with him to understand the requirements for a dashboard that would be useful for the team to see in our team Slack channel on a regular basis. Then I start querying.

First, I created a chart to show the number of points each rep had based on the opportunities they had sourced, and at what stage the opportunities were at in the sales process. 

Next I created a chart to show the number of activities each rep had completed in the month. I included a column for total activities and for calls specifically, since each value had to be met to qualify for the spiff. I then added a field to calculate whether both requirements were met - if they were, the value in that columns would become "Qualified", otherwise, it would show "Not Qualified".

Finally, I created a chart to aggregate the total points for each team. I did this by bucketing each indiviudal into a team, then finding the grouped sum of their points. 

With this basic dashboard in place, a few other requirements came up. IT was only after I created these three charts that it was decided that upsells would be included. Upsells are owned by a Customer Success Manager, so I had to use a different field to include those in the final point results. This meant that I had to create separate CTEs to paste in the values from different queries within the chart to get a final aggregate table. It also meant that it would be useful to break out points per indiviual and team by new business opportunities, upsells, and total points. 

Several other requirements came up as I was developing the dashboard, such as changing the point structure for upsells (easy to do since they were being pulled with a separate CTE already), and limiting upsells to those worth over $5,000.

Overall this was a fun, useful project to do over the course of about a week. It yielded a dashboard posted in slack that served to motivate people to get to the top of the leaderboard, and to qualify for the spiff, which would ultimate result in more pipeline and deals won for Sisense.
