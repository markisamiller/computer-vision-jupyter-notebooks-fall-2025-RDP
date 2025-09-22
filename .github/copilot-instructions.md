# Computer Vision Jupyter Notebooks - AI Coding Agent Instructions

## Overview
This is an educational computer vision repository structured as interactive Jupyter notebooks covering fundamental CV topics from basic image processing to stereo vision. Each chapter builds progressively, combining theory with hands-on coding exercises.

## Project Architecture

### Chapter Structure
- **Sequential learning path**: Chapters 1-12 follow a logical progression from basic concepts to advanced applications
- **Self-contained chapters**: Each chapter directory includes notebooks, images, and sometimes data folders
- **Problem-driven approach**: Each notebook starts with a real-world problem context (e.g., license plate recognition, traffic sign detection)

### Key Directories
- `Chapter XX. Topic/`: Contains numbered notebooks (e.g., `2.1 IP tools.ipynb`), `images/`, and sometimes `data/`
- `utils/`: Shared visualization and geometry utilities (see patterns below)
- `Assignment 1/`: Contains coursework with PDF specifications

## Technology Stack & Dependencies

### Core Libraries (requirements.txt)
- **OpenCV 4.2.0** (`opencv-contrib-python`): Primary computer vision library
- **NumPy 1.18.1**: Array operations and mathematical functions
- **Matplotlib 3.2.0**: Plotting and visualization (figure size set to 15x15 by default)
- **Jupyter ecosystem**: Interactive notebook environment with widgets support

### Import Patterns
Standard imports found in most notebooks:
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
import matplotlib
matplotlib.rcParams['figure.figsize'] = (15.0, 15.0)  # or (8.0, 8.0)
```

## Coding Conventions

### Image Handling
- **File paths**: Use `images_path = './images/'` variable for relative paths
- **Image loading**: `cv2.imread()` with explicit color flags (`cv2.IMREAD_GRAYSCALE`, `cv2.IMREAD_COLOR`)
- **Display**: Always use `plt.imshow()` with `cmap='gray'` for grayscale images
- **Subplot organization**: Heavy use of `plt.subplot()` for side-by-side comparisons

### Mathematical Notation
- **LaTeX formatting**: Extensive use of LaTeX in markdown cells for mathematical expressions
- **Equation blocks**: Use `$$` for complex formulas and `$` for inline math
- **Figure spacing**: Add `$\\[2pt]$` or similar for vertical spacing after images

### Visualization Patterns
- **Histograms**: Use `plt.hist(image.ravel(), 256, [0,256])` for intensity distribution
- **Interactive widgets**: Import `from ipywidgets import interactive, fixed, widgets` for parameter exploration
- **Color coding**: Random colors for feature visualization: `tuple(np.random.randint(0,255,3).tolist())`

## Utils Directory Patterns

### Specialized Visualization Functions
- `drawlines.py`: Epipolar line visualization with random colors
- `PlotEllipse.py`: Gaussian covariance ellipse plotting (uncertainty visualization)
- `plot3DScene.py`: 3D point cloud rendering with RGB coloring and specific view angles
- `third_party/pysift.py`: Custom SIFT implementation following Lowe's paper

### Function Signatures
Utils follow this pattern:
- Input validation and preprocessing
- Mathematical computations using eigenvalue decomposition
- Matplotlib-based rendering with customizable parameters
- Return plot handles for further manipulation

## Assignment & Exercise Patterns

### Problem Context Sections
Each notebook begins with a real-world scenario:
- Background story (UMA parking security, AliquindoiCars startup)
- Specific technical challenge
- Provided datasets and expected deliverables

### Assignment Structure
- **Green highlighted sections**: `**<span style="color:green"><b><i>ASSIGNMENT X</i></b></span>**`
- **Progressive complexity**: Start with feature extraction, progress to classification
- **Matrix operations**: Heavy use of shape-specific matrices (e.g., 20x7 for Hu moments)

## Development Workflow

### Image Processing Pipeline
1. Load images with appropriate color space
2. Apply preprocessing (smoothing, enhancement, binarization)
3. Feature extraction (contours, keypoints, descriptors)
4. Visualization with side-by-side comparisons
5. Statistical analysis (histograms, scatter plots)

### Camera Calibration Workflow
- Checkerboard pattern detection
- Intrinsic/extrinsic parameter estimation
- Distortion correction using polynomial models
- 3D reconstruction and stereo vision applications

## Integration Points

### OpenCV-Matplotlib Bridge
- Convert BGR to RGB: `cv2.cvtColor(image, cv2.COLOR_BGR2RGB)`
- Coordinate system differences handled in geometry utilities
- Consistent colormap usage across visualization functions

### Educational Integration
- Theory sections use mathematical notation and academic references
- Code immediately follows theoretical concepts
- Real-world applications demonstrate practical relevance
- Progressive skill building from basic to advanced topics

When working with this codebase, prioritize educational clarity over optimization, maintain consistent visualization patterns, and ensure mathematical concepts are properly illustrated with code examples.