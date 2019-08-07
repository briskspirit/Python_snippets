# Python_snippets

+++ https://github.com/vinta/awesome-python - good libraries 

* **:
- conda install module_name or pip install module_name

Basic:
- 1*1 1-1 1+1 1/2 2**2 2**0.5
- += -= *= /= you can use this to skip s = s + 5 to s += 5 (so replacing with result)
- 10 % 3 returns 1 (modulo, remainder after division) so 4 % 2 returns 0
- comments are created with # char or tripple quotes ''' here is the comment '''
- type() function to check object type in python. (bool,str,dict,list and etc)
- cast variable to different type through: list() str() int() dict(), tuple() and etc (not all can be converted!!). Casting helps to insure that exact type will be addressed
- isupper() and .islower() returns boolean
- \ in the end of the line brakes it, so we can continue long statements or if conditions on the next line
- del l     - will delete our object from memory(in this case it is our list for example, can be ANY obj!)
- exit()    - built in function to break your python execution(?)
- if function returns iterator - you can cast it as list()
- max() or min()    - returns max or min value from given list
- import random      and then random.randint(min,max)
- #! python3   - tells in the beginning of the line which version to use
- DO NOT USE PRINT FOR DEBUG MESSAGES! Instead use import logging (read at bottom of this file)
- import sys
sys.argv - list of passed arguments to our .py file. [0] index will contain self filename
sys.getsizeof(object) - will return object size(in memory(?)) in bytes.
---
- sorted() will return list sorted, but won't change it itself.
- object that is started with _ (underscore) means protected.
- _ (underscore or double __) can be used as variable name, that is won't be never used(throw away value) (like temp/trash var when some func needs to return values that you don't need!)
- preserve two lines between functions when writing them
- __name__ - variable that contains name of the current module. In case of our main program will return __main__
- chr(9) - will convert to char(\t) by its ascii table char number
- help() - show help for object
- if __name__ = '__main__':  # - so we are checking the scope. If .py run itself - do code. If it was imported as a module - don't run.
- print(string, output) - if output is skipped - will out to default output(console), print(string, file) will output to file(should object type file, not just path!)!  

-------------------------------------------------------------

