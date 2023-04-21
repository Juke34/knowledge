# How to profile your perl code 

How to profile your perl code in order to point out the bottelneck performances.
[NYTProf](https://metacpan.org/pod/Devel::NYTProf) is one of the library allowing such profiling. Let's look how to use it in 3 steps. 

#### Step one: install NYTProf

```bash
cpanm install Devel::NYTProf
```
You may want to have a look at the documentation. Either visit the [metacpan](https://metacpan.org/pod/Devel::NYTProf) or use perldoc:
```bash
perldoc Devel::NYTProf
```

#### Step two: launch your script in behalf of NYTProf
```bash
perl -d:NYTProf my_perl_script.pl
```
The script with rum much slowly as usual because NYTProf is catching lot of information in background.
Iw will create a file called **nytprof.out**

#### Step three: open the NYTProf output file
```bash
nytprofhtml --open
```
It will open an html file containing plenty of performance information. Enjoy it !
