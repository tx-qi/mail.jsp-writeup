# Intro

Hi, this is txqi. The task given is try study the sample to answer the question.

Tools used:
 - Sample (mail.jsp)
 - Cyberchef
 - related online tools 

## Kudos

 - Allah
 - Fareed (Question Maker, Helper)
 - Afif (Helper)

## Starting
![](/res/Capture.PNG)
By opening the sample (careful, dont execute), right on the bat we know that it is not even written in jsp.


## 1) Identifying language
![](/res/Capture2.PNG)
By reading the prior lines, we know that it try to create a variable, following with command   IEX. Quick google shows that it is a command for powershell 
![](/res/Capture3.PNG)


## 2) Running the sample
![](/res/Capture4.PNG)
As we know it is file from poweshell, either we rename the file to ps1 and run it in sandbox, or run the known function@variable manually in powershell. In this case, Ill go with the latter.

![](/res/Capture5.PNG)
As you can see, after the run the, we can see the code of the sample. However, it is very gibberish. But, upon closer inspection, there is something that we can read(?)

![](/res/Capture6.PNG)
We can see that the character is reversed. 'ecalper' is 'replace' and 'rahc' is 'char'. Do you smell something? It mean that we must fired up the kitchen!

## 3)Cooking with CyberChef
Here is most of the deobfuscation occured
![](/res/Capture7.PNG)
Now, the code became little bit clearer. It is readable. However there are some obfuscation by using:

 - repeated pattern
 -  "+" sign

"+" sign is not a major problem as we can read easily, however repeated pattern make the code harder to understand. It hard to determine whether is it real phrase of argument/variable or it is mixed with some bs words.

Luckily, the sample itself must remove the obfuscated word in order to run properly. So we just have to find the function/command that removed repeated pattern. You can manually read and remove repeated pattern,but it is truly inefficient.

![](/res/Capture8.PNG)
There we go, now, we just have determine what is the repeated words.
As we can see in the code, it will replace certain phrase/word with other  phrase/or word.

![](/res/Capture9.PNG)
The way i determine what word it will replace is by echo manually in poweshell (Damn, i hate this.But it is better than manually determine the character one by one)

![](/res/Capture10.PNG)
here, we can see, the first is words contain in the code it will be and the second one is what it'll be subtitute. 

## Final
![](/res/Capture11.PNG)
Now, the sample code can be read a little bit easily However there are some part that is a little bit hard to understand,I'll leave it up to you to solve it yourself lol.Happy answering 
