# 🤖 JARVIS AI Assistant

A complete AI assistant inspired by Iron Man's JARVIS, powered by **Mistral AI** with voice recognition, system control, and web automation capabilities.

## ✨ Features

- 🎤 **Continuous Voice Recognition** - Always listening for your commands
- 🗣️ **Natural Speech Synthesis** - JARVIS speaks back to you
- 🌐 **Web Control** - Open websites, perform searches, navigate the internet  
- 💻 **System Integration** - Launch applications, manage files, control desktop
- 📧 **Communication** - Send emails, WhatsApp messages, manage contacts
- 🧠 **AI Intelligence** - Powered by Mistral AI for smart responses
- ⏰ **Task Management** - Set reminders, manage tasks, schedule events
- 🎵 **Media Control** - Control Spotify, manage music playback
- 💡 **Code Generation** - Create code for any project on demand
- 📊 **System Monitoring** - Check system stats, take screenshots

## 🚀 Quick Start

### Option 1: Automated Installation (Windows)
1. Download all files to a folder
2. Run `install.bat` as Administrator
3. Edit `.env` file with your API keys
4. Run `start_jarvis.bat` to start backend
5. Open `index.html` in your browser

### Option 2: Manual Installation

#### Prerequisites
- Python 3.8 or higher
- Modern web browser (Chrome, Edge, Firefox)
- Microphone for voice input
- Internet connection

#### Step 1: Install Python Dependencies
```bash
# Create virtual environment
python -m venv jarvis_env

# Activate virtual environment
# Windows:
jarvis_env\Scripts\activate
# Linux/Mac:
source jarvis_env/bin/activate

# Install packages
pip install -r requirements.txt
```

