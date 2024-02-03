
**Data Acquisition in Computer Forensics - Project**

**Description:**
Explore the intricacies of data acquisition in the field of computer forensics through this hands-on lab. Learn the essential steps to prepare a target drive for acquisition in a Linux environment. This lab provides a comprehensive walkthrough of partitioning, formatting, and mounting a Microsoft FAT32 drive, enabling you to conduct forensic analysis seamlessly within Linux. Whether you're a cybersecurity enthusiast or a student, dive into this lab to enhance your skills and understanding of data acquisition techniques in computer forensics.

---

**README.md**

# Data Acquisition in Computer Forensics - Lab

## Introduction

This lab focuses on data acquisition in computer forensics, specifically the process of preparing a target drive for acquisition in a Linux environment. You will learn how to partition, format, and mount a Microsoft FAT32 drive, a crucial skill for conducting forensic analysis within Linux.

## Task 1 - Prepare Linux File System

### Step 1: Power on the Required Devices
- Ensure that all required devices are powered on, as mentioned in the lab introduction.

### Step 2: Log in to Kali Linux
- Use the provided credentials to log in to Kali Linux:
  - Username: root
  - Password: Passw0rd

### Step 3: Launch GParted (Graphical Partition Editor)
- Open the terminal and run the following command to launch GParted, a graphical partition editor:
  ```
  gparted
  ```

> Note: Typing "gparted" on the command prompt in Kali Linux opens a visual interface to configure the FAT32 file system.

### Step 4: Select the Target Disk
- In GParted, select the target disk (/dev/sdb) by changing the selection in the top-right corner.

### Step 5: Unmount the Partition
- Right-click on /dev/sdb1 and select "Unmount."

### Step 6: Delete the Partition
- Right-click on /dev/sdb1 and select "Delete."

### Step 7: Create a New Partition
- Right-click on "unallocated" space and select "New."
- Set the new size to 4096 MiB, select "fat32" as the file system, and set the label to "Windows."
- Click "Add" to create the new partition.
- Apply the changes.

### Step 8: Save Changes
- Save the changes made to the file system by clicking the green checkmark.

### Step 9: Complete the Process
- Click "Apply" to apply the pending operations.
- Wait for the operations to complete and then click "Close."

### Step 10: Keep Terminal Open
- Keep the terminal window open for the next task.

## Task 2 - Mounting a Disk Volume

### Step 1: Find Device File Names
- Run the following command in the terminal to find out the names of device files:
  ```
  fdisk -l
  ```

### Step 2: Create a Mount Directory
- Create a directory where you will mount the device:
  ```
  mkdir /mnt/sdb1
  ```

> Note: Another important command is "mkdir /mnt/sdb1," which is used to create a directory where the device will be mounted.

### Step 3: Edit the fstab File
- Open the fstab file for editing:
  ```
  leafpad
  ```
- Add the following entry at the end of the file:
  ```
  /dev/sdb1  /mnt/sdb1  vfat  defaults  0  0
  ```
- Save and close the file.

### Step 4: Clear the Terminal
- Clear the terminal screen:
  ```
  clear
  ```

### Step 5: Launch GParted Again
- Reopen GParted and select the /dev/sdb disk.

### Step 6: Mount the Partition
- Right-click on /dev/sdb1 and select "Mount on > /mnt/sdb1."

### Step 7: Complete the Mounting Process
- Wait for the partition to be mounted.
- Close GParted.

## Conclusion

I successfully prepared a target drive for acquisition in Linux and mounted the partition for further use. This lab is designed to help you understand the essential steps of data acquisition in computer forensics.
