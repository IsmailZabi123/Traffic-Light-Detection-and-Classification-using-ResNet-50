# Traffic Light Detection and Classification using ResNet-50

## Overview

This project implements a **Traffic Light Detection and Classification System** using the ResNet-50 deep learning architecture. The application detects and classifies traffic lights into 7 different categories with a user-friendly GUI built using Tkinter.

## Features

- **Multi-class Classification**: Classifies traffic lights into 7 categories:
  - Go
  - Go Forward
  - Go Left
  - Stop
  - Stop Left
  - Warning
  - Warning Left

- **Deep Learning Model**: Uses ResNet-50 pre-trained model with transfer learning
- **GUI Interface**: Interactive Tkinter-based graphical interface for easy usage
- **Model Training**: Functionality to train models on custom datasets
- **Accuracy Evaluation**: Provides precision, recall, F1-score, and confusion matrices
- **Image Processing**: Leverages OpenCV for image preprocessing and manipulation
- **Data Visualization**: Matplotlib integration for visualizing results and metrics

## Project Structure

```
TrafficLight/
├── README.md                          # Project documentation
├── requirements.txt                   # Python dependencies
├── run.bat                           # Batch script to run the application
├── TrafficLight.py                   # Main application file
├── Dataset/                          # Training dataset
│   ├── go/
│   ├── goForward/
│   ├── goLeft/
│   ├── stop/
│   ├── stopLeft/
│   ├── warning/
│   └── warningLeft/
├── model/                            # Pre-trained models and weights
│   ├── frozen_inference_graph.pb
│   ├── graph.pbtxt
│   ├── model.ckpt.data-00000-of-00001
│   ├── model.ckpt.index
│   ├── model.ckpt.meta
│   ├── mscoco_label_map.pbtxt
│   ├── resnet_history.pckl           # Training history
│   ├── resnet_weights.hdf5           # Trained ResNet-50 weights
│   ├── X.txt.npy                     # Feature data
│   └── Y.txt.npy                     # Label data
├── testImages/                       # Test images for evaluation
├── Videos/                           # Video files for testing
└── utils/                            # Utility modules
    ├── __init__.py
    ├── category_util.py
    ├── config_util.py
    ├── dataset_util.py
    ├── label_map_util.py
    ├── learning_schedules.py
    ├── metrics.py
    ├── np_box_list_ops.py
    ├── np_box_list.py
    ├── np_box_ops.py
    ├── object_detection_evaluation.py
    ├── per_image_evaluation.py
    ├── shape_utils.py
    ├── static_shape.py
    ├── string_int_label_map_pb2.py
    ├── test_utils.py
    ├── variables_helper.py
    ├── visualization_utils.py
    └── BUILD
```

## Installation

### Prerequisites

- Python 3.x
- pip package manager

### Step 1: Clone or Download the Project

Navigate to the project directory in your terminal.

### Step 2: Install Dependencies

Install all required packages using the requirements.txt file:

```bash
pip install -r requirements.txt
```

Or install manually using the provided dependency list:

```bash
pip install numpy==1.19.2
pip install pandas==0.25.3
pip install matplotlib==3.1.1
pip install keras==2.3.1
pip install tensorflow==1.14.0
pip install h5py==2.10.0
pip install protobuf==3.16.0
pip install scikit-learn==0.22.2.post1
pip install seaborn==0.10.1
pip install opencv-python==4.1.1.26
pip install opencv-contrib-python==4.3.0.36
pip install Pillow==9.5.0
```

## Usage

### Running the Application

#### Option 1: Using the Batch Script (Windows)
```bash
run.bat
```

#### Option 2: Running with Python
```bash
python TrafficLight.py
```

### GUI Features

Once the application launches, you can:

1. **Load Dataset**: Select and load images from the Dataset folder
2. **Train Model**: Train the ResNet-50 model on your dataset
3. **Evaluate Model**: Test the model and view accuracy metrics
4. **Predict on Images**: Classify traffic light images
5. **View Metrics**: See precision, recall, F1-score, and confusion matrices
6. **Process Videos**: Detect and classify traffic lights in video files

## Model Architecture

The project uses **ResNet-50** (Residual Network with 50 layers):

- **Transfer Learning**: Pre-trained weights from ImageNet
- **Customization**: Final layers adapted for 7-class traffic light classification
- **Optimization**: Uses categorical cross-entropy loss with Adam optimizer
- **Regularization**: Includes dropout and batch normalization layers

## Dataset Structure

The dataset is organized into 7 classes under the `Dataset/` folder:

- `go/` - Images of green lights for general movement
- `goForward/` - Green lights for forward movement
- `goLeft/` - Green lights for left turn
- `stop/` - Red lights indicating stop
- `stopLeft/` - Red lights for left turn restriction
- `warning/` - Yellow/amber warning lights
- `warningLeft/` - Yellow/amber for left turn warnings

Each class folder contains labeled training images in common formats (JPG, PNG, etc.).

## Output and Results

The application generates:

1. **Trained Model**: Saved as `model/resnet_weights.hdf5`
2. **Training History**: Stored as `model/resnet_history.pckl` (accuracy, loss plots)
3. **Feature Data**: `model/X.txt.npy` and `model/Y.txt.npy`
4. **Evaluation Metrics**:
   - Accuracy score
   - Precision per class
   - Recall per class
   - F1-score per class
   - Confusion matrix visualization

## Technologies Used

- **Python 3.x**: Programming language
- **TensorFlow/Keras**: Deep learning framework
- **ResNet-50**: Pre-trained CNN architecture
- **OpenCV**: Image processing
- **Scikit-learn**: Machine learning utilities and metrics
- **Matplotlib & Seaborn**: Data visualization
- **Tkinter**: GUI framework
- **NumPy & Pandas**: Numerical and data processing
- **Pillow**: Image manipulation

## Performance Metrics

The model evaluation includes:
- **Accuracy**: Overall classification accuracy
- **Precision**: True positive rate per class
- **Recall**: Sensitivity per class
- **F1-Score**: Harmonic mean of precision and recall
- **Confusion Matrix**: Visual representation of classification results

## Notes

- Ensure all image files in the Dataset folder are properly organized by traffic light category
- The pre-trained weights (`resnet_weights.hdf5`) should be present in the `model/` folder
- Test images should be placed in the `testImages/` folder for evaluation
- Videos for testing should be placed in the `Videos/` folder
- GPU support is recommended for faster training on large datasets

## Troubleshooting

1. **Import Errors**: Ensure all packages from requirements.txt are installed
2. **Memory Issues**: If training on large datasets, consider using a machine with more RAM or GPU
3. **Model Loading Errors**: Verify that the pre-trained weights file exists at `model/resnet_weights.hdf5`
4. **Dataset Issues**: Ensure the Dataset folder structure matches the expected format

## Future Enhancements

- Real-time video stream processing
- Deployment as a web application
- Support for additional traffic light variants
- Performance optimization for edge devices
- Mobile application version

## License

This project is provided as-is for educational and research purposes.

## Author

Traffic Light Detection using ResNet-50

---

**Last Updated**: 2026
