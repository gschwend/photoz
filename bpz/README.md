
## Directory to experiment and learn about BPZ

The original BPZ code (Benitez, 2000) is written in Python 2. 

#### Installation steps: 

* Download BPZ from `https://www.stsci.edu/~dcoe/BPZ/` to your home dir 
* Run 
```shell 
conda create -n py27 python=2.7
conda activate py27
``` 
* Create (or update) ~/.cshrc file with the contents: 
```shell   
export HOME=<path to your home>
export BPZPATH="$HOME/bpz-1.99.3"
export PYTHONPATH="$PYTHONPATH:$BPZPATH"
alias bpz="python $BPZPATH/bpz.py"
export NUMERIX="numpy"
``` 
* Run
```shell 
source ~./cshrc
```  
* Fix some known bugs in `$BPZPATH/plots/sedplotAB.py` 
  - row 107: `id_str` -> `id_str.any()` 
  - row 136: `self.id` -> `self.id.any()`  
* Go to `$BPZPATH/test` and run test commands:
```shell
bpz UDFtest.cat -INTERP 2
python $BPZPATH/bpzfinalize.py UDFtest
python $BPZPATH/plots/webpage.py UDFtest
``` 
* Check the output (`open` works for mac Terminal):
```shell
open ~/bpz-1.99.3/test/html/index.html
```





 
