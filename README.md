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