Print Formating:   (https://pyformat.info)
NEWEST METHOD:
print("some text {} here, cos it {} be more {}".format('place', 'is', 'convenient'))
---
- print('Hi \n new string \t and Tab space')
- print('my variable content: %s' %(s))    (%s transforms to string inside)
- print('my variable content: %s' %(123)) Converts to string
- print ('floating point var cut of decimal: %1.2f' %(13.13566)) returns with 13.14 float . 1 tells how many max digits can be(leave space) and 2 tells how many digits should be!
- print('my variable content: %s, second: %s, third: %1.2f' %('one', 'two', 12.324524))
- print('First: {x} , Second: {x}'.format(x = s)) or print('First: {x} , Second: {x}'.format(x = 'word')) or print('First: {y} , Second: {x}'.format(x = 'word', y = 'fine'))

----------------------------------------------------------
Advanced Numbers:

hex() , bin() - will convert to hex or binary.
pow(2,4) is same as 2**4
pow(2,4,3) is same as 2**4 mod 3
abs() returns absolute value
round(3.1) returns rounded value. returns floating point
round(3.141592,2) returns 3.14
-------------------------------------------------------------

Strings:
- s = 'string'
- s = r'string'   - raw string, where is escape chars \ is treated as regular chars. Mostly used in regular expressions!
- all string variables are immutable in python!, meaning you can't use indexing to change individual elements of a string, but you can concatenate strings(add) with + sign or reassining.
- strings can be multiplicated with *. Like s='z' s*10 returns zzzzzzzzzz
- len('Hello') - return string length
- s = 'Hello' s[0] return H by index (indexing)
- s = 'Hello' s[1:] return ello or s[:3] return Hel by slicing string (from(including) and up to(not including)). Can be used in reverse: s[-1] returns o . s[:-1] returns Hell (everything, exept last letter)
- s[::1] in this case we are specifying frequency(so grab each char from start to end) or s[::2] - grab each 2nd char from start to end.
- s[::-1] telling reverse stepsize, so all string will be reversed
- common string methods are: .upper() .capitalize() .lower() .split()(return list) .split(e)(returns list which is split on elements by 'e': ['H','llo'])

Andvanced Strings:

s = 'hello world'

s.capitalize() 
s.upper()
s.lower()
s.title() #The Title Cased String
s.count('o') returns quantity 2
s.find('o') returns index 4
s.center(20,'z')  returns zzzzhello worldzzzzz    (so centers your string between z and overall length is 20)
.strip() will cut all whitespaces, \n \t etc..
---
s = 'hello'
s.isalnum() #checks if all is alphanumeric
s.isaplpha() #checks if all is alphabet
s.isdecimal() # checks for digits
s.islower() #checks if lowercase
s.isspace() #if we have spaces
s.istitle() # if title cased?
s.isupper() #
s.replace('one','two',2) #Replace first two instances of 'one' with 'two'
s.endswith('o') # check if last char is equal to 
''.join(c for c in data if c.isdigit()) #removes all non-digits
''.join(c for c in data if c.isalpha()) # removes all non-alphabetic

s.split('e') #returns ['h','llo']
s.partition('e') #returns ('h','e','llo')   and checks only for first instance!!
----
import fnmatch # full name match module. returns list of names that will match pattern. Input should be a list(?)!

l = ["some 1 string","2 string","some 3 list"]
k = "*some*"
fnmatch.filter(l,k)
# will return ['some 1 string', 'some 3 list']
----------------------------------------------------------
StringIO module - implements in-memory file-like object. Or faster cStringIO is present. Can be used to read/scrapping strings from the web.

import StringIO

message = 'This is just a normal string'

f = StringIO.StringIO(message)

f.read()    # so we can perform all files operations and methods like .read .write .seek(0)
-------------------------------------------------------------

Lists(like array?):
- s = [1,2,3] or even s = ['string', 123, 12.335] - different object types!
- len(s) Counting number of objects inside the list
- s[0] returns first element by index
- list takes all index and slicing options of string like [1:] etc.
- concatenate list as s + 'newobject' will add to list or concatenate lists OR to use method .append('') to add
- s = ['a', 'x', 'w', 's'] common methods .count() .reverse() 
- .pop() returns last object and removes it! OR .pop(1) returns second element and removes it!
- s_1 = [1,2,3] s_2 = [4,5,6] s_3 = [7,8,9]       matrix = [s_1,s_2,s3]
- matrix[0] returns [1,2,3] OR matrix[0][0] returns 1
- first_col = [row[0] for row in matrix] will return fist columm of our matrix [1,4,7]


Advanced Lists:

l = [1,2,3]

l.append(4) # will append an item 4 to list
l.count(1) # how many 1 is on our list
x = [1,2,3]
x.append([4,5])  #returns [1,2,3,[4,5]]
x.extend([4,5])  #returns [1,2,3,4,5]
l.index(2) # will return index 1 , if is not in list - will get ValueError
l.insert(index,value) #insert value to the index place and move later elements to the right
ele = l.pop() # will cut last element from list and move it to ele , or you can set which index to pop(remove)
l.remove('value') # will remove value by it's name, not by index. Will remove only the first accurance!
l.reverse()  # will reverse your list permanently
l.sort() # sorts your list in place

-------------------------------------------------------------

Dictionaries:
- d = {'key1':'value1','key2':'value2'}      d['key1'] returns 'value1'
- d['key1'] returns string, so we can work with it like with string: d['key1'][0] will return 'v'
- nested dictionaries: d = {'key1':{'subkey1':1,'subkey2':2},'key2':{'subkey3':3,'subkey4':4}} with indexing to take d[key1][subkey2] will return 2
- method .keys() will return the list of all keys , .values() will return list of values. BUT! sequences will NOT be exact like by index!
- .items() will return key to value tuples
- we can but lists inside dictionaries as any other object
- .pop('somekey', None) - will pop key and value from a dictionary and will return a value if key is exists on will return None if it is not there
- creation of new keys through assignment d['newkey1'] = 'newvalue'
- DICTIONARIES DO NOT RETAIN ORDER!

Advanced Dictionaries:

d = {'k1':1,'k2':2}

{x:x**2 for x in range(10)} # will create dictionary from dictionary comprehention
{k:v**2 for k,v in zip(['a','b'],range(2))} # will return {'a':0,'b':1}

- dictionaries can be iterated through .iter methods (python2?)
-------------------------------------------------------------

Tuples:     (they are like lists, but are immutable!)
- t = ('one',2,'three')
- len(t) how many elements
- any type of object
- indexed as lists t[0], slicing and etc
- t.index('three') returns 2
- t = (1,1,2,3)   t.count(1) returns 2
- NOT ALLOWED: t[0] = 'newvalue'
- WHAT THEY ARE FOR?? When you need immutability !!! (example: calendar dates and etc)
- we can make math in form of tuple unpacking: a,b = a+b, a  (Same as a = a+b and b = a but simulaniosly!!(Search for fibonacci here!))

-------------------------------------------------------------

Files:

NEW TECHNICS TO WORK WITH FILES:

with open('test.txt', 'w') as test_file:
  #do files operation. with operator will close the file automaticaly.

---

- (JUPITER ONLY MAGIC) : %%writefile test.txt to create file from Jupiter without notepad

- in windows path backslashes should be escaped or string should be raw r'path'
- f = open('test.txt')
- f.read()  To read again you need make f.seek(0) to read again
- f.readlines() returns a list of lines as strings from file. May have problems with big files(reads to memory), better to use open()
- f.close() To close file
- f = open('test.txt','w') To open in the write mode.  To write plain Unicode text you should use binary mode ONLY! ('wb')
- f = open('test.txt','a') To open in the append mode. Will append info to the end of existing file(or will create)
- f.write('Hello....!!') will return how many bytes were written. After the end of operation f should be closed!
 
- for line in open('test.txt')
		print(line)   Will print lines from file

- pwd lists current dir full path(?)
-----
You can save your Python variables, lists, dictionaries and non-text(!!) objetcts into binary shelve file! Shelve file is a dictionary itself. 

import shelve
shelveFile = shelve.open('mydata')
shelveFile['cats'] = ['name1', 'name2', 'name3', 'name4']
shelveFile.close()

shelveFile = shelve.open('mydata')
shelveFile['cats']  will return our saved list

shelveFile.keys()
shelvefile.values()
- which you can cast as list and etc...
-----
import shutil

shutil.copy('source','destination') - copy file, returns destination full path. can be copy+rename
shutil.copytree(src_dir,dst_dir) - copy folder
shutil.move(src, dst) move file or folder recursively. returns new full path. Can be used as rename.
shutil.rmtree(src) delete dir and all it's content!!
-----
import send2trash - should be installed with pip, not included

send2trash.send2trash(src) will send file or folder to the recycling bin instead of permanent deletition.
-----
OS module:

import os
os.path.join('folder1','folder2','file.txt') - makes full path, for multi-OS use
os.path.split(path) - returns list(tuple?) of separate folders
os.getcwd() - get current working dir
os.chdir('C:\\') - change current working dir
. - this folder
.. - parent folder
os.path.abspath('spam.png') - will return absolute file path
os.path.isabs() - check if path is absolute
os.path.relpath('c:\\folder1\\folder2\\spam.png','C:\\folder1') - will return folder2\\spam.png as a diff between absolute and relative paths.
os.path.dirname() will return folder path from full path
os.path.basename() will return file name from full path
os.path.exists() checks if folder or file exists
os.path.isfile() if file exists
os.path.isdir() id dir exists
os.path.getsize() returns size in bytes
os.listdir() returns list of files and folders
os.makedirs() creates new folder(s) (will create recursively)
os.unlink(file_name) delete file 
os.rmdir(src) delete folder, should be EMPTY!
os.walk('src') - returns full list of the dir and inside it recurcively, is used in for loops like:

for folderName, subfolders, filenames in os.walk('C:\\folder1'):
    folderName - where we are now
    subfolders - which subfolders are inside current folder
    filenames - which files are inside current folder
    -- each iteration of the loop will go into the next folder

-------------------------------------------------------------

Sets:
- Set is unordered collection of the UNIC elements. Almost like a dictionary, but only with keys and they are ONLY UNIC!
- x = set()
- x.add(1)
- set() can cast list and show only unic elements. l = [1,1,1,1,1,2,2,2,2,3,3,4,4,4]     set(l) returns {1,2,3,4}

Advanced Sets:

s = set()

s.add(1)
s.add(2)
s.add(2)
s returns {1,2}
s.clear() # will clear set
s = {1,2,3}
sc = s.copy() # will copy original set
s.add(4)
s.difference(sc) # will return 4 as the diff
---
s1 = {1,2,3}
s2 = {1,4,5}
s1.difference_update(s2) # will delete from set s all that is in set sc and will leave {2,3}
---
s.discard(2) # will remove 2 if it is a member of the set
---
s1 = {1,2,3}
s2 = {1,2,4}
s1.intersection(s2) # returns {1,2}
s1.intersection_update(s2) # updates s1 to be {1,2}
---
s1 = {1,2}
s2 = {1,2,4}
s3 = {5}
s1.isdisjoint(s2) # returns False
s1.isdisjoint(s3) # returns True (they don't have intersection)
s1.issubset(s2) # returns True
s2.issuperset(s1) # returns True (is inverse of issubset)
s1.symmetric_difference(s2) # will return {4}
s1.union(s2) # will return {1,2,4}
s1.update(s2) # will take extra elements from s2 to s1
-------------------------------------------------------------

Booleans:
- a = True
- can be None and must be assigned like b = None (used as a placeholder)
- SO THERE IS 3 STATES: True, False, None
- 1 > 2 returns False , 11 > 2 returns True
- Operators of comparision: == != <>(similar to !=) > < >= <=
- comp operators or/and. Can be chained 1 < 2 < 3 same as 1 < 2 and 2 < 3 

-------------------------------------------------------------

Statements:
- if a>b:
		a = 2
		b = 4
  else: OR elif:

- if "x" in board[:]:  cycles through the list and checking for if statement(like for inside if?)

- One line if: value_when_true if condition else value_when_false
- Example: isApple = True if fruit == 'Apple' else False

- for item in object:      Name of the item variable can be any! DO not depend on object
- for (t1,t2) in t:      to unpack tuple like t = [(1,2),(3,4),(5,6)]
- for k,v in d.items():       to iterate through dictionary like d = {'k1':1,'k2':2,'k3':3} . .items() will return iterators

- while statement:
  else:
- pass      breaks out of the current closest enclosing loop
- continue  goes to the top of the closest enclosing loop
- pass      does nothing at all

- while True:    - will run loop until you break it! (or need to continue)

-------------------------------------------------------------

Iterators and Generators:      - generator functions allow us to write a function that can send back a value and then later resume to pick up where it left off. Allows us to generate a sequene of values over time. (In most cases they are like regular functions. But they do not regulary return value and exit, they suspend and resume). 
A generator is simply a function which returns an object on which you can call next, such that for every call it returns some value, until it raises a StopIteration exception, signaling that all values have been generated. Such an object is called an iterator.
- Normal functions return a single value using return, just like in Java. In Python, however, there is an alternative, called yield. Using yield anywhere in a function makes it a generator. (We can use as many yield statements as we want, but by default it is used inside loop(for loops call next in the background))
Observe that a generator object is generated once, but its code is not run all at once. Only calls to next() actually execute (part of) the code. After yelding all values we will get StopIteration error!

def gencubes(n):
	for num in range(n):
		yield num**3

for x in gencubes(10):
	print x



-----

def fibonacci(n):
    a = 1
    b = 1
    
    for i in range(n):
        yield b
        t = a+b
        b = a
        a = t
        #or instead of last three lines use tuple unpacking: a,b = a+b, a
        
list(fibonacci(10)) #OR WITH next:
fib = fibon(10)

print (next(fib)) # - each call will take new(next) generated value! 

----

- Iterator and iterable: for example string(and list/tuple...) is iterable, but if we will try to use next() func we will get an error, because it is not an iterator. So we could use iter() func to make iterable object like string become iterator(to be used with next() or to cast as list)

s = "Hello string"
s_iter = iter(s)

print(next(s_iter)) # - after each call will get next symbol OR can cast all iterable as a list/tuple : list(s_iter) or tuple(s_iter)

----

- range(start,stop[,step]) - used in loops like: for num in range(0,10):    not saved in memory; CAN'T be used like x = range(0,10), but can cast as x = list(range(0,10)) or x = tuple(range(0,10))
return num in range(low,high+1) - returns true or false
if num in range(low,high+1):

-------------------------------------------------------------

Generator expressions:      - almost same as list comprehentions
g = (n for n in range(3, 5))    #    - is comparable to list comprehention: lc = [n for n in range(3, 5)]    will return the list

next(g) # - each call will take new(next) generated value!

-------------------------------------------------------------

List comprehentions:         - To make lists filling more clean and efficient than standard loops.
- l = [letter for letter in 'word']   or   l = [x**2 for x in range(1,11)]   so we can put result of loop into list directly
- lst = [number for number in range(11) if number % 2 == 0]  returns lst = [0,2,4,6,8,10] . So we can put if statement inside list directly too!
- comprehension lists can be nested!    l = [[x**2 for x in range(1,6)], [x**3 for x in range(1,6)]] or   l = [x**2 for x in [x**2 for x in range(1,6)]]


-------------------------------------------------------------


Functions:
- def name_of_function(arg1, arg2):   to define it
  		return result
- name_of_function('arg1','arg2')  to call it

---
Recursive functions:   - they call themselves (calc factorial, fibonacci etc)(but loop is faster! So use only if realy needed)

def factorial(n):
# n! also can be defined as n * (n-1)!

  if n <= 1:
    return 1
  else:
    return n * factorial(n-1)
---
*args and **kwargs - arguments and keyword arguments

*args - gives an ability to pass any number of parameters to function and will be enterpreted inside our function as a tuple. (You can use any name in place of *args(used by convention). But you can use *some (Not good!!))
def myfunc(*args): 
  return sum(args) * 0.05 

**kwargs - enterpreted inside function as a dictionary of key:value pairs. 
def myfunc(**kwargs):
  if 'fruit' in kwargs:
    print("My fruit: {}".format(kwargs['fruit']))
  else:
    print("No fruits here!")

myfunc(fruit='apple', veggie='cucumber', somekey='any number') - so we need to pass to function any number of assigned variables that will be used as key:value dictionary

Both could be used together, but must be in the same order as you set - args and kwargs:

def myfunc(*args, **kwargs):
  print('I would like {} {}'.format(args[0], kwargs['food']))

myfunc(10,20,30,veggy='cucumber', food='eggs', animal='dogs')

will return: I would like 10 eggs
-------------------------------------------------------------

Lambda expressions  - is like def functions, but for small expressions and fast/clean. Lambda's body is same what we would put into return statement of def function.
- def square(num):
      result = num**2
      return result

Can be changed to: def square(num): return num**2    - BAD STYLE!!
Another form(lambda expression): square = lambda num: num**2            Call square(10)       Same as function
Second example: even = lambda num: num%2 == 0           (So this is if statement, but without if itself)
Third: adder = lambda x,y: x+y
Or if it private/anonymous, we don't need to save it to square variable. Just like: lambda num: num%2 == 0
map() filter() reduce() are comon functions that is used with lambda expressions!
Can be passed as an argument to a function??

-------------------------------------------------------------

Nested Statements and Scope:    Variables are stored in the namespace and they have their own scope!

In simple terms, the idea of scope can be described by 3 general rules:
1.Name assignments will create or change local names by default.
2.Name references search (at most) four scopes, these are:
local
enclosing functions
global
built-in
3.Names declared in global and nonlocal statements map assigned names to enclosing module and function scopes.

Example:
x = 1
def func():
    global x
    print 'This function is now using the global x!'
    print 'Because of global x is: ', x
    x = 2
This way we are telling from the start of our function that we want to use global variable and not the local one!

You can use globals() and locals() function to check what globals and locals variables you have.

----
nonlocal variable - not global, but must exist in the enclosing scope(so nonlocal declared in parent func and must be used inside nested child funcs(?)). So it won't be available global to all prog.

USE global AND nonlocal ONLY WHEN IT IS NECESSERY !

===========================OOP========================================

Class:

- starts from capital letter, uses CamelCase convention, do NOT use underscores!
- inside class we can define class attributes and methods
- For example we can create a class called Dog. An attribute of a dog may be its breed or its name, while a method of a dog may be defined by a .bark() method which returns a sound.
- In Python there are also class object attributes. These Class Object Attributes are the same for any instance of the class. For example, we could create the attribute species for the Dog class. Dogs (regardless of their breed,name, or other attributes will always be mammals.
- in Python every type is a class!
class Dog(object):
	species = 'mammal'            - Note that the Class Object Attribute is defined outside of any methods in the class before the init.

    def __init__(self, breed, name):     - The special method __init__() is called automatically right after the object has been created
        self.breed = breed        - Each attribute in a class definition begins with a reference to the instance object (self)
        self.name = name

sam = Dog('Lab','Sam')

We have created instance of the class Dog. Now we can access to it's attributes through call: sam.breed and sam.name ;Or class object attribute sam.species

-------------------------------------------------------------

Methods and Attributes:
- A method is an operation we can perform with the object(function). Methods are functions defined inside the body of a class. They are used to perform operations with the attributes of our objects.
- Attribute is a variable bound to an instance of a class. Attributes with two underscores __ will be "hidden" from public use!

class Circle(object):
    """Here is a Doc string"""
    pi = 3.14

    # This is a static method that should be used only inside our class object! should be used later inside other methods as Circle._some_method()
    @staticmethod
    def _some_method():
        doing stuff

    # Circle get instantiated with a radius (default is 1)
    def __init__(self, radius=1):
        """Here is a Doc string"""
        self.radius = radius
        self.__hiden_radius = radius #Attributes with two underscores __ will be "hidden" from public use!

    # Area method calculates the area. Note the use of self.
    def area(self):
        """Here is a Doc string"""
        return self.radius * self.radius * Circle.pi

    # Method for resetting Radius
    def setRadius(self, radius):
        self.radius = radius

    # Method for getting radius (Same as just calling .radius)
    def getRadius(self):
        return self.radius


c = Circle()

c.setRadius(2)
print 'Radius is: ',c.getRadius()
print 'Area is: ',c.area()
-------------------------------------------------------------
Getters and Setters:  - functions inside the class to get or set data to/from hidden(private) attribute. funcs that starts from _get_ and _set_ folowing attribute name. After that should be declared as property.

class Player(object):

  def __init__(self):
    self._lives = 3

  def _get_lives(self):
    return self._lives

  def _set_lives(self,lives):
    self._lives = lives

  lives = property(_get_lives, _set_lives)  #property(fget, fset, fdel, doc) to set Setter, Getter and Deletter :) (?) and doc to set docstring of that property

vasia = Player()
vasia.lives # returns 3
vasia.lives = 1 # sets value to 1

--OR more common method!--

class Player(object):

  def __init__(self):
    self._lives = 3

  @property
  def lives(self): # Getter
    return self._lives

  @lives.setter
  def lives(self, lives): #Setter
   self._lives = lives

vasia = Player()
vasia.lives # returns 3
vasia.lives = 1 # sets value to 1
-------------------------------------------------------------

Inheritance:
- Inheritance is a way to form new classes using classes that have already been defined. The newly formed classes are called derived classes, the classes that we derive from are called base classes. Important benefits of inheritance are code reuse and reduction of complexity of a program. The derived classes (descendants) override or extend the functionality of base classes (ancestors).

class Animal(object):
    def __init__(self, name):
        self.name = name
        print "Animal created"

    def whoAmI(self,some_param):
        self.some_param = some_param * 2
        print "Animal"

    def eat(self):
        print "Eating"

#---For Python 2 and 3:----

class Dog(Animal):
    def __init__(self, name):
        Animal.__init__(self, name=name)
        print "Dog created"

    def whoAmI(self):    - overriding inherrited method!
        print "Dog"

    def bark(self):
        print "Woof!"

#--OR only for Python3---

class Dog(Animal):
    def __init__(self, name):
        super().__init__(name=name) # Same as: super(Animal, self).__init__(name=name)
        print ("Dog created")

    def whoAmI(self,some_param):    - overriding inherrited method!
        super().whoAmI(self, some_param = some_param) # without this structure we can override full method, or we can call parent method and add some code before 
                                                      #or after it, so we will not fully override, but append.
        print ("Biiig Dog")

    def bark(self):
        print ("Woof!")

-----
Composition: - when we don't need to inherit superclass, but instead we create needed classes and use them inside our main class. So for composition we create instances of needed classes inside our main class. If we delete instance of our main class - other classes inside it will be deleted too.(this is like function call inside other function:) )
-----
Aggregation: - Almost same as composition except that we use inside our main class existing instances of needed classes! So if we delete instance of our main class - others will keep alive.

-------------------------------------------------------------

Special Methods:
- Classes in Python can implement certain operations with special method names. These methods are not actually called directly but by Python specific language syntax      The __init__(), __str__(), __len__() and the __del__() methods.  They allow us to use Python specific functions on objects created through our class.

class Book(object):
    def __init__(self, title, author, pages):
        print "A book is created"
        self.title = title
        self.author = author
        self.pages = pages

    def __str__(self):    - so class will know what to return on basic call(like when returning contents of a list object)
        return "Title:%s , author:%s, pages:%s " %(self.title, self.author, self.pages)

    def __len__(self):    - is used when you are asking python about length of an object
        return self.pages

    def __del__(self):    - delete object from memory
        print "A book is destroyed"

book = Book("Python Rocks!", "Jose Portilla", 159)

#Special Methods
print book
print len(book)
del book

book.__dict__ - prints dictionary of objects that belong to book object.

-------------------------------------------------------------
-------------------------------------------------------------
-------------------------------------------------------------

Modules:        - Modules are created to save time on writing code :)
import math               - import all module, then will be used as math.some_func
from math import sqrt     - just to import exact function!
from math import *        - will import all module's functions to our namespace ! (what about global vars?)

---

in our manually created module in main func(if it exists and if your module can run by itself, for example we have made a game blackjack.py and want later to use it in our game collection):
if __name__ = '__main__':  # - so we are checking the scope. If .py run itself - do code. If it was imported as a module - don't run.
    do code in main func to execute program itself

-------------------------------------------------------------

map(function, sequence):  - applies function to each element in the sequence and returns new list(iterator!) with results! Sequence = list.
- map usualy is used with Lambda expressions.
- function name is passed without ()
- for python3 map() returns iterator(!!!) so we need to cast it with list()

def fahrenheit(T):
    return (9.0/5)*T + 32
temp = [0,22.5,40,100]
map(fahrenheit,temp)
- Will give result to list [32.0, 72.5, 104.5, 212.0]
- Or with lambda: 
map(lambda T: (9.0/5)*T + 32, temp)
- We can pass more than one arg to map() . Like map(lambda x,y: x+y,a,b) . a and b are our lists to take as x and y

-------------------------------------------------------------

reduce(function, sequence):    -The function reduce(function, sequence) continually applies the function to the sequence. It then returns a single value.(In python3 moved to functools module! Need to install and import!)
from functools import reduce

If seq = [ s1, s2, s3, ... , sn ], calling reduce(function, sequence) works like this:

At first the first two elements of seq will be applied to function, i.e. func(s1,s2)
The list on which reduce() works looks now like this: [ function(s1, s2), s3, ... , sn ]
In the next step the function will be applied on the previous result and the third element of the list, i.e. function(function(s1, s2),s3)
The list looks like this now: [ function(function(s1, s2),s3), ... , sn ]
It continues like this until just one element is left and return this element as the result of reduce()

lst =[47,11,42,13]
reduce(lambda x,y: x+y,lst)   - result is 113

-------------------------------------------------------------

filter(function, list)   - Returns the list(iterable!) of  given elements in the list, to which function will return True.
- frequently used with Lambda expressions

def even_check(num):
    if num % 2 == 0:
        return True
    else:
        return False

filter(even_check, lst)  - will return only even integers(that returned True through the function)

-------------------------------------------------------------

zip(lst1,lst2,...)       - returns the list(iterable) of tuples from given lists(from two and more...). Will be defined by the shortest iterable!
- can zip dictionaries, but will return list of keys only. As iteration through the dictionary returns keys only.

x = [1,2,3]
y = [4,5,6]

zip(x,y)  -returns the list of tuples [(1,4),(2,5),(3,6)]

-------------------------------------------------------------

enumerate(list)    - allows you to keep a count as you iterate through an object. It does this by returning a tuple in the form (count, element).

l = ['a','b','c']
count = 0
for item in l:
    print item
    print count
    count += 1

OR

l = ['a','b','c']
for count,item in enumerate(l):
	prunt count
	print item

-------------------------------------------------------------

all() and any() are funcs that allow to check for bollean matching in an iterable. all() will return True if all elements in an iterable are True. any() - will return True if any of them true.

complex()   - makex complex integer(?)

complex(2,3)   - returns(2+3j)
complex('10+2j')    - returns(10+2j)

-------------------------------------------------------------

Decorators   - function which modify functionality of another function. They help to make your code shorter and more "Pythonic".

- functions could be assigned to variable, returned through return or be taken as an argument by other function. And it will not be attached! So we can delete parent function after assignment and child func will be "alive"
- Such way we wraped old func with new code
def hello():
    print("We will decorate this func")
    
def decorator(func):
    
    def wrapper():
        print("Here is the code before decorated func")
        
        func()
        
        print("There is a code after decorated func")
        
    return wrapper

hello = decorator(hello)
hello()

# Or other way to do that:

def decorator(func):
    
    def wrapper():
        print("Here is the code before decorated func")
        
        func()
        
        print("There is a code after decorated func")
        
    return wrapper

@decorator
def hello():
    print("We will decorate this func")
hello()

----------------------------------------------------------
=====================Collections=Module==================================
----------------------------------------------------------
#Counter - is a dict subclass which helps to count hashable objects. Inside of it elements are stored as dictionary keys and the counts of the objects are stored as the value. Counts elements of iterable(?)

from collections import Counter

l = [1,1,1,1,1,1,33,3,4,4,4,5,5,5,5]
Counter(l)

result: ({4: 3,1: 6, 5: 4, 33: 1, 3: 1})

.most_common(2) - will show two most common elements
sum(l.values) - will return sum of all elements.
set(l) - convert to set (same for list)
l.most_common()[:-n-1:-1]  - n least common elements

---------------------------------------------------
#Default dictionary - will return default value if key is not in the dictionary. Will not rase an error, instead it will create value.

from collections import defaultdict

d = defaultdict(object) # - initially by default initialised by object type.

-----------------------------------
#OrderedDict - remembers an order in which elements were added(retains an order)

from collections import OrderedDict

d = OrderedDict()

-----------------------------------
#namedtuple - assign not only values to indexes(but indexes remains), but also assign names. It is almost like creating a class very quickly.
- so this is like a tupl-o-class )))

