# **Morse code converter**
## what is morse codde:
Morse code is a way of encrypting the text into a dot and a line. It is one of the old methods for secret message hiding. For more information on this read [here](https://en.wikipedia.org/wiki/Morse_code)  
# Diagram for morse code used in the code
![diagram for morse](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b5/International_Morse_Code.svg/260px-International_Morse_Code.svg.png)
# Requirements
* python 3
* python ide 
# Algorithm
This code used two fuction encryptor and decryptor with the manipulaton of space. Feth data in dict using `.get` method for faster and efficient searching.
### Encryptor function
```pyhton
def encryptor(text):
    encrypted_text = ""
    for letters in text:
        if letters != " ":
            encrypted_text = encrypted_text + MORSE_CODE_DICT.get(letters) + " "
        else:
            encrypted_text += " "
    print(encrypted_text)
```
### Decryptor function
```pyhton
# function for decryption 
def decryptor(text):
    text += " "
    key_list = list(MORSE_CODE_DICT.keys())
    val_list = list(MORSE_CODE_DICT.values())
    morse = ""
    normal = ""
    for letters in text:
        if letters != " ":
            morse += letters
            space_found = 0
        else:
            space_found += 1
            if space_found == 2:
                normal += " "
            else:
                normal = normal + key_list[val_list.index(morse)]
                morse = ""
    print(normal)
```