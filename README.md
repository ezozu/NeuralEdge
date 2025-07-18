# NeuralEdge: Optimized Neural Network Inference at the Edge

NeuralEdge is a TypeScript library designed to enable efficient and performant neural network inference on edge devices. It provides a lightweight, modular architecture allowing developers to seamlessly integrate pre-trained machine learning models into resource-constrained environments such as embedded systems, mobile applications, and IoT devices. By optimizing for minimal memory footprint and latency, NeuralEdge facilitates real-time decision making and data processing directly at the source, reducing reliance on cloud connectivity and improving overall system responsiveness.

This library addresses the increasing demand for deploying complex machine learning models outside of traditional server environments. It focuses on providing tools for model conversion, quantization, and optimization specifically tailored for edge deployment. NeuralEdge allows developers to bridge the gap between powerful cloud-based training and the practical limitations of edge devices, empowering them to create intelligent, autonomous systems that can operate reliably in diverse and challenging environments. The library prioritizes flexibility and extensibility, offering a pluggable architecture that can be adapted to accommodate various hardware platforms and machine learning frameworks.

NeuralEdge strives to minimize dependencies and maximize portability, ensuring that it can be easily integrated into existing projects with minimal overhead. The core principles guiding its development include: performance optimization, resource efficiency, ease of use, and platform independence. By providing a robust and well-documented framework for edge inference, NeuralEdge aims to democratize access to advanced machine learning capabilities, enabling developers to build innovative solutions across a wide range of industries and applications.

## Key Features

*   **Model Conversion and Optimization:** Supports conversion of models from popular frameworks like TensorFlow and PyTorch to a lightweight, optimized format suitable for edge deployment. Includes tools for model pruning and layer fusion. Specifically, the convertModel function takes a TensorFlow SavedModel path as input and outputs a NeuralEdge compatible JSON representation after quantization.
    
*   **Quantization:** Offers various quantization techniques (e.g., post-training quantization, quantization-aware training) to reduce model size and improve inference speed without significant loss of accuracy. Uses dynamic range quantization by default with options for more advanced methods like integer quantization.
*   **Custom Layer Support:** Allows developers to define and integrate custom layers tailored to specific hardware architectures or application requirements. This can be achieved by implementing the `ILayer` interface and registering the layer with the NeuralEdge runtime.
*   **Hardware Acceleration Integration:** Designed to be easily integrated with hardware acceleration libraries (e.g., TensorFlow Lite, Core ML) to leverage the capabilities of specific edge devices. Offers a plugin system for hardware backends, enabling developers to target diverse hardware platforms.
*   **Lightweight Inference Engine:** Provides a minimal runtime engine optimized for low latency and minimal memory consumption. The inference engine is written in highly optimized TypeScript code with no external dependencies.
*   **ONNX Support:** Enables the direct deployment of ONNX models, providing compatibility with a wider range of model sources and simplifying the model deployment pipeline. Supports ONNX version 1.10 and later.
*   **Asynchronous Inference:** Supports asynchronous inference for improved responsiveness and throughput, particularly in real-time applications. The `predictAsync` method allows non-blocking execution of inference requests.

## Technology Stack

*   **TypeScript:** Primary programming language, providing strong typing and enhanced developer tooling. Used for all core components, including the inference engine and optimization tools.
*   **TensorFlow.js (Optional):** Used for model conversion and quantization from TensorFlow models. Required only if converting models from TensorFlow.
*   **ONNX Runtime (Optional):** Used for running ONNX models directly. Required only if deploying ONNX models.
*   **Node.js:** Development environment for building and testing the library. Required for running conversion scripts and unit tests.
*   **npm/yarn:** Package manager for managing dependencies and building the project.

## Installation

1.  **Install Node.js:** Ensure that Node.js (version 16 or higher) and npm (or yarn) are installed on your system. Download the latest version from the official Node.js website.
2.  **Clone the Repository:** Clone the NeuralEdge repository from GitHub using the following command:

    `git clone https://github.com/ezozu/NeuralEdge.git`

3.  **Navigate to the Project Directory:** Change your current directory to the NeuralEdge project directory:

    `cd NeuralEdge`

4.  **Install Dependencies:** Install the required dependencies using npm or yarn:

    `npm install` or `yarn install`

5.  **Build the Project:** Build the TypeScript code into JavaScript using the TypeScript compiler:

    `npm run build` or `yarn build`

## Configuration

NeuralEdge uses environment variables to configure certain aspects of its behavior. The following environment variables are supported:

*   `NEURALEDGE_QUANTIZATION_MODE`: Specifies the quantization mode to use (e.g., `DYNAMIC_RANGE`, `INTEGER`). Defaults to `DYNAMIC_RANGE`.
*   `NEURALEDGE_HARDWARE_BACKEND`: Specifies the hardware backend to use (e.g., `CPU`, `GPU`). Defaults to `CPU`. This requires the relevant backend library to be installed separately.
*   `NEURALEDGE_MODEL_PATH`: Specifies the path to the NeuralEdge model file.

These variables can be set in your shell environment or defined in a `.env` file in the project root directory.

## Usage

**Basic Inference:**

First, load a pre-converted NeuralEdge model from a JSON file:



**Asynchronous Inference:**



**Custom Layer Implementation:**

To create a custom layer, implement the `ILayer` interface:



Then, register your custom layer with the inference engine:



## Contributing

We welcome contributions to NeuralEdge! Please follow these guidelines when contributing:

1.  Fork the repository and create a branch for your changes.
2.  Ensure that your code adheres to the project's coding style and conventions.
3.  Write unit tests for your changes to ensure they are working correctly.
4.  Submit a pull request with a clear description of your changes and the problem they solve.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/ezozu/NeuralEdge/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for their contributions to the tools and libraries that make NeuralEdge possible. Specifically, we acknowledge the developers of TensorFlow, PyTorch, and ONNX Runtime.