from collections import namedtuple

Dog = namedtuple('Dog','age breed name')  # name of the class and string with attribute fields(names for values)
sam = Dog(age=2,breed='Lab',name='Sammy')
sam.age  # returns 2
sam.breed # returns Lab

-----------------------------------
#Datetime
- has a lots of methods 

import datetime

t = datetime.time(4,24,1) # 5 hours, 25 mins, 01 sec

print t # result 05:25:01

---
d = datetime.date.today()
d.timetuple()

d1 = datetime.date(2015,3,11)
d2 = d1.replace(year=1990)
d1 - d2   #returns datetime.timedelta(9131)

----------------------------------------------------------
Timezones: pip install pytz

import pytz
import datetime

country = 'Europe/Moscow'

tz_to_display = pytz.timezone(country)
local_time = datetime.datetime.now(tz=tz_to_display)
print("Time in {} is {}".format(country, local_time))
print("UTC is {}".format(datetime.datetime.utcnow()))

pytz.all_timezones  - list of all timezones names
pytz.utc.localize(datetime.datetime.utcnow()) - gives current time in UTC(???)
----------------------------------------------------------
Timing your code - timeit

import timeit

"-".join(str(n) for n in range(100))  # will create 0-1-2-3-4-5-6
"-".join(map(str,range(100))) # same! but faster

