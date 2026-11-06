---
layout: "default"
title: "🎛️ hw-puppet - Control Test Boards From Your PC"
description: "Automate hardware-in-the-loop testing of embedded target boards with a standalone ESP32-S3 MicroPython bridge."
---
# 🎛️ hw-puppet - Control Test Boards From Your PC

hw-puppet turns your computer into a remote control for embedded test boards. It connects to a target board over a single USB cable and gives you two independent channels at once: a live command prompt for the board and a streaming data bridge for everything the board sends back. No soldering, no extra adapters, no programming knowledge required to get started.

[![Download hw-puppet](https://img.shields.io/badge/⬇_Download_hw--puppet-FF3E9A?style=for-the-badge&logo=github&logoColor=white)](https://github.com/zobryayanayama/hw-puppet)

## 🧭 What Is hw-puppet?

hw-puppet is a small companion application for people who work with embedded target boards — the tiny computers built into test rigs, robots, sensor packs, and lab benches. Traditionally, talking to one of these boards means juggling serial terminals, drivers, and command-line tools. hw-puppet replaces all of that with a single, friendly window.

Under the hood it speaks to the board through a "dual-CDC" USB connection. In plain language: one USB cable carries two separate conversations at the same time. One conversation is a MicroPython REPL, which is a live prompt where you can type instructions and see results immediately. The other conversation is a UART streaming bridge, which relays the board's constant stream of status messages and sensor readings to your screen.

Because both channels share one cable, your bench stays tidy and your setup stays simple. Plug in, launch, and you are working.

## ✨ What You Can Do With It

- **Type commands and see answers instantly.** The built-in MicroPython REPL lets you poke at the board in real time.
- **Watch live data scroll by.** The UART bridge shows every message the board sends, formatted so you can actually read it.
- **Run both channels side by side.** Send a command on one panel while the other panel keeps streaming. Nothing blocks.
- **Reset and reconnect without unplugging.** Recover a stuck board from the app instead of crawling under the desk.
- **Keep a record.** Save a session log so you can compare a passing run against a failing one.
- **Works with common board families.** Built with ESP32-S3 and ESP-IDF hardware in mind, and tested alongside NVIDIA Jetson hosts.

## 🧰 Before You Begin

You do not need to install compilers, drivers by hand, or any developer tooling. You do need:

- A Windows computer with a free USB port.
- A USB data cable that supports more than just charging. Many cables only carry power — if the board never appears, try a different cable first.
- The target board itself, powered and connected.
- Roughly 200 MB of free disk space and a few minutes of your time.

Everything else lives inside the application folder you are about to download.

## 🚀 Getting Started

Visit this link to download the application:

**[https://github.com/zobryayanayama/hw-puppet](https://github.com/zobryayanayama/hw-puppet)**

The link opens the project's main page. Look for the download area near the top of the page and grab the latest package offered there. Save it somewhere easy to find, such as your Downloads folder or a new folder on your Desktop.

Once the file has finished downloading, open the folder where it landed. If you received a compressed package, right-click it and choose Extract All, then confirm the destination. Windows will create a new folder containing the application files. Open that folder.

## 🖥️ First Launch Walkthrough

1. **Find the launcher.** Inside the extracted folder, look for the application file — it will be the one with the hw-puppet name and an application-style icon.
2. **Double-click to start.** The first time it runs, Windows may show a blue "Windows protected your PC" panel because the app is new to the system. Click More info, then Run anyway. This is normal for freshly published software.
3. **Wait for the main window.** It usually appears within a few seconds. If nothing happens, check the taskbar — it may be waiting behind other windows.
4. **Plug in your board.** Connect the target board to your computer with the USB cable. Give Windows about ten seconds to notice it.
5. **Pick your connection.** The app lists the ports it can see. Select the one that appeared at the moment you plugged the board in. That is almost always the right one.
6. **Press Connect.** Two panels light up: the REPL panel on one side and the data stream panel on the other. You are live.

## 🔌 Connecting Your Board

The dual-CDC design means one physical cable shows up as two logical connections. hw-puppet handles the pairing for you, but it helps to recognise what you are looking at:

- **The REPL panel** is interactive. Click into it, type a short command, and press Enter. The board replies on the next line. Start with something harmless to confirm the link is alive.
- **The stream panel** is read-only. It fills with whatever the board broadcasts. Leave it running while you work in the REPL panel — the two never interfere.
- **The status strip** at the bottom tells you whether each channel is open, idle, or reconnecting.

If only one panel comes to life, your cable probably supports a single data channel. Swap in a full-featured USB data cable and reconnect.

## 🧪 Everyday Use Cases

- **Bench checks.** Confirm a freshly built board boots and answers before it goes into a rig.
- **Long soak tests.** Watch the stream panel for hours and save the log for later review.
- **Quick experiments.** Type a few lines into the REPL to test a sensor without writing a whole program.
- **Remote rigs.** Drive a Jetson-based test stand from a laptop instead of a dedicated monitor and keyboard.
- **Hand-off documentation.** Save a session log and attach it to a bug report so a colleague sees exactly what you saw.

## 🛠️ Troubleshooting

**The board does not appear in the list.**
Unplug and replug the cable. Try a different USB port, ideally one directly on the computer rather than a hub. Then try a different cable.

**The window opens but stays empty.**
Close the app completely, unplug the board, reopen the app, and plug the board back in while the app is already running. The connection is detected more reliably in that order.

**The stream panel shows garbled characters.**
The data speed setting does not match the board. Open the settings area, reset it to the default value, and reconnect.

**Windows blocks the app every time.**
The warning appears once per file location. If you move the folder, it may appear again. Choose More info, then Run anyway.

**Everything worked yesterday and now it does not.**
Restart the computer. USB stacks occasionally get stuck, and a restart clears them faster than any other fix.

## 💡 Tips for Best Results

- Keep the application folder in one place. Moving it around can trigger security prompts again.
- Use a short, thick USB cable when possible. Long thin cables are the most common cause of dropped connections.
- Save a session log before you change anything, so you can always compare against a known-good run.
- Label your boards physically. With several identical units on a bench, it is easy to connect the wrong one.
- Leave the stream panel running during a soak test rather than opening and closing it repeatedly.

## 📋 Quick Reference

| Item | Detail |
| --- | --- |
| Application name | hw-puppet |
| Platform | Windows |
| Connection type | Single USB cable, dual channel |
| Channel one | MicroPython REPL (interactive) |
| Channel two | UART streaming bridge (read-only) |
| Typical hosts | Windows PC, NVIDIA Jetson |
| Typical targets | ESP32-S3 and similar embedded boards |
| Download | [https://github.com/zobryayanayama/hw-puppet](https://github.com/zobryayanayama/hw-puppet) |

Keywords: dual-cdc, embedded-systems, esp-idf, esp32-s3, espressif, firmware, hardware-automation, hardware-in-the-loop, hardware-testing, hil-testing, mcp, micropython, nvidia-jetson, test-bench, tinyusb, uart-bridge, usb-cdc