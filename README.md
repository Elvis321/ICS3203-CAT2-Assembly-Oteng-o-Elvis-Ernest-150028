# ICS3203-CAT2-Assembly-Oteng-o-Elvis-Ernest-150028

This repository contains the practical tasks demonstrating basic Assembly programming concepts such as control flow, array manipulation, modular programming, and data monitoring. The tasks involve creating small programs to handle specific logic and operations, which are documented and explained with challenges and insights faced during development.

---

## Task 1: Control Flow and Conditional Logic

### Program Overview:
This program prompts the user for a number and classifies it as either "POSITIVE," "NEGATIVE," or "ZERO" using conditional and unconditional jumps.

### Steps:
1. The program asks for user input.
2. Based on the input, it checks whether the number is positive, negative, or zero.
3. It uses conditional jumps (like `jg`, `jl`, `je`) to handle the branching logic and unconditional jumps (`jmp`) for flow control.

### Documentation:
- **Jump Instructions**: 
   - `jg` (greater than) is used to check if the number is positive.
   - `jl` (less than) checks if the number is negative.
   - `je` (equal) checks for zero.
   - Unconditional `jmp` is used to exit the program if no further checks are required.

---

## Task 2: Array Manipulation with Looping and Reversal

### Program Overview:
This program takes an array of five integers as input, reverses the array in place using loops, and prints the reversed array.

### Steps:
1. The user enters five integers.
2. The array is reversed in place by swapping elements.
3. The program prints the reversed array.

### Requirements:
- **Memory Usage**: The program avoids using additional memory to store the reversed array and instead directly modifies the original array in place.
- **Looping**: A loop is used to swap elements and reverse the array.

### Documentation:
- **Reversal Process**: 
   - The loop iterates over the first half of the array, swapping elements with the corresponding elements in the second half.
   - Each step of the reversal process is documented to explain the in-place modification of the array.

### Insights/Challenges:
- Handling memory directly in Assembly can be tricky because there is no built-in abstraction like high-level languages, requiring careful index and memory address manipulation.

---

## Task 3: Modular Program with Subroutines for Factorial Calculation

### Program Overview:
This program computes the factorial of a number received as input. It uses a subroutine to perform the calculation, demonstrating the use of the stack to preserve registers and maintain modularity.

### Steps:
1. The user provides an integer input.
2. The factorial calculation is done in a separate subroutine.
3. Registers are preserved on the stack to ensure that no values are overwritten during the subroutine call.

### Documentation:
- **Register Management**:
   - Registers are saved onto the stack before the subroutine is called.
   - After the subroutine finishes, the registers are restored, demonstrating proper register handling and function modularity.
   
### Insights/Challenges:
- Stack management and understanding how to preserve register values between function calls in Assembly was one of the most challenging aspects.
- Properly managing the stack in a modular program can help avoid bugs like overwriting critical register values.

---

## Task 4: Data Monitoring and Control Using Port-Based Simulation

### Program Overview:
This program simulates the control of a motor and alarm system based on a water level sensor value. The program reads the sensor value and performs actions like turning on the motor or triggering an alarm based on the water level.

### Steps:
1. The program reads the sensor value from a specific memory location.
2. Based on the sensor value:
   - If the water level is too high, the program triggers an alarm.
   - If the water level is moderate, the motor is turned off.
3. The motor and alarm status are simulated by setting specific memory locations or ports.

### Documentation:
- **Sensor and Action Logic**:
   - If the sensor value exceeds a threshold (e.g., 8), an alarm is triggered.
   - If the sensor value is moderate (e.g., 3-7), the motor is turned off.
   - The status of the motor and alarm is reflected by setting bits in memory locations.

### Insights/Challenges:
- This task highlighted the need for memory manipulation and port-based simulation to interact with hardware-like components (motor, alarm).
- Handling direct memory addressing and bit manipulation for control logic was challenging.

---

## Requirements

### Software:
- **Assembler**: NASM (Netwide Assembler) for compiling the Assembly code.
- **Linker**: LD for linking the object files and creating the executable.

### System:
- A Linux-based system is recommended to run the Assembly code since it uses `sys_write` and `sys_read` system calls for input/output.

### Commands:
To assemble and link the code, use the following commands:
1. Assemble the code:
   ```bash
   nasm -f elf32 -o program.o program.asm
   ld -m elf_i386 -o program program.o
   ./program

