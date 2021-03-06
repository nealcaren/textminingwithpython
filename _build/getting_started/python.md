---
redirect_from:
  - "getting-started/python"
interact_link: content/getting_started/python.ipynb
title: 'Python 101'
prev_page:
  url: /placeholder
  title: 'Installation'
next_page:
  url: /getting_started/pandas
  title: 'pandas 101'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

*If you click the Interactive button above, you can run the code on this page and complete each of the exercises. If you click the Notebook button, you will be redirected to an interactive Jupyter notebook. Both of these options are powered by [Binder](https://mybinder.org).*

*The answers to each of the exercises can be revealed by selecting the plus button on the right side of the page below each exercise.*

## Python 101


This section introduces some of the most relevant aspects of working with Python for social scientists. This includes the different data types available and ways to modify them. 

In 2009, as part of his first State of the Union address, President Barack Obama said: 

> Let us invest in our people without leaving them a mountain of debt

To store that in Python, create a new variable called `sentence`



{:.input_area}
```python
sentence =  'Let us invest in our people without leaving them a mountain of debt.'
```


The text is surrounded by a single quote (`'`) on each side. 
To make sure that you typed the tweet correctly, you can type `sentence`:



{:.input_area}
```python
sentence
```





{:.output .output_data_text}
```
'Let us invest in our people without leaving them a mountain of debt.'
```



You can get almost the same response using the `print` function:





{:.input_area}
```python
print(sentence)
```


{:.output .output_stream}
```
Let us invest in our people without leaving them a mountain of debt.

```

The only difference is that the first response was wrapped in single quotes and the second wasn’t. As a side note, the single quotes weren’t because you put them there. If you used double quotes, Python would still show a single-quote.



{:.input_area}
```python
sentence =  "Let us invest in our people without leaving them a mountain of debt."

sentence
```





{:.output .output_data_text}
```
'Let us invest in our people without leaving them a mountain of debt.'
```



In addition to `'` and `"`, strings can also be marked with a `'''`. This last one is particularly useful when your text contains contractions or quotation marks. 



{:.input_area}
```python
new_sentence = '''Let's invest in our people without leaving them a mountain of debt.'''
```




{:.input_area}
```python
print(new_sentence)
```


{:.output .output_stream}
```
Let's invest in our people without leaving them a mountain of debt.

```

### Your turn
Create a new string called <code>food</code>  that is a sentence about your most recent meal. Display the contents of your new string. 




{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
food = 'My standard lunch is a veggie burrito.'
print(food)
```


{:.output .output_stream}
```
My standard lunch is a veggie burrito.

```

## Strings

Python has a few tools for manipulating text, such as `lower` for making the string lower-case.



{:.input_area}
```python
sentence.lower()
```





{:.output .output_data_text}
```
'let us invest in our people without leaving them a mountain of debt.'
```



This did not alter the original string, however.



{:.input_area}
```python
sentence
```





{:.output .output_data_text}
```
'Let us invest in our people without leaving them a mountain of debt.'
```



In Python, strings are immmutable, meaning once created, they can not be altered in place. We could store the results in a new variable.



{:.input_area}
```python
lower_sentence = sentence.lower()

lower_sentence
```





{:.output .output_data_text}
```
'let us invest in our people without leaving them a mountain of debt.'
```



### Your turn
Create a new, lower cased version of your <code>food</code> string.



{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python

lower_food = food.lower()

print(lower_food)

```


We can also `replace` words within the string.



{:.input_area}
```python
sentence.replace("nation", "country")
```





{:.output .output_data_text}
```
'Let us invest in our people without leaving them a mountain of debt.'
```



`replace` can also be used to remove text by not including anything with the replacement quotation marks.



{:.input_area}
```python
sentence.replace(".", "")
```





{:.output .output_data_text}
```
'Let us invest in our people without leaving them a mountain of debt'
```



As before, this does not alter the original string. If you wanted to save the string edits, you would need to create a new variable.








{:.input_area}
```python
edited_sentence = sentence.lower()
print(edited_sentence)
```


{:.output .output_stream}
```
let us invest in our people without leaving them a mountain of debt.

```

If you were doing a series of manipulations, you could reuse a varaiable name, although it is best practices to keep a version of the original string in case you ever need to go back to it. 



{:.input_area}
```python
edited_sentence = sentence.lower()
print(edited_sentence)

edited_sentence = edited_sentence.replace(".", "")
print(edited_sentence)
```


{:.output .output_stream}
```
let us invest in our people without leaving them a mountain of debt.
let us invest in our people without leaving them a mountain of debt

```

You can also stack multiple transformations together, although combining too many may make your code harder to follow.



{:.input_area}
```python
edited_sentence.replace(".", "").lower()
```





{:.output .output_data_text}
```
'let us invest in our people without leaving them a mountain of debt'
```



### Your turn
Create a new string called <code>boring</code> that removes the exclamation marks and capitalization from the sentence "Way to go!!!".  




{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
boring = "Way to go!!!".lower().replace('!', '')

print(boring)
```


## Slicing

If you had a very long text, such as the entire text of the State of the Union, you might only want to look at the first few characters. In Python, this is called by slicing.



{:.input_area}
```python
sentence
```





{:.output .output_data_text}
```
'Let us invest in our people without leaving them a mountain of debt.'
```





{:.input_area}
```python
sentence[0:20]
```





{:.output .output_data_text}
```
'Let us invest in our'
```



A slice is signaled with brackets (`[]`). The first number is the starting position, where 0 indicates the beginning. This is followed by a colon (`:`) and then the end position, which, in this case, is a 20. Note that this is splitting on characters, not words.

Here is a section from the middle of the string:



{:.input_area}
```python
sentence[20:32]
```





{:.output .output_data_text}
```
' people with'
```



For convience, if you ommit the number before the colon, it defaults to the string beginning.



{:.input_area}
```python
sentence[:40]
```





{:.output .output_data_text}
```
'Let us invest in our people without leav'
```



Ommitting the second number defaults to the end.



{:.input_area}
```python
sentence[40:]
```





{:.output .output_data_text}
```
'ing them a mountain of debt.'
```



Finally, negative numbers are interpreted as distance from the end of the string.



{:.input_area}
```python
sentence[-20:]
```





{:.output .output_data_text}
```
' a mountain of debt.'
```



### Your turn
Create a new string called `s` that contains `The weather is hot and humid today.` Find the slices for each of the following :
* "The w"
* "today."
* "hot and humid"




{:.input_area .hidecode}
```python
s = 'The weather is hot and humid today.'

print(s[:5])
print(s[-6:])
print(s[15:28])
```


{:.output .output_stream}
```
The w
today.
hot and humid

```

#### Numbers

We can also count the number of characters in a string with the `len` function.



{:.input_area}
```python
len(sentence)
```





{:.output .output_data_text}
```
68
```



In this case, Python returned an interger instead of string. This also can be stored in a variable.



{:.input_area}
```python
sentence_length = len(sentence)
```




{:.input_area}
```python
sentence_length
```





{:.output .output_data_text}
```
68
```



### Your turn
What is the length of <code>How many dogs do you own?</code>? Store it in a variable called <code>sl</code>.




{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
question = 'How many dogs do you own?'
sl = len(question)
print(sl)
```


Since the length of a string  is a number, we can do standard math operations with it.



{:.input_area}
```python
print(sentence_length * 3)
```


{:.output .output_stream}
```
204

```



{:.input_area}
```python
print(sentence_length / 2)
```


{:.output .output_stream}
```
34.0

```



{:.input_area}
```python
print(sentence_length + sentence_length)
```


{:.output .output_stream}
```
136

```

### Your turn
What is one-third the length of <code>sl</code>?



{:.input_area .hidecode}
```python
sl/3
```


As with strings, these can be saved in new variables.



{:.input_area}
```python
double_length = sentence_length + sentence_length

print(double_length)
```


{:.output .output_stream}
```
136

```

These same operators also work with strings.



{:.input_area}
```python
print(sentence * 2)
```


{:.output .output_stream}
```
Let us invest in our people without leaving them a mountain of debt.Let us invest in our people without leaving them a mountain of debt.

```



{:.input_area}
```python
print(sentence + sentence)
```


{:.output .output_stream}
```
Let us invest in our people without leaving them a mountain of debt.Let us invest in our people without leaving them a mountain of debt.

```

The operators can't be used to combine different data types, however.



{:.input_area}
```python
print("The sentence was " + sentence_length + "characters.")
```



{:.output .output_traceback_line}
```
---------------------------------------------------------------------------
```

{:.output .output_traceback_line}
```
TypeError                                 Traceback (most recent call last)
```

{:.output .output_traceback_line}
```
<ipython-input-63-9041347a8e39> in <module>
----> 1 print("The sentence was " + sentence_length + "characters.")

```

{:.output .output_traceback_line}
```
TypeError: can only concatenate str (not "int") to str
```


Conviently, the `str` function will convert an interger to a string.



{:.input_area}
```python
print("The sentence was " + str(sentence_length) + " characters.")
```


{:.output .output_stream}
```
The sentence was 68 characters.

```

I manually had to include the spaces before and after `sentence_length`. Otherwise, it all is smushed together. 



{:.input_area}
```python
print("The sentence was" + str(sentence_length) + "characters.")
```


{:.output .output_stream}
```
The sentence was68characters.

```

### Your turn

Print `The length of the word "hippopotamus" is [x].` where `[x]` is the length of the word hippopotamus  .




{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
l = len('hippopotamus')

print('The length of the word "hippopotamus" is ' + str(l) + '.')
```


## Lists

You can also `split` the sentence into a series of strings. By default, this splits based on spaces and other whitespace characters such as a line break (`\n`) or tab character (`\t`). 



{:.input_area}
```python
print(sentence.split())
```


{:.output .output_stream}
```
['Let', 'us', 'invest', 'in', 'our', 'people', 'without', 'leaving', 'them', 'a', 'mountain', 'of', 'debt.']

```

What is returned here is a third data type (the first two were strings and intergers) called a list. A list is enclosed in brackets (`[]`) and the items are seperated by commas. In this case each item is in quotation marks because they are all strings. Items in a list, however, can be of any sort.



{:.input_area}
```python
my_list = ['Speeches', 7, 'Data']
my_list
```





{:.output .output_data_text}
```
['Speeches', 7, 'Data']
```



While `len` returned the number of characters in a string, it returns the number the items in a list.



{:.input_area}
```python
len(my_list)
```





{:.output .output_data_text}
```
3
```





{:.input_area}
```python
sentence_length = len(sentence.split())
sentence_length
```





{:.output .output_data_text}
```
13
```



In the second example, the list created by `sentence.split()` is not saved in any way; only its length.

#### Your turn
Create a list called **ate** that includes at least three things you ate today. Use `len` to count the number of items in the list.






{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
ate = ['apple', 'dosa', 'pizza slice']

print(len(ate))
```


Like, strings, lists can also be sliced. The first three items of a list:



{:.input_area}
```python
words = sentence.split()
print(words[:3])
```


{:.output .output_stream}
```
['Let', 'us', 'invest']

```

We can also extract specific items from a list by their position. As it did with strings, slicing in Python starts with 0.



{:.input_area}
```python
words[0]
```





{:.output .output_data_text}
```
'Let'
```



The third word:



{:.input_area}
```python
words[2]
```





{:.output .output_data_text}
```
'invest'
```



The fifth word from the end:



{:.input_area}
```python
words[-5]
```





{:.output .output_data_text}
```
'them'
```



The last two words:



{:.input_area}
```python
words[-2:]
```





{:.output .output_data_text}
```
['of', 'debt.']
```



### Your turn
Display the first two items of your **ate** list. What is the last item?




{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
print(ate[:2])
print(ate[-1])
```


{:.output .output_stream}
```
['apple', 'dosa']
pizza slice

```

Slicing a list returns a list. If you ask for the first three items, you will get a list made up of those items. In contrast, if your request a specific location, such as `words[2]`, Python returns the specific object stored in the place, which may be a string, number, or event an entire list. 

Unlike a string, lists are mutable. That means that we can remove or as is more frequently the case text analysis, add things to it. This is done with `append`.



{:.input_area}
```python
male_words = ['his', 'him', 'father']
male_words.append('brother')
print(male_words)
```


{:.output .output_stream}
```
['his', 'him', 'father', 'brother']

```

Since `append` is changing `male_words`, we do not want to use an `=`. The Python interpreter is editing our original list but not returning anything.



{:.input_area}
```python
not_going_to_work = male_words.append('brother')
print(not_going_to_work)
```


{:.output .output_stream}
```
None

```

Lists can be also be combined using `+`.



{:.input_area}
```python
gendered_words = male_words + ['her', 'she', 'mother']
print(gendered_words)
```


{:.output .output_stream}
```
['his', 'him', 'father', 'brother', 'brother', 'her', 'she', 'mother']

```

As note above, the items in a list can include a variety of data types. This includes lists.



{:.input_area}
```python
gendered_lists = [ male_words ,  ['her', 'she', 'mother'] ]
```


Note the two closing brackets next to each other. The first closes the list that ends with 'mother' while the second closes our `gendered_lists`.



{:.input_area}
```python
len(gendered_lists)
```





{:.output .output_data_text}
```
2
```



`gendered_lists` has a length of two because it contains just two items, each a list of varying lengths.



{:.input_area}
```python
print(gendered_lists)
```


{:.output .output_stream}
```
[['his', 'him', 'father', 'brother', 'brother'], ['her', 'she', 'mother']]

```

### Your turn
Add three more items to your `food` list. Use `append` for one. 
For the other two, places them in a list and then combine the two lists. 



{:.input_area .hidecode}
```python
# solution
```


### Dictionaries

A fourth useful data type is a dictionary. A dictionary is like a list in that it holds multiples items. The items in a list can be identified by their position in the list. In contrast, the values in a dictionary are associated with a keyword. The analogy here is a to a physical dictionary, which has a list of unique words, and each word has a definition. In this case, the entries are called keys, and the definitions, which can be any data type, are called values. 

Alternatively, you can think of a dictionary as a single row of data from a dataset, where the keys are the variable names.



{:.input_area}
```python
respondent = {'sex'   : "female",
              'abany' : 1,
              'educ'  : 'College'}
```


Dictionaries are surrounded by curly brackets (`{}`). Each entry is pair consisting of the key, which must be a string, followed, by a colon and then the value. Like in a list, entries are seperated by commas.



You can access the contents of a dictionary by enclosing the key in brackets (`[]`).



{:.input_area}
```python
respondent['sex']
```





{:.output .output_data_text}
```
'female'
```



If the key is not dictionary, you will get a `KeyError`.



{:.input_area}
```python
respondent['gender']
```



{:.output .output_traceback_line}
```
---------------------------------------------------------------------------
```

{:.output .output_traceback_line}
```
KeyError                                  Traceback (most recent call last)
```

{:.output .output_traceback_line}
```
<ipython-input-10-4da2e0df882d> in <module>
----> 1 respondent['gender']

```

{:.output .output_traceback_line}
```
KeyError: 'gender'
```


You can inspect all the keys in a dictionary, in case you forgot or someone else made it.



{:.input_area}
```python
respondent.keys()
```





{:.output .output_data_text}
```
dict_keys(['sex', 'abany', 'educ'])
```





{:.input_area}
```python
len(respondent.keys())
```





{:.output .output_data_text}
```
3
```



Dictionaries are mutable, so we can change the value of existing keys, remove keys, or add new ones.



{:.input_area}
```python
respondent['race'] = 'Black'

print(respondent)
```


{:.output .output_stream}
```
{'sex': 'female', 'abany': 1, 'educ': 'College', 'race': 'Black'}

```



{:.input_area}
```python
respondent['abany'] = 'Yes'

print(respondent)
```


{:.output .output_stream}
```
{'sex': 'female', 'abany': 'Yes', 'educ': 'College', 'race': 'Black'}

```

### Your turn
Add a new key to the dictionary called `age` with a value of 37. Confirm that you did it correctly by displaying the value of `age`.





{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
respondent['age'] = 37

print(respondent['age'])
```


As noted above, while the keys have to be strings, the values can be any data type. You could add the ages of the respondent's children as a list.



{:.input_area}
```python
respondent['children ages'] = [3, 5, 10]

print(respondent)
```


{:.output .output_stream}
```
{'sex': 'female', 'abany': 'Yes', 'educ': 'College', 'race': 'Black', 'age': 37, 'children ages': [3, 5, 10]}

```

## Spaces


Within the Python community, there are strong norms about how code should be written. Many of these are centered around have code be readable, both by others and by your future self. As a trivial example, `2+2` is allowed, by is almost always written `2 + 2`. Likewise I defined my respondent dictionary with plenty of white space in order to maximize readability.



{:.input_area}
```python
respondent = {'sex'   : "female",
              'abany' : 1,
              'educ'  : 'College'}
```


This is identical to:



{:.input_area}
```python
respondent={'sex':'female','abany':1,'educ':'College'}

```




but putting it all on one line obscures the logic of the dictionary. In this case, what is a key and what is a value is quite clear in the first version, while distinguishing between the two is more problematic in the single-line version. 





{:.input_area}
```python
r2 = {'sex':'male',   'abany':1, 'educ':'College'     }
r3 = {'sex':'female', 'abany':0, 'educ':'High School' }
r4 = {'sex':'male',   'abany':0, 'educ':'Some College'}
```




{:.input_area}
```python
respondents = [respondent, r2, r3, r4]
```




{:.input_area}
```python
respondents
```





{:.output .output_data_text}
```
[{'sex': 'female', 'abany': 1, 'educ': 'College'},
 {'sex': 'male', 'abany': 1, 'educ': 'College'},
 {'sex': 'female', 'abany': 0, 'educ': 'High School'},
 {'sex': 'male', 'abany': 0, 'educ': 'Some College'}]
```



This is now looks a lot like the common data format JSON!

### Loops



{:.input_area}
```python
for person in respondents:
    print(person['educ'])
```


{:.output .output_stream}
```
College
College
High School
Some College

```



{:.input_area}
```python
for item in [1,2,'bobcat']:
    print(item)
```


{:.output .output_stream}
```
1
2
bobcat

```

#### Your turn

Loop over the items in your `food` list. For each item, print its length.





{:.input_area}
```python
 
```




{:.input_area .hidecode}
```python
# Answer
```




### Functions

For those who come from Stata or R background, one of the more striking aspects of Python code is the frequency of user defined functions. They are deployed not just for things where you think there should be a function, like counting words in a sentence, but also for highly-custom situations, such as scraping the contents of a particular web page. This style of programming, with many small functions, tends to make code more readable easier to debug than code written in a more traditional social science style.

A standard function has three parts. First the function is named and defined. Subsequent line or lines actually do the thing. Finally the results are returned.  

A trivial function that returns the `Hello!` might look like:



{:.input_area}
```python
def make_hello():
    word = 'Hello!'
    return word
```


Of note, `def` signals that your are defining a function. This is followed by the name of the function. In this case, `make_hello`. Since this function doesn't take any arguments, such as accepting a variable to modify or have any options, it is followed by `()`. The first line ends with a colon.

All subsequent lines are indented. The second line creates a new string variable called `word` which contains `Hello!`. The third and final line of the functions returns the value stored in word. 



{:.input_area}
```python
make_hello()
```





{:.output .output_data_text}
```
'Hello!'
```



More commonly in text analysis, a user-defined function modifies an existing string. In this case, the variable name that will be used within the function is established within the parenthesis on the opening line. 

A second trivial function takes a text string and returns an all-caps version. 



{:.input_area}
```python
def scream(text):
    text_upper = text.upper()
    return text_upper
```




{:.input_area}
```python
scream('Hi there!')
```





{:.output .output_data_text}
```
'HI THERE!'
```



The `text` and `text_upper` variable only exist within the function. That means that you can pass a variable not called `text` to the function.



{:.input_area}
```python
scream(sentence)
```





{:.output .output_data_text}
```
'LET US INVEST IN OUR PEOPLE WITHOUT LEAVING THEM A MOUNTAIN OF DEBT.'
```



It also means that everything but the returned `text` disappears.



{:.input_area}
```python
text_upper
```



{:.output .output_traceback_line}
```
---------------------------------------------------------------------------
```

{:.output .output_traceback_line}
```
NameError                                 Traceback (most recent call last)
```

{:.output .output_traceback_line}
```
<ipython-input-37-9374ae9251ac> in <module>
----> 1 text_upper

```

{:.output .output_traceback_line}
```
NameError: name 'text_upper' is not defined
```


It is a good idea to include a comment within the function that explains the function. This is helpful for other people reading your code and when you return to your own code months and days later.



{:.input_area}
```python
def scream(text):
    '''Returns an all-caps version of text string.'''
    text_upper = text.upper()
    return text_upper
```


#### Your turn

Make a function called `whisper` that replaces all exclamation marks with a period and returns a lower case version of a string. Test it out.



{:.input_area .hidecode}
```python
def whisper(text):
    ''''''
    
    return quite_text
```

