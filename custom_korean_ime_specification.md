# Custom Korean IME - Specification

## 1. Overview
This document defines the specifications for the **custom Korean Input Method Editor (IME)** used in this project.

⚠ **Note:** This IME behaves differently from standard OS/browser Korean IMEs. Users may experience behavior that differs from typical Korean typing.

**Purpose:** Provide a project-specific, optimized Korean input experience.

**Core Features:**
- Custom composition of initial, medial, and final consonants
- Special character and number input handling
- Real-time input feedback

This document focuses purely on the specification. Implementation examples and live demo links will be provided once the IME is integrated into the CVUI framework.

---

## 2. Custom IME Characteristics
- **Non-standard behavior:** Differs from OS/browser default IMEs.
- **Custom Jamo composition:** Initial, medial, and final consonants are combined using project-specific logic.
- **Special character handling:** Escaping, combination, and conversion differ from standard.
- **Number handling:** Numeric input is processed differently from typical IMEs.
- **Predictability:** Input results may not match expectations from standard Korean IMEs.

> ⚠ Developers and users should understand that this is a **custom IME**, not a standard one.

---

## 3. Usage Notes
Actual code usage examples will be provided after the IME is fully integrated with the CVUI framework. This section will describe how to initialize and use the IME in a real interface.

---

## 4. Development & Maintenance
- **Testing:** Unit and integration tests are performed internally.
- **Contribution:** Fork the repository and submit a pull request. Follow ESLint coding rules.
- **Updates:** When the input logic changes, `specification.md` must be updated accordingly.

---

## 5. License & Copyright
- **License:** MIT License
- **Copyright:** Project development team