#### Step 2: Get API Keys
1. **Mistral AI API Key** (Required):
   - Go to [Mistral Console](https://console.mistral.ai/)
   - Create account and get API key
   - Copy the key

2. **Email Setup** (Optional):
   - Use Gmail App Password, not regular password
   - Enable 2FA and create App Password in Google Account settings

#### Step 3: Configure Environment
Create `.env` file:
```env
MISTRAL_API_KEY=your-actual-mistral-api-key-here
EMAIL_ADDRESS=your-email@gmail.com
EMAIL_PASSWORD=your-gmail-app-password
WEATHER_API_KEY=your-weather-api-key
```

#### Step 4: Start the System
```bash
# Start backend server
python jarvis_server.py

# Open frontend in browser
# Open index.html in your web browser
```

## 🎯 Voice Commands

### Website Control
- "Open YouTube" - Opens YouTube
- "Open Google" - Opens Google  
- "Open Instagram" - Opens Instagram
- "Open ChatGPT" - Opens ChatGPT
- "Search YouTube for Python tutorials"
- "Search Google for weather today"

### Application Control
- "Open Notepad" - Opens text editor
- "Open Calculator" - Opens calculator
- "Open Spotify" - Opens Spotify
- "Open Task Manager" - Opens system monitor
- "Open VS Code" - Opens code editor

### AI & Code Generation  
- "Create code for a web scraper"
- "Write code for a Python game"
- "Generate a React component"
- "Help me build a mobile app"

### Communication
- "Send email to John" - Compose email
- "Send WhatsApp message" - Send message
- "What are my contacts?" - View contacts

### Task Management
- "Set reminder to call mom" - Set reminder
- "What are my tasks?" - View tasks
- "Add task buy groceries" - Add new task
- "Mark task as complete" - Complete task

### System Control
- "Take screenshot" - Capture screen
- "System information" - View system stats
- "What's the weather?" - Get weather info
- "Show desktop" - Minimize all windows

### Media Control
- "Play music on Spotify" - Start music
- "Pause music" - Pause playback
- "Next song" - Skip track
- "Volume up/down" - Control volume

### General Conversation
- "Hello JARVIS" - Greeting
- "How are you?" - Status check
- "What can you do?" - Show capabilities
- "Thank you" - Acknowledgment

## 🔧 Configuration

### File Structure
```
jarvis-ai-assistant/
├── index.html              # Frontend interface
├── jarvis_server.py        # Backend server
├── config.py              # Configuration settings
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables
├── install.bat           # Windows installer
├── start_jarvis.bat      # Backend startup script
├── start_frontend.bat    # Frontend startup script
└── README.md             # This guide
```

### Environment Variables
```env
# Required
MISTRAL_API_KEY=your-mistral-api-key

# Optional Email Setup
EMAIL_ADDRESS=your-email@gmail.com
EMAIL_PASSWORD=your-app-password

# Optional Weather API
WEATHER_API_KEY=your-openweather-api-key

# Optional WhatsApp API
WHATSAPP_API_TOKEN=your-whatsapp-token
```

### Customizing Application Paths
Edit `config.py` to add or modify application paths:
```python
WINDOWS_APP_PATHS = {
    'your_app': r'C:\Path\To\Your\App.exe',
    'custom_tool': 'custom_command.exe'
}
```

## 🛠️ Advanced Setup

### Adding New Voice Commands
1. Edit `jarvis_server.py`
2. Add pattern matching in `analyze_command()` method
3. Implement action in `execute_action()` method
4. Test with voice input

### Custom Mistral AI Prompts
Modify the system prompt in `get_mistral_response()`:
```python
system_prompt = """You are JARVIS, a sophisticated AI assistant.
Your custom instructions here..."""
```

### Email Integration
For Gmail integration:
1. Enable 2-Factor Authentication
2. Generate App Password in Google Account
3. Use App Password in EMAIL_PASSWORD
4. Never use your regular Gmail password

### WhatsApp Integration
Requires WhatsApp Business API:
1. Get API token from WhatsApp Business
2. Set WHATSAPP_API_TOKEN in .env
3. Configure webhook endpoints

## 🔐 Security & Privacy

### Data Protection
- All processing happens locally
- No data sent to third parties except Mistral AI for responses
- Voice data not stored permanently
- Tasks and reminders stored locally only

### API Key Security
- Store API keys only in .env file
- Never commit .env to version control
- Use environment variables in production
- Rotate keys regularly

### System Access
- JARVIS can access system applications
- Be cautious with file system commands
- Review code before adding new system functions
- Use least privilege principle

## 🐛 Troubleshooting

### Common Issues

**Backend won't start:**
```bash
# Check Python version
python --version

# Check if packages installed
pip list | grep flask

# Reinstall requirements
pip install -r requirements.txt
```

**Voice recognition not working:**
- Allow microphone access in browser
- Use Chrome or Edge (best compatibility)
- Check microphone permissions in system settings
- Speak clearly and wait for response

**Mistral API errors:**
- Verify API key is correct
- Check account credits/limits
- Ensure internet connection
- Check Mistral service status

**Applications won't open:**
- Check application paths in config.py
- Verify applications are installed
- Run as Administrator if needed
- Check Windows/Mac/Linux compatibility

### Error Messages

| Error | Solution |
|-------|----------|
| "Backend not connected" | Start jarvis_server.py |
| "Speech recognition not supported" | Use Chrome/Edge browser |
| "Mistral API error" | Check API key and credits |
| "Application not found" | Update paths in config.py |
| "Email not configured" | Set EMAIL_* variables in .env |

### Debug Mode
Enable debug mode in `config.py`:
```python
DEBUG = True
LOG_LEVEL = 'DEBUG'
```

## 📈 Performance Optimization

### System Requirements
- **Minimum:** 4GB RAM, 2-core CPU
- **Recommended:** 8GB RAM, 4-core CPU
- **Storage:** 500MB free space
- **Network:** Stable internet for AI responses

### Optimization Tips
1. Close unnecessary applications
2. Use SSD for better performance
3. Keep Python environment updated
4. Regular system maintenance
5. Monitor resource usage

## 🔄 Updates & Maintenance

### Updating Dependencies
```bash
pip install --upgrade -r requirements.txt
```

### Backup Configuration
```bash
# Backup important files
copy .env .env.backup
copy jarvis_tasks.json tasks_backup.json
```

### Version Control
```bash
git init
echo ".env" >> .gitignore
echo "jarvis_env/" >> .gitignore
git add .
git commit -m "Initial JARVIS setup"
```

## 🤝 Contributing

### Adding Features
1. Fork the repository
2. Create feature branch
3. Add functionality
4. Test thoroughly
5. Submit pull request

### Reporting Issues
- Use GitHub Issues
- Include error messages
- Provide system information
- Steps to reproduce

## 📚 API Reference

### Backend Endpoints

#### Health Check
```
GET /health
Response: {"status": "healthy", "message": "JARVIS backend is operational"}
```

#### Process Command
```
POST /process_command
Body: {"command": "your voice command"}
Response: {"response": "AI response", "actions": [...], "status": "success"}
```

#### Task Management
```
GET /get_tasks
Response: {"tasks": [...]}

POST /add_task
Body: {"task": "task description"}
Response: {"message": "Task added", "task": {...}}
```

#### System Status
```
GET /system_status
Response: {"status": "system information"}
```

## 🎮 Usage Examples

### Basic Interaction
1. Click microphone button
2. Say "Hello JARVIS"
3. Wait for response
4. Continue conversation

### Complex Commands
- "Search YouTube for Python machine learning tutorials and then open VS Code"
- "Create code for a weather app, send it via email, and set reminder to test it"
- "Take screenshot, check system info, and remind me to backup files"

### Productivity Workflow
1. "Good morning JARVIS" - Daily greeting
2. "What are my tasks for today?" - Check schedule
3. "Open Gmail and WhatsApp" - Communication setup
4. "Set reminder to call client at 3 PM" - Schedule tasks
5. "Create code for client project" - Work assistance

## 📞 Support

### Getting Help
- Check this README first
- Review error messages carefully
- Test individual components
- Check system compatibility

### Community
- GitHub Discussions for questions
- Issues for bug reports
- Wiki for additional documentation
- Examples repository for use cases

### Commercial Support
For business deployments:
- Custom integrations available
- Enterprise security features
- Dedicated support channels
- Training and consultation

---

## 🎉 Congratulations!

You now have a fully functional JARVIS AI assistant! Start with simple commands and gradually explore advanced features. Remember to:

- ✅ Keep your API keys secure
- ✅ Regular backups of tasks/reminders  
- ✅ Update dependencies periodically
- ✅ Customize for your workflow
- ✅ Have fun with your AI assistant!

**"Sir, all systems are operational. How may I assist you today?"** 🤖