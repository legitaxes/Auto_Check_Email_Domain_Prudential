# Auto_Check_Email_Domain_Prudential
__TLDR: This program uses UIPath to select and highlight correct email domains in the excel sheet__

## Some information about UIPath
- The program is not exactly very practical to use for tasks that are very miniscule in 'weight' 
- There are quite a bit of limitations in UIPath and many workarounds has to be done on it for it to work properly
- UIPath is only highly recommended for tasks such as this; whereby it is extremely mundane and repetitive

## What Does it Do?
- Start up a form for the user to select the countries they want to be filtered. 

![image](https://user-images.githubusercontent.com/73578449/116346981-e84fe480-a81d-11eb-8e0d-d39432627462.png)

- Filter through the selected countries one by one

- Search and highlight the correct email domain addresses for each selected countries to red text.
  - This is done to check whether the email address entered by the participants are correct based on the parameter list

- It takes about 5 minutes or so for the process to check through the selected countries

- While the process is running, it is __not recommended__ to touch the mouse or keyboard as it may mess up the process.

- If Philippines has been selected, it will prompt and remind the user to check through the email addresses with gmail and yahoo’s `pluk`

## Pros
- With just an input of the initial form that starts up upon initialization, the bot will be able to check through selected countries only.

- You are able to do something else in real life while this process is running and doing its job

- It makes 0 mistakes during the process. It will never fail you when checking the email domains.

- Fully customizable selection of countries (this was not a feature from before)

- Able to fill dummy data to prevent possible crashes [WIP]

- Able to select countries that are not yet filtered

- Easy to add new countries and parameters of email if needed [WIP: Instruction Journal]

## Cons
- Program will crash in 2 scenarios (I have tried my best to fix it and have workarounds for it)


__Scenario 1__


The selected country only have one row of data. And it does not proceed to click on the filter button after searching for the first email domain search.
Example: 
![image](https://user-images.githubusercontent.com/73578449/116346260-79be5700-a81c-11eb-8b8e-9ce809a84fd3.png)

In this example, Thailand only has one email address. After filtering for the first search result, the program will stop working.


__Solution: A simple fix can be done by entering dummy data for all the countries before the program starts__
1. Input the dummy data from the file “dummy_data.txt” at the last line of the data
2. Copy the text in the file 
3. Paste the text at the last line of the table like so:
![image](https://user-images.githubusercontent.com/73578449/116346367-af634000-a81c-11eb-8fc5-078c980881b5.png)


__Scenario 2__


Do not change the `select colour` button. This may sound confusing.. But I’ll do my best to explain.


In MSExcel, if you changed colour using the font colour picker, it will change the name of the button
![image](https://user-images.githubusercontent.com/73578449/116346431-d588e000-a81c-11eb-91ee-e6aa1a472652.png)

For example, the name of the button if you did not change the colour is `default red colour font`. But if you picked another colour, the name of the button will change. 

Let’s say you picked the colour blue, the name of the button will change to `blue colour font`

Even if you change the color back to red, this will not fix it. The button will instead be renamed to `red colour font` and not `default red colour font`

__A simple fix would be to re-open the file but have the colour be red before closing. This will then change the name of the button to `default red colour font` again when you re-open excel__
UIPath is very specific on the names of the buttons it clicks on and this is one prime example of the limitations of UIPath.

## More Cons
- The process will not be able to stop once it has started. There is no ‘fail-safe’ button to stop the process. The only solution is to try your best to reach for the stop button once it is running. 
  - _Tab into UIPath window and press `f2`_
 ![image](https://user-images.githubusercontent.com/73578449/116347332-95c2f800-a81e-11eb-9609-faec71737c62.png)


- While the process is running, you cannot touch the mouse or keyboard as it may mess up the process.
- The speed of the process is dependent on your CPU and Memory. 
- It may be slightly slower than doing it normally, but it has an accuracy of 100% when checking for email domains.
- It is not able to check for exception in certain cases. May have to check manually if there are any. 
