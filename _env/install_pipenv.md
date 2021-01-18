# Installation Notes for pipenv on Ubuntu 18.04

#### 1. Add `~/.local/bin` to `PATH`


[https://github.com/pypa/pipenv/issues/2122#issuecomment-386207878](https://github.com/pypa/pipenv/issues/2122#issuecomment-386207878)
```
echo 'export PATH="${HOME}/.local/bin:$PATH"' >> ~/.bashrc
```

#### 2. Install pip if not already installed

Python3
```
sudo apt install python3-pip
```

Python 2
```
sudo apt install python-pip
```


#### 3. Install pipenv

for Python3:
```
python3 -m pip install --user pipenv
```

or for python2:
```
python -m pip install --user pipenv
```

#### Troubleshooting and removal

Installing pipenv will break pip, and attempting to use pip after a pipenv install will likely result in:

```
Traceback (most recent call last):
  File "/usr/bin/pip", line 9, in <module>
    from pip import main
ImportError: cannot import name main
```

If installation fails and pip cannot be restored. Completely remove pip and reinstall:


Python 3
```
sudo apt remove python3-pip
sudo rm -rf ~/.local/lib/python3.6/site-packages/pip*
sudo apt install python3-pip

```

Python 2
```

sudo apt remove python-pip
sudo rm -rf ~/.local/lib/python2.7/site-packages/pip*
sudo apt install python-pip

```

