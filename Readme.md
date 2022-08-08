# Bot to add commits in GitHub
**Idea from Akshay Saini**

**This is only for educational propose.
That's why all the commits made from this repo are public in my profile.**

## Main Idea
The main idea is that, we are making commits in the past date. Whenever we make any commits to any repo, GitHub tracks them by associating those commits with a specific time(i.e. the date and time when we created that commit). So, here we are manipulating that time to some past date, so we can make commits in the past. And when we push those commits with modified date and time, GitHub populates the contribution graph based on those past dates.

**Does this work for future date as well?**<br>
**If you are curious do try it out and let me know**

## Coding approach 
- As we need to manipulate the date, we will use a package called **[Moment](https://www.npmjs.com/package/moment)**. It is a JavaScript library for parsing, validating, manipulating, and formatting dates.<br>
- Next, we will use a package called **[simple-git](https://www.npmjs.com/package/simple-git)**. It helps us to run git commands like push, commit in nay node.js applications.<br>
- We will also use a **[jsonfile](https://www.npmjs.com/package/jsonfile)** package to write those manipulated date into a json file. Once we write those random dates into the json file, then we can commit them in GitHub. We will add that file into the `.add()` method from simple-git and will make the commit using `.commit()` method.
- Last package we will be using is **[random](https://www.npmjs.com/package/random)**. We will use this package to generate random integers which will be our random dates.<br>
#### Check the comments in [index.js](https://github.com/prajun7/github-commit-bot/blob/main/index.js) file for better undestanding.

## Installation
Clone and fork the repository to make the changes in your local system.
```git-bash
git clone https://github.com/prajun7/github-commit-bot.git
cd github-commit-bot
```
Now this command creates a directory named node_modules and installs all the required packages in it.
```javascript
npm install
```
Finally, run the project to see what the moment package does.
```javascript
node index.js
```
You can see the commit date in terminal.

## Make design and text in your graph

```javascript
subtract(year, "y");
```
year here represents the year to start the commits. You can go, 1 year back from today or 2 years and so on

```javascript
add(week, "w");
add(days, "d");
```
#### Here you can modify the weeks and days to make commits at the specific point in the graph. Weeks are the x-Axis and days are the y-Axis.<br>
#### To modify weeks(x-Axis), you nned to change this variable 'x' [here](https://github.com/prajun7/github-commit-bot/blob/main/index.js#L23)<br>
#### To modify days(y-Axis), you need to change this variable 'y' [here](https://github.com/prajun7/github-commit-bot/blob/main/index.js#L24)<br>
#### The top left corner of the contribution graph has the (0,0) coordinates.<br>
#### So, based on this information you can make commits at a specific point in the contribution graph and can make some beautiful pattern or text.<br>
