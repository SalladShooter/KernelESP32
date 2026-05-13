# KernelESP32 v1.0

A Unix-like shell and RAM filesystem for ESP-32. Write files, control GPIO pins, read sensors, and run simple scripts all from the serial terminal.

<img width="769" height="659" alt="554" src="https://github.com/user-attachments/assets/82aa5f0c-bf22-4f83-865a-ba3b4258011e" />


# Commands (26):

- `ls - list contents of working directory`
- `cd - change working directory`
- `pwd - prints working directory`
- `mkdir - makes a directory`
- `touch - makes an empty file`
- `cat - prints the contents of a file`
- `echo - prints to an output`
- `rm - removes a file or directory`
- `info - prints info about a file/directory`
- `pinmode - changes the pinmode of a gpio`
- `write - digitalWrite() for the terminal`
- `read - digitalRead() for the terminal`
- `gpio - shorthand for write`
- `pwm - analogWrite() pwm for the terminal`
- `sh - run a script`
- `uptime - prints current uptime`
- `uname - prints system info`
- `dmesg - prints debug messages`
- `df - prints free ram `
- `free - prints free ram `
- `whoami - prints user (always root)`
- `clear - clears screen`
- `reboot - reboots esp32`
- `find - finds file`
- `alias - makes an alias`
- `slots - prints remaining file/directory slots`
- `edit - basic text editor, terminate by typing a "." (no quotes)`
- `sleep - sleeps/waits for a specific amount of time`

## How It Works

The code manages a virtual filesystem stored in RAM:
- Maximum 64 files/directories
- Max 1024 bytes per file content
- 24 character names
- Automatic `/home` and `/dev` directories created on boot
- `/dev/pin2`, `/dev/pin3`, `/dev/pin4` are special files for GPIO

GPIO control uses standard Arduino functions: `pinMode()`, `digitalWrite()`, `digitalRead()`, and `analogWrite()`.

Input is buffered from the serial connection and parsed line-by-line. Commands are case-insensitive.

## Planned Features

- EEPROM support
- I2C interface
- Date cmd
- neofetch cmd

## License

BSD3 - Original by [Arc1011](https://github.com/Arc1011/KernelUNO)

