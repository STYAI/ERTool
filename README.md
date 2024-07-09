# ERTool

<kbd>***ERTool***</kbd> is a Python Package for Efficient Implementation of Multi-Source Evidence Fusion Based on the Evidential Reasoning Approach. It aims to provide an intuitive and flexible approach for integrating ER processes, particularly suitable for data analysis and decision support systems. For more information, please visit https://ertool.online/.


## Features

- Easy-to-use implementation of Evidential Reasoning.
- Efficient in handling complex ER tasks.
- Flexible interface suitable for various application scenarios.

## Installation

You can install <kbd>***ERTool***</kbd> directly from PyPI using pip:

```
pip install ertool
```

## Using Instruction

### er_algorithm

```python
ertool.er.er_algorithm(W, DBF, numOfEvidence, numOfPropositions)
```
<kbd>er_algorithm()</kbd> can implement the Evidential Reasoning (ER) algorithm.

#### Input
- ***W***: A one-dimensional array of floats. It represents the weights of each piece of evidence. These weights are used in the algorithm to adjust the influence of each evidence.
- ***DBF***: A two-dimensional array of floats. It stands for "Degrees of Belief" and is one of the main inputs to the algorithm, used to represent the initial belief degree of each proposition supported by each evidence.
- ***numOfEvidence***: An integer. It indicates the number of evidence to be combined. In the DBF array, this typically corresponds to the number of rows.
- ***numOfPropositions***: An integer. It indicates the number of propositions or evidential grades. In the DBF array, this typically corresponds to the number of columns.

#### Output
- ***B Array***: Upon completion of the algorithm, the B array is updated with the final calculation results. It reflects the degree of belief of each proposition or evidential grades for the object being assessed after combining all available evidence. The pre-Numofproposition values in the B represent the belief degree of each proposition after evidence fusion. The last value of the B represents the belief degree of the overall uncertainty.
- ***False (Boolean)***: It returns True if the algorithm successfully executes and completes all computations. If any error is encountered during execution (e.g., division by zero), it returns False.


### dempster_rule
```python
ertool.er.dempster_rule(DBF, numOfEvidence, numOfPropositions)
```

<kbd>dempster_rule()</kbd> can implement the original Dempster-Shafer evidence theory.

#### Input
- ***DBF***: A two-dimensional array of floats. It stands for "Degrees of Belief" and is one of the main inputs to the algorithm, used to represent the initial belief degree of each proposition supported by each evidence. The pre-Numofproposition values in the B represent the belief degree of each proposition after evidence fusion. The last value of the B represents the belief degree of the overall uncertainty.
- ***numOfEvidence***: An integer. It indicates the number of evidence to be combined. In the DBF array, this typically corresponds to the number of rows.
- ***numOfPropositions***: An integer. It indicates the number of propositions or evidential grades. In the DBF array, this typically corresponds to the number of columns.

#### Output
- ***B Array***: Upon completion of the Dempster's Rule, the B array is updated with the final calculation results. It reflects the degree of belief of each proposition or evidential grades for the object being assessed after combining all available evidence.
- ***False (Boolean)***: It returns True if the algorithm successfully executes and completes all computations. If any error is encountered during execution (e.g., division by zero), it returns False.


### yager_rule
```python
ertool.er.yager_rule(DBF, numOfEvidence, numOfPropositions)
```

<kbd>yager_rule()</kbd> can implement the original Yager's Rule.

#### Input
- ***DBF***: A two-dimensional array of floats. It stands for "Degrees of Belief" and is one of the main inputs to the algorithm, used to represent the initial belief degree of each proposition supported by each evidence. The pre-Numofproposition values in the B represent the belief degree of each proposition after evidence fusion. The last value of the B represents the belief degree of the overall uncertainty.
- ***numOfEvidence***: An integer. It indicates the number of evidence to be combined. In the DBF array, this typically corresponds to the number of rows.
- ***numOfPropositions***: An integer. It indicates the number of propositions or evidential grades. In the DBF array, this typically corresponds to the number of columns.

#### Output
- ***B Array***: Upon completion of the Yager's Rule, the B array is updated with the final calculation results. It reflects the degree of belief of each proposition or evidential grades for the object being assessed after combining all available evidence.
- ***False (Boolean)***: It returns True if the algorithm successfully executes and completes all computations. If any error is encountered during execution (e.g., division by zero), it returns False.

### murphy_rule
```python
ertool.er.murphy_rule(DBF, numOfEvidence, numOfPropositions)
```

<kbd>murphy_rule()</kbd> can implement the original Murphy's Rule.

#### Input
- ***DBF***: A two-dimensional array of floats. It stands for "Degrees of Belief" and is one of the main inputs to the algorithm, used to represent the initial belief degree of each proposition supported by each evidence. The pre-Numofproposition values in the B represent the belief degree of each proposition after evidence fusion. The last value of the B represents the belief degree of the overall uncertainty.
- ***numOfEvidence***: An integer. It indicates the number of evidence to be combined. In the DBF array, this typically corresponds to the number of rows.
- ***numOfPropositions***: An integer. It indicates the number of propositions or evidential grades. In the DBF array, this typically corresponds to the number of columns.

