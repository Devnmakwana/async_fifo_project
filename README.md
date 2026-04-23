# Async FIFO Project — Linux IPC with GTKWave Visualization

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Language](https://img.shields.io/badge/Language-C-blue)
![Tool](https://img.shields.io/badge/Tool-GTKWave-orange)
![OS](https://img.shields.io/badge/OS-Ubuntu_23-purple)
![License](https://img.shields.io/badge/License-MIT-yellow)
![IPC](https://img.shields.io/badge/IPC-Named_Pipe-red)

---

##  Overview

Designed and implemented a fully functional **Asynchronous FIFO (First In First Out)** communication system using **C programming** on **Ubuntu Linux**. The project demonstrates real-time **Inter-Process Communication (IPC)** using Linux Named Pipes with non-blocking I/O, advanced select() system call for async reading, and complete **GTKWave waveform visualization** with VCD file generation.

>  This project simulates how hardware FIFO buffers work in digital systems — implemented entirely in software!

---

##  Key Highlights

-  **Non-blocking Async I/O** using O_NONBLOCK flag
-  **Real-time message passing** between writer and reader processes
-  **select() system call** for efficient async monitoring
-  **GTKWave VCD waveform** visualization of all FIFO signals
-  **Makefile** for easy one-command build and run
-  **Hardware-accurate signal simulation** (wr_en, rd_en, data_valid, fifo_empty, fifo_full)

---

##  Features

| Feature | Description |
|---|---|
| Named Pipe FIFO | Linux kernel-level IPC mechanism |
| Async Non-blocking | O_NONBLOCK flag for non-blocking open |
| select() Monitoring | Efficient async event-driven reading |
| Multi Message | 4 real-time messages transmitted |
| VCD Generation | C-generated waveform dump file |
| GTKWave Visual | Full signal waveform 0-200ns |
| Makefile | make all / make run / make clean |

---

## Tools and Technologies

| Tool | Version | Purpose |
|---|---|---|
| GCC | 13.x | C Compiler |
| GTKWave | 3.3.x | Waveform Viewer |
| GNU Make | 4.x | Build Automation |
| Ubuntu | 23.04 | OS Platform |
| Linux Kernel | 6.x | Named Pipe IPC |
| nano | 7.2 | Code Editor |

---

## Project Structure

async_fifo_project/
├── writer.c        Writer process sends messages to FIFO
├── reader.c        Reader process async receives via select()
├── vcd_gen.c       VCD waveform generator in C
├── fifo_wave.vcd   GTKWave compatible waveform dump
├── Makefile        Build system all/run/clean
├── writer          Compiled writer binary
└── reader          Compiled reader binary

---

##  GTKWave Signals Explained

| Signal | Type | Description |
|---|---|---|
| wr_en | wire | Write Enable HIGH when writer is active |
| rd_en | wire | Read Enable HIGH when reader is active |
| data_valid | wire | HIGH when valid data is present in FIFO |
| fifo_empty | wire | HIGH when FIFO has no data |
| fifo_full | wire | HIGH when FIFO is completely full |

---

## System Architecture

Writer Process → open /tmp/myfifo O_WRONLY → write msg → FIFO Named Pipe → Reader Process → open /tmp/myfifo O_RDONLY → select() wait → read buf → print Received

---

## How to Run

git clone https://github.com/Devnmakwana/async_fifo_project.git
cd async_fifo_project
make all
make run
gtkwave fifo_wave.vcd
make clean

---

##  Sample Output

Reader waiting for messages...
Sent: Message 1: Hello!
Received: Message 1: Hello!
Sent: Message 2: FIFO Works!
Received: Message 2: FIFO Works!
Sent: Message 3: Async is Great!
Received: Message 3: Async is Great!
Sent: Message 4: Hello from Mr. Makwana!
Received: Message 4: Hello from Mr. Makwana!
Timeout - no more data!

---

Screenshots

### Writer Code
<img width="1600" height="1055" alt="WhatsApp Image 2026-04-23 at 12 28 16" src="https://github.com/user-attachments/assets/6765f04f-d0a9-425e-bb61-59c56122a2a5" />




### Reader Code
<img width="1600" height="954" alt="WhatsApp Image 2026-04-23 at 12 29 11" src="https://github.com/user-attachments/assets/ac3aafc4-c9b8-48e1-a6db-e3306dc04510" /> <img width="1600" height="915" alt="WhatsApp Image 2026-04-23 at 12 29 37" src="https://github.com/user-attachments/assets/430f6c5e-3bf6-4fff-8e73-db467c1c3f42" />




###  Terminal Output
<img width="1600" height="1250" alt="WhatsApp Image 2026-04-23 at 12 27 02" src="https://github.com/user-attachments/assets/bc3f724c-0f31-46e1-9d73-cd02aa40e67d" />




### GTKWave Waveform Simulation
<img width="1600" height="1011" alt="WhatsApp Image 2026-04-23 at 12 23 06" src="https://github.com/user-attachments/assets/0a081032-3385-4bb5-a652-dd8e8f690f71" />



---

##  Concepts Demonstrated

- Linux Named Pipes FIFO for IPC
- Non-blocking I/O with O_NONBLOCK
- select() system call for async I/O multiplexing
- VCD Value Change Dump file format
- GTKWave digital waveform analysis
- Makefile build automation
- Multi-process communication in Linux

---

##  Author

**Dev Makwana**
- 🎓 ECE Student — Government Engineering College Gandhinagar
- 🔗 LinkedIn: https://linkedin.com/in/dev-makwana-a8815129a
- 🐙 GitHub: https://github.com/Devnmakwana

---

⭐ Star this repo if you found it helpful!
