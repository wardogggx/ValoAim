# Arduino Mouse Spoofer - Permission Fix Guide

## Common Error
If you encounter this error when running the spoofer:
```
PermissionError: [Errno 13] Permission denied: 'C:\\Users\\skyxs\\AppData\\Local/Arduino15\\packages/arduino/hardware/avr/1.8.6/boards.txt'
```

## Solution: Fix Read-Only Attribute

### Step 1: Navigate to the Arduino Directory
1. Open File Explorer
2. Navigate to: `C:\Users\[YourUsername]\AppData\Local\Arduino15\packages\arduino\hardware\avr\1.8.6\`
3. Or press `Win + R`, type `%LOCALAPPDATA%\Arduino15\packages\arduino\hardware\avr\1.8.6\` and press Enter

### Step 2: Uncheck Read-Only
1. Right-click on the `boards.txt` file
2. Select "Properties"
3. In the Properties window, look for "Attributes" section
4. **Uncheck the "Read-only" checkbox**
5. Click "Apply"
6. Click "OK"

### Step 3: Run the Spoofer
1. Now you can run `Hide.py` or `Hide alertnative.py` without permission errors
2. The script will be able to modify the boards.txt file successfully

## Alternative Solutions
- **Run as Administrator**: Right-click the script and select "Run as Administrator"
- **Close Arduino IDE**: Make sure Arduino IDE is completely closed before running
- **Use Un-spoof First**: Run option 2 first to clean up, then option 1 to spoof

## Why This Happens
Windows protects system directories and files by marking them as read-only. The Arduino boards.txt file is in a protected location, so the spoofer needs write permissions to modify it.

## Note
After running the spoofer, you may want to re-check the read-only attribute for security purposes.
