# 1搭建环境 #

安装包连接[http://python.org/downloads/](http://python.org/downloads/)安装Python3

安装过程中，记得勾选Add Python to PATH

# 2变量和简单数据类型 #

## 2.1变量 ##

变量的命名和C语言的规则一样，变量不用像C语言一样指明变量类型

    message = "Hello Python Crash Course reader!"

## 2.2字符串 ##

### 2.2.1修改字符串大小写 ###

1.使首字母大写**title()**

2.使全部转为大写或者小写**upper(),lower()**

    name = "ada lovelace"
    print(name.title())
    name = "Ada Lovelace"
    print(name.upper())
    print(name.lower())

### 2.2.2拼接字符串 ###

使用**+**

    first_name = "ada"
    last_name = "lovelace"
    full_name = first_name + " " + last_name
    print("Hello, " + full_name.title() + "!")

### 2.2.3添加和删除空白 ###

1.添加：使用**制表符\t**或**换行符\n**或**空格**

2.删除：使用 **strip()** 删除两边的,**rstrip()** 删除右边的,**lstrip()** 删除左边的

	favorite_language = '  python  '
	print(favorite_language.rstrip())
	print(favorite_language.lstrip())
	print(favorite_language.strip())

## 2.3数字 ##

1.整数：加（+ ） 减（- ） 乘（* ） 除（/ ） 乘方（** ）余数（% ）

2.浮点数

3.数字型转字符型**str()**

## 2.4注释 ##

使用 #

# 3列表 #
类似数组，使用方括号 **[]** 表示列表

	bicycles = ['trek', 'cannondale', 'redline', 'specialized']
	print(bicycles)

## 3.1使用列表 ##

1.访问：与C语言类似

2.修改：与C语言类似

3.添加：使用 **append()** ，在列表末尾添加元素

4.插入：使用 **insert()** ，在指定位置插入元素

5.删除：

1）使用 **del**语句 ，删除指定位置的元素

2）使用 **pop()** ，删除列表末尾的元素，类似栈，弹出最后一个元素

3）使用 **pop()** ，删除指定位置的元素，括号中是指定的位置

4）使用 **remove()** ,根据值删除元素

	bicycles = ['trek', 'cannondale', 'redline', 'specialized']
	print(bicycles[0])#访问
	bicycles[0] = 'ducati'#修改
	print(bicycles)
	bicycles.append('ducati')#添加
	print(bicycles)
	bicycles.insert(0, 'yamaha')#插入
	print(bicycles)
	del bicycles[0]#删除del
	print(bicycles)
	popped_bicycle = bicycles.pop()#删除pop()
	print(bicycles)
	print(popped_bicycle)
	first_owned = bicycles.pop(0)#删除pop(n)
	print(bicycles)
	print(first_owned)
	bicycles.remove('redline')#删除remove()
	print(bicycles)

## 3.2组织列表 ##

1.永久性排序：

1）使用**sort()** ，按照字母顺序排列

2）使用**sort(reverse=True)** ，按照字母相反顺序排列

3）使用**reverse()** ,按照原来的相反顺序排列，而不是只字母顺序

2.临时性排序：使用**sorted()** ，不改变原来的排列顺序

3.确定长度：使用**len()** ,

	cars = ['bmw', 'audi', 'toyota', 'subaru']
	cars.reverse()#永久性排序，reverse()
	print(cars)
	cars.sort()#永久性排序，sort()
	print(cars)
	cars.sort(reverse=True)#永久性排序，sort(reverse=True)
	print(cars)
	print(sorted(cars))#临时性排序
	print(cars)
	print(len(cars))#确定长度，len()

# 4操作列表 #

## 4.1遍历整个列表 ##

使用**for循环 需要值得注意的地方**： 1）缩进代表归属 2）冒号

	magicians = ['alice', 'david', 'carolina']
	for magician in magicians:
	    print(magician)

## 4.2数值列表 ##

1）使用**range()** 生成一系列数字

2）使用**range()** 创建数字列表

3）最大值**max()** ，最小值**min()** ，总和**sum()**

4）列表解析

**PS** :range(a,b,c)

a是头，b是尾，c是间距

和str[a:b:c]是一样的道理


	for value in range(1,5):#1
		print(value)
	numbers = list(range(1,6))#2
	print(numbers)
	even_numbers = list(range(2,11,2))#2
	print(even_numbers)
	print(max(numbers))#3
	print(min(numbers))#3
	print(sum(numbers))#3
	
	squares = []
	for value in range(1,11):
	squares.append(value**2)
	print(squares)
	
	squares = [value**2 for value in range(1,11)]##4效果和上面这段代码一样
	print(squares)
## 4.3使用列表的一部分 ##
### 4.3.1切片 ###
处理列表中的部分元素。

切片的应用场景：例如，编写游戏时，你可以在玩家退出游戏时将其最终得分加入到一个列表中。然后，为获取该玩家的三个最高得分，你可以将该列表按降序排列，再创建一个只包含前三个得分的切片。处理数据时，可使用切片来进行批量处理；编写Web应用程序时，可使用切片来分页显示信息，并在每页显示数量合适的信息。

1)要**指定使用的第一个元素和最后一个元素的索引**

2)如果未指定第一个元素，默认为列表开头

3)如果未指定最后一个元素，默认为列表末尾

4)还可以指定负数。离列表末尾相应距离的元素

    players = ['charles', 'martina', 'michael', 'florence', 'eli']
    print(players[0:3])#1
    print(players[1:4])#1
    print(players[:4])#2
    print(players[2:])#3
    print(players[-3:])#4
### 4.3.2遍历切片 ###
for循环使用切片

	players = ['charles', 'martina', 'michael', 'florence', 'eli']
	print("Here are the first three players on my team:")
	for player in players[:3]:
	    print(player.title())
### 4.3.3复制列表 ###
要复制列表，可创建一个包含整个列表的切片，方法是同时省略起始索 引和终止索引（**[:]**） 。这让Python创建一个始于第一个元素，终止于 最后一个元素的切片，即复制整个列表。如果没有使用（**[:]**），就会出现如下情况，复制指针

    my_foods = ['pizza', 'falafel', 'carrot cake']
    friend_foods = my_foods[:]
    print(my_foods)
    print(friend_foods)

    ?#错误实例
    my_foods = ['pizza', 'falafel', 'carrot cake']
    friend_foods = my_foods
    my_foods.append('cannoli')
    friend_foods.append('ice cream')
    print(my_foods)
    print(friend_foods)