timeit.timeit(' "-".join(str(n) for n in range(100)) ', number=10000) # will calculate time of n-times execution. (for all 10000 times execution)

%timeit "-".join(str(n) for n in range(100))
----------------------------------------------------------
----------------------------------------------------------
----------------------------------------------------------
Regular Expressions

import re

mo = re.search('hello','hello world!') # Easy example: You will get a Match object, not boolean. In case if match not found - it will return None 
print(mo.group())
# List of patterns to search for
patterns = [ 'term1', 'term2' ]

# Text to parse
text = 'This is a string with term1, but it does not have the other term.'

for pattern in patterns:
    print ('Searching for "%s" in: \n"%s"' % (pattern, text))
    
    #Check for match
    if re.search(pattern,  text):
        print ('\n')
        print ('Match was found. \n')
    else:
        print ('\n')
        print ('No Match was found.\n')
-------
OR whe can use that syntax when there is no list of patterns:

searchPattern = re.compile('here is our pattern')
searchPattern.search(string) # Find first match
searchPattern.findall(string) # will find all occurances, will return list!! instead of an object OR list of tuples if there was two or more regex groups!
----
match = re.search(patterns[0],text) #will wind only first occurance, will return Match object
match = re.findall(patterns[0],text) # will find all occurances, will return list!! instead of an object OR list of tuples if there was two or more regex groups!
match.start() # will return at what index match starts
match.end() # index of the end
match.group() # will print what was found
- and others methods
----
method .sub() works like find and replace!