#### Output
- ***B Array***: Upon completion of the Murphy's Rule, the B array is updated with the final calculation results. It reflects the degree of belief of each proposition or evidential grades for the object being assessed after combining all available evidence.
- ***False (Boolean)***: It returns True if the algorithm successfully executes and completes all computations. If any error is encountered during execution (e.g., division by zero), it returns False.

### show_er_result
```python
ertool.er.show_er_result(B, P = None)
```
<kbd>er.show_er_result()</kbd> can visualize the result of evidential reasoning algorithm.

#### Input
- ***B***: The ER result of belief degree.
- ***P***: The name array of propositions.

### run_algorithm_from_file
```python
ertool.er.run_algorithm_from_file(file_path, algorithm = ’ER’)
```

<kbd>run_algorithm_from_file()</kbd> reads CSV or XLSX files and performs multi-source evidence fusion on the data using ER approach or Dempster-Shafer’s theory.

#### Input
- ***file_path***: A string. The location of the CSV or XLSX file. Note that the format of data strictly follows the format of the provided template.
- ***algorithm***: 'ER', 'Demp', 'Yager' or 'Murphy'. 'ER' stands for using the Evidence Inference algorithm, 'Demp' stands for using the Dempster-Shafer algorithm, 'Yager' stands for using the Yager's Rule, and 'Murphy' stands for using the Murphy's Rule.


#### Output
- ***B Array***: Upon completion of the algorithm, the B array is updated with the final calculation results. It reflects the degree of belief in each proposition or evaluation grade for the object being assessed after combining all available evidence. The first numofPropositions members in the B represent the belief degree in each proposition after evidence fusion. The last member of the B represents the belief degree in the overall uncertainty.
- ***False (Boolean)***: It returns True if the algorithm successfully executes and completes all computations. If any error is encountered during execution (e.g., division by zero), it returns False.

### multi_level_multi_source
```python
ertool.er.multi_level_multi_source(folder_path)
```

The <kbd>multi_level_multi_source()</kbd> function can perform multi-level multi-source evidence fusion for folders that have already been structured using directory tree recursion method.

#### Input
- ***folder_path***: A string. The folder address of the data that requires multi-level multi-source evidence fusion is stored in a fixed format.

#### Output
The result of multi-level multi-source evidence fusion is generated in the root folder and written into the “Objects_combined.csv” file.


## Quick Start
Here is a basic usage example of <kbd>***ERTool***</kbd>.

Consider a medical scenario. 
There are three medical experts (weights 10, 8, and 5). For one patient, the three experts rated the different likelihood of the diagnosis of cold, common pneumonia, COVID-19, and other diseases. As shown in the table.

| Experts & Diseases | Expert 1 | Expert 2 | Expert 3 |
| :---:        |    :----:   |  :---: |  :---: |
| Cold | 90% | 0 | 0 |
| Common Pneumonia |0 | 90% | 0|
| COVID-19 | 0 | 0 | 90% |

In this case, the ***numOfEvidence*** is 3 (the number of experts) and the ***numOfPropositions*** is 3 (cold, common pneumonia and COVID-19).

The ***W*** array is the weights array of every expert and the <kbd>***ERTool***</kbd> package can normalize them automatically.

We can write the code using the <kbd>***ERTool***</kbd> package:

```python
from ertool import er
import numpy as np

W = np.array([10,8,5])
DBF = np.array([[0.9, 0, 0], 
                [0, 0.9, 0], 
                [0, 0, 0.9]])

# List or numpy array are both OK.
# W = [10,8,5]
# DBF = [[0.9, 0, 0], 
#        [0, 0.9, 0], 
#        [0, 0, 0.9]]

numOfEvidence = 3
numOfPropositions = 3
B = er.er_algorithm(W, DBF, numOfEvidence, numOfPropositions)
print("The result: ", B)

P = ['Cold', 'Common Pneumonia', 'COVID-19']
er.show_er_result(B, P)
```
With the code, we can calculate the probability that the patient will be diagnosed with each disease using evidential reasoning.

```
The result: [0.43317251 0.307059 0.16390311 0.09586537]
```
The calculation results show that the probability of the patient being diagnosed with a cold, common pneumonia, and COVID-19 are 0.43317251, 0.307059, and 0.16390311, respectively. The last member of B represents overall uncertainty, and it is 0.09586537 in this example.

## Contributing
Contributions to <kbd>***ERTool***</kbd> are welcome. Please contact us for how to contribute to the project.

## Reference
Tongyue Shi, Liya Guo, Zeyuan Shen, Guilan Kong. ERTool: A Python Package for Efficient Implementation of the Evidential Reasoning Approach for Multi-Source Evidence Fusion. Health Data Science. 2024.

## Contact
This project is supported by Peking University. For any questions or suggestions, please contact us at **tyshipku@gmail.com**.
