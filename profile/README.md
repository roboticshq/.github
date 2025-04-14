# Robotics.dev - Peer-to-Peer ROS2 Robotics Platform

<div align="center">
  <img src="https://www.robotics.dev/nodebot-192.png" alt="Robotics.dev Logo" width="400" height="auto">
  <h3>The Next Generation Platform for Robotics Development and Operations</h3>
  <p>Connect, Code, and Control ROS robots remotely via secure peer-to-peer connectivity</p>
</div>

## 🚀 About Robotics.dev

Robotics.dev is a cutting-edge peer-to-peer platform designed specifically for the robotics community, leveraging the power of ROS2 (Robot Operating System 2) to provide seamless development and operational capabilities. Our platform bridges the gap between robotics development and deployment, enabling teams to efficiently build, test, and operate robots in distributed environments without the limitations of traditional centralized architectures.

### Why Robotics.dev?

- **True Peer-to-Peer Connectivity**: Direct robot-to-robot and developer-to-robot connections without centralized bottlenecks, even across the internet
- **Advanced ROS2 Integration**: Leverages ROS2's DDS implementation with optimized discovery server configuration for improved performance
- **Simplified DevOps**: Streamlined workflows from development to deployment and operations with containerized environments
- **Cross-Network Support**: Works seamlessly across NAT, firewalls, and different network topologies without complex VPN setup
- **Enhanced Collaboration**: Multi-user development environment with real-time code sharing and version control
- **Global P2P Connectivity**: Extend ROS2 robotics capabilities beyond local area networks for worldwide robot control
- **Multi-Robot Orchestration**: Develop and run AI tasks across fleets of robots from anywhere in the world

## ✨ Key Features

### For Developers

- **Integrated Development Environment**: Code, simulate, and test in one platform with remote robot access
- **Remote Debugging**: Debug robots in real-time regardless of physical location or network configuration
- **Containerized Development**: Isolated, reproducible environments using Docker/Kubernetes integration
- **CI/CD Pipelines**: Automated testing and deployment specifically designed for robotics applications
- **Package Management**: Simplified management of ROS2 packages, dependencies, and custom extensions
- **Powerful Developer Tools**:
  - VSCode/Cursor Extension
  - Copilot Gen-AI
  - Robotics CLI
  - NodeJS P2P RDK
  - Python P2P RDK
  - REST APIs and WebSocket support

### For Operators

- **Fleet Management**: Monitor and manage multiple robots from a single dashboard across different networks
- **Performance Analytics**: Real-time metrics and historical performance data with minimal network overhead
- **Remote Control**: Secure remote access and control capabilities over encrypted peer-to-peer connections
- **OTA Updates**: Safe, efficient over-the-air updates with rollback capability for distributed robot fleets
- **Health Monitoring**: Proactive system health checks with customizable alerts and notification thresholds
- **P2P Web Teleop**: Control from anywhere in the world over browsers with P2P streaming video, supporting both software and hardware joysticks/gamepads
- **Mobile Support**: Works great on mobile devices for on-the-go robot control

### Connectivity

- **Secure P2P Communication**: End-to-end encrypted communications using state-of-the-art cryptographic protocols
- **Multi-Network Support**: Seamless operation across LAN, WAN, cellular, and satellite networks without reconfiguration
- **Optimized Discovery**: Intelligent service discovery using FastDDS Discovery Server reducing network traffic by up to 90%
- **Low-Latency Data Transfer**: Direct peer-to-peer connections minimize latency for real-time robotics operations
- **Connection Resilience**: Automatic failover and reconnection with store-and-forward capability for intermittent networks
- **P2P Compute**: Run AI-powered robotics apps peer-to-peer on the cloud, edge, your development environment, or on the robot itself

## 🔧 Technical Architecture

Robotics.dev is built on a modern, scalable architecture optimized for distributed robotics:

- **Core Platform**: Distributed microservices architecture with peer-to-peer message routing
- **Communication Layer**: Optimized DDS implementation with advanced QoS policies and topic filtering
- **Security Framework**: Military-grade encryption and authentication with fine-grained access control
- **Data Management**: Efficient handling of high-volume sensor data with selective streaming and caching
- **Extensible API**: Comprehensive RESTful and WebSocket APIs for integration with existing systems
- **Hardware Support**: Works out-of-the-box with any ROS2 robotics hardware, including Raspberry Pi (Zero, 3, 4, 5), Radxa X4, LattePanda 3 Delta, Intel NUC, and Arduino/ESP32

## 💻 Getting Started

### On Your Robot

```bash
# Install the Robotics.dev CLI on your ROS2 robot
npm install -g robotics

# Get Robot ID
robotics id

# Add your developer API token to your robot
robotics set --token=YOUR_API_TOKEN

# Start Communications
robotics connect

# Start Motors (defaults to Raspberry Pi)
robotics start motors

# Start 2D Camera (defaults to device /dev/video0)
robotics start camera

# Get help on all commands and parameters
robotics help
```

### On Your Development Machine

#### NodeJS RDK
```bash
# Install Robotics.dev NodeJS RDK
npm install robotics-dev

# Example code
const robotics = require('robotics-dev');

// Define ROS twist movement commands
const moveForward = {
  linear: {x: 0.2, y: 0.0, z: 0.0},
  angular: {x: 0.0, y: 0.0, z: 0.0}
};

const stop = {
  linear: {x: 0.0, y: 0.0, z: 0.0},
  angular: {x: 0.0, y: 0.0, z: 0.0}
};

const robotId = 'YOUR_ROBOT_ID';
const apiToken = 'YOUR_API_TOKEN';

// Connect RDK to robot via P2P and start listening for ROS messages
robotics.connect({robot: robotId, token: apiToken}, (ros) => {
  console.log('Received p2p data:', ros);
  
  // Move robot forward
  robotics.twist(robotId, moveForward);
  
  // Stop after 5 seconds
  setTimeout(() => {
    robotics.twist(robotId, stop);
  }, 5000);
});
```

#### Python RDK
```bash
# Install Robotics.dev Python RDK
pip install robotics-dev
```

## 📊 Use Cases

- **Distributed Research**: Collaborate on robotics research across multiple institutions and physical locations
- **Industrial Automation**: Deploy and manage industrial robotic systems at scale across multiple facilities
- **Field Robotics**: Operate robots in remote locations with intermittent connectivity and challenging environments
- **Multi-Robot Coordination**: Coordinate fleets of heterogeneous robots for complex tasks with minimal infrastructure
- **Edge-to-Cloud Robotics**: Seamlessly integrate edge computing with cloud services for scalable robotics applications
- **Remote Teleoperations**: Control robots from anywhere in the world using web-based interfaces and P2P connectivity

## 📚 Documentation

For comprehensive documentation, tutorials, and API references, visit our [Documentation Portal](https://docs.robotics.dev).

## 🤝 Community

Join our growing community of robotics developers and operators:

- [Discord Channel](https://discord.gg/roboticsdev)
- [GitHub Organization](https://github.com/roboticshq)

## 📞 Support

Need help? Our team is ready to assist:

- [Discord Channel](https://discord.gg/roboticsdev)
- Email: support@robotics.dev

## 📄 License

Robotics.dev is available under a dual licensing model:
- Open Source Core: [PolyForm Noncommercial License 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0/)
- Enterprise Features: Commercial license available for business users

---

<div align="center">
  <p>Empowering the future of robotics, one connection at a time.</p>
  <p>© 2025 Robotics.dev | All rights reserved</p>
</div>