searchPattern = re.compile(r'Agent \w+')
searchPattern.sub('REDACTED', 'Agent Alice gave the secret documents to Agent bob.')  # Returns the string with replaced occurances.

searchPattern = re.compile(r'Agent (\w)\w*')
searchPattern.sub(r'Agent \1*****', 'Agent Alice gave the secret documents to Agent bob.')  # Returns the string with replaced occurances. \1 pattern tells to take result from group 1 (\w) of our search result.
----
mo = re.search('(hel)(lo)','hello hello world!') 
print(mo.group(2)) # - our keyword to search is divided for groups. And we can return each group separately.
| pipe character can be used inside group as OR operator
----
split_term = '@'
phrase = 'What is your e-mail. Is it hello@gmail.com?'
re.split(split_term, phrase) # will return list that is splitted. Similar to .split method
----
Repetition Syntax

def multi_re_find(patterns,phrase):
    '''
    Takes in a list of regex patterns
    Prints a list of all matches
    '''
    for pattern in patterns:
        print 'Searching the phrase using the re check: %r' %pattern
        print re.findall(pattern,phrase)
        print '\n'

test_phrase = 'sdsd..sssddd...sdddsddd...dsds...dsssss...sdddd'

test_patterns = [ 'sd*',     # s followed by zero or more d's
                'sd+',          # s followed by one or more d's
                'sd?',          # s followed by zero or one d's
                'sd{3}',        # s followed by three d's
                'sd{2,3}',      # s followed by two to three d's
                ]

