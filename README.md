[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/OpMbFSfa)
# final-project-skeleton

This codebase will be used first in A07G Exploring the CLI, then will be expanded upon in parts of A08G Comm Protocols, A09G The Bootloader Waltz, A10G Cloud, A12G Firmware Drivers, and A14G Final Submission. Please write the answers in the README file corresponding to the assignment number - not this one!

## GitHub Repo Submission Resources

* [ESE5160 Example Repo Submission](https://github.com/ese5160/example-repository-submission)
* [Markdown Guide: Basic Syntax](https://www.markdownguide.org/basic-syntax/)
* [Adobe free video to gif converter](https://www.adobe.com/express/feature/video/convert/video-to-gif)
* [Curated list of example READMEs](https://github.com/matiassingers/awesome-readme)
* [VS Code](https://code.visualstudio.com/) is heavily recommended to develop code and handle Git commits
  * Code formatting and extension recommendation files come with this repository.
  * Ctrl+Shift+V will render the README.md (maybe not the images though)

# Part1: Software Architecture

# Part2: Understanding the Starter Code

**1. What does “InitializeSerialConsole()” do? In said function, what is “cbufRx” and “cbufTx”? What type of data structure is it?**

The function InitializeSerialConsole() initializes the serial console by setting up buffers for receiving and transmitting data, configuring the USART, setting interrupt priority, and starting the reception of data. cbufRx and cbufTx are variables that store pointers to circular buffers used for handling incoming (RX) and outgoing (TX) serial data. They are "ring buffers".

**2. How are “cbufRx” and “cbufTx” initialized? Where is the library that defines them (please list the C file they come from).**

They are initialized using circular_buf_init(). The function takes two arguments:
1. A pointer to the memory buffer (rxCharacterBuffer for RX and txCharacterBuffer for TX).
2. The size of the buffer (RX_BUFFER_SIZE for RX and TX_BUFFER_SIZE for TX).
It returns a pointer to a circular buffer structure, which is assigned to cbufRx and cbufTx. 
They are defined in "SerialConsole.c".

**

