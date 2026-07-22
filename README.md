# MapReduce Engine

## Project Title
Distributed MapReduce Engine from Scratch with Hash Partitioning

## Objective
This project demonstrates the working of the MapReduce programming model using Python. It counts the frequency of each word from an input text file by implementing the Map, Partition, Shuffle & Sort, and Reduce phases.

## Project Files

```
Project/
│── input.txt
│── main.py
│── mapper.py
|── partition.py
│── reducer.py
│── intermediate/
│── output/
│── README.md
```

## File Description

### 1. input.txt
Contains the input data (names/words) to be processed.

### 2. main.py
Acts as the MapReduce Driver.

Functions:
- Splits the input into multiple chunks.
- Executes mapper processes.
- Partitions mapper output using a custom hash function.
- Stores intermediate data.
- Sorts intermediate key-value pairs.
- Executes reducer processes.
- Stores the final output.

### 3. mapper.py
Reads the input from standard input and emits:

```
word    1
```

Example:

Input

```
Lio Monkey Tiger
```

Output

```
Lion 1
Monkey 1
Tiger 1
```

### 4. reducer.py
Reads sorted mapper output and sums the occurrences of each word.

Example

Input

```
Lion 1
Lion 1
Lion 1
```

Output

```
Lion 3
```

## MapReduce Workflow

1. Split Input
2. Map Phase
3. Partition Phase
4. Write Intermediate Files
5. Shuffle and Sort
6. Reduce Phase
7. Generate Final Output

## Technologies Used

- Python 3.x
- Standard Python Libraries
  - os
  - sys
  - shutil
  - subprocess

## Input Dataset

The input file contains names such as:

```
Tiger Lion Elephant Tiger Deer Lion Rabbit Tiger
Monkey Elephant Tiger Fox Rabbit Lion Monkey
Deer Tiger Fox Elephant Monkey Rabbit Deer Tiger
Lion Deer Monkey Fox Tiger Elephant Rabbit Lion
Fox Lion Deer Tiger Monkey Elephant Fox Rabbit
Rabbit Tiger Deer Lion Fox Monkey Elephant Tiger
Tiger Elephant Rabbit Monkey Deer Fox Lion Rabbit
Lion Tiger Elephant Deer Monkey Rabbit Fox Tiger
```

## Expected Output

```
  Deer: 8
  Elephant: 8
  Fox: 8
  Lion: 9
  Monkey: 8
  Rabbit: 9
  Tiger: 13
```

(Output is generated inside the **output** folder.)

## How to Run

Run the driver program:

```
python main.py
```

The program automatically executes:

- mapper.py
- reducer.py

and stores the final results inside the **output** folder.

## Features

- Custom MapReduce implementation
- Multiple Mapper Processes
- Multiple Reducer Processes
- Custom Hash Partitioner
- Shuffle and Sort Phase
- Intermediate File Generation
- Word Count Analysis

## Applications

- Big Data Processing
- Word Frequency Analysis
- Hadoop Streaming Concepts
- Text Analytics
- Distributed Data Processing

## Conclusion

This project successfully demonstrates the complete MapReduce workflow using Python. It simulates Hadoop's processing model by dividing input data among multiple mappers, partitioning intermediate key-value pairs, sorting them, and finally reducing them to generate the total word frequencies.
