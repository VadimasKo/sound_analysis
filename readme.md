## Project list
- [wav_visualizer](#wav_visualizer) - A terminal-based application that visualizes `.wav` files.

## wav_visualizer
This is a TUI (Text User Interface) application that reads `.wav` files and displays the signal in a time graph.

1. The user selects a `.wav` file using `bubbletea file-picker`.
2. The application decodes essential information about the file (bit depth, sample rate, etc.).
3. It creates a `waveline` chart model that handles point rendering.
4. The application reads the `.wav` file in batches and processes it using Go routines.
5. Go routine sample processing steps:
   - Normalizes signal values to [-1, 1] based on the maximum bit depth value.
   - Calculates signal timestamps based on the sample index and channel count.
   - Aggregates parsed results inside a 2D points channel.
6. After aggregation, points are added to the `waveline` model.
7. The result is displayed using the `bubbletea` framework.

<img width="733" alt="Screenshot 2024-09-28 at 16 30 40" src="https://github.com/user-attachments/assets/cdaad0da-4791-4728-9fc8-3f61eef3c207">
