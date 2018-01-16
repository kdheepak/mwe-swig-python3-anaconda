 # MWE for error with python3 from anaconda

https://stackoverflow.com/questions/48289858/fatal-error-in-extension-pythreadstate-get-no-current-thread-when-using-swig-w

### Install

```bash
$ swig -python test.i # (optional)
$ cc -c $(python3-config  --cflags) test.c test_wrap.c
$ cc -bundle -L/Users/$USER/miniconda3/lib/python3.6/config-3.6m-darwin -lpython3.6m -ldl test.o test_wrap.o -o _test.so
```

### Run

```bash
python test.py
```

### Problem

On a Mac, with python from Anaconda3/Anaconda3+Python3-env/Anaconda2+Python3-env the above throws an error.

On a Mac, with python from Anaconda2/Anaconda3+Python2-env/Anaconda2+Python2-env/Homebrew-Python2/Homebrew-Python3 the above works fine.

However, I have with me two machines where with Anaconda3 I'm able to get the above to work.


$ cc -c $(python-config  --cflags) test.c test_wrap.c
$ cc -bundle -L/Users/$USER/miniconda3/envs/python27/lib -lpython2.7 -ldl -framework CoreFoundation test.o test_wrap.o -o _test.so
