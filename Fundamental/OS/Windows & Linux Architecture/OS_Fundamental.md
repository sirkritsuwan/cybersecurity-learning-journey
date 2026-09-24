# Operating System

OS : software interface between hardware and software(application)

architecture
```
┌───────────────────────────┐
│       Applications        │
└─────────────┬─────────────┘
              │
              │ System Calls
              ▼
┌───────────────────────────┐
│          KERNEL           │
│ OS services:              │
│ Process Management        │
│ Memory Management         │
│ File Systems              │
│ Networking                │
│ Device Drivers            │
│ Security                  │
└─────────────┬─────────────┘
              │ Driver
              ▼
┌───────────────────────────┐
│         HARDWARE          │
└───────────────────────────┘
```

| concept | windows | linux |
|---|---|---|
| kernel | windows NT kernel | linux kernel |
| services | windows services | daemons/systemd |
| admin privilege | administrator/system | root |


---



# Kernel

kernel : interface for resources management

## function
  1. process management    // `ps aux` 
     ```
     Process (contain PID)
        │
        ├── Thread 1
        ├── Thread 2
        ├── Thread 3
        └── Thread 4
     ```
  2. CPU scheduling
  3. I/O management