## 4.4元组 ##
列表是可以修改的，不可修改的列表叫做元组，使用**圆括号**来标识


	dimensions = (200, 50)
	print(dimensions[0])
	print(dimensions[1])
	
	dimensions[0] = 250#这条代码无法执行，禁止修改
### 4.4.1遍历元组中所有值 ###
和列表一样

	dimensions = (200, 50)
	for dimension in dimensions:
	    print(dimension)
### 4.4.2修改元组变量 ###
虽然不能修改元组的元素，但是可以存储元组的变量赋值。即重新定义整个元组

	dimensions = (400, 100)
	for dimension in dimensions:
	    print(dimension)
	dimensions = (200, 50)
	for dimension in dimensions:
	    print(dimension)
## 4.5设置代码格式 ##
1.PEP 8建议每级缩进都使用四个空格

2.很多Python程序员都建议每行不超过79字符

3.PEP 8还建议注释的行长都不超过72字符

4.要将程序的不同部分分开，可使用空行

5.访问[https://python.org/dev/peps/pep-0008/](https://python.org/dev/peps/pep-0008/) ，阅读PEP 8格式设置指南

# 5 if语句 #
使用方法与C语言大同小异

## 5.1条件测试 ##
1.检测是否相等 if car == 'audi'

**2.检查是否相等时不考虑大小写** if car.lower() == 'audi'

3.检查是否不相等 if requested_topping != 'anchovies'

4.比较数字 if answer <= 42

5.检查多个条件 and 和 or

6.检查特定值是否包含在列表中 if 'pepperoni' in requested_toppings

7.检查特定值是否不包含在列表中 if user not in banned_users:

8.布尔表达式
## 5.2if语句 ##
1.if

2.if-else

3.if-elif-else

4.多个elif

5.省略else

6.多个if（并非嵌套）

## 5.3if语句处理列表 ##
### 5.3.1检查特殊元素 ###
即在for循环中嵌套if语句
	
	requested_toppings = ['mushrooms', 'green peppers', 'extra cheese']
	for requested_topping in requested_toppings:
	    if requested_topping == 'green peppers':
	        print("Sorry, we are out of green peppers right now.")
	    else:
	        print("Adding " + requested_topping + ".")
	5.4.2确定列表不是空的¶
	In [ ]:
	requested_toppings = []
	if requested_toppings:
	    for requested_topping in requested_toppings:
	        print("Adding " + requested_topping + ".")
	    print("\nFinished making your pizza!")
	else:
	    print("Are you sure you want a plain pizza?")
## 5.5设置if语句的格式 ##
PEP 8提供的唯一建议是，在诸如== 、>= 和<= 等比较运算符两边各添加一个空格

# 6.字典 #
类似结构体，类似索引，字典用放在**花括号{}** 中的一系列键—值对表示。

如果字典中，键相同，对应的值是最后一对，而不是累加一起。

	alien_0 = {'color': 'green',
	           'points': 5}
	print(alien_0['color'])
	print(alien_0['points'])
## 6.1 使用字典 ##
### 6.1.1访问字典中的值 ###
	new_points = alien_0['points']
### 6.1.2添加键—值对 ###
字典是一种动态结构，可随时在其中添加键—值对。要添加键—值对， 可依次指定字典名、用方括号括起的键和相关联的值。

	alien_0 = {'color': 'green', 'points': 5}
	print(alien_0)
	alien_0['x_position'] = 0
	alien_0['y_position'] = 25
	print(alien_0)
### 6.1.3 创建空字典 ###
可使用一对空的花括号定义一个字典

	alien_0 = {}
	alien_0['color'] = 'green'
	alien_0['points'] = 5
	print(alien_0)
### 6.1.4 修改字典中的值 ###

	alien_0['color'] = 'yellow'
### 6.1.5 删除键—值对 ###
对于字典中不再需要的信息，可使用del 语句将相应的键—值对彻底删除。使用del 语句时，必须指定字典名和要删除的键。
	
	del alien_0['points']
### 6.1.6 由类似对象组成的字典 ###
字典存储的是一个对象（游戏中的一个外星人） 的多种信息，但你也可以使用字典来存储众多对象的同一种信息。例如，假设你要调查很多人，询问他们最喜欢的编程语言，可使用一个字典来存储这种简单调查的结果

	favorite_languages = {
	    'jen': 'python',
	    'sarah': 'c',
	    'edward': 'ruby',
	    'phil': 'python',
	    }
### Python中中括号[]、小括号()、花括号{}的说明 ###
python语言最常见的括号有三种，分别是：小括号( )、中括号[ ]和大括号也叫做花括号{ }。其作用也各不相同，分别用来代表不同的python基本内置数据类型。

1 小括号( )：代表tuple元组数据类型，元组是一种不可变序列。 tup = (1,2,3)

2 python中的中括号[ ]：代表list列表数据类型，列表是一种可变的序列 x=[1,2,3,4,5,6,7,8,9,10]

3 python大括号{ }花括号：代表dict字典数据类型，字典是由键对值组组成。冒号':'分开键和值，逗号','隔开组。用大括号创建的方法如下： dic={'jon':'boy','lili':'girl'}

## 6.2遍历字典 ##
### 6.2.1遍历所有的键—值对 ###
要编写用于遍历字典的for 循环，使用 item() ，可声明两个变量，用于存储键—值对中的键和值。对于这两个变量，可使用任何名称。

	user_0 = {
	    'username': 'efermi',
	    'first': 'enrico',
	    'last': 'fermi',}
	for key, value in user_0.items():
	    print("\nKey: " + key)
	    print("Value: " + value)

---------

	favorite_languages = {
	    'jen': 'python',
	    'sarah': 'c',
	    'edward': 'ruby',
	    'phil': 'python',
	    }
	for name, language in favorite_languages.items():
	    print(name.title() + "'s favorite language is " + 
	          language.title() + ".")
### 6.2.2遍历所有的键 ###
使用**keys()** 或者 **不使用**

	for name in favorite_languages.keys():
	    print(name.title())
如果将上述代码中的for name in favorite_languages.keys(): 替换为for name in favorite_languages: ，输出将不变

	favorite_languages = {
	    'jen': 'python',
	    'sarah': 'c',
	    'edward': 'ruby',
	    'phil': 'python',
	    }
	friends = ['phil', 'sarah']
	for name in favorite_languages.keys():
	    print(name.title())
	    if name in friends:
	        print(" Hi " + name.title() +
	              ", I see your favorite language is " +
	              favorite_languages[name].title() + "!")

----------

	favorite_languages = {
	    'jen': 'python',
	    'sarah': 'c',
	    'edward': 'ruby',
	    'phil': 'python',
	    }
	if 'erin' not in favorite_languages.keys():
	    print("Erin, please take our poll!")
### 6.2.3按顺序遍历字典中的所有键 ###
字典总是明确地记录键和值之间的关联关系，但获取字典的元素时，获取顺序是不可预测的。 使用函数sorted() 来获得按特定顺序排列的键列表的副本：

	for name in sorted(favorite_languages.keys()):
	    print(name.title() + ", thank you for taking the poll.")
### 6.2.4遍历所有的值 ###
使用**values()**

	for language in favorite_languages.values():
	    print(language.title())
这种做法提取字典中所有的值，而没有考虑是否重复. 为剔除重复项，可使用集合（set）

	for language in set(favorite_languages.values()):
	    print(language.title())
## 6.3嵌套 ##
将一系列字典存储在列表中，或将列表作为值存储在字典中，这称为嵌套 。 你可以在列表中嵌套字典、在字典中嵌套列表甚至在字典中嵌套字典。

### 6.3.1字典列表 ###
列表里存放字典

	alien_0 = {'color': 'green', 'points': 5}
	alien_1 = {'color': 'yellow', 'points': 10}
	alien_2 = {'color': 'red', 'points': 15}
	aliens = [alien_0, alien_1, alien_2]
	for alien in aliens:
	    print(alien)

----------
	
	aliens = []# 创建一个用于存储外星人的空列表
	
	for alien_number in range(30):# 创建30个绿色的外星人
	    new_alien = {'color': 'green', 'points': 5, 'speed': 'slow'}
	    aliens.append(new_alien)
	
	for alien in aliens[:5]:# 显示前五个外星人
	    print(alien)
	print("...")
	
	print("Total number of aliens: " + str(len(aliens)))# 显示创建了多少个外星人

### 6.3.2字典中存放列表 ###


	pizza = {# 存储所点比萨的信息
	    'crust': 'thick',
	    'toppings': ['mushrooms', 'extra cheese'],
	    }
	
	print("You ordered a " + pizza['crust'] + "-crust pizza " +
	      "with the following toppings:")# 概述所点的比萨
	for topping in pizza['toppings']:
	    print("\t" + topping)

----------
	favorite_languages = {
	    'jen': ['python', 'ruby'],
	    'sarah': ['c'],
	    'edward': ['ruby', 'go'],
	    'phil': ['python', 'haskell'],
	    }
	for name, languages in favorite_languages.items():
	    print("\n" + name.title() + "'s favorite languages are:")
	    for language in languages:
	        print("\t" + language.title())
### 6.3.3在字典中储存字典 ###

	users = {
	    'aeinstein': {
	        'first': 'albert',
	        'last': 'einstein',
	        'location': 'princeton',
	        },
	    'mcurie': {
	        'first': 'marie',
	        'last': 'curie',
	        'location': 'paris',
	        },
	    }
	for username, user_info in users.items():
	    print("\nUsername: " + username)
	    full_name = user_info['first'] + " " + user_info['last']
	    location = user_info['location']
	    print("\tFull name: " + full_name.title())
	    print("\tLocation: " + location.title())
# 7用户输入和while循环 #
## 7.1用户输入 ##
1.函数**input()** 让程序暂停运行，等待用户输入一些文本（字符串）

2.使用**int()** 来获取数值输入


	age = input("How old are you? ")#1
	print(age)
	age = int(age)#2
	print(age)
## 7.2while循环 ##
1.用法与C语言的类似

2.用户选择何时退出

3.使用标志

4.使用**break**退出

5.使用**continue**


	current_number = 1
	while current_number <= 5:
	    print(current_number)
	    current_number += 1

----------
	prompt = "\nTell me something, and I will repeat it back to you:"
	prompt += "\nEnter 'quit' to end the program. "
	message = ""
	while message != 'quit':
	    message = input(prompt)
	    if message != 'quit':
	        print(message)

----------
	prompt = "\nTell me something, and I will repeat it back to you:"
	prompt += "\nEnter 'quit' to end the program. "
	active = True
	while active:
	    message = input(prompt)
	    if message == 'quit':
	        active = False
	    else:
	        print(message)

----------
	prompt = "\nPlease enter the name of a city you have visited:"
	prompt += "\n(Enter 'quit' when you are finished.) "
	while True:
	    city = input(prompt)
	    if city == 'quit':
	        break
	    else:
	        print("I'd love to go to " + city.title() + "!")

----------
	current_number = 0
	while current_number < 10:
	    current_number += 1
	    if current_number % 2 == 0:
	        continue
	    print(current_number)
## 7.3使用while循环来处理列表和字典 ##
1.**列表之间移动元素**

2.**删除特定值的元素**：使用函数**remove()**

3.**用户输入增加元素**


	''' 首先，创建一个待验证用户列表'''
	''' 和一个用于存储已验证用户的空列表'''
	unconfirmed_users = ['alice', 'brian', 'candace']
	confirmed_users = []
	''' 验证每个用户，直到没有未验证用户为止'''
	''' 将每个经过验证的列表都移到已验证用户列表中'''
	while unconfirmed_users:
	    current_user = unconfirmed_users.pop()
	    print("Verifying user: " + current_user.title())
	    confirmed_users.append(current_user)
	
	print("\nThe following users have been confirmed:")# 显示所有已验证的用户
	for confirmed_user in confirmed_users:
	    print(confirmed_user.title())

----------
	pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
	print(pets)
	
	while 'cat' in pets:
	    pets.remove('cat')
	    
	print(pets)


----------

	responses = {}
	''' 设置一个标志，指出调查是否继续'''
	polling_active = True
	while polling_active:
	    ''' 提示输入被调查者的名字和回答'''
	    name = input("\nWhat is your name? ")
	    response = input("Which mountain would you like to climb someday? ")
	    ''' 将答卷存储在字典中'''
	    responses[name] = response
	    ''' 看看是否还有人要参与调查'''
	    repeat = input("Would you like to let another person respond? (yes/ no) ")
	    if repeat == 'no':
	        polling_active = False
	''' 调查结束，显示结果'''
	print("\n--- Poll Results ---")
	for name, response in responses.items():
	    print(name + " would like to climb " + response + ".")
# 8函数 #
## 8.1定义函数 ##
1.使用**def** 申明是一个函数

2.在括号中向函数传递信息

	def greet_user():
	    """显示简单的问候语"""
	    print("Hello!")
	greet_user()

----------
	def greet_user(username):
	    """显示简单的问候语"""
	    print("Hello, " + username.title() + "!")
	greet_user('jesse')
## 8.2传递实参 ##
1.**位置实参**（参数顺序不能颠倒）

2.**关键字实参**（参数顺序无所谓）

3.**设置默认值**

**PS**：等号两边不要有空格

	def describe_pet(animal_type, pet_name):
	    """显示宠物的信息"""
	    print("\nI have a " + animal_type + ".")
	    print("My " + animal_type + "'s name is " + pet_name.title() + ".")
	describe_pet('hamster', 'harry')#1
	describe_pet('dog', 'willie')
	
	describe_pet(animal_type='hamster', pet_name='harry')#2
	describe_pet(pet_name='harry', animal_type='hamster')
	In [ ]:
	def describe_pet(pet_name, animal_type='dog'):#3
	    """显示宠物的信息"""
	    print("\nI have a " + animal_type + ".")
	    print("My " + animal_type + "'s name is " + pet_name.title() + ".")
	describe_pet(pet_name='willie')
	describe_pet('willie')
	describe_pet(pet_name='harry', animal_type='hamster')
	describe_pet('harry', 'hamster')
## 8.3返回值 ##
1.使用**return**语句，获取返回值

2.**实参变得可选**

3.返回**字典**

4.**函数和while结合**

	def get_formatted_name(first_name, last_name):
	    """返回整洁的姓名"""
	    full_name = first_name + ' ' + last_name
	    return full_name.title()
	musician = get_formatted_name('jimi', 'hendrix')
	print(musician)


----------

	def get_formatted_name(first_name, last_name, middle_name=''):
	    """返回整洁的姓名"""
	    if middle_name:
	        full_name = first_name + ' ' + middle_name + ' ' + last_name
	    else:
	        full_name = first_name + ' ' + last_name
	    return full_name.title()
	musician = get_formatted_name('jimi', 'hendrix')
	print(musician)
	musician = get_formatted_name('john', 'hooker', 'lee')
	print(musician)

----------

	def build_person(first_name, last_name):
	    """返回一个字典，其中包含有关一个人的信息"""
	    person = {'first': first_name, 'last': last_name}
	    return person
	musician = build_person('jimi', 'hendrix')
	print(musician)


----------

	def get_formatted_name(first_name, last_name):
	    """返回整洁的姓名"""
	    full_name = first_name + ' ' + last_name
	    return full_name.title()
	
	while True:# 这是一个无限循环!
	    print("\nPlease tell me your name:")
	    print("(enter 'q' at any time to quit)")
	    f_name = input("First name: ")
	    if f_name == 'q':
	        break
	    l_name = input("Last name: ")
	    if l_name == 'q':
	        break
	    formatted_name = get_formatted_name(f_name, l_name)
	    print("\nHello, " + formatted_name + "!")
## 8.4传递列表 ##
将列表传递给函数后，函数就能直接访问其内容。下面使用函数来提高处理列表的效率

	def greet_users(names):
	    """向列表中的每位用户都发出简单的问候"""
	    for name in names:
	        msg = "Hello, " + name.title() + "!"
	        print(msg)
	usernames = ['hannah', 'ty', 'margot']
	greet_users(usernames)
1.在**函数中修改列表**：在函数中对这个列表所做的任何修改都是**永久性的**

2.**禁止函数修改列表**:可向函数传递列表的**副本**而不是原件 function_name(list_name[:])

	def print_models(unprinted_designs, completed_models):
	    """
	    模拟打印每个设计，直到没有未打印的设计为止
	    打印每个设计后，都将其移到列表completed_models中
	    """
	    while unprinted_designs:
	        current_design = unprinted_designs.pop()
	        # 模拟根据设计制作3D打印模型的过程
	        print("Printing model: " + current_design)
	        completed_models.append(current_design)
	        
	def show_completed_models(completed_models):
	    """显示打印好的所有模型"""
	    print("\nThe following models have been printed:")
	    for completed_model in completed_models:
	        print(completed_model)
	        
	unprinted_designs = ['iphone case', 'robot pendant', 'dodecahedron']
	completed_models = []
	
	print_models(unprinted_designs, completed_models)
	show_completed_models(completed_models)
	

----------

	print_models(unprinted_designs[:], completed_models)
## 8.5传递任意数量的实参 ##
**在参数前面加 ***

	def make_pizza(*toppings):
	    """概述要制作的比萨"""
	    print("\nMaking a pizza with the following toppings:")
	    for topping in toppings:
	        print("- " + topping)
	make_pizza('pepperoni')
	make_pizza('mushrooms', 'green peppers', 'extra cheese')
### 8.5.1结合使用位置实参和任意数量实参 ###
如果要让函数接受不同类型的实参，**必须在函数定义中将接纳任意数量实参的形参放在最后**。Python先匹配位置实参和关键字实参，再将余下的实参都收集到最后一个形参中

	def make_pizza(size, *toppings):
	    """概述要制作的比萨"""
	    print("\nMaking a " + str(size) +
	          "-inch pizza with the following toppings:")
	    for topping in toppings:
	        print("- " + topping)
	make_pizza(16, 'pepperoni')
	make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
### 8.5.2 使用任意数量的关键字实参 ###
形参** user_info 中的两个星号让Python创建一个名为user_info 的空字典


	def build_profile(first, last, **user_info):
	    """Build a dictionary containing everything we know about a user."""
	    profile = {}
	    profile['first_name'] = first
	    profile['last_name'] = last
	    for key, value in user_info.items():
	        profile[key] = value
	    return profile
	
	user_profile = build_profile('albert', 'einstein',
	                             location='princeton',
	                             field='physics')
	print(user_profile)
## 8.6函数存储在模块中 ##
类似C语言中，将函数存储在C文件中

import语句允许在当前运行的程序文件中使用模块中的代码（C语言中是include）

### 8.6.1导入方法 ###
1.导入整个模块：**import module_name**

通过**module_name.function_name()** 来调用文件中的任何一个函数

2.导入模块中的所有函数:**from module_name import ***

由于导入了每个函数，可通过名称来调用每个函数，而无需使用句点表示法

然而，**使用并非自己编写的大型模块时，最好不要采用这种导入方法**：如果模块中有函数的名称与你的项目中使用的名称相同，可能导致意想不到的结果：**Python可能遇到多个名称相同的函数或变量，进而覆盖函数**，而不是分别导入所有的函数

3.使用as 给模块指定别名：**import module_name as mn**

4.导入特定的函数：**from module_name import function_name**和

**from module_name import function_0, function_1, function_2**

5.使用as 给函数指定别名：**from module_name import function_name as fn**

	def make_pizza(size, *toppings):#pizza.py文件
	    """概述要制作的比萨"""
	    print("\nMaking a " + str(size) +
	        "-inch pizza with the following toppings:")
	    for topping in toppings:
	        print("- " + topping)

----------

	'''1.导入整个模块
	making_pizzas.py文件
	'''
	import pizza
	
	pizza.make_pizza(16, 'pepperoni')
	pizza.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

----------
	'''2.导入模块中的所有函数'''
	from pizza import *
	make_pizza(16, 'pepperoni')
	make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

----------
	'''3.使用as 给模块指定别名'''
	import pizza as p
	
	p.make_pizza(16, 'pepperoni')
	p.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

----------
	'''4.导入特定的函数'''
	from pizza import make_pizza
	
	make_pizza(16, 'pepperoni')
	make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

----------
	'''5.使用as 给函数指定别名'''
	from pizza import make_pizza as mp
	
	mp(16, 'pepperoni')
	mp(12, 'mushrooms', 'green peppers', 'extra cheese')
# 9.类 #
根据类来创建对象被称为实例化 ，这让你能够使用类的实例。

1.编写一些类并创建其实例。

2.指定可在实例中存储什么信息，定义可对这些实例执行哪些操作。

3.编写一些类来扩展既有类的功能，让相似的类能够高效地共享代码。

4.把自己编写的类存储在模块中，并在自己的程序文件中导入其他人编写的类。

## 9.1创建和使用类 ##
### 9.1.1创建Dog类 ###
在Python中，首字母大写的名称指的是类。

这个类定义中的括号是空的，因为我们要从空白创建这个类

	 class Dog():
	    """一次模拟小狗的简单尝试"""
	    
	    def __init__(self, name, age):
	        """初始化属性name和age"""
	        self.name = name
	        self.age = age
	        
	    def sit(self):
	        """模拟小狗被命令时蹲下"""
	        print(self.name.title() + " is now sitting.")
	        
	    def roll_over(self):
	        """模拟小狗被命令时打滚"""
	        print(self.name.title() + " rolled over!")
类中的函数称为方法；前面有关函数的一切都适用于方法，唯一的差别就是调用方法的方式

1.**方法init()**

**init()** 是一个特殊的方法，每当你根据Dog 类创建新实例时，Python都会自动运行它。在这个方法的名称中，**开头和末尾各有两个下划线**，这是一种约定，旨在避免Python默认方法与普通方法发生名称冲突

方法**init()** 定义成了包含三个形参：self 、name 和age。**形参self 必不可少，还必须位于其他形参的前面**。因为Python调用这个**init()** 方法来创建Dog 实例时，将自动传入实参self 。每个与类相关联的方法调用都自动传递实参self ，它是一个指向实例本身的引用，让实例能够访问类中的属性和方法。

我们将通过实参向Dog() 传递名字和年龄；self 会自动传递，因此我们不需要传递它。每当我们根据Dog 类创建实例时，都只需给最后两个形参（name 和age）提供值。

定义的两个变量都有前缀self 。以self 为前缀的变量都可供类中的所有方法使用，我们还可以通过类的任何实例来访问这些变量。self.name = name 获取存储在形参name 中的值，并将其存储到变量name 中，然后该变量被关联到当前创建的实例。像这样可通过实例访问的变量称为属性 。

### 9.1.2根据类创建实例 ###

	class Dog():
	    --snip--
	my_dog = Dog('willie', 6)
	print("My dog's name is " + my_dog.name.title() + ".")
	print("My dog is " + str(my_dog.age) + " years old.")
通常可以认为首字母大写的名称（如Dog ） 指的是类，而小写的名称（如my_dog ） 指的是根据类创建的实例。

Python使用实参'willie' 和6 调用Dog 类中的方法**init()**

方法**init() **并未显式地包含return 语句，但Python自动返回一个表示这条小狗的实例。

访问属性和调用方法：句点法my_dog.name

## 9.2使用类和实例 ##
### 9.2.1给属性指定默认值 ###

	class Car():
		def __init__(self, make, model, year):
			"""初始化描述汽车的属性"""
			self.make = make
			self.model = model
			self.year = year
			self.odometer_reading = 0

		def read_odometer(self):
			"""打印一条指出汽车里程的消息"""
			print("This car has " + str(self.odometer_reading) + " miles on it.")
创建一个名为odometer_reading 的属性，并将其初始值设置为0。还定义了一个名为ead_odometer() 的方法，获悉汽车的里程。
### 9.2.2修改属性值 ###
1. 直接修改

	my_new_car.odometer_reading = 23
2. 通过方法修改
3. 通过方法递增

	class Car():
		--snip--
		
		def update_odometer(self, mileage):
			"""将里程表读数设置为指定的值"""
			self.odometer_reading = mileage

		def increment_odometer(self, miles):
			"""将里程表读数增加指定的量"""
			self.odometer_reading += miles

## 9.3继承 ##
如果你要编写的类是另一个现成类的特殊版本，可使用继承 。一个类继承 另一个类时，它将自动获得另一个类的所有属性和方法；原有的类称为父类/超类，而新类称为子类 。子类继承了其父类的所有属性和方法，同时还可以定义自己的属性和方法。

### 9.3.1子类的方法__init__() ###
Car类是父类，ElectricCar类是子类，父类必须在子类前面。
定义子类时，必须在括号内指定父类的名称。方法__init__() 接受创建Car实例所需的信息。
**super()**函数使父类和子类关联起来

	class Car():
		--snip--

	class ElectricCar(Car):
		"""电动汽车的独特之处"""
		def __init__(self, make, model, year):
			"""初始化父类的属性"""
			super().__init__(make, model, year)

### 9.3.2给子类定义属性和方法 ###

	class Car():
		--snip--
	class ElectricCar(Car):
		
		def __init__(self, make, model, year):
			"""
			电动汽车的独特之处
			初始化父类的属性，再初始化电动汽车特有的属性
			"""
			super().__init__(make, model, year)
			self.battery_size = 70

		def describe_battery(self):
			"""打印一条描述电瓶容量的消息"""
			print("This car has a " + str(self.battery_size) + "-kWh battery.
其中新加属性self.battery_size,还新加新方法describe_battery()

### 9.3.3重写父类的方法 ###
假设Car类中有一个fill_gas_tank() 的方法，它对全电动汽车来说毫无意义，因此你可能想重写它。

	def ElectricCar(Car):
		--snip--
		def fill_gas_tank():
			"""电动汽车没有油箱"""
			print("This car doesn't need a gas tank!")
### 9.3.4将实例用做属性 ###
类中的属性可以用类来表示
将大型类拆分成多个协同工作的小类。例如，不断给ElectricCar 类添加细节时，我们可能会发现其中包含很多专门针对汽车电瓶的属性和方法。在这种情况下，我们可将这些属性和方法提取出来，放到另一个名为attery 的类中，并将一个Battery 实例用作ElectricCar 类的一个属性：

	class Car():
		--snip--
	class Battery():
		"""一次模拟电动汽车电瓶的简单尝试"""
		def __init__(self, battery_size=70):
			"""初始化电瓶的属性"""
			self.battery_size = battery_size
		def describe_battery(self):
			"""打印一条描述电瓶容量的消息"""
			print("This car has a " + str(self.battery_size) + "-kWh battery."
	class ElectricCar(Car):
		"""电动汽车的独特之处"""
		def __init__(self, make, model, year):
			"""
			初始化父类的属性，再初始化电动汽车特有的属性
			"""
			super().__init__(make, model, year)
			self.battery = Battery()
	my_tesla = ElectricCar('tesla', 'model s', 2016)
	print(my_tesla.get_descriptive_name())
	my_tesla.battery.describe_battery()

在ElectricCar 类中，我们添加了一个名为self.battery 的属性，创建一个新的Battery实例

**PS**：
1. def __init__(self, battery_size=70):   左右两边是两条下划线
2. class ElectricCar(Car):    子类类名后面的括号需要填写父类
3. super().__init__(make, model, year)    继承父类这部分不要写self

## 9.4导入类 ##
### 9.4.1导入单个类 ###
和include差不多，将类单独写在一个文件中，在其他文件中使用include导入

在car.py文件中，只包含Car类的代码：

	class Car():
		"""一次模拟汽车的简单尝试"""

		def __init__(self, make, model, year):
			"""初始化描述汽车的属性"""
			self.make = make
			self.model = model
			self.year = year
			self.odometer_reading = 0

		def get_descriptive_name(self):
			"""返回整洁的描述性名称"""
			long_name = str(self.year) + ' ' + self.make + ' ' + self.model
			return long_name.title()

		def read_odometer(self):
			"""打印一条消息，指出汽车的里程"""
			print("This car has " + str(self.odometer_reading) + " miles on it.")

		def update_odometer(self, mileage):
			"""
			将里程表读数设置为指定的值
			拒绝将里程表往回拨
			"""
			if mileage >= self.odometer_reading:
			self.odometer_reading = mileage
			else:
			print("You can't roll back an odometer!")

		def increment_odometer(self, miles):
			"""将里程表读数增加指定的量"""
			self.odometer_reading += miles
在my_car.py文件中，导入Car类并创建实例：**from car import Car**

	from car import Car

	my_new_car = Car('audi', 'a4', 2016)

	print(my_new_car.get_descriptive_name())
	my_new_car.odometer_reading = 23
	my_new_car.read_odometer()
### 9.4.2在一个模块中存储多个类 ###
在car.py文件中，包含Car类，Battery类和ElectricCar类

	class Car():
		--snip--

	class Battery():
		"""一次模拟电动汽车电瓶的简单尝试"""

		def __init__(self, battery_size=60):
			"""初始化电瓶的属性"""
			self.battery_size = battery_size

		def describe_battery(self):
			"""打印一条描述电瓶容量的消息"""
			print("This car has a " + str(self.battery_size) + "-kWh battery.")

		def get_range(self):
			"""打印一条描述电瓶续航里程的消息"""
			if self.battery_size == 70:
				range = 240
			elif self.battery_size == 85:
				range = 270

			message = "This car can go approximately " + str(range)
			message += " miles on a full charge."
			print(message)

	class ElectricCar(Car):
		"""模拟电动汽车的独特之处"""

		def __init__(self, make, model, year):
			"""
			初始化父类的属性，再初始化电动汽车特有的属性
			"""
			super().__init__(make, model, year)
			self.battery = Battery()
在my_electric_car.py文件中，导入ElectricCar类并创建实例

	from car import ElectricCar

	my_tesla = ElectricCar('tesla', 'model s', 2016)

	print(my_tesla.get_descriptive_name())
	my_tesla.battery.describe_battery()
	my_tesla.battery.get_range()
### 9.4.3从一个模块中导入多个类 ###
在my_car.py文件中，导入Car类和ElectricCar类并创建实例:**from car import Car, ElectricCar**

	from car import Car, ElectricCar
	
	my_beetle = Car('volkswagen', 'beetle', 2016)	
	print(my_beetle.get_descriptive_name())

	my_tesla = ElectricCar('tesla', 'roadster', 2016)
	print(my_tesla.get_descriptive_name())

**PS**
导入多个类时，要用**逗号**隔开，不能用空格

### 9.4.4导入整个模块 ###

导入整个模块，再使用句点表示法访问需要的类.在my_car.py文件中，导入整个car模块:**import car**

	import car

	my_beetle = car.Car('volkswagen', 'beetle', 2016)
	print(my_beetle.get_descriptive_name())

	my_tesla = car.ElectricCar('tesla', 'roadster', 2016)
	print(my_tesla.get_descriptive_name())

### 9.4.5导入模块中所有的类 ###

<b>from module_name import *</b>

**不推荐使用这种方法**

1.不清楚到底导入了哪些类
	
2.容易出现同名
	

### 9.4.6在一个模块中导入另一个模块 ###

Car类存储在一个模块car.py中，并将ElectricCar类和Battery类存储在另一个模块electric_car.py中

在car.py文件中

	class Car():
		--snip--

在electric_car.py文件中

	from car import Car

		class Battery():
			--snip--

		class ElectricCar(Car):
			--snip--

在my_cars.py文件中

	from car import Car
	from electric_car import ElectricCar

	my_beetle = Car('volkswagen', 'beetle', 2016)
	print(my_beetle.get_descriptive_name())

	my_tesla = ElectricCar('tesla', 'roadster', 2016)
	print(my_tesla.get_descriptive_name())

## 9.5Python标准库 ##

[http://pymotw.com/ ](http://pymotw.com/ )

## 9.6类编码风格 ##

类名应采用驼峰命名法 ，即将类名中的每个单词的首字母都大写，而不使用下划线。实例名和模块名都采用小写格式，并在单词之间加上下划线

对于每个类，都应紧跟在类定义后面包含一个文档字符串

在类中，可使用一个空行来分隔方法；而在模块中，可使用两个空行来分隔类

需要同时导入标准库中的模块和你编写的模块时，先编写导入标准库模块的import 语句，再添加一个空行，然后编写导入你自己编写的模块的import 语句

# 10文件和异常 #

pi_digits.txt文件中
		3.1415926535
		8979323846
		2643383279

### 10.1从文件中读取数据 ###

	with open('pi_digits.txt') as file_object:
		contents = file_object.read()
		print(contents)
函数open() 接受一个参数：要打开的文件的名称。Python在当前执行的文件所在的目录中查找指定的文件

关键字with 在不再需要访问文件后将其关闭，可让Python去确定：你只管打开文件，并在需要时使用它，Python自会在合适的时候自动将其关闭。

也可以使用open()和close()函数操作文件开启和关闭

**末尾多了一个空行**。为何会多出这个空行呢？因为read() 到达文件末尾时返回一个空字符串，而将这个空字符串显示出来时就是一个空行。要删除多出来的空行，可在print 语句中使用**rstrip()**


### 10.1.2文件路径 ###
相对路径
绝对路径

### 10.1.3逐行读取 ###

	filename = 'pi_digits.txt'

	with open(filename) as file_object:
		for line in file_object:
			print(line.rstrip())

### 10.1.4创建一个包含文件各行内容的列表 ###
readlines() 从文件中读取每一行，并将其存储在一个列表中

	filename = 'pi_digits.txt'

	with open(filename) as file_object:
		lines = file_object.readlines()
	for line in lines:
		print(line.rstrip())

### 10.1.5使用文件的内容 ###

	filename = 'pi_digits.txt'

	with open(filename) as file_object:
		lines = file_object.readlines()

	pi_string = ''
	for line in lines:
		pi_string += line.rstrip()

	print(pi_string)
	print(len(pi_string))

### 10.1.6包含一百万位的大型文件 ###

	filename = 'pi_million_digits.txt'

	with open(filename) as file_object:
		lines = file_object.readlines()

	pi_string = ''
	for line in lines:
		pi_string += line.strip()

	print(pi_string[:52] + "...")
	print(len(pi_string))

### 10.1.7圆周率包含你的生日吗 ###

**if birthday in pi_string:**

	filename = 'pi_million_digits.txt'
	
	with open(filename) as file_object:
		lines = file_object.readlines()

	pi_string = ''
	for line in lines:
		pi_string += line.rstrip()

	birthday = input("Enter your birthday, in the form mmddyy: ")
	if birthday in pi_string:
		print("Your birthday appears in the first million digits of pi!")
	else:
		print("Your birthday does not appear in the first million digits of pi.")

## 10.2写入文件 ##
### 10.2.1 写入空文件 ###
**Python只能将字符串写入文本文件**

	filename = 'programming.txt'
	
	with open(filename, 'w') as file_object:
		file_object.write("I love programming.")
### 10.2.2 写入多行 ###

	filename = 'programming.txt'
	with open(filename, 'w') as file_object:
		file_object.write("I love programming.\n")
		file_object.write("I love creating new games.\n")

### 10.2.3 附加到文件 ###

	filename = 'programming.txt'
	with open(filename, 'a') as file_object:
		file_object.write("I also love finding meaning in large datasets.\n")
		file_object.write("I love creating apps that can run in a browser.\n")

## 10.3 异常 ##
Python使用被称为异常 的特殊对象来管理程序执行期间发生的错误。
每当发生让Python不知所措的错误时，它都会创建一个异常对象。
如果你编写了处理该异常的代码，程序将继续运行；如果你未对异常进行处理，程序将停止，并显示一个traceback，其中包含有关异常的报告。

### 10.3.1处理ZeroDivisionError 异常 ###
	
	print(5/0)

### 10.3.2 try-except 代码块 ###

	try:
		print(5/0)
	except ZeroDivisionError:
		print("You can't divide by zero!")

### 10.3.3 try-except-els 代码块 ###
	
	print("Give me two numbers, and I'll divide them.")
	print("Enter 'q' to quit.")
	while True:
		first_number = input("\nFirst number: ")
		if first_number == 'q':
			break
		second_number = input("Second number: ")
		try:
			answer = int(first_number) / int(second_number)
		except ZeroDivisionError:
			print("You can't divide by 0!")
		else:
			print(answer)

### 10.3.4 处理FileNotFoundError 异常 ###

**找不到文件**

	filename = 'alice.txt'
	with open(filename) as f_obj:
		contents = f_obj.read()

----------
	
	filename = 'alice.txt'
	try:
		with open(filename) as f_obj:
			contents = f_obj.read()
	except FileNotFoundError:
		msg = "Sorry, the file " + filename + " does not exist."
		print(msg)

### 10.3.5 分析文本 ###

	filename = 'alice.txt'
	try:
		with open(filename) as f_obj:
			contents = f_obj.read()
	except FileNotFoundError:
		msg = "Sorry, the file " + filename + " does not exist."
		print(msg)
	else:
		'''计算文件大致包含多少个单词'''
		words = contents.split()
		num_words = len(words)
		print("The file " + filename + " has about " + str(num_words) + " words.")

### 10.3.6 使用多个文件 ###
	
	def count_words(filename):
		"""计算一个文件大致包含多少个单词"""
		try:
			with open(filename) as f_obj:
				contents = f_obj.read()
		except FileNotFoundError:
			msg = "Sorry, the file " + filename + " does not exist."
			print(msg)
		else:
			''' 计算文件大致包含多少个单词'''
			words = contents.split()
			num_words = len(words)
			print("The file " + filename + " has about " + str(num_words) +			" words.")
	filenames = ['alice.txt', 'siddhartha.txt', 'moby_dick.txt', 'little_women.txt']
	for filename in filenames:
		count_words(filename)

### 10.3.7 失败时一声不吭 ###
	
	except FileNotFoundError:
		pass

## 10.4 存储数据 ##
### 10.4.1 使用json.dump() 和json.load() ###
	
	import json
	numbers = [2, 3, 5, 7, 11, 13]
	filename = 'numbers.json'
	with open(filename, 'w') as f_obj:
		json.dump(numbers, f_obj)

----------

	import json
	filename = 'numbers.json'
	with open(filename) as f_obj:
		numbers = json.load(f_obj)
	print(numbers)

### 10.4.2 重构 ###
代码能够正确地运行，但可做进一步的改进——将代码划分为一系列完成具体工作的函数

# 11测试代码 #
使用Python模块unittest 中的工具来测试代码

## 11.1 测试函数 ##

### 11.1.1 单元测试和测试用例 ###

单元测试 用于核实函数的某个方面没有问题；

测试用例 是一组单元测试，这些单元测试一起核实函数在各种情形下的行为都符合要求

name_function.py文件

	def get_formatted_name(first, last):
	    """Generate a neatly formatted full name."""
	    full_name = first + ' ' + last
	    return full_name.title()

		
### 11.1.2 可通过的测试 ###	

要为函数编写测试用例，可先导入模块unittest 以及要测试的函数，

再创建一个继承unittest.TestCase 的类，并编写一系列方法对函数行为的不同方面进行测试。	

test_name_function.py文件

	import unittest
	from name_function import get_formatted_name

	class NamesTestCase(unittest.TestCase):
		"""测试name_function.py"""
		def test_first_last_name(self):
			"""能够正确地处理像Janis Joplin这样的姓名吗？"""
			formatted_name = get_formatted_name('janis', 'joplin')
			self.assertEqual(formatted_name, 'Janis Joplin')
	unittest.main()	

### 11.1.3 不能通过的测试 ###		

name_function.py文件

	def get_formatted_name(first, middle, last):
		"""生成整洁的姓名"""
		full_name = first + ' ' + middle + ' ' + last
		return full_name.title()	

### 11.1.4 测试未通过时怎么办 ###	
	
name_function.py文件
	
	def get_formatted_name(first, last, middle=''):
		"""生成整洁的姓名"""
		if middle:
			full_name = first + ' ' + middle + ' ' + last
		else:
			full_name = first + ' ' + last
		return full_name.title()

### 11.1.5 添加新测试 ###

test_name_function.py文件

	import unittest
	from name_function import get_formatted_name

	class NamesTestCase(unittest.TestCase):
		"""测试name_function.py """

		def test_first_last_name(self):
			"""能够正确地处理像Janis Joplin这样的姓名吗？"""
			formatted_name = get_formatted_name('janis', 'joplin')
			self.assertEqual(formatted_name, 'Janis Joplin')

		def test_first_last_middle_name(self):
		"""能够正确地处理像Wolfgang Amadeus Mozart这样的姓名吗？"""
		formatted_name = get_formatted_name('wolfgang', 'mozart', 'amadeus')
		self.assertEqual(formatted_name, 'Wolfgang Amadeus Mozart')

	unittest.main()

## 11.2 测试类 ##

### 11.2.1 各种断言方法 ###

|方法 | 用途| 
| ------ | ------ |
|assertEqual(a, b) | 核实a == b|
|assertNotEqual(a, b) | 核实a != b|
|assertTrue(x) | 核实x 为True|
|assertFalse(x) | 核实x 为False|
|assertIn(item , list ) | 核实 item 在 list 中|
|assertNotIn(item , list )| 核实 item 不在 list 中|

### 11.2.4 方法setUp() ###
使用setUp() 来创建一个调查对象和一组答案，
供方法test_store_single_response() 和
test_store_three_responses() 使用

	import unittest
	from survey import AnonymousSurvey

	class TestAnonymousSurvey(unittest.TestCase):
		"""针对AnonymousSurvey类的测试"""

		def setUp(self):
			"""
			创建一个调查对象和一组答案，供使用的测试方法使用
			"""
			question = "What language did you first learn to speak?"
			self.my_survey = AnonymousSurvey(question)
			self.responses = ['English', 'Spanish', 'Mandarin']

		def test_store_single_response(self):
			"""测试单个答案会被妥善地存储"""
			self.my_survey.store_response(self.responses[0])
			self.assertIn(self.responses[0], self.my_survey.responses)

		def test_store_three_responses(self):
			"""测试三个答案会被妥善地存储"""
			for response in self.responses:
				self.my_survey.store_response(response)
			for response in self.responses:
				self.assertIn(response, self.my_survey.responses)

	unittest.main()

方法setUp() 做了两件事情：创建一个调查对象；创建一个答案列表

**PS** 
运行测试用例时，每完成一个单元测试，Python都打印一个字符：测试通过时打印一个句点；测试引发错误时打印一个E ；测试导致断言失败时打印一个F 。这就是你运行测试用例时，在输出的第一行中看到的句点和字符数量各不相同的原因。