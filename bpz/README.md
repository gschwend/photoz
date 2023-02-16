
## Directory to experiment and learn about BPZ

BPZ is written in Python 2

Installation steps: 

* Download BPZ from https://www.stsci.edu/~dcoe/BPZ/ to your home dir 
* `conda create -n py27 python=2.7`
* vim ~/.cshrc 
    Paste contents: 
```shell   
export HOME=<path to your home>
export BPZPATH="$HOME/bpz-1.99.3"
export PYTHONPATH="$PYTHONPATH:$BPZPATH"
alias bpz="python $BPZPATH/bpz.py"
export NUMERIX="numpy"
``` 
* source ~./cshrc 
* Fix some known bugs: 
  Open file $BPZPATH/plots/sedplotAB.py
  - row 107: id_str -> id_str.any() 
  - row 136: self.id. -> self.id.any()  
* Go to $BPZPATH/test and run test commands:
```shell
bpz UDFtest.cat -INTERP 2
python $BPZPATH/bpzfinalize.py UDFtest
python $BPZPATH/plots/webpage.py UDFtest
``` 
* Check the output:
```shell
~/bpz-1.99.3/test/html/index.html
```




 
