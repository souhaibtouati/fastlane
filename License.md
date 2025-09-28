# fastlane Licensing Overview

fastlane is a hybrid automotive RTOS designed for safety-critical and adaptive ECUs. It is released under a dual-license model to balance open innovation with commercial-grade safety and support.

---

## 🧩 Open Core License: Apache 2.0

The following components are licensed under the permissive [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0):

- `pal/` — Platform Abstraction Layer
- `generator/` — Manifest-driven code generation tools
- `bridge/` — IPC bridge and safety gateway logic
- `docs/` — Developer guides and architecture documentation
- `tools/` — CLI utilities and validators

You are free to use, modify, and distribute these components in commercial or non-commercial projects, provided you comply with the terms of Apache 2.0.

---

## 🔐 Commercial License: fastlane Enterprise

The following components are available under a **commercial license only**:

- `drivers/` — Certified driver kits (CAN FD, TSN Ethernet, etc.)
- `services/` — Adaptive microservices (telemetry, diagnostics, etc.)
- `ota/` — OTA updater, rollback logic, and telemetry hooks
- `security/` — Secure bootloader, key management, and HSM integration
- `ci/` — Safety-compliant CI/CD pipelines and WCET gates
- `docs/safety-case/` — ISO 26262 safety case artifacts and templates

These components are not covered by the Apache 2.0 license and require a commercial agreement for use in production systems.

To inquire about licensing, support, or integration services, please contact:

📧 **souhaib@fastlane-rtos.com**

---

## 🛡️ Safety & Compliance

fastlane is designed to support ASIL-C/D safety goals. Commercial modules include:

- WCET-validated drivers
- Fault injection testvectors
- Traceable safety case documentation
- Long-term support and update guarantees

---

## 🤝 Contributing

We welcome contributions to the open core. By submitting pull requests, you agree to license your contributions under the Apache 2.0 license.

For commercial modules, please contact us to discuss partnership or integration.

---

## 📦 Summary

| Component Group     | License        | Notes |
|---------------------|----------------|-------|
| Core (PAL, bridge, generator) | Apache 2.0     | Open source |
| Certified drivers   | Commercial     | Requires license |
| OTA & security stack| Commercial     | Requires license |
| Safety case docs    | Commercial     | Requires license |

