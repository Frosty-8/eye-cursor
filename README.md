# 👁️🖱️ Eye Controlled Mouse

A Python-based computer vision project that lets you control your mouse **using your eyes**!  
Built using `MediaPipe`, `OpenCV`, and `PyAutoGUI`, this program tracks your eye movements and blinks to move the cursor and perform clicks, offering a futuristic hands-free experience.

---

## 📦 Features

- ✅ Real-time face and eye landmark tracking with MediaPipe
- 🧠 Cursor control using eye movement
- 👁️ Blink-based click detection
- 🔁 Smooth and responsive performance
- 🖥️ Simple setup with `Makefile`

---

## 📸 Demo

> ![Eye Controlled Mouse](https://user-images.githubusercontent.com/your-image-here.gif)  
> *Demo of eye tracking and click gesture*

---

## 🧰 Requirements

Install these using the `Makefile` or manually via `pip`:

```
mediapipe
opencv-python
pyautogui
```

---

## 🧪 Setup Instructions

### 🔧 1. Clone the Repository

```bash
git clone https://github.com/yourusername/eye-controlled-mouse.git
cd eye-controlled-mouse
```

### ⚙️ 2. Run with Makefile (Recommended for Windows)

```bash
make all
```

Or manually:

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

---

## 🧠 System Architecture

The following diagram describes the flow of data and modules involved in this project:

```mermaid
flowchart TD
    subgraph "Runtime Pipeline"
        direction TB
        Webcam["Input Device: Webcam"]:::input
        Video["Video Capture Module (OpenCV)"]:::processing
        FaceMesh["FaceMesh Engine (MediaPipe)"]:::processing
        subgraph "Landmark Processor"
            direction TB
            EyeMap["Eye-movement mapper"]:::processing
            BlinkDet["Blink detector (threshold <0.004)"]:::processing
        end
        Cursor["Cursor Controller (PyAutoGUI)"]:::actuation
        CLI["User Interface/CLI (exit key)"]:::control
    end

    Webcam -->|"video frame"| Video
    Video -->|"video frame"| FaceMesh
    FaceMesh -->|"landmark coords"| EyeMap
    FaceMesh -->|"landmark coords"| BlinkDet
    EyeMap -->|"cursor coords"| Cursor
    BlinkDet -->|"click event"| Cursor
    CLI -.->|"exit command"| Webcam

    subgraph "Project Files"
        direction TB
        Make["Setup Automation: Makefile"]:::control
        Req["Dependencies: requirements.txt"]:::control
        Readme["Documentation: README.md"]:::control
    end

    click Webcam "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click Video "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click FaceMesh "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click EyeMap "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click BlinkDet "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click Cursor "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click CLI "https://github.com/frosty-8/eye-cursor/blob/main/main.py"
    click Make "https://github.com/frosty-8/eye-cursor/tree/main/Makefile"
    click Req "https://github.com/frosty-8/eye-cursor/blob/main/requirements.txt"
    click Readme "https://github.com/frosty-8/eye-cursor/blob/main/README.md"

    classDef input fill:#D0E7FF,stroke:#333,stroke-width:1px
    classDef processing fill:#D0FFD6,stroke:#333,stroke-width:1px
    classDef actuation fill:#FFE2B3,stroke:#333,stroke-width:1px
    classDef control fill:#E0E0E0,stroke:#333,stroke-width:1px
```

> ☝️ You can view this Mermaid diagram properly on platforms like GitHub (with Mermaid enabled), Obsidian, or VS Code (with Mermaid plugin).

---

## 🎮 Controls

| Action            | Trigger                            |
|------------------|------------------------------------|
| Move cursor       | Move your right eye                |
| Click             | Blink left eye (detects vertical distance) |
| Exit Program      | Press `Q` on your keyboard         |

---

## 📁 Project Structure

```
.
├── main.py             # Main application code
├── Makefile            # Automation for setup and run
├── requirements.txt    # Project dependencies
├── README.md           # Project documentation
```

---

## 🐞 Troubleshooting

- Make sure your webcam is functional.
- Run the script in good lighting for accurate detection.
- If `pyautogui` clicks too frequently, adjust the blink detection threshold (`<0.004`).

---

## 💡 Future Improvements

- Add support for both eyes or head movement
- Gesture-based scrolling
- Cross-platform support with Linux/MacOS setup

---

## 🧑‍💻 Author

**Sarthak Dongare**  
📧 Mail : [Mail](sarthakdongare8@gmail.com)  
🌐 Portfolio: [Portfolio](https://my-new-prof.vercel.app/)  
🐙 GitHub: [@Frosty-8](https://github.com/Frosty-8)

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

> ✨ *Built with Python, passion, and a blink of an eye!*