test_patterns = [ '[sd]',    # either s or d
            's[sd]+']   # s followed by one or more s or d

test_patterns=[ '[a-z]+',      # sequences of lower case letters
                '[A-Z]+',      # sequences of upper case letters
                '[a-zA-Z]+',   # sequences of lower or upper case letters
                '[A-Z][a-z]+'] # one upper case letter followed by lower case letters

test_patterns=[ r'\d+', # sequence of digits
                r'\D+', # sequence of non-digits
                r'\s+', # sequence of whitespace
                r'\S+', # sequence of non-whitespace
                r'\w+', # alphanumeric characters
                r'\W+', # non-alphanumeric
                ]

multi_re_find(test_patterns,test_phrase)

----
re.findall('[^!.? ]+',test_phrase)

- We can use ^ to exclude terms by incorporating it into the bracket syntax notation. For example: [^...] will match any single character not in the brackets. 
- Use [^!.? ] to check for matches that are not a !,.,?, or space. Add the + to check that the match appears at least once, this basically translate into finding the words.
- $ signaling "at the end of the string" and ^ as "at the beginning of the string"(?)
- ^string$ will match full string!
- . any character

VERBOSE:

re.compile(r'''
our reg    # our cooment
expression # still can be here
is here
(and can)
(be in groups)
''', re.VERBOSE)

----------------------------------------------------------
----------------------------------------------------------
----------------------------------------------------------
Errors and Exceptions

- Exception is the type of error
- Basic syntax is: try and except statements
- The code which can cause an exception to occur is put in the try block and the handling of the exception is implemented in the except block of code
- We can also just check for any exception with just using except:
- The finally: block of code will always be run regardless if there was an exception in the try code block.
try:
   You do your operations here...
   ...
except ExceptionI:
   If there is ExceptionI, then execute this block.
