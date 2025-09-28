
# Developer Onboarding Guide for fastlane

Welcome to **fastlane** — a modular, safety-compliant RTOS for automotive ECUs. This guide will help you set up your development environment, understand the repo structure, and start contributing effectively.

---

## 🚀 Quick Start

### 1. Clone the repo with submodules

```bash
git clone --recurse-submodules https://github.com/souhaibtouati/fastlane.git
cd fastlane
```

If you forgot `--recurse-submodules`, run:

```bash
git submodule update --init --recursive
```

### 2. Install prerequisites

- Git (with submodule support)
- Python 3.10+
- CMake + Ninja
- ARM GCC toolchain
- Visual Studio Code or CLion (recommended)

Optional:
- Docker (for isolated builds)
- QEMU (for virtual target testing)

---

## 🧱 Repo Structure Overview

| Folder                     | Purpose                                      |
|----------------------------|----------------------------------------------|
| `adaptive-runtime/zephyr/` | Zephyr fork (submodule)                      |
| `safety-kernel/sel4/`      | seL4 fork (submodule)                        |
| `pal/`                     | Platform Abstraction Layer                   |
| `drivers/`                 | Driver kits with manifests                   |
| `services/`                | Adaptive microservices                       |
| `manifests/`               | ECU and driver manifest definitions          |
| `generator/`               | Codegen tools (manifest → headers/scripts)  |
| `bridge/`                  | IPC bridge between domains                   |
| `ota/`                     | OTA updater and rollback logic               |
| `security/`                | Secure boot and key management               |
| `ci/`                      | CI/CD pipelines and test configs             |
| `docs/`                    | Developer guides and safety case             |
| `tools/`                   | CLI utilities and validators                 |

---

## 🧩 Manifest-Driven Workflow

fastlane uses declarative manifests to drive configuration and code generation.

### Example workflow:

1. Define your ECU in `manifests/ecu/my_ecu.yaml`
2. Add driver manifests in `manifests/drivers/`
3. Run the generator:

```bash
python generator/cli/gen_config.py --ecu manifests/ecu/my_ecu.yaml
```

This will emit:
- PAL bindings
- Linker scripts
- Task tables
- Build overlays

---

## 🛠️ Building Zephyr Targets

```bash
cd adaptive-runtime/zephyr
west init -l .
west update
west build -b <board> samples/hello_world
```

For fastlane overlays:

```bash
west build -b <board> -- -DEXTRA_CONF_FILE=fastlane.conf
```

---

## 🧪 Testing seL4 Safety Domain

```bash
cd safety-kernel/sel4
make clean
make kernel ARCH=arm PLATFORM=tx2
```

For IPC bridge integration:

```bash
make bridge-test ARCH=arm PLATFORM=tx2
```

---

## 🤝 Contributing

### Code Standards

- C/C++: use `clang-format`
- Python: follow PEP8
- YAML: 2-space indentation, validate with `yamllint`

### Branching

- `main`: stable releases
- `dev`: active development
- `feature/*`: new features
- `fix/*`: bug fixes

### Commit Style

```
[driver] Add CAN FD manifest and testvector
[generator] Fix linker script output path
```

---

## 📬 Need Help?

- Issues: [GitHub Issues](https://github.com/souhaibtouati/fastlane/issues)
- Email: souhaib@fastlane-rtos.com
- Docs: See `docs/architecture.md`, `docs/pal-api.md`, and `docs/manifest-guide.md`

---

Welcome aboard 
```
