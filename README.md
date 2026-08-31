1 CS

def encrypt(text, shift): result = "" for char in text: if char.isalpha(): if char.isupper(): result += chr((ord(char) - 65 + shift) % 26 + 65) else: result += chr((ord(char) - 97 + shift) % 26 + 97) else: result += char return resultdef decrypt(text, shift): return encrypt(text, -shift)text = input("Enter Plain Text: ")shift = int(input("Enter Shift Value: "))cipher = encrypt(text, shift)print("Encrypted Text:", cipher)plain = decrypt(cipher, shift)print("Decrypted Text:", plain)


2 AC

alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"key = "QWERTYUIOPASDFGHJKLZXCVBNM"plain = input("Enter Plain Text: ").upper()cipher = ""for ch in plain: if ch in alphabet: cipher += key[alphabet.index(ch)] else: cipher += chprint("Encrypted:", cipher)decrypt = ""for ch in cipher: if ch in key: decrypt += alphabet[key.index(ch)] else: decrypt += chprint("Decrypted:", decrypt)


3 VC

def generateKey(text, key): key = list(key) if len(text) == len(key): return("".join(key)) else: for i in range(len(text) - len(key)): key.append(key[i % len(key)]) return("".join(key))def encrypt(text, key): cipher = [] for i in range(len(text)): x = (ord(text[i]) + ord(key[i])) % 26 x += 65 cipher.append(chr(x)) return("".join(cipher))def decrypt(cipher, key): plain = [] for i in range(len(cipher)): x = (ord(cipher[i]) - ord(key[i]) + 26) % 26 x += 65 plain.append(chr(x)) return("".join(plain))text = input("Enter Text: ").upper()key = input("Enter Key: ").upper()key = generateKey(text, key)cipher = encrypt(text, key)print("Encrypted:", cipher)plain = decrypt(cipher, key)print("Decrypted:", plain)


4 PC

def encrypt(text): text = text.upper().replace(" ", "") if len(text) % 2 != 0: text += "X" cipher = "" for i in range(0, len(text), 2): cipher += chr((ord(text[i]) - 65 + 3) % 26 + 65) cipher += chr((ord(text[i+1]) - 65 + 3) % 26 + 65) return cipherplain = input("Enter Message: ")cipher = encrypt(plain)print("Encrypted:", cipher)


5 HC

import numpy as nptext = input("Enter Text (4 letters): ").upper()if len(text) % 2 != 0: text += "X"cipher = ""for i in range(0, len(text), 2): pair = np.array([[ord(text[i]) - 65], [ord(text[i+1]) - 65]]) result = np.dot(key, pair) % 26 cipher += chr(result[0][0] + 65) cipher += chr(result[1][0] + 65)print("Encrypted:", cipher)



6 SDC

plain = input("Enter Text: ")single = plain[::-1]print("Single Transposition:", single)double = single[::-1]print("Double Transposition:", double)
