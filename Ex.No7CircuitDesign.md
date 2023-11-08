# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE: 02.09.2023                                                                           
### REGISTER NUMBER : 212221040110
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:
```
# Define logic gate functions
def AND_gate(a, b):
return a & b
def OR_gate(a, b):
return a | b
def XOR_gate(a, b):
return a ^ b
def NOT_gate(a):
return ~a & 1
# Half Adder
def half_adder(a, b):
sum_bit = XOR_gate(a, b)
carry_out = AND_gate(a, b)
return sum_bit, carry_out
# Half Subtractor
def half_subtractor(a, b):
difference = XOR_gate(a, b)
borrow_out = AND_gate(NOT_gate(a), b)
return difference, borrow_out
# Test the logic
# Half Adder test
print("Half Adder Test:")
a = 1
b = 1
sum_bit, carry_out = half_adder(a, b)
print(f"Input A: {a}, Input B: {b}")
print(f"Sum: {sum_bit}, Carry Out: {carry_out}")
# Half Subtractor test
print("\nHalf Subtractor Test:")
a = 1
b = 0
difference, borrow_out = half_subtractor(a, b)
print(f"Input A: {a}, Input B: {b}")
print(f"Difference: {difference}, Borrow Out: {borrow_out}")
```










### Output:
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/c913614c-0a08-45d4-a106-89bb2b3b335d)



### Result:
Thus the truth table of circuit verified sucessfully.