except ExceptionII:
   If there is ExceptionII, then execute this block.
   ...
else:
   If there is no exception then execute this block.
   ...
finally:
   Do even if there is an exception(It will be executed even if all statement is in loop and it was broken(break) in other statement)


   def askint():
    while True:
        try:
            val = int(raw_input("Please enter an integer: "))
        except:
            print "Looks like you did not enter an integer!"
            continue
        else:
            print 'Yep thats an integer!'
            break
        finally:
            print "Finally, I executed!"
        print val 

-====-====-====-===-
Manual exceptions:   - to handle some errors that is not Python-related, but more program/logic-specific

raise Exception('This is the error message')

------
i = int(input('Enter digit, but not 2!'))

assert not i == 2, 'This is the error message'  # So if assert becomes False - it will raise an error.

-====-====-====-===-
Manual tracebacks:

import traceback

try:
    raise Exception('This is the error message')
except:
    errorFile = open('error.log','a')
    errorFile.write(traceback.format_exc())
    errorFile.close()
    print('The traceback was written to log')

-====-====-====-===-
Logging:  - We can use it as print() function, but with more info! And it could be switched off! DO NOT USE PRINT FOR DEBUG MESSAGES!

import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(levelname)s - %(message)s')
log = logging.getLogger(__name__)
--OR--
logging.basicConfig(filename='log.txt', filemode='a', level=logging.DEBUG, format='%(asctime)s - %(levelname)s - %(message)s') # Write log to file
log = logging.getLogger(__name__)

log.disable(logging.CRITICAL) # - to disable after software was debugged!(release version, will disable all)

log.debug('Start program')
log.info('Some info')
log.warning('warning')
log.error('Doing code...Got error')
log.critical('Critical error!!')

in child modules we can use it:
import logging
log = logging.getLogger(__name__)

================================
Python Debugger - pdb

import pdb

pdb.set_trace()

- will set interactive stop point. we can do operations or exit with q .
-------
================================
================================
================================
webbrowser module:

import webbrowser

webbrowser.open('http://goggle.com') - opens the page in your default browser.

------------------
import pyperclip     - should be installed by pip

info = pyperclip.paste() - will return a string of data in the clipboard.
------------------
import requests       - should be installed

res = requests.get(src)  - downloads file from the Web, returns server answer
res.status_code   - returns status code like 200, 404, 503 and etc.
res.text  - contents of the downloaded file
res.raise_for_status() - will raise an exception if there was an error and will be blank if downloaded successfully

playFile = open('text.txt','wb') - opens file in write binary mode. To write plain Unicode text you should use binary mode ONLY!
for chunk in res.iter_content(100000): - pass 100000 bytes per loop iteration (To save our file by chunks?)
     playFile.write(chunk)

playFile.close()
--------------------
Web Scraping(parsing):

import bs4    - need to be installed (beautiful soup 4? )
import requests

res = requests.get('http://somepage.com/page_any.php') 
res.raise_for_status()  - check for download status and throw error in case of failure
soup = bs4.BeautifulSoup(res.text, 'html.parser')
elems = soup.select('#mediaNo > div.a-row > span.a-size-medium.price')  - we need to pass css selector(for example)(Copy CSS path in browser). Will return a list.
elems[0].text.strip()   - will cut excessive whitespaces, \n \t 

========================SELENIUM=======================
You must install through pip selenium and use Firefox browser

from selenium import webdriver
browser = webdriver.Firefox()   - will run browser
browser.get('http://google.com') - will open page
elem = browser.find_element_by_css_selector('here is css selector path')
elem.click() - emulate click
elems = browser.find_elements_by_css_selector('p')  - will return the list(?) of all <p> elements found (Has lots of methods like find by name, style, id etc)
len(elems)  - how many items was found

searchElem = browser.find_element_by_css_selector('.search-field')
searchElem.send_keys('search something')
searchElem.submit()

browser.back()
browser.forward()
browser.refresh()
browser.quit()

elem = browser.find_element_by_css_selector('some_selector')
elem.text  - returns contents of found selector

elem = browser.find_element_by_css_selector('html')  - will get entire web page
======================END_SELENIUM======================
Word:     pip install python-docx

import docx

d = docx.Document('test.docx')  - open existing. if want to create a new one - do not pass an argument.
d.paragraphs   - contains the list of paragraph objects(new line)
d.paragraphs[0].text   - text of the first paragraph
p = d.paragraphs[1]   - each paragraph has Runs. Each run starts with a mew change of the text style.
p.runs[0].text
p.runs[1].text   - this both runs will have separate parts of the same paragraph with different styles!
p.runs[1].bold   - style boolean
p.runs[1].italic   - style boolean
p.runs[1].underline   - style boolean
p.style    - style of the paragraph, string value containing it's name(from Word?)
p.add_run(string) - adds new run to the paragraph

d.add_paragraph(string) - adds new paragraph

d.save('test2.docx')

=========================
Excel:     pip install openpyxl

import openpyxl

workbook = openpyxl.load_workbook('example.xlsx') - opens existing workbook(file)
workbook = openpyxl.Workbook()  - create new workbook
workbook.get_sheet_names() - will return sheet names (list)
sheet = workbook.get_shhet_by_name('Sheet1')
cell = sheet['A1']
cell.value  - will return cell object(depends on internal Excel formating)
-OR-
str(sheet['A1'].value)

sheet.cell(row=1, column=2) - We can select not by name(A1 etc) but as row and column. Good for loops.
workbook = create_sheet() - will create new sheet

workbook.save('example.xlsx')

=========================
PDF: need to install  (Can extract text ONLY...)

import PyPDF2

pdfFile = open('test.pdf','rb')
reader = PyPDF2.PdfFileReader(pdfFile)
reader.numPages  - how much pages
page = reader.getPage(0) - will return first page
page.extractText()  - will return extracted text from the page, need to loop over all pages to get all

etc... GOOGLE! )

=============================================
Send e-mails:

import smtplib

conn = smtplib.SMTP('smtp.gmail.com',587)
conn.ehlo()
conn.starttls()
conn.login(username, password)

body = 'Subject: Hello... \n\nHi, this is our body!'

conn.sendmail(fromaddress, toaddress, body) - returns a list of failed to send addresses.
conn.quit()

