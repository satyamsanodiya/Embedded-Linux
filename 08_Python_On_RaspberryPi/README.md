# Python on Raspberry Pi

## Objective

Learn how to develop and execute Python programs on Raspberry Pi using the Linux command line.

---

## Why Python on Raspberry Pi?

Python is widely used in Embedded Linux systems for:

* GPIO control
* Sensor interfacing
* UART communication
* I2C communication
* SPI communication
* Automation scripts
* Data logging
* IoT applications

---

## Python Version

Check installed Python version:

```bash
python3 --version
```

Example Output:

```text
Python 3.x.x
```

---

## Interactive Mode

Python can be executed directly from the terminal.

Start Interactive Mode:

```bash
python3
```

Example:

```python
>>> print("Hello Raspberry Pi")
Hello Raspberry Pi
```

Exit Interactive Mode:

```python
>>> exit()
```

or

```python
>>> quit()
```

---

## Batch Mode

Python programs can be stored in files and executed later.

### Create Python File

Using Nano:

```bash
nano hello.py
```

### Example Program

```python
print("Hello Raspberry Pi")
```

Save the file and exit Nano.

---

## Execute Python Program

Run:

```bash
python3 hello.py
```

Output:

```text
Hello Raspberry Pi
```

---

## Practical Activities Performed

* Verified Python installation.
* Used Python Interactive Mode.
* Executed Python statements directly from terminal.
* Created a Python script using Nano text editor.
* Saved Python file with .py extension.
* Executed Python script using python3 command.
* Learned the difference between Interactive Mode and Batch Mode.

---

## Interactive Mode vs Batch Mode

| Feature               | Interactive Mode      | Batch Mode        |
| --------------------- | --------------------- | ----------------- |
| Execution             | One command at a time | Entire file       |
| Usage                 | Learning and testing  | Real applications |
| File Required         | No                    | Yes               |
| Suitable for Projects | No                    | Yes               |

---

## Learning Outcome

Successfully created and executed Python programs on Raspberry Pi using both Interactive Mode and Batch Mode.

This forms the foundation for future Embedded Linux projects involving GPIO, UART, I2C, SPI, sensors, and automation.
