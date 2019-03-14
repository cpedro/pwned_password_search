# Is my password pwned?

Python script that checks a password against the
[Have I Been Pwned](https://haveibeenpwned.com/) database, and reports back on
whether or not it has been listed.

You may need to install the `requests` module first before running.
```
$ pip install requests
```
**OR**
```
$ pip3 install requests
```

This method may be preferable to putting your password directly into the site
because this script only sends the first 5 characters of the SHA1 hash of your
password over the internet instead of your whole password or hash.

For more info see the
[API docs](https://haveibeenpwned.com/API/v2#SearchingPwnedPasswordsByRange)

This script was inspired by Computerphile's 
[YouTube video](https://youtu.be/hhUb5iknVJs) featuring 
[Mike Pound](https://github.com/mikepound), and later I took some code from the 
Python script [he wrote](https://github.com/mikepound/pwned-search) that does 
the same thing.

## Running:
* Prompts you for a single password (echo off):
  ```
  $ python is_it_pwned.py
  ```
* Reads passwords from a file:
  ```
  $ python is_it_pwned.py < file
  ```
* Reads passwords written to standard output by another command:
  ```
  $ cmd | is_it_pwned pwned.py
  ```
* Checks passwords given command line arguments: (**Beware** the password may be
  saved in shell history and that other users on the system may be able to observe
  the command line.)
  ```
  $ python is_it_pwned.py <password1> [<password2> ...]
  ```
