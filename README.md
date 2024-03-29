# Aaron's Projects
 This Github is used to display different elements of my coding ventures specifically specific projects that show different skills, it will
 include screenshots of projects along with explanations of the program and my contributution to it. Additionally in the github there is access 
 code that isn't proprietory. 

## Number Gussing Game
The First Project that is shown is a simple number guessing game where the user tries to determine a number from 1-100.
They do this by guessing numbers after which they are told higher or lower to inform their next guess.
This program was developed using a mixture of HTML, CSS, PHP and Javascript code which was written by me.

An example of the session code implementaion would be:
```html
    <p>You won!</p>
    <p>The number was: <?php echo $_SESSION["gameID"]?></p>
    <p><?php echo "You guessed the number in " . $_SESSION["guesses"] . " guesses!"?></p>
```

![NewUser](https://user-images.githubusercontent.com/74752965/162883924-6bf21820-5691-4bb9-ae46-81b8d6c8cd9e.PNG)

This screenshot shows the login page, this login was connected to a databasd of usernames and hashed and salted
passawords. This allowed me to have a secure login for many players

![numGuessing](https://user-images.githubusercontent.com/74752965/162883942-ac6a2ac5-5c8a-48a6-be24-0b571fce623c.PNG)

This screenshot shows the signup page, new usernames were required and the passwords and usernames were stored in the
database with the passwords obviously being hashed and salted.

![scoresNumber](https://user-images.githubusercontent.com/74752965/162883964-853788ca-7ee4-4409-86ea-26ef9581d0fb.PNG)

Here is a display of the information, it showed highscores across all accounts and allowed people to compare their highscores
to one another

### Takeaways
The most interesting part of working on this project for me was dealing with php. Having no experience with the language
it was a struggle to make everything work correctly, however it was a great experience that helped me learn how to 
teach myself a language on the fly and implement it in a away to achieve my goals.

## Hangman Game
The second project on this readme is a simple hangman game, it used csharp game logic alongside razor pages and
websockets in order to create an asyncronous playing experience

![LoginHangman](https://user-images.githubusercontent.com/74752965/162883997-b6547089-d6f2-4230-b099-9847a5cc80cb.PNG)

The login similiar to that of the number guessing game had its own database that allowed users to store usernames and
secure passwords

![hangmanGame](https://user-images.githubusercontent.com/74752965/162884008-2cd98171-4cb0-4b50-905f-1e1d53c975f7.png)

The login page likewise was secure and enforced new usernames to be created, with passwords being hashed and salted.

![hangmanScore](https://user-images.githubusercontent.com/74752965/162884018-a673e999-7165-4b04-b707-3e321839f15f.png)

This page showed highscores amongst all accounts similar to that of the number guessing game.
```c#
if (game.CheckResult())
{
    Array.Clear(buffer, 0, buffer.Length);
    for (int i = 0; i < gameWinMsg.Length; i++)
    {
	buffer[i] = (byte)gameWinMsg[i];
    }
    SessionVar.Score = game.GetLives();
} 


await webSocket.SendAsync(new ArraySegment<byte>(buffer, 0, buffer.Length), result.MessageType, result.EndOfMessage, CancellationToken.None);

result = await webSocket.ReceiveAsync(new ArraySegment<byte>(buffer), CancellationToken.None);
```
### Contributions

This project was done in a group of 4, I was principally assigned to working with the game logic for the hangman game, which
was the majority of the c# code used. After a teammember had some difficulties, I was also key in implementing the websockets
necessary for the asyncronous enviornment. The websocket was where we had the most issues with in the project and the above code was what we
ended up using to achieve our goal.

### Technologies
.NET 6, SQLite, HTML, Javascript

## Speed Game

The Speed Game was an asyncronous project that used a WebApp and Signal R in order to allow two different people to play the game
of speed against one another.

![2personAsyncSpeedGame](https://user-images.githubusercontent.com/74752965/162884058-f3c258d7-1870-44ec-a10f-47adfc85296f.PNG)

This Screenshot shows the game at the start, when both players had yet to play. Everything functioned correctly in this program
with the button being used to reshuffle the middle piles indefinitely untill there was a clear winner

![winSpeed](https://user-images.githubusercontent.com/74752965/162884066-9495058d-8944-405c-b3a5-9fb1048f7fc2.PNG)

This screenshot displays the win and loss screen and the option of the players to hit playagain and return to a new game state.
```c#
if (ExStack1.Count == 0)
{
    Stack<Card> shuffleStack = new Stack<Card>();
    int count = PlayStack1.Count();
    for (int i = 0; i < count; i++)
    {
        shuffleStack.Push(PlayStack1.Pop());
    }
    count = PlayStack2.Count();
    for (int i = 0; i < count; i++)
    {
        shuffleStack.Push(PlayStack2.Pop());
    }

    count = (shuffleStack.Count() / 2) - 1;
    for (int i = 0; i < count; i++)
    {
        ExStack1.Push((Card)shuffleStack.Pop());
        ExStack2.Push((Card)shuffleStack.Pop());
    }
    PlayStack1.Push(shuffleStack.Pop());
    PlayStack2.Push(shuffleStack.Pop());
}
else
{
    PlayStack1.Push(ExStack1.Pop());
    PlayStack2.Push(ExStack2.Pop());
} 
```
The above code is part of our CardFlip method, which was able to completely rearrange all of our elements in the program.
The use of a stacks allowed us to keep an easy to use framework when working with a deck of cards and greatly added to 
the efficiency of the program.

### Contributions
My contributions were great in this project, with me developing the vast majority of the game logic, including the javascript
and C# programming, and fixing the majority of the issues. I also added mobile capabalities for the program to handle different
devices.

### Technologies
The technologies used for this program were C# specifically .NET 6, Signal R, Javascript, and Bootstrap
## Scholarship App
For Weber State's Computer Science department some years ago there was a capstone project that developed the scholarship portal
for computer science. We were tasked with upgrading it from netcore 2.1 to netcore 6.0 in addition to fix some bugs that had
surfaced over the years. My main part of the project along with assisting with the other issues was to develop an entity database
framework. This allowed databases to be created on startup and was a far more efficient way to manage the database then it would have
been before.

