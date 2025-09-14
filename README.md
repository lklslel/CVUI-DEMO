# CVUI Demo — Canvas-based UI Experiments

This repository demonstrates how **Canvas + JavaScript** alone can be used to build simple UI systems, without relying on HTML DOM elements.  
The idea is to show students and developers that JavaScript is inherently flexible and can implement windows, buttons, sliders, and even data-binding on a raw canvas.

This project is licensed under the MIT License - see the LICENSE file for details.

## Steps

### 1. Minimal Window (`01_minimal_window.html`)
- A single draggable window with a title bar.
- Demonstrates the basic idea of drawing UI on canvas and moving it with pointer events.

### 2. Multi Window + FPS (`02_multi_window.html`)
- Multiple draggable windows.
- One window acts as an FPS meter, showing how state can be updated and rendered in real-time.

### 3. Button + Slider (`03_button_slider.html`)
- Introduces interactive components:
  - A **Button** that logs a message when clicked.
  - A **Slider** that logs its current value as it changes.

### 4. Data Binding (`04_data_binding.html`)
- Shows how UI components can update and reflect a shared data object.
- Includes:
  - A **Slider** that updates a value.
  - A **Textbox** for text input.
  - A **Data Viewer Window** that displays the current slider value and text.
  - An **FPS Meter Window** remains for performance reference.

This final step demonstrates a **UI ↔ Data ↔ UI cycle** — similar to modern frameworks — but implemented entirely on a canvas.

## Live Demo
If you enable GitHub Pages for this repository, you can view the final demo here (replace `username` with your GitHub ID):

```
https://lklslel.github.io/cvui-demo/
```

## How to Run Locally
Simply open the HTML files in a modern web browser (Chrome, Firefox, Edge). No server is required.

## Purpose
- Educational: Show that canvas can be used for more than just graphics — it can host interactive UI.
- Inspirational: Encourage experimentation outside of existing frameworks.
- Archival: Capture an approach to UI that values low-level control and creativity.

