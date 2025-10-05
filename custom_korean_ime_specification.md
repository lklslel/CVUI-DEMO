# Custom Korean IME - Specification

## 1. Overview
This document defines the specifications for the **custom Korean Input Method Editor (IME)** used in this project.  

⚠ **Note:** This IME behaves differently from standard OS/browser Korean IMEs. Users may experience behavior that differs from typical Korean typing.

**Purpose:** Provide a project-specific, optimized Korean input experience.  
**Core Features:** Custom composition of initial, medial, and final consonants, special character and number input handling, real-time feedback.

---

## 2. Custom IME Characteristics
- **Non-standard behavior:** Differs from OS/browser default IMEs.
- **Custom Jamo composition:** Initial, medial, and final consonants are combined using project-specific logic.
- **Special character handling:** Escaping, combination, and conversion differ from standard.
- **Number handling:** Numeric input is processed differently from typical IMEs.
- **Predictability:** Input results may not match expectations from standard Korean IMEs.

> ⚠ Developers and users should understand that this is a **custom IME**, not a standard one.

---

## 3. Code Structure
```
src/
 ├─ customIME.js       # Core IME logic
 ├─ utils.js           # Helper functions
 └─ tests/             # Unit and integration tests
```
- **customIME.js:** Implements the core input logic.
- **utils.js:** Provides helper functions for composition, escaping, and input conversion.
- **tests/:** Contains unit and integration tests.

---

## 4. Usage Examples

### 4.1 Standard Input
| Input | Output |
|-------|--------|
| ㅇㅏㄴㄴㅕㅇ | 안녕 |

### 4.2 Special Characters & Numbers
| Input | Output |
|-------|--------|
| \     | \ (escaped) |
| 1+2   | 1+2 (custom number handling) |

### 4.3 Example Code
```javascript
import { initIME } from './src/customIME.js';

initIME({
  target: document.getElementById('input-area')
});
```

---

## 5. Development & Maintenance
- **Testing:** Unit and integration tests using Jest/Mocha.
- **Contribution:** Fork the repository and submit a pull request. Follow ESLint coding rules.
- **Updates:** When the input logic changes, `specification.md` must be updated accordingly.

---

## 6. License & Copyright
- **License:** MIT License
- **Copyright:** Project development team

