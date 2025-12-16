# 📦 AutoBuildWatcher

A smart Bash utility that automatically watches your C++ project for changes and rebuilds using CMake and Make. It’s designed for rapid C++ development with minimal configuration.

---

## 🚀 Features

* 🔍 **Live file watching** with `entr`
* 💪 Automatically rebuilds on:

  * 🔧 File changes (`.cpp`, `.h`, `.hpp`) → triggers `make`
  * 🧱 Structural changes (new/deleted files/folders) → triggers `cmake + make`
* 🧰 Auto-creates project structure:

  * `src/`, `include/`, `build/`
  * Generates default `main.cpp`
  * Generates minimal `CMakeLists.txt`
* 🧪 Runs your binary after successful build
* 🛌 Cleans up watchers with `Ctrl+C`

---

## 🧱 Requirements

Make sure you have the following tools installed:

* `bash`
* `cmake`
* `make`
* [`entr`](https://eradman.com/entrproject/)

The script can install any missing tools for you (Linux/macOS).

---

## 📁 Project Structure

After the first run, your project will look like:

```
.
├── autoBuildWatcher.sh
├── build/                # Compiled binaries
├── include/              # Header files
├── src/
│   ├── main.cpp          # Entry point
│   └── CMakeLists.txt    # CMake source definition
└── CMakeLists.txt        # Root CMake config
```

---

## 🔧 Installation

### Linux (Debian/Ubuntu):

```bash
sudo apt update
sudo apt install entr cmake make
```

### macOS (with Homebrew):

```bash
brew install entr cmake make
```

If you don’t have Homebrew, the script will prompt to install it for you.

---

## ▶️ Usage

1. Make the script executable:

```bash
chmod +x autoBuildWatcher.sh
```

2. Run it:

```bash
./autoBuildWatcher.sh
```

This will:

* Create necessary folders and files
* Build the project with CMake/Make
* Start watching your files and folders

---

## ⚙️ How It Works

The script uses two watchers:

### 1. **Structure Watcher**

* Watches for file/folder additions or deletions
* Runs:

  ```bash
  cd build && cmake .. && make && ./src/app
  ```

### 2. **File Modification Watcher**

* Watches `.cpp`, `.h`, `.hpp` changes
* Runs:

  ```bash
  cd build && make && ./src/app
  ```

---

## 🧼 Stopping the Watchers

Press `Ctrl + C` to stop the watchers.
The script handles cleanup and stops background processes safely.

---

## 📃 Example Output

```bash
📁 Creating folders and files if necessary...
✔ Created folder: src
✔ Created folder: include
✔ Created folder: build
✔ Created file: main.cpp
✔ Created file: CMakeLists.txt
✔ Created file: src/CMakeLists.txt

🚰 Initializing build directory...
-- Configuring done
-- Generating done
-- Build files written to ./build

📡 Watcher : Rebuilding watch list for structure changes...
[🖁 STRUCTURE CHANGED]

📡 Watching for file modifications...
[⚙️  FILE MODIFIED]
```

---

## 🧠 FAQ

**Q: Why two watchers?**
A: To minimize rebuild cost. Modifying a `.cpp` just runs `make`, while structure changes (new files/folders) re-trigger `cmake`.

**Q: Why use `entr`?**
A: It's efficient and lightweight for watching file changes without manually polling or writing complex watchers.

**Q: Can I customize the project name or binary?**
A: Yes. Edit the generated `CMakeLists.txt` or change the output name inside the script.

---

## 🙌 Contribution

Feel free to fork the repo and make improvements! PRs are welcome.

Happy Coding! 🚀
