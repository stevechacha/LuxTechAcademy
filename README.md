# LuxTechAcademy
How to write python password generator

### Python password generator

### steps creating random string
### 1.Import string and random module

The string module contains various string constant which contains the ASCII characters of all cases.
It has separate constants for lowercase, uppercase letters, digits, and special symbols, which we use as a source to generate a random string.
Pass string constants as a source of randomness to the random module to create a random string

```python
import random
import string
```

### 2.Use the string constant ascii_lowercase
The``string.ascii_lowercase`` returns a list of all the lowercase letters from ‘a’ to ‘z’. This data will be used as a source to generate random characters.Decide the length of a string
Decide how many characters you want in the resultant string.

### 3.Use a for loop and random choice() function to choose characters from a source
Execute a for loop till the decided string length and use the ` random.choice() `function in each iteration to pick a single character from the string constant and add it to the string variable using a` join()` function. print the final string after loop competition

### 4.Generate a random Password
Use the `string.ascii_letters`,` string.digits`, and `string.punctuation` constants together to create a random password and repeat the first four steps.


String Constants
Constant	                                              Description

`ascii_lowercase`	                   Contain all lowercase letters
`ascii_uppercase`	                   Contain all uppercase letters
`ascii_letters	`                   Contain both lowercase and uppercase letters
`digits`                           Contain digits ‘0123456789’.
`punctuation`                    All special symbols !”#$%&'()*+,-./:;<=>?@[\]^_`{|}~.



```python
import random
import string

def get_random_string(length):
    # choose from all lowercase letter
    letters = string.ascii_lowercase
    result_str = ''.join(random.choice(letters) for i in range(length))
    print("Random string of length", length, "is:", result_str)

get_random_string(8)
get_random_string(6)
get_random_string(4)

```
### output get_random_string(8)
```
wzqhyhtc

```
### output get_random_string(6)
```
 goxsfl

```
### output get_random_string(4)
```
dfci

```

```python
#import the necessary modules!
import random
import string

print('hello, Welcome to Password generator!')

#input the length of password
length = int(input('\nEnter the length of password: '))                      

#define data
lower = string.ascii_lowercase
upper = string.ascii_uppercase
num = string.digits
symbols = string.punctuation
#string.ascii_letters

#combine the data
all = lower + upper + num + symbols

#use random 
temp = random.sample(all,length)

#create the password 
password = "".join(temp)

#print the password
print(password)

```
### output
```

tc8U<:`'dp
```
#### Random String of Lower Case and Upper Case Letters

In Python, to generate a random string with the combination of` lowercase `and `uppercase letters`, we need to use the `string.ascii_letters` constant as the source. 
This constant contains all the lowercase and uppercase letters.

```python
import random
import string

def get_random_string(length):
    # With combination of lower and upper case
    result_str = ''.join(random.choice(string.ascii_letters) for i in range(length))
    # print random string
    print(result_str)

# string of length 8
get_random_string(8)
get_random_string(8)
```

### output
```
dPRUSiDy

wsHaeUxv

```

### Random string of specific letters
If you wanted to generate a random string from a fixed set of characters, please use the following example.

```python
import random

# Random string of length 5
result_str = ''.join((random.choice('abcdxyzpqr') for i in range(5)))
print(result_str)
```

### output 
```
rxaxq
```
### Random String without Repeating Characters
Note: The `choice()` method can repeat characters. If you don’t want repeated characters in a resultant string, then use the random.sample() method.

```python
import random
import string

for i in range(3):
    # get random string of length 6 without repeating letters
    result_str = ''.join(random.sample(string.ascii_lowercase, 8))
    print(result_str)
    
 
 ```
    
### output 
  ```
  gmhvjaif
  ehxislun
  chkeoavt
  
  ```
 ####   Create Random Password with Special characters, letters, and digits
A password that contains a combination of characters, digits, and special symbols is considered a strong password.


### Generate a random string token
We can use` secrets.token_hex()` to get a secure random text in hexadecimal format.
```python
import secrets
print("Secure hexadecimal string token", secrets.token_hex(32))
```
### output
```
0544c9c492e0cda52d7ba7f0ce78f1fa58467fc9d420c3b9a79c4553c47b29ef
```

### Generate universally unique secure random string Id
The random string generated using a UUID module is suitable for the Cryptographically secure application. The UUID module has various functions to do this. Here in this example, we are using a ` uuid4() function ` to generate a random string Id.

```python
import uuid
stringId  = uuid.uuid4()
print("Secure unique string id", stringId)
```

### output
```
2fe6001a-3c06-455e-ac3d-672e60aa093b
```

### Use the StringGenerator module to generate a random string
The StringGenerator module is not a part of a standard library. However, if you want you can install it using pip and start using it.

Steps: –

pip install StringGenerator.
Use a ` render() function `of StringGenerator to generate randomized strings of characters using a template

```python
import strgen

random_str = strgen.StringGenerator("[\w\d]{10}").render()
print(random_str)
# Output 4VX1yInC9S

random_str2 = strgen.StringGenerator("[\d]{3}&[\w]{3}&[\p]{2}").render()
print(random_str2)
```


### output
```
X2iQYH8t84
83WFm*4;

```

### Random alphanumeric string with a fixed count of letters and digits

```python
import random
import string

def get_string(letters_count, digits_count):
    letters = ''.join((random.choice(string.ascii_letters) for i in range(letters_count)))
    digits = ''.join((random.choice(string.digits) for i in range(digits_count)))

    # Convert resultant string to list and shuffle it to mix letters and digits
    sample_list = list(letters + digits)
    random.shuffle(sample_list)
    # convert list to string
    final_string = ''.join(sample_list)
    print('Random string with', letters_count, 'letters', 'and', digits_count, 'digits', 'is:', final_string)

get_string(5, 3)


get_string(6, 2)
```

### Output get_string(5, 3)
```
 g0GE99wG
```
### Output get_string(6, 2)
```
1Wh0XzyY

```



