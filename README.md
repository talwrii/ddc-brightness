# ddc-brightness
**@readwithai** - [X](https://x.com/readwithai) - [blog](https://readwithai.substack.com/) - [machine-aided reading](https://www.reddit.com/r/machineAidedReading/) - [📖](https://readwithai.substack.com/p/what-is-reading-broadly-defined
)[⚡️](https://readwithai.substack.com/s/technical-miscellany)[🖋️](https://readwithai.substack.com/p/note-taking-with-obsidian-much-of)

**This has been merged into lumix: I suggest you use lumix instead**

A simple, fast command-line tool for controlling monitor brightness on Windows and Linux. Designed for easy brightness management across multiple displays. Supports increasing or decreasing brightness by a set amount.

This is a fork of [lumix](https://github.com/Yrrrrrf/lumix) with added support for brigtness.

## Features

- 🖥️ Multi-monitor support
- 📊 Visual brightness indicator
- 🚀 Fast and lightweight
- 🎯 Simple command interface
- 📈 Show brightness range for each monitor
- 🎨 Formatted output
- 💯 Changing brightness by a relative amount

## Alternatives and prior work

I tried various approaches before coming across lumix. There is the `ddcutil` tool - but I had issues with intermittent failures. I tried the monitorcontrol python package - but this did not work at all. There is a monitorcontrol rust package - but this didn't install. There are various libraries in rust for interacting with ddc at a lower level. This makes use the `ddc` package.

## Usage

### Basic Commands

- Get brightness:
```bash
ddc-brightness get  # List all monitors and their brightness
ddc-brightness get 12345  # Specific monitor brightness
```

- Set brightness:
```bash
ddc-brightness set 75  # All monitors to 75%
ddc-brightness set 10+  # Increase all monitors by 10%
ddc-brightness set 5-  # Decrease all monitors by 5%
ddc-brightness set 12345 50  # Specific monitor to 50%
```

You may wish to create a shortcut in your window manager to control the brightness.

### Output Example

```
Monitor 12345: 75% [0..=100] ██████████░░░░░░░░░░
```

Where:
- `12345`: Monitor identifier
- `75%`: Current brightness (bold)
- `██████████░░░░░░░░░░`: Visual brightness indicator
- `[0..=100]`: Supported brightness range

## Troubleshooting

### Common Issues

1. **Monitor Not Found**
   - Ensure the monitor supports DDC/CI
   - Verify the monitor handle is correct

2. **Permission Denied**
   - Run the command prompt as administrator

3. **Invalid Brightness Value**
   - Use values between 0 and 100

### Error Messages

- `Monitor X not found`: Invalid monitor handle
- `Invalid brightness value`: Brightness must be 0-100
- `Error setting brightness`: Monitor might not support DDC/CI

## License

This project is licensed under the [MIT License](./LICENSE).

## About me
I am **@readwithai**. I create tools for reading, research and agency sometimes using the markdown editor [Obsidian](https://readwithai.substack.com/p/what-exactly-is-obsidian).

I also create a [stream of tools](https://readwithai.substack.com/p/my-productivity-tools) that are related to carrying out my work.

I write about lots of things - including tools like this - on [X](https://x.com/readwithai).
My [blog](https://readwithai.substack.com/) is more about reading and research and agency.
