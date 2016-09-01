# Hash generator
You can use this tool to generate password hashes of different types and the john or hashcat commands you need to crack them. Before trying to crack a generated hash it may be a good idea to use the "estimator.rb" too to check if your hash is likely to be cracked in any reasonable amount of time.

## Usage
Run the ruby script with no special parameters:
```
ruby generator.rb
```

The script will prompt you for any information it requires, such as hash types and attack methods. It will write a file to the current working directory containing the generated hash and output the command to crack it in the terminal.

## Notes on bcrypt
In order to make the password cracking a little more manageable for bcrypt hashes there is a bcrypt_reduced option available in the algorithms. The default work factor has been brought down from 10 to 5. This reduces the memory requirement and processing time required for bcrypt hashes. Though the default work factor for bcrypt hashes is usually 10, allowing you to generate hashes with a work factor of 5 makes it possible to experiment with bcrypt hashes on some lower end hardware too.

## Notes on scrypt
Scrypt hash generation is mostly broken right now. For hashcat it might work, I'm not entirely sure. For john it's definitely broken. 