# SPECIFICATION.md

# Korean IME Specification

## 1. Overview
This document describes the structure and behavior of the Korean IME (Input Method Editor) class.
The IME converts keyboard input into Korean characters, handling initial (choseong), medial (jungseong), and final (jongseong) consonants.
It also supports English input, numbers, and special keys.

**High-level flow:**
1. Key input received.
2. Detect mode (Korean or English).
3. Process input: initial, medial, final consonants.
4. Check for composable characters.
5. Compose final character.
6. Return `{ commit, preedit }`.

---

## 2. Data Structures

- **`ko_f`**: Initial consonants array.
- **`ko_s`**: Medial vowels array.
- **`ko_t`**: Final consonants array.
- **`ko_s_ma`**: Mapping array for medial vowel combinations.
- **`ko_t_ma`**: Mapping array for final consonant combinations.
- **`keymap`**: Keyboard keys (A-Z) mapped to Hangul characters.
- **`korean`**: Hangul characters corresponding to `keymap`.
- **`sp`**: Special function keys (Backspace, Enter, Shift, etc.).
- **`F`**: Function keys F1-F12.
- **`keep`**: Currently pressed keys (used to detect Shift, etc.).
- **`#f` / `#s` / `#t`**: Current composing initial, medial, and final characters.
- **`#str`**: Committed string.
- **`#mode`**: Current input mode (0 = English, 1 = Korean).

---

## 3. Core Methods

- **`mix_(pre_input, mix_array, char)`**  
  Combines two characters into one using a mapping array. Returns the combined character or `false` if combination is not possible.

- **`is_mix_str(mix_array, string)`**  
  Checks if a given string exists in a mix array. Returns object `{ ma_index, index }` if exists, otherwise `false`.

- **`mix_second(char)`**  
  Uses `mix_` for medial vowel combination.

- **`mix_third(char)`**  
  Uses `mix_` for final consonant combination.

- **`getComposed()`**  
  Returns the composed Hangul character based on `#f`, `#s`, and `#t`. Uses Unicode calculation to form correct syllable. Returns empty string if nothing to compose.

- **`input(e, char_)`**  
  Main input handler. Steps:
  1. Detect if `char_` is special character or key.
  2. If special key (Backspace, Space, HangulMode, etc.), handle accordingly.
  3. If English mode:
     - Reset Korean composing characters if any.
     - Commit character directly.
  4. If Korean mode:
     - Map key to Hangul character (shifted or not).
     - Handle initial, medial, final input.
     - Use `mix_second()` and `mix_third()` for valid combinations.
     - Return `{ commit, preedit }`.

- **`catch(char)` / `release(char)`**  
  Track currently pressed keys in `keep` array.

- **`reset()`**  
  Clears `#f`, `#s`, and `#t`.

- **`add_string(str_)` / `get_string()`**  
  Add to or retrieve committed string.

---

## 4. Design Philosophy

- **Speed-focused**: Uses array indices instead of complex calculations.
- **Minimal exceptions**: Functions assume valid data, reducing runtime checks.
- **Human-curated abstraction**: Predefined mapping arrays simplify real-time input.

---

## 5. Flow Diagram (Text Version)

```
Key Input
   │
   ▼
Mode Check (Korean / English)
   │
   ├─ English Mode ──> Commit character directly
   │
   └─ Korean Mode ──> Map key to Hangul character
                       │
                       ▼
                 Determine type:
                 ┌───────────┬───────────┬───────────┐
                 │ Initial   │ Medial    │ Final     │
                 └───────────┴───────────┴───────────┘
                       │
                       ▼
               Check for mix combinations
                       │
                       ▼
                 Compose character
                       │
                       ▼
                  Return { commit, preedit }
```

---

## 6. Extension Points

- Add new mapping rules for Hangul combinations.
- Extend event handling for additional keys or shortcuts.
- Support new input modes or alternative layouts.

---

