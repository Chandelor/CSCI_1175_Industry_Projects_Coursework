# Hangman Game

## Synopsis
This project is based off of a fairly well known game called hangman where a player will be given a random word that they don't know and will need to guess based off of the given letter count. My project re creates this game and adds it's own custom blitz mode where the player will specify a time limit and try to guess as many 4 letter words as they can to get a high score.

## Motivation
My main motivation towards working on this project was to understand more about advanced javafx uses and with enough remaining time to work more with server/client communtions.

## How to Run
To run this Hangman game you will need to download the project folder and import it to your code editors workspace. After that's been done, all that's left is to run the program since all the necessary files are included in the project folder.
[Game Image](GameImage.png)

## Code Example
I thought this method is pretty cool because it sets up the alphabet in 2 lines as Labels that you can click on, before coding this the only clickable thing I had done was just some regular buttons, using this method as well had solved some possible bugs that I could have had with the code.
```
	public void availableCharacters(String gameType) {
		HBox line1 = new HBox(13);
		HBox line2 = new HBox(13);
		VBox allLines = new VBox(2);
		
		line1.getChildren().clear();
		line2.getChildren().clear();
		allLines.getChildren().clear();
		line1.setAlignment(Pos.CENTER);
		line2.setAlignment(Pos.CENTER);
		
		Label[] characters = new Label[26];
		for(int i = 0; i < 26; i++){
			char temp = (char) (i + 65);
			characters[i] = new Label();
			characters[i].setUnderline(true);
			characters[i].setText(String.valueOf(temp));
			characters[i].setFont(new Font(20));
			
			if (i <= 12) line1.getChildren().add(characters[i]);
			else if (i > 12) line2.getChildren().add(characters[i]);
		}
		
		allLines.getChildren().addAll(line1, line2);
		display.getChildren().addAll(allLines);
		
		characterClicked(characters, line1, line2, gameType);
	}
```

## Tests
The only method that is available for testing is the grabWord method in the wordManager class. It receives a letter count and file path in the form of a String to find a random word from the given txt file. The word selected at random and only returned if it matches the given letter count. To test the method I've provided a junitTest.txt file with the text "HelloWorld". Sending an int of 10 and the correct file path and the JUnit test will work correctly.

## Contributors
I wasn't able to find the creator of the .gif that I used on my main menu, but besides that everything else was created by myself.
