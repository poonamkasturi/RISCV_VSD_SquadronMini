# RISCV_VSD_SquadronMini
## Lab exercises of RISCV workshop by Kunal Ghosh
## Instructor : Kunal Ghosh

### PRE-REQUISITE: Installing the required applications for the workshop - Virtual Box, Ubuntu on VBBOX and VDI files

## TASK-1: 
## A: Write a simple C code and compile it with gcc comipler. 
## B: Compile the same code with RISCV comipler to generate the assembly code for the same. Further Evaluate RISCV assembly code for the sample C code with two different options of comiplation.

## NECESSARY INSTALLATIONS
### Step 1: Setting up the virtual environment to work on
- Install Oracle Virtual Box, VMBox<br/>
- Launch Virtual Machine on VMBox<br/>
- Attach the VDI file to the Virtual Machine instance in VMBox<b>

### Step 2: Install Leafpad - the word editor
    $    sudo apt install leafpad <br/>

### TASK 1A - COMPILE AND EXECUTE A SIMPLE C CODE USING GCC COMPILER
    $   cd <br/>                           Navigate to home directory:<br>
    $   leafpad filename.c & <br/>         This opens a blank file with filename.c, type the c code
    
![image](https://github.com/user-attachments/assets/3a04abb4-3369-4564-bcf8-d73b6b845152)
Save the file<br> 
Come back to terminal<br>
Press entre to come to the home prompt<br>
To see the results Run the following commands

    $    gcc filename.c <br>
    $    ./a.out <br>
![image](https://github.com/user-attachments/assets/8310c8c6-46cf-4652-96c1-e6174aa564ae)
Change the value of n in filename.c <br>
Recompile and see the results <br>
![image](https://github.com/user-attachments/assets/0f5ec3fa-ba7e-4e16-9324-6fc827f94570)

# TASK-1B: ASSEMBLY CODE ON RISCV COMPILER AND GCC COMPILER
cat sum1to9.c           --shows the content of the *.c file on the terminal tab <br>

    $    riscv64-unknown-elf-gcc -O1 -mabl=lp64 -march=rv64i -o sum1to9.o sum1to9.c <br>       .. creates an object file for source file, before linking them together, into the final executable.<br>
![image](https://github.com/user-attachments/assets/72db8c59-817a-4a0f-8c8a-3d033af60e96)

### To see the contents of the *.o object file 
In a new tab execute the command <br>

    $    riscv64-unknown-elf-objdump -d sum1to9.o <br>
![image](https://github.com/user-attachments/assets/7e180792-4f71-4c83-a8e0-ce819db24077)

To look into the assembly code generated by RISCV compiler execute the command <br>

    $    riscv64-unknown-elf-objdump -d sum1to9.o | less <br>
![image](https://github.com/user-attachments/assets/70770eb0-c6d8-423d-a9b9-dec154d76e9c)

To look for the assembly code corresponding to main () <br>

type     /main <br>
![image](https://github.com/user-attachments/assets/d9eefe98-6144-4c65-be7d-dd0966d61ec2)

Highlight main and press n to find where all it is <br>  
![image](https://github.com/user-attachments/assets/e5e2864f-c8e5-4437-a3f4-4d3c6ad79477)

Starting address of main is 10184 and the next block is at 101c0 <br>
To find the total memory locations (space) taken by main 101c0 – 10184 =     3C  (These values are in hex) <br>
3C (hex) = 60 (decimal) <br>
No of instructions = (101C0 – 10184)/4 = 15 (divide by 4 because each instruction is taking 4 bytes) <br>

The number of assembly instructions generated is 15 with option -O1 <br>

Execute the command with **-Ofast** option in Tab 1 and see the difference <br>

    $    Riscv64-unknown-elf-gcc -Ofast -mabl=lp64 -march=rv64i -o sum1to9.o sum1to9.c <br>

![image](https://github.com/user-attachments/assets/d176ded5-63ac-4488-8aa7-26720e23ed63)

Run the commands again In tab 2 to examine the assembly code generated <br>
    $    riscv64-unknown-elf-objdump -d sum1to9.o <br>
    $    riscv64-unknown-elf-objdump -d sum1to9.o | less <br>

![image](https://github.com/user-attachments/assets/3e8a2065-f5ee-48d8-b4f8-99d66314a04d)

![image](https://github.com/user-attachments/assets/678d4fae-351e-450f-a4da-2059b7b7d393)

type     /main <br>
Highlight main and press n to find where all it is <br> 
![image](https://github.com/user-attachments/assets/ebee73fc-e401-470d-b174-c9e12e0e202e)

Starting address of main is 100b0 and the next block is at 100e0 <br>
To find the total memory locations (space) taken by main 100e0 – 100bo =     30  (These values are in hex) <br>
3C (hex) = 48 (decimal) <br>
No of instructions = (101C0 – 10184)/4 = 12 (divide by 4 because each instruction is taking 4 bytes) <br>

The number of assembly instructions generated is 12 with option -Ofast <br>




