# treasure hunt at Science Fest 2022

<iframe width="560" height="315" src="https://www.youtube.com/embed/s-z2kYapD8c?start=115" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

## Working

Treasure hunt game is originally implemented using Flask, Heroku and Postgres. Every Team of 2-3 participants had to enter their event participant ID in this format(ex:PU12PU34). Once they enter Id, a random key is generated. The random key should be entered in the entry page after an exact time(marking the start of the event). Each team can get the link of entry page by scanning a QR Code.

As the random key is entered and submitted, 10 random non-repeating locations along with 10 riddles are populated in the database for each ID that the team has used for registration(ex:PU12PU14). A riddle(pointing to a lab, place or Hall) is displayed in the entry\*page along with unique_key. After arriving at their first location(solution to the riddle in entry_page), team should scan QR code to get the URL of the page containing next riddle and enter the unique_key from previous page. QR codes are sticked to walls or objects in real locations. This cycle of **figuring out next location and entering the previously obtained unique_key** is repeated for all the 10 locations.

The average distance and time taken to traverse between all the ten locations are caculated before the commencement of the game. Find the path distances CSV file [here](https://github.com/nikhilkanta/th-bvj/blob/main/treasurehunt-pathlogic.xlsx%20-%20Sheet3.csv)

The final winner of the game is decided on this basis

- maximum distance covered by a team in the best time compared to the average_time_measurement to traverse between all these 10 locations.

## Result

results are calculated using jupyter notebook utilising pandas, numpy and matplotlib.

## Participation

More than 160 students had participated in the treasure hunt event. 37 teams successfully finished the game with each team consisting of 2 or 3 members.

## Credits

I am grateful to [Nikhil Kanta](https://github.com/nikhilkanta) for his guidance.
