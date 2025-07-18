# NeuralEdge: Quantized Forex Binary Options Trading with Reinforcement Learning

A cutting-edge platform for developing and deploying quantized reinforcement learning agents to trade Forex binary options, leveraging high-frequency tick data and a custom backtesting infrastructure.

NeuralEdge is designed to bridge the gap between academic research in reinforcement learning and practical, real-world application in the volatile Forex market. Our primary goal is to empower quantitative traders and machine learning engineers with the tools necessary to build, train, and deploy sophisticated trading strategies that can capitalize on fleeting market opportunities. By employing a combination of deep reinforcement learning, quantization techniques, and a meticulously crafted backtesting environment, NeuralEdge offers a robust and efficient solution for automated Forex binary options trading.

The core of NeuralEdge lies in its ability to process and analyze high-frequency tick data. This granular level of detail allows our reinforcement learning agents to learn subtle patterns and anticipate short-term price movements. We utilize quantization methods to reduce the computational burden associated with deep neural networks, making it feasible to deploy these complex models on resource-constrained environments. The custom backtesting infrastructure allows for rigorous evaluation of trading strategies across diverse historical market conditions, ensuring the robustness and reliability of the deployed agents.

NeuralEdge is more than just a trading platform; it's a research and development environment. We provide the tools and documentation necessary for users to experiment with different reinforcement learning algorithms, quantization techniques, and trading strategies. The modular design of the system allows for easy integration of new data sources, models, and evaluation metrics. Our aim is to foster a community of researchers and developers who are pushing the boundaries of automated trading using cutting-edge artificial intelligence.

## Key Features

*   **Reinforcement Learning Agents:** Implements various reinforcement learning algorithms, including Deep Q-Networks (DQN), Proximal Policy Optimization (PPO), and Advantage Actor-Critic (A2C), specifically tailored for Forex binary options trading. Each algorithm is highly configurable and allows for fine-tuning of hyperparameters.
*   **Quantized Neural Networks:** Employs quantization techniques, such as post-training quantization and quantization-aware training, to reduce the model size and inference time of the reinforcement learning agents. This enables deployment on resource-constrained environments, such as edge devices.
*   **High-Frequency Tick Data Handling:** Provides efficient data ingestion and processing pipelines for handling high-frequency Forex tick data. This includes data cleaning, feature engineering, and storage optimized for time-series analysis. Uses libraries like Polars for optimized data processing.
*   **Custom Backtesting Infrastructure:** Offers a comprehensive backtesting environment that simulates real-world trading conditions, including transaction costs, slippage, and market impact. The backtesting engine supports vectorized backtesting for efficient evaluation of trading strategies across different time periods and market conditions.
*   **Binary Options Specific Logic:** Implements the specific logic required for trading binary options, including payoff calculations, expiration times, and strike price selection. The platform supports a variety of binary option types, such as call/put options and one-touch options.
*   **Risk Management Modules:** Integrates risk management modules that allow users to define risk parameters, such as maximum position size, stop-loss orders, and take-profit orders. These modules help to mitigate risk and protect capital.
*   **Modular Architecture:** Features a modular architecture that allows for easy integration of new data sources, reinforcement learning algorithms, and trading strategies. This promotes code reusability and facilitates experimentation.

## Technology Stack

*   **TypeScript:** The primary programming language used for developing the platform, providing strong typing and code maintainability.
*   **Node.js:** The runtime environment for executing the TypeScript code, providing a scalable and efficient platform for running the trading agents and backtesting infrastructure.
*   **TensorFlow.js:** A JavaScript library for training and deploying machine learning models in the browser and Node.js. Used for implementing the reinforcement learning agents and quantization techniques.
*   **Polars:** A high-performance DataFrame library for processing and analyzing high-frequency Forex tick data. Offers significant performance advantages over Pandas.
*   **Redis:** An in-memory data structure store used for caching data and managing the state of the reinforcement learning agents.
*   **Jest:** A JavaScript testing framework used for unit testing and integration testing.

## Installation

1.  **Clone the repository:**

    git clone https://github.com/ezozu/NeuralEdge.git

2.  **Install Node.js:**

    Ensure that Node.js (version 18 or higher) and npm are installed on your system. You can download the latest version from the official Node.js website.

3.  **Install dependencies:**

    cd NeuralEdge
    npm install

4.  **Install global dependencies:**

    npm install -g typescript ts-node

## Configuration

1.  **Environment Variables:**

    Create a `.env` file in the root directory of the project. Define the following environment variables:

    DATABASE_URL=your\_database\_connection\_string
    REDIS_HOST=localhost
    REDIS_PORT=6379
    API_KEY=your\_forex\_data\_api\_key

2.  **Database Configuration:**

    Configure the database connection string in the `.env` file. NeuralEdge supports PostgreSQL. You will need to create a database and configure the connection string accordingly.

3.  **API Key:**

    Obtain an API key from a Forex data provider (e.g., OANDA, FXCM). Store the API key in the `.env` file.

## Usage

1.  **Data Ingestion:**

    Use the data ingestion scripts to download and store historical Forex tick data. Example:

    ts-node src/data\_ingestion/download\_data.ts --symbol EURUSD --start 2023-01-01 --end 2023-01-07

2.  **Training Reinforcement Learning Agents:**

    Use the training scripts to train the reinforcement learning agents. Example:

    ts-node src/training/train\_dqn.ts --symbol EURUSD --episodes 1000 --learning\_rate 0.001

3.  **Backtesting:**

    Use the backtesting scripts to evaluate the performance of the trained agents. Example:

    ts-node src/backtesting/backtest.ts --symbol EURUSD --start 2023-01-08 --end 2023-01-15 --model\_path models/dqn\_eurusd.tf

## Contributing

We welcome contributions to NeuralEdge! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise commit messages.
4.  Submit a pull request with a detailed description of your changes.
5.  Ensure that your code adheres to the coding style guidelines.
6.  Write unit tests for your code.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/ezozu/NeuralEdge/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the following open-source projects and libraries for their contributions to NeuralEdge:

*   TensorFlow.js
*   Polars
*   Redis
*   Jest