# Calculator-Bot-Extention

![Java](https://img.shields.io/badge/Java-11%2B-ED8B00?logo=openjdk&logoColor=white)
![JSON](https://img.shields.io/badge/org.json-2016-lightgrey)
![Bot](https://img.shields.io/badge/Type-Math_Bot-blueviolet)

## Project Description

**Calculator-Bot** is a server-side extension for the **Nwitter-Backend-Server**. Designed as an interactive "robot user," it listens to direct messages or mentions containing mathematical expressions. It parses string input (e.g., `(12 * 5) + 20`), performs the arithmetic operation, and sends the result back to the user in real-time.

## Features

  * **Math Parsing:** Evaluates standard arithmetic expressions including addition, subtraction, multiplication, and division (`Operator.java`).
  * **Real-time Response:** Instantly processes incoming JSON message packets and constructs a reply.
  * **Server Integration:** Maintains a persistent socket connection with the main Nwitter server.
  * **Configurable:** Easy setup for server IP and port targeting via property files.

## System Requirements

  * **Java Development Kit (JDK):** Version 11 or higher.
  * **Nwitter Server:** Must be running for the bot to connect.
  * **Dependencies:**
      * `json-20160212.jar`

## Detailed File Analysis

The source code is contained within `calculator_bot/src/`.

  * **`Main.java`**: The entry point of the application. It establishes the socket connection to the Nwitter server, handles the input/output streams, and loops to listen for incoming message objects.
  * **`Operator.java`**: The core logic class. It contains the algorithms to parse the string commands received from the chat and compute the mathematical result.
  * **`config.java`**: A utility class responsible for loading the connection settings (IP and Port) from the `addressConfig.properties` file.

## Installation & Running

### 1\. Setup

Clone the repository:

```bash
git clone https://github.com/nikelroid/calculator_bot.git
cd calculator_bot
```

### 2\. Configuration

Open `calculator_bot/addressConfig.properties` and ensure the connection details point to your Nwitter Server instance:

```properties
# Configuration
ip=127.0.0.1
port=8086
```

*Note: Ensure the port (e.g., 8086) is distinct from the main client and other bots if defined in your server config.*

### 3\. Dependencies

Ensure `json-20160212.jar` located in the `lib` folder is added to your project classpath.

### 4\. Execution

Run the `Main` class to start the bot:

```bash
java -cp "calculator_bot/lib/*:calculator_bot/src" Main
```

## Usage

Once running, any user on the Nwitter Client can send a message to this bot's account.

  * **Input:** `2 + 2 * 5`
  * **Bot Reply:** `12`

## Contributing

Pull requests are welcome. If adding support for complex mathematical functions (trigonometry, logs), please ensure to update the `Operator` class logic safely.

## License

Distributed under the MIT License.

## Contact

Project Maintainer - [GitHub Profile](https://www.google.com/search?q=https://github.com/nikelroid)