=============================================
Receive e-mails:
import imaplib - very complicated! So better to use two third-party modules: pip install imapclient , pip install pyzmail
----

import imapclient

conn = imapclient.IMAPClient('imap.google.com', ssl=True)
conn.login(login, password)
conn.select_folder('INBOX', readonly=True)  - readonly=False if you want to delete some messages!
UIDs = conn.search(['SINCE 20-Aug-2015'])  - own IMAP search syntax! returns list of IDs

conn.delete_messages([list_of_UIDs])  - deleting messages

raw_message = conn.fetch([UID_here], ['BODY[]', 'FLAGS'])

import pyzmail

message = pyzmail.PyzMessage.factory(raw_message[UID_here][b'BODY[]'])
message.get_subject()
message.get_addresses('from')
message.get_address('to')
message.text_part  - returns text part of the mail and None if it is empty
message.html_part  - same for html
message.tex_part.get_payload().decode('UTF-8') - to get text part of our mail

conn.logout()

===========================
pyautogui - to control mouse or keyboard, screenshots , third-party module

pyautogui.moveTo((x,y), duration=1) - move mouse to x,y with duration in seconds.
pyautogui.click(x,y)  - can accept just two integers or a tuple containing two integers.

Mouse and Keyboard: GOOGLE or official docs ) 

----
Screenshot and recognition:

import pyautogui

pyautogui.screenshot('screen.png')  - returns and saves screenshot, or without args just return without saving.

pyautogui.locateOnScreen('filename_of_whattofind.png') - we give as arg image of an element that we want to find on the screen! For example image of the button. And it will return (tuple) coordinates of what it found like (907, 316, 50, 41) . It represents x,y and size of an object found.

pyautogui.locateCenterOnScreen('img.png') - same, but returns (x,y) of the center of found image.

- SLOW and MUST be pixel-perfect! Read docs how to speedup and make partial search.

===========================TKINTER===========================
import tkinter #- cross-platform GUI for Python

mainWindow = tkinter.Tk()

mainWindow.title("Popup window")
mainWindow.geometry('640x480+8+200')  #- position can be specified too, not just size

label = tkinter.Label(mainWindow, text="hello world") # - all elements(called widgets!) should have window they are belong to.
label.pack(side='top')  # we can use pack method or grid method to place elements

leftFrame = tkinter.Frame(mainWindow)
leftFrame.pack(side='left', anchor='n', fill=tkinter.Y, expand=False)

canvas = tkinter.Canvas(leftFrame, relief='raised',borderwidth=1)  #- canvas is used to draw something inside window(?)
canvas.pack(side='left', anchor='n')

rightFrame = tkinter.Frame(mainWindow)
rightFrame.pack(side='right', anchor='n', expand=True) # - anchor equal north,south,east,west, will be used vertically as horisontal placement now made by side arg
button1 = tkinter.Button(rightFrame, text='button1')
button2 = tkinter.Button(rightFrame, text='button2')
button3 = tkinter.Button(rightFrame, text='button3')
button1.pack(side='top') 
button2.pack(side='top')
button3.pack(side='top')

mainWindow.mainloop()

--OR-- use grid manager instead of pack! A lot EASIER! (like building in Excel?))

import tkinter #- cross-platform GUI for Python

mainWindow = tkinter.Tk()

mainWindow.title("Popup window")
mainWindow.geometry('640x480-8-200')  #- position can be specified too, not just size

label = tkinter.Label(mainWindow, text="hello world") # - all elements(called widgets!) should have window they are belong to.
label.grid(row=0, column=0)  # we can use pack method or grid method to place elements

leftFrame = tkinter.Frame(mainWindow)
leftFrame.grid(row=1, column=1) 

canvas = tkinter.Canvas(leftFrame, relief='raised',borderwidth=1)  #- canvas is used to draw something inside window(?)
canvas.grid(row=1, column=0) 

rightFrame = tkinter.Frame(mainWindow)
rightFrame.grid(row=1, column=2, sticky='n') 
button1 = tkinter.Button(rightFrame, text='button1')
button2 = tkinter.Button(rightFrame, text='button2')
button3 = tkinter.Button(rightFrame, text='button3')
button1.grid(row=0, column=0) 
button2.grid(row=1, column=0) 
button3.grid(row=2, column=0) 

mainWindow.mainloop()
==============================================

Multi Treading:

# Just a hint how to use and where to dig to make 4 threads that will be running same function with same(but separate chunks) data. Could be used to process large amount of data. 

from multiprocessing.dummy import Pool as ThreadPool
from multiprocessing.dummy import current_process


pool = ThreadPool(4)
pool.map(myfunction, mydata)
pool.close()
pool.terminate()
pool.join()

==============================================

Console Menu: - how to make a menu in the console application(CUI)

from consolemenu import *
from consolemenu.items import *

if __name__ = 'main':

  menu = ConsoleMenu("IAAI.com Auction Parser", "Cars in DB: " + str(len(iaai.cars_db)) + " DB file: " + db_file)
  parse_html_menu = FunctionItem("Parse html files from auctions", parse_html_menu)
  enhance_cars_menu = FunctionItem("Enhance cars in DB(download more info and photos)", enhance_cars_menu)
  clean_cars_menu = FunctionItem("Clean cars from DB that could't be enhanced", clean_cars_menu)
  list_attributes_menu = FunctionItem("Find unique attribute values", list_attributes_menu)

  menu.append_item(parse_html_menu)
  menu.append_item(enhance_cars_menu)
  menu.append_item(clean_cars_menu)
  menu.append_item(list_attributes_menu)
  menu.show()

==============================================

JSON: open or write JSON file. Will work as a dictionary with key:value pairs.

import json

def write_cars_db(self):
  with open(self.json_path + self.cars_db_filename + ".json", 'w') as file:
    file.write(json.dumps(self.cars_db, sort_keys=True, indent=4))

def read_cars_db(self):

  try:
      with open(self.json_path + self.cars_db_filename + ".json", 'r') as file:
          log.debug("Reading DB file...")
          try:
              self.cars_db = json.loads(file.read())
              log.debug("File was read, parsing JSON")
          except ValueError:
              log.warning("Can't read DB file")

==============================================

Count script execution time:

from time import perf_counter

start_time = perf_counter()

(do some workload)

print("--- {} seconds ---".format(perf_counter() - start_time))