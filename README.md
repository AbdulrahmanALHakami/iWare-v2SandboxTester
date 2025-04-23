# iWare-v2-SandboxTester

**iWare-v2-SandboxTester** is an iOS-based sandbox testing utility designed to run on jailbroken devices. This tool attempts to bypass iOS sandbox protections by accessing restricted system paths, writing to protected locations, and spawning processes — helping security researchers and forensic analysts identify potential sandbox violations or signs of advanced spyware infection.

---

## Purpose

This project simulates common sandbox evasion behaviors to evaluate:
- File system access outside the app’s sandbox
- Write permissions to restricted locations
- Process spawning via `posix_spawn()`

---

##  How It Works

Upon pressing the **"Run SandboxTester"** button:
1. The app attempts to access a list of sensitive file paths.
2. Tries writing to `/var/root/iware_test.txt`.
3. Attempts to spawn a system process (`ls`) using `posix_spawn`.

Results are printed live within the app’s UI.

---

##  Result Interpretation

Each test returns a message like:

- `Allowed` → The file or directory was accessible (indicates a sandbox bypass)
- `Denied` →  Access was blocked (sandbox is intact)
- `Success` → Writing or process spawning succeeded
- `Failed with error: ...` → Operation was blocked or encountered an error (permission denied, etc.)

These outputs help determine the device’s current security posture.

---

## ⚠️ Disclaimer

This tool is **designed for educational and forensic research** purposes **only**. It requires a **jailbroken device** and will not function properly on stock iOS due to Apple’s security restrictions.

---

##  Author

**Abdulrahman Al-Hakami**  
Cybersecurity Researcher | iOS/macOS Reverse Engineer  
[GitHub](https://github.com/AbdulrahmanALHakami)
