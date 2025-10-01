![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
# Ultra-lightweight Canvas  based UI experiment. 
This project is not related to cvui (C++ OpenCV UI library). It is a pure JavaScript + Canvas ultra-light UI experiment.

DOM-free, framework-free UI rendering on HTML5 Canvas.

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

You can try the live demo here:  
[Canvas UI Demo](https://lklslel.github.io/CVUI-DEMO/)

## How to Run Locally
Simply open the HTML files in a modern web browser (Chrome, Firefox, Edge). No server is required.

## Purpose
- Educational: Show that canvas can be used for more than just graphics — it can host interactive UI.
- Inspirational: Encourage experimentation outside of existing frameworks.
- Archival: Capture an approach to UI that values low-level control and creativity.

## Roadmap

**Phase 0 algorithm & architecture design** <<- Now Here

- Basic User Interface implementation on the HTML5 <CANVAS> with PURE JS(like Windows OS)

@ Why need to implementation to UI on <CANVAS> TAG?
: DOM has to Heavy Weight and High Cost since HTML5.
: canvas vs DOM ; System Performance differents you can see. random noise in canvas's 500 × 500 area / random string update of 50 input tags.
: CANVAS VS INPUT : WINNER was CANVAS in 2015. CANVAS tag has Performance and Speed at ALL in NOW.

- korean IME implementation without <INPUT>. Window Object Can Keyboard Event Listening without <INPUT>

@ Why Do This Ways? Human wants convenience.
so, add the HotKey or Shortcut;
TAB : Move to Tab index
Alt-F4 : close the window, ...
So, Web Browser Can Detect Key Input WITHOUT <input> tag.

You can see the next;

1. add the key event on the ' Document ' OBJECT
2. write down ' consloe.log(e.key); ' in Key Event Listener
3. Add Key Event Listener
4. Open the Developer Tool
5. Select Console Tab Menu.
6. Just One Click On the Webpage. and press key and look around to Console

**Phase 1 (Demo)**
- Basic grid (cells with input)
- Formula bar (simple expressions like =A1+B1)
- Minimal functions: SUM, AVG
- Basic chart support (bar or line)

**Phase 2 (Extended)**
- More functions (MIN, MAX, etc.)
- Additional chart types (pie, area)
- Basic cell styling (color, bold)

**Phase 3 (Future Ideas)**
- Image insertion
- Advanced formulas (IF, VLOOKUP)
- Collaboration features

*Note: This project is experimental and will grow step by step.*

## About cvui

cvui is a small experiment with UI on HTML5 canvas.  
It was not made to replace standards or to propose a framework.  
The goal was only to test what might be possible if UI elements  
were drawn and interacted with directly on canvas.  

This code is unfinished and simple, but it records the idea that  
different approaches to UI can be tried outside of the DOM.
