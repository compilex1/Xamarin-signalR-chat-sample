# Xamarin SignalR Chat Sample

A cross-platform mobile chat application built with Xamarin.Forms and ASP.NET Core SignalR, demonstrating real-time communication capabilities across multiple platforms.

## 🚀 Features

- **Real-time Chat**: Instant messaging using SignalR Hub connections
- **Cross-platform Support**: Works on Android and iOS devices
- **User Management**: Join/leave chat functionality with user notifications
- **Message Types**: Support for user messages and system notifications
- **Modern UI**: Clean, responsive interface with Material Design-inspired styling
- **Connection Management**: Connect/disconnect functionality with status indicators

## 🏗️ Architecture

### Project Structure
```
BuildChat/
├── BuildChat/                 # Shared Xamarin.Forms project
│   ├── Models/               # Data models
│   ├── ViewModels/           # MVVM view models
│   ├── Converters/           # XAML value converters
│   └── Views/                # XAML pages
├── BuildChat.Android/        # Android-specific project
└── BuildChat.iOS/            # iOS-specific project
```

### Technology Stack
- **Frontend**: Xamarin.Forms 3.3.0
- **Real-time Communication**: ASP.NET Core SignalR Client 1.1.0
- **Architecture Pattern**: MVVM (Model-View-ViewModel)
- **Platforms**: Android, iOS
- **Target Framework**: .NET Standard 2.0

## 📱 Screenshots

The app features a clean chat interface with:
- Connection status overlay
- Real-time message display
- User join/leave notifications
- Different message styling for own vs. other users
- System message indicators

## 🛠️ Prerequisites

- Visual Studio 2019 or later with Xamarin workload
- Xamarin.Forms 3.3.0 or later
- .NET Standard 2.0 support
- Android SDK (for Android development)
- Xcode (for iOS development, macOS only)

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd Xamarin-signalR-chat-sample
```

### 2. Open the Solution
- Open `BuildChat.sln` in Visual Studio
- Restore NuGet packages if prompted

### 3. Configure SignalR Hub
The app connects to a SignalR hub at: `http://signalrdemomsph.azurewebsites.net/chatHub`

To use your own hub:
1. Update the URL in `MainViewModel.cs` line 75:
```csharp
hubConnection = new HubConnectionBuilder()
    .WithUrl("YOUR_HUB_URL_HERE")
    .Build();
```

### 4. Build and Run
- Select your target platform (Android/iOS)
- Build the solution
- Deploy to device or emulator

## 🔧 Configuration

### SignalR Hub Methods
The app implements the following SignalR hub methods:

- **JoinChat**: Notifies when a user joins the chat
- **LeaveChat**: Notifies when a user leaves the chat  
- **SendMessage**: Sends a message to all connected users
- **ReceiveMessage**: Receives messages from other users

### Message Model
```csharp
public class MessageModel
{
    public string User { get; set; }
    public string Message { get; set; }
    public bool IsOwnMessage { get; set; }
    public bool IsSystemMessage { get; set; }
}
```

## 📖 Usage

### Connecting to Chat
1. Launch the app
2. Enter your chat name in the connection overlay
3. Tap "Connect" to join the chat

### Sending Messages
1. Type your message in the input field
2. Tap "Send" to broadcast to all connected users

### Disconnecting
- Tap the "Close" button in the header to disconnect from chat

## 🏗️ Project Components

### MainViewModel
- Manages SignalR connection lifecycle
- Handles message sending/receiving
- Implements INotifyPropertyChanged for UI binding
- Manages connection state

### MainPage
- Main chat interface
- Message list with custom styling
- Connection overlay for initial setup
- Input controls for messaging

### Converters
- `InverseBoolConverter`: Inverts boolean values for XAML binding

## 🔌 SignalR Integration

The app demonstrates key SignalR concepts:

- **Hub Connection**: Establishes connection to SignalR hub
- **Real-time Communication**: Instant message delivery
- **User Management**: Track user presence
- **Error Handling**: Connection state management

## 🚀 Deployment

### Android
- Build the `BuildChat.Android` project
- Generate APK or AAB for distribution
- Deploy to Google Play Store or direct installation

### iOS
- Build the `BuildChat.iOS` project
- Archive and distribute via App Store or TestFlight

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test on both platforms
5. Submit a pull request

## 📄 License

This project is provided as a sample for educational purposes. Please refer to the original Microsoft Build 2019 materials for licensing information.

## 🔗 Related Resources

- [Xamarin.Forms Documentation](https://docs.microsoft.com/xamarin/xamarin-forms/)
- [ASP.NET Core SignalR](https://docs.microsoft.com/aspnet/core/signalr)
- [Microsoft Build 2019](https://www.microsoft.com/en-us/build)

## 📞 Support

For issues and questions:
- Check the existing issues in this repository
- Review SignalR and Xamarin.Forms documentation
- Contact the development team

---

**Note**: This is a sample application created for Microsoft Build 2019. The SignalR hub endpoint may not be permanently available. For production use, deploy your own SignalR hub and update the connection URL accordingly.
