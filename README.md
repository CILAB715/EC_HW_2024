# EC_hw_2024
## Sample Code Usage
Clone this repository to local,
```bash
git clone https://github.com/fffchameleon/EC_hw_2024.git
cd EC_hw_2024
```
If you will write this assignment with C++,
```bash
cd cpp/ && make
./hw_sch -n 10 -r binary -p 100 -u 0 -c 0.9 -m 0.1 -g 100 -d
```
If you prefer to use Python, use,
```bash
cd py
python3 main.py -n 10 -r binary -p 100 -u 0 -c 0.9 -m 0.1 -g 100 -d
```
Both should print the following,
```
-------------------------------------------
|Parameter           |Value               |
-------------------------------------------
|dimension           |10                  |
|representation      |binary              |
|population_size     |100                 |
|uniform_crossover   |false               |
|crossover_method    |2-point             |
|cross_prob          |0.9                 |
|mut_prob            |0.1                 |
|num_generations     |100                 |
-------------------------------------------
421 421 421 421 421 421 421 421 421 421
```
## Input/Output Format
We provide sample parser code for two languages (C++/Python). 

You can write your own parser, but it must be capable of accepting the following parameters, and your program must provide at least the following 8 options. 

p.s. You may add more options to make your experiments more convenient, but adding more options will not affect your grade.

| Options       | Description | Default |
| ------------- | ----------- | ------- |
| `-n, --dimension` | The dimension of Schwefel function | 10 |
| `-r, --representation`    | The representation to use. Binary or real-valued (binary, real) | binary |
| `-p, --population_size`	  |  Number of the population |100 |
| `-u, --uniform_crossover`  | The crossover method using uniform crossover (1) or not (0). If not, then for binary GA, it will use 2-point crossover and for real-valued GA will use whole arithmetic crossover | 0 |
| `-c, --pc` |	Probability for the crossover | $p_c$=0.9 |
| `-m, --pm` |	Probability for the mutation  |  $p_m$=0.1 |
| `-g, --generations`  |  Max number of generations to terminate | 500 |
| `-d, --debug`        | Turn on debug prints | false |

### Input
For example, with testcase/01.in, our judger will execute your executable file + the first line of configuration in testcase/*.in.

If written in C++, please remember to upload a Makefile, and the compiled executable should be named hw_sch.
```bash
./hw_sch -n 10 -r binary -p 100 -u 0 -c 0.9 -m 0.1 -g 100
```
If written in Python, your main.py file will be executed directly.
```bash
python3 ./main.py -n 10 -r binary -p 100 -u 0 -c 0.9 -m 0.1 -g 100
```
The following context is `01.in`. The first line contains the parameters we will use for testing, followed by a debug print table. If you do not include -d or --debug, it will not print.
```
-n 10 -r binary -p 100 -u 0 -c 0.9 -m 0.1 -g 100
-------------------------------------------
|Parameter           |Value               |
-------------------------------------------
|dimension           |10                  |
|representation      |binary              |
|population_size     |100                 |
|uniform_crossover   |false               |
|crossover_method    |2-point             |
|cross_prob          |0.9                 |
|mut_prob            |0.1                 |
|num_generations     |100                 |
-------------------------------------------
```
### Output
Please directly print all $x_i$ found by the GA according to the number of dimensions. 

For example, with `01.in`, the dimension is 10, so the output should be 10 $x_i$ values separated by spaces.

**Remember, when uploading your code, ensure that your code does not print the configuration table without -d, --debug.**
- Sample output: `01.out`
  In `testcase/*.out`, the first line is the sample output. Your code-generated output will be compared with this sample output to calculate the RMSE.
  If the RMSE is within a reasonable range (indicated on the second line of *.out), it is considered correct.
  ```
  421 421 421 421 421 421 421 421 421 421
  rmse: 10
  ```
## Grading
- Compilation failure with Makefile (-5)
- Not following input/output format (-5)
- Incorrect filename (-3)
- Each failed testcase deducts 1 point
