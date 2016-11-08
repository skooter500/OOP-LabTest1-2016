# DT228 DT282 Lab Test 1 2016

## Rules of the test
- This is an open book test. You can use any of your own sketches, any of the examples from [the course website](https://github.com/skooter500/OOP-2016-2017) or the [Processing reference](https://processing.org/reference/) during the test.
- No conferring or collaboration.
- No use of Google, Facebook, Sloack or any any other web resources permitted.
- There are marks going for correct use of git, but I recommend that you save regularly and also submit a zipped copy of your test through websourses when you are finished just to be safe.

## Instructions

- This is the sketch you will be making today:

- Start with a blank sketch. Name it StarMap and commit it to a new git repository on github of the same name.
- Download [this CSV file]() to the data folder of your sketch folder. The data contains information on stars within a distance of 15 light years of the sun. I have removed some entries to make the data easier to visualise. The 0th row gives the column headers. Each row from the file contains lots of information about the star, but we are only interested in the following columns:

| Column (starting from 0)| Name | Description |
|--------|------|-------------|
| 2	| Hab? | Habitability flag	1 = star has a high probability of hosting a human habitable planet |
| 3	| DisplayName | The name of the star |
| 12 | Distance	| Distance from the sun in parsecs |
| 13, 14, 15 | Xg	Yg	Zg | xyz galactic cartesian co-ordinates in parsecs (used to draw the star map) |
| 16| AbsMag | Star's size |

- Create a class Star to encapsulate the columns of interest from a single row from the file. The columns of interest are given in the table above!
- Write a constructor that takes a TableRow as a parameter and assigns the fields in the class from the appropriate columns in the TableRow. You might want to look at [this page from the Processing reference](https://processing.org/reference/TableRow.html) if you need to know how a TableRow works.
- Declare a global ArrayList of Star objects
- Write a method called loadData that loads the data from the file and populates the ArrayList. Call this from setup.
- Write a method called printStars that prints the contents of the ArrayList after it has been loaded. You should make a toString method on the Star class to help you do this.
- Write code to draw the purple gridlines with labels. You should leave a 50 pixel border around the outside of the drawing window. These gridlines go from -5 parsecs to 5 parsecs on the x and y axis.
- Write code to plot the stars onto the grid. For each star you should:
	- Use the star's Xg and Yg values. Ignore the Zg value when drawing the Star.
	- Draw a yellow cross at the star position on the grid
	- Draw a red circle with a *diameter* of the star's size.
	- Print the star name beside the star. The text should be left aligned horizontally and centred vertically.
- Write code so that you can
	- Click inside a single star and draw a yellow line to the mouseX and mouseY
	- When you click a second star, the yellow line should join the two stars and you should print the text:

	Distance from <Star1> to <Star2> is <?> parsecs

	At the bottom if the screen.

	You should calculate the distance between the two stars using the [dist](https://processing.org/reference/dist_.html) method in Processing. Use the star's Xg, Yg, Zg values to calculate the distance.