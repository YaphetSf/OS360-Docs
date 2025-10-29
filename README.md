# OS360 - Professional Gimbal Control System

OS360 is a comprehensive gimbal control system consisting of an ESP32-based WiFi bridge and a professional iOS application for precise gimbal parameter tuning and control.

## 🎯 Overview

OS360 provides professional-grade gimbal control capabilities for cinema and broadcast applications. The system enables real-time parameter adjustment, profile management, and advanced automation features for compatible gimbal hardware.

## 🏗️ System Architecture

### ESP32 WiFi Bridge (`ESP_Wifi/`)
- **Hardware**: ESP32 microcontroller
- **Function**: WiFi Access Point and TCP server
- **Network**: Creates "OS_AR_001" WiFi network (password: "OS_AR_001")
- **Protocol**: Custom binary protocol over TCP port 23
- **UART**: Communicates with gimbal hardware via UART1 (115200 baud)

### iOS Application (`OS360/`)
- **Platform**: iOS (SwiftUI)
- **Function**: Professional control interface
- **Features**: Real-time parameter tuning, profile management, automation
- **Communication**: TCP client connecting to ESP32

## 🚀 Key Features

### Real-Time Control
- **PID Tuning**: Precise Proportional, Integral, Derivative parameter adjustment
- **Power Control**: Motor power management for all axes
- **Multi-Axis Support**: Pan (Yaw), Tilt (Pitch), and Roll control
- **Live Monitoring**: Real-time parameter feedback and status

### Profile Management
- **5 User Profiles**: Customizable parameter sets for different scenarios
- **Profile Switching**: Instant switching between saved configurations
- **Import/Export**: Profile data management and sharing
- **Auto-Sync**: Automatic synchronization with hardware

### Advanced Features
- **Automation Slots**: 5 programmable automation sequences
- **Script Management**: Custom script creation and execution
- **Board Information**: Hardware version and status monitoring
- **Connection Status**: Real-time WiFi connection monitoring

### Professional UI
- **Modern Design**: Clean, professional interface optimized for field use
- **Dark/Light Themes**: Adaptive theming for different lighting conditions
- **Haptic Feedback**: Tactile response for all interactions
- **Multi-Language**: Localization support for international use

## 📱 Device Support

### AR Series
- Optimized interface for AR gimbal systems
- Specialized control layouts and parameter ranges
- AR-specific automation features

### Trinity Series
- Advanced control for Trinity gimbal systems
- Enhanced parameter sets and automation capabilities
- Trinity-specific UI adaptations

## 🔧 Technical Specifications

### ESP32 Bridge
- **WiFi**: 802.11 b/g/n (2.4GHz)
- **Power**: 20dBm maximum transmit power
- **UART**: 115200 baud, 8N1 configuration
- **Protocol**: Custom binary protocol with CRC16 validation
- **Heartbeat**: 5-second interval with 15-second timeout

### iOS App
- **Minimum iOS**: iOS 14.0+
- **Architecture**: SwiftUI with Combine framework
- **Networking**: TCP socket communication
- **Data Persistence**: Core Data with UserDefaults
- **Threading**: Async/await with actor-based concurrency

### Communication Protocol
- **Start Byte**: 0x24 (normal commands) / 0x11 (heartbeat)
- **CRC16**: Polynomial 0x8005 with little-endian byte order
- **State Machine**: Robust packet parsing with timeout handling
- **Error Handling**: Automatic reconnection and retry logic

## 🛠️ Installation & Setup

### ESP32 Setup
1. Flash the `ESP_Wifi.ino` sketch to your ESP32
2. Connect UART1 (GPIO 20/21) to your gimbal hardware
3. Power on the ESP32 - it will create "OS_AR_001" WiFi network

### iOS App Installation
1. Open `OS360.xcodeproj` in Xcode
2. Select your target device or simulator
3. Build and run the project
4. Connect to "OS_AR_001" WiFi network
5. Launch the OS360 app

### First-Time Setup
1. **Authentication**: Sign in or use guest mode
2. **Device Selection**: Choose AR or Trinity gimbal type
3. **Connection**: App will automatically connect to ESP32
4. **Profile Setup**: Configure your first parameter profile

## 📖 Usage Guide

### Basic Operation
1. **Connect**: Ensure ESP32 is powered and iOS device is on the same WiFi
2. **Select Profile**: Choose from 5 available profiles or create new ones
3. **Tune Parameters**: Use the intuitive sliders to adjust PID and power values
4. **Write Changes**: Save parameters to gimbal hardware
5. **Monitor**: Watch real-time feedback and connection status

### Advanced Features
- **Automation**: Program sequences using the automation slots
- **Scripts**: Create custom control scripts for complex operations
- **Live View**: Monitor real-time gimbal status and parameters
- **Data Management**: Import/export profiles and configuration data

### Parameter Categories
- **PID Parameters**: P, I, D values for each axis (Pan, Tilt, Roll)
- **Power Settings**: Motor power levels for each axis
- **Follow Settings**: Speed and filtering for follow modes
- **RC Settings**: Remote control speed, filtering, and deadband
- **Limits**: Minimum and maximum position limits for each axis

## 🔒 Security & Privacy

- **Local Network Only**: All communication occurs over local WiFi
- **No Data Collection**: No personal data is collected or transmitted
- **Offline Operation**: Full functionality without internet connection
- **Secure Protocol**: CRC16 validation ensures data integrity

## 🐛 Troubleshooting

### Connection Issues
- Ensure ESP32 is powered and WiFi network is available
- Check that iOS device is connected to "OS_AR_001" network
- Verify UART connections between ESP32 and gimbal hardware
- Restart both ESP32 and iOS app if connection fails

### Parameter Issues
- Use "Read" button to fetch current parameters from hardware
- Check that parameter values are within valid ranges
- Ensure "Write" operation completes successfully
- Use "Reset" to restore default values if needed

### Performance Issues
- Close other apps to free up system resources
- Ensure stable WiFi connection
- Check ESP32 power supply and UART connections
- Restart the system if problems persist

## 📄 License

This project is proprietary software developed by Optical Support. All rights reserved.

## 🤝 Support

For technical support and inquiries:
- **Email**: osproducts@opticalsupport.com
- **Documentation**: See project documentation files
- **Issues**: Report bugs and feature requests through appropriate channels

## 🔄 Version History

- **v1.0**: Initial release with basic PID control and profile management
- **v1.1**: Added automation slots and script management
- **v1.2**: Enhanced UI with themes and improved connectivity
- **v1.3**: Added Trinity series support and advanced features

---

**OS360** - Professional Gimbal Control System  
*Precision Control for Professional Applications*
