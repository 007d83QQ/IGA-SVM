# IGA-SVM
> This is a sub-project within the MicroRNA-signatures-Identify project.

By combining the Intelligence Genetic Algorithm and classification algorithms, better feature selection results are achieved to handle datasets with a large 
number of variables and a small number of samples. This project uses the Random Forest algorithm as the fitness function for the Intelligence Genetic Algorithm.
## Usage
* 1. Save the files and open them in your project.
* 2. Change file path the encoding length of bit_string_length according to the number of variables you have in `main`(default is 16).
```cpp
bioinfo bio("your_data.csv",5);
int bit_string_length= 16;
```
* 3. If needed, modify the following parameters in the GA.init() function in `main` : mode parameter, population size, selection rate, crossover rate, mutation rate.
```cpp
/*  Stop condition, mode parameter, population size, selection rate
, crossover rate, mutation rate, fitness function data  */
GA.init(STOP_CONDITION_GENERATION, 100, 30, 0.1f, 0.5f, 0.008f, &fitnessfunction_data);
```
* 4. After completing the above steps, execute the program.

## Result analysis
The following figure illustrates how the results of the IGA-SVM program should appear (Partial results) :

![image](https://github.com/007d83QQ/IGA-SVM/blob/main/github/IGA-result.png)

* If you want to analyze the evolution process of feature selection, select the best evolution score of each generation output from the evolution result 
and plot it against the generation, thus observing the evolutionary process.

* If you want to analyze the feature selection results, the feature selection result outputted at the end of the evolution is used. 
According to the set `bit_string_length`, it undergoes binary transformation. After transformation, '1' indicates selection, and '0' indicates non-selection.
Please note that the first two data points represent the SVM parameters c and Y, and do not need to be included in the feature selection column.
