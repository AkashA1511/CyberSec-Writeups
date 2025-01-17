Room Link:
[TryHackMe | Python Basics](https://tryhackme.com/r/room/pythonbasics)


# Python Basics Walkthrough
This room provides basic yet necessary insights on:
- Variables
- Loops
- Functions
- Data Structures
- If statements
- Files

## Task 2: Hello World
```python
print("Hello World")
```
Type this on the `script.py` terminal.

The output is: `THM{PRINT_STATEMENTS}`

## Task 3: Mathematical Operators

Various Mathematical arithmetic operators are: `+`, `—`, `*`, `/`, `%`, `**`

- `**` = exponentiation i.e. `2**4 = 2*2*2*2 = 16`
- `%` = modulus i.e. it gives the remainder after division

1. **In the code editor, print the result of 21 + 43. What is the flag?**:
    ```python
    print(21 + 43)  # => THM{ADDITI0N}
    ```

2. **Print the result of 142 - 52. What is the flag?**:
    ```python
    print(142 - 52)  # => THM{SUBTRCT}
    ```

3. **Print the result of 10 * 342. What is the flag?**:
    ```python
    print(10 * 342)  # => THM{MULTIPLICATION_PYTHON}
    ```

4. **Print the result of 5 squared. What is the flag?**:
    ```python
    print(5 ** 2)  # => THM{EXP0N3NT_POWER}
    ```

## Task 4: Variables and Data Types

1. In the code editor, create a variable called height and set its initial value to 200.
    ```python
    height = 200
    ```

2. On a new line, add 50 to the height variable.
    ```python
    height += 50  # it is same as height = height + 50
    ```

3. On another new line, print out the value of height. What is the flag that appears?
    ```python
    print(height)  # => THM{VARIABL3S}
    ```

## Task 5: Logical and Boolean Operators

Logical operators include: `>`, `>=`, `<`, `<=`, `==`

Boolean operators include: `AND`, `OR`, `NOT`

In this code section, instead of else, `elif` is the correct syntax that is used in Python.

```python
name = "bob"
hungry = True
if name == "bob" and hungry == True:
    print("bob is hungry")
elif name == "bob" and not hungry:
    print("Bob is not hungry")
else:  # If all other if conditions are not met
    print("Not sure who this is or if they are hungry")
```

## Task 6: Introduction to If Statements

In this exercise, we will code a small application that calculates and outputs the shipping cost for a customer based on how much they’ve spent.

In the code editor, click on the `shipping.py` tab and follow the instructions to complete this task.

```python
"""
In this project, you’ll create a program that calculates the total
cost of a customer's shopping basket, including shipping.
— If a customer spends over $100, they get free shipping
— If a customer spends < $100, the shipping cost is $1.20 per kg of the basket's weight
Print the customer's total basket cost (including shipping) to complete this exercise.
"""
customer_basket_cost = 34
customer_basket_weight = 44
# Write if statement here to calculate the total cost
shipping_cost = 0
if customer_basket_cost >= 100:
    shipping_cost = 0
else:
    shipping_cost = customer_basket_weight * 1.2
total_cost = shipping_cost + customer_basket_cost
print(total_cost)  # => THM{IF_STATEMENT_SHOPPING}
```

In `shipping.py`, on line 12 (when using the Code Editor’s Hint), change the `customer_basket_cost` variable to 101 and re-run your code. You will get a flag (if the total cost is correct based on your code); the flag is the answer to this question.

```python
customer_basket_cost = 101
customer_basket_weight = 44
# Write if statement here to calculate the total cost
shipping_cost = 0
if customer_basket_cost >= 100:
    shipping_cost = 0
else:
    shipping_cost = customer_basket_weight * 1.2
total_cost = shipping_cost + customer_basket_cost
print(total_cost)  # => THM{MY_FIRST_APP}
```

## Task 7: Loops

On the code editor, click back on the `script.py` tab and code a loop that outputs every number from 0 to 50.

```python
for i in range(51):
    print(i)
```
Output: `THM{L00P***HILE_FOR}`

## Task 8: Bitcoin Project Introduction to Functions

You’ve invested in Bitcoin and want to write a program that tells you when the value of Bitcoin falls below a particular value in dollars.

In the code editor, click on the `bitcoin.py` tab. Write a function called `bitcoinToUSD` with two parameters: `bitcoin_amount`, the amount of Bitcoin you own, and `bitcoin_value_usd`, the value of bitcoin in USD. The function should return `usd_value`, which is your bitcoin value in USD (to calculate this, in the function, you multiply the `bitcoin_amount` variable by the `bitcoin_value_usd` variable and return the value). The start of the function should look like this:

```python
def bitcoinToUSD(bitcoin_amount, bitcoin_value_usd):
    usd_value = bitcoin_amount * bitcoin_value_usd
    return usd_value
```

Once you’ve written the `bitcoinToUSD` function, use it to calculate the value of your Bitcoin in USD, and then create an if statement to determine if the value falls below $30,000; if it does, output a message to alert you (via a print statement).

```python
investment_in_bitcoin = 1.2
bitcoin_to_usd = 25000
# 1) write a function to calculate bitcoin to usd
def bitcoinToUSD(bitcoin_amount, bitcoin_value_usd):
    usd_value = bitcoin_amount * bitcoin_value_usd
    return usd_value
answer = bitcoinToUSD(1.2, 40000)
if answer <= 30000:
    print("alert")
# OUTPUT: THM{BITC0I***VESTOR}
```

## Task 9: Files

In the code editor, write Python code to read the `flag.txt` file. What is the flag in this file?

```python
f = open("flag.txt", "r")
print(f.read())  # OUTPUT: THM{F1L****AD}
```

## Task 10: Imports

**Important points:**
- `pip` is Python’s package manager.
- To install a library that is not built-in use `pip install Library_name`.

**Popular Libraries:**
- `Request` — simple HTTP library.
- `Scapy` — send, sniff, dissect and forge network packets.
- `Pwntools` — a CTF & exploit development library.
```

This markdown file includes a step-by-step walkthrough for each task, complete with code snippets and explanations. Save this as a `.md` file to get the proper formatting for your markdown content.