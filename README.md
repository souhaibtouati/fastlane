# fastlane 🚀  
**Adaptive, Safety‑Critical RTOS Infrastructure**

`fastlane` is an **open‑core runtime and tooling ecosystem** for building adaptive, safety‑critical systems on top of **Zephyr**, **seL4**, and other RTOS kernels. It provides a **Platform Abstraction Layer (PAL)**, manifest‑driven configuration, and tooling to streamline integration across hardware and software stacks.

---

## ✨ Features

- **Platform Abstraction Layer (PAL)**  
  Unified APIs across multiple RTOS kernels (Zephyr, seL4, …).

- **Manifest‑Driven Configuration**  
  YAML manifests define system composition, drivers, and services.

- **Code Generation**  
  Generator tools produce boilerplate, configs, and integration glue.

- **Bridge & Tooling**  
  Utilities for testing, simulation, and developer productivity.

- **Safety‑Critical Extensions (Commercial)**  
  Certified drivers, OTA stack, security modules, and safety case docs.

---

## 📌 Positioning

**fastlane is not another operating system.**  
It’s an **adaptive runtime and tooling ecosystem** that sits *on top of existing RTOS kernels* (Zephyr, seL4, …) to make them **safety‑ready, developer‑friendly, and automation‑first**.

Whereas projects like **Genode OS** reimagine the entire OS stack with a microkernel and user‑space components, fastlane takes a **pragmatic integration approach**:

- Keep using the kernels you already trust (Zephyr, seL4).  
- Add a **Platform Abstraction Layer (PAL)** for portability.  
- Drive everything from **manifests** and **generators** for error‑proof builds.  
- Layer in **certified drivers, OTA, and safety case docs** when you need commercial‑grade assurance.  

---

## 🆚 How fastlane Stands Apart
- **Not a new OS** → complements existing RTOS kernels instead of replacing them.  
- **Safety pipeline built‑in** → manifests, traceability, and safety case docs are first‑class citizens.  
- **Automation‑first** → CI/CD skeletons, Renovate/Dependabot integration, pre‑commit hooks, and governance baked in.  
- **Open‑core model** → Apache 2.0 for PAL, manifests, tooling; commercial license for certified drivers, OTA, and safety modules.  
- **Developer experience** → onboarding, contributor automation, and governance are as important as runtime features.  

---

## 🎯 Who fastlane is for
- Teams building **adaptive, safety‑critical embedded systems** (automotive, avionics, industrial).  
- Projects that want **Zephyr’s ecosystem** or **seL4’s formal verification**, but need a **unified runtime and safety case pipeline**.  
- Communities that value **automation, clarity, and contributor empowerment** as much as technical rigor.  

---

## 📂 Repository Structure

```
fastlane/
├── pal/                # Platform Abstraction Layer (open core)
├── manifests/          # YAML manifests for system composition
├── generator/          # Code generation tools (Python)
├── bridge/             # Integration utilities
├── docs/               # Documentation (open core)
│   └── safety-case/    # Safety case docs (commercial)
├── drivers/            # Certified drivers (commercial)
├── services/           # Safety-critical services (commercial)
├── ota/                # OTA update stack (commercial)
├── security/           # Security modules (commercial)
└── safety-kernel/      # seL4 integration
```

---

## 📜 Licensing

- **Apache 2.0** → Core components (`pal/`, `manifests/`, `generator/`, `bridge/`, `docs/`, `tools/`)  
- **Commercial License** → Certified drivers, OTA stack, security modules, safety case docs  

See [LICENSE](./LICENSE) and [LICENSE-commercial.md](./LICENSE-commercial.md) for details.

---

## 🚀 Getting Started

### Prerequisites
- **Zephyr SDK** and `west` tool  
- **CMake**, `ninja`, `gcc-arm-none-eabi`  
- **Python 3.10+` with `pip`  

### Build Example (Zephyr)
```bash
cd adaptive-runtime/zephyr
west init -l .
west update
west build -b qemu_x86 samples/hello_world
```

### Build Example (seL4)
```bash
cd safety-kernel/sel4
make kernel ARCH=arm PLATFORM=tx2
```

---

## 🧪 CI/CD

- **Linting**: YAML manifests (`yamllint`), C/C++ style (`clang-format`)  
- **Builds**: Zephyr (`qemu_x86`), seL4 (`tx2`)  
- **Static Analysis**: `clang-tidy`, `cppcheck`  
- **Unit Tests**: CMake + CTest  

See [`.github/workflows`](./.github/workflows) for details.

---

## 👥 Contributing

We welcome contributions! Please follow:

- **Branch naming**:  
  - `feature/<short-description>`  
  - `fix/<short-description>`  
  - `hotfix/<short-description>`  
  - `release/v<major>.<minor>.<patch>`  

- **PR requirements**:  
  - Pass CI (lint, build, tests)  
  - Follow [CODEOWNERS](./.github/CODEOWNERS) rules  
  - Complete PR checklist  

See [CONTRIBUTING.md](./CONTRIBUTING.md) for full guidelines.

---

## 🛡️ Governance & Safeguards

- **Branch protection** on `main` and `dev`  
- **Required status checks** (lint, build, tests)  
- **CODEOWNERS enforcement** for PAL, manifests, and safety‑critical code  
- **Pre‑commit hooks** for formatting and linting  

---

## 📬 Contact

- 📧 Commercial licensing & support: **souhaib@fastlane-rtos.com**  
- 🌐 Project updates: [fastlane-rtos.org](https://fastlane-rtos.org) *(placeholder)*  

---

## 🗺️ Roadmap

- [ ] Expand PAL coverage for additional RTOS kernels  
- [ ] Harden OTA stack with delta updates (commercial)  
- [ ] Add automated safety case generation  
- [ ] Continuous fuzzing & formal verification integration  

---
