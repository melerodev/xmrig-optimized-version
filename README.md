# XMRig - Donation-Free Fork

> [!CAUTION]
> **This is NOT the official XMRig repository.**
>
> This is a modified fork of the original project. For the official and up-to-date version, visit:
>
> **Original repository:** [https://github.com/xmrig/xmrig](https://github.com/xmrig/xmrig)

---

## 🔧 Modifications Made

> [!WARNING]
> This version contains **ONLY ONE MODIFICATION** compared to the original code:
>
> * **Donation level set to 0%** (completely disabled)

### Specific Change

Modified file: `src/donate.h`

```cpp
// ORIGINAL (1% default donation)
constexpr const int kDefaultDonateLevel = 1;
constexpr const int kMinimumDonateLevel = 1;

// MODIFIED (0% donation)
constexpr const int kDefaultDonateLevel = 0;
constexpr const int kMinimumDonateLevel = 0;
```

---

## ⚖️ Ethical Consideration

> [!IMPORTANT]
> **XMRig is an open-source and free project.**
>
> The original developers request a **1% donation** (1 minute per 100 minutes) to support the project's development.
>
> If you decide to use this donation-free version, **please consider making a one-time donation** to the creators: 

**XMR Wallet:**

```
48edfHu7V9Z84YzzMa6fUueoELZ9ZRXq9VetWzYGzKt52XU5xvqgzYnDK9URnRoJMk1j8nLwEVsaSWJ4fhdUyZijBGUicoD
```

**More info:** [https://xmrig.com/donate](https://github.com/xmrig/xmrig)

---

## 🏗️ Building from Source

> [!TIP]
> Make sure all dependencies are installed before compiling.

### Linux / WSL

```bash
# 1. Install dependencies
sudo apt-get update
sudo apt-get install -y git build-essential cmake libuv1-dev libssl-dev libhwloc-dev

# 2. Clone repository
git clone [YOUR_REPOSITORY_URL]
cd xmrig

# 3. Compile
mkdir build && cd build
cmake .. 
make -j$(nproc)

# Binary will be at: ./xmrig
```

### macOS

```bash
# 1. Install dependencies (requires Homebrew)
brew install cmake libuv openssl hwloc

# 2. Compile
mkdir build && cd build
cmake ..  -DOPENSSL_ROOT_DIR=/usr/local/opt/openssl
make -j$(sysctl -n hw.ncpu)
```

### Windows

```bash
# Requirements: Visual Studio 2019+ and CMake

mkdir build
cd build
cmake .. -G "Visual Studio 16 2019" -A x64
cmake --build .  --config Release

# Binary will be at: build\Release\xmrig.exe
```

---

## 🚀 Basic Usage

```bash
# Generic example
./xmrig -o POOL:PORT -u YOUR_WALLET -p x

# Example with NiceHash
./xmrig -o stratum+tcp://randomxmonero.auto.nicehash.com:9200 \
        -u YOUR_WALLET. WORKER_NAME \
        -p x \
        --nicehash \
        -a rx/0
```

> [!TIP]
> For advanced configuration, use a JSON file:
>
> ```bash
> ./xmrig -c config.json
> ```
>
> Generate an example config with: `./xmrig --print-config > config.json`

---

## 📋 Check Donation Level

To confirm the donation level is 0%: 

```bash
# Method 1: Check configuration
./xmrig --dry-run | grep -i donate

# Method 2: Check startup output
./xmrig --version

# Method 3: Search binary
strings ./xmrig | grep -i donate
```

You should see: `donate-level: 0` or `DONATE 0%`

---

## ⚠️ Disclaimer

> [!CAUTION]
>
> * This modification is **for educational and personal use only**
> * **We are not responsible** for how this software is used
> * **Respect your local laws** regarding cryptocurrency mining
> * Some pools or services may have policies regarding modified software
> * **DO NOT provide technical support** while claiming to be the original project

---

## 📜 License

This project keeps the same license as the original:

**GNU General Public License v3.0**

See [LICENSE](LICENSE) file for full details.

---

## 🔗 Useful Links

| Resource                   | URL                                                                            |
| -------------------------- | ------------------------------------------------------------------------------ |
| **Official repository**    | [https://github.com/xmrig/xmrig](https://github.com/xmrig/xmrig)               |
| **Official documentation** | [https://xmrig.com/docs](https://xmrig.com/docs)                               |
| **Official support**       | [https://github.com/xmrig/xmrig/issues](https://github.com/xmrig/xmrig/issues) |
| **Web configurator**       | [https://xmrig.com/wizard](https://xmrig.com/wizard)                           |
| **XMRig Reddit**           | [https://www.reddit.com/r/XMRig/](https://www.reddit.com/r/XMRig/)             |
| **Benchmarks**             | [https://xmrig.com/benchmark](https://xmrig.com/benchmark)                     |

---

## 📝 FAQ

<details>
<summary><b>Why does this fork exist?</b></summary>

Some users prefer full control over their software and removing any automatic donation, opting to make voluntary direct contributions when they see fit.

</details>

<details>
<summary><b>Is it legal to modify XMRig?</b></summary>

Yes, XMRig uses the GPL-3.0 license which **allows modifications**. However, you must:

* Keep the same license
* Clearly indicate the modifications made
* Not remove the original credits

</details>

<details>
<summary><b>Will I get automatic updates?</b></summary>

No. This is a static fork. To get the latest features and security fixes, you must:

* Follow the official repository
* Apply the modification manually to new versions
* Or compile from the original repository with your changes

</details>

<details>
<summary><b>Should I still donate?</b></summary>

**We strongly recommend it.** If you profit from using XMRig, consider donating to the original project. Quality software development requires time, effort, and resources.

</details>

---

## 🤝 Contributions

> [!NOTE]
> If you find bugs or improvements, consider reporting them to the **original repository** rather than this fork, so everyone benefits.
>
> Only use issues here for problems specific to this modification.

---

## 🌟 Credits

**Original XMRig Developers:**

* [@xmrig](https://github.com/xmrig)
* [@sech1](https://github.com/SChernykh)

And all [original project contributors](https://github.com/xmrig/xmrig/graphs/contributors).
message.txt
6 KB
