# 🎓 AI SmartNotes – Lecture Capture & Study Assistant

AI SmartNotes is an intelligent system that records classroom lectures and automatically converts them into clean, structured, and easy-to-study notes using Speech-to-Text and NLP techniques. Perfect for students who want to focus on learning instead of note-taking!

---

## ✨ Key Features

- 🎙️ **Hardware Recording** – Records classroom audio using an ESP32-based device with I2S microphone
- 📝 **Speech-to-Text Conversion** – Converts audio to text using advanced AI models
- 🧠 **Intelligent Processing** – Uses NLP to clean, organize, and summarize content automatically
- 📚 **Structured Notes** – Generates organized notes with headings, bullet points, and key highlights
- 🌐 **Web Interface** – Simple and intuitive interface for uploading audio and viewing processed notes
- 💾 **Database Storage** – Securely stores all notes for future reference

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Hardware** | ESP32, I2S Microphone |
| **Backend** | Node.js, Express.js |
| **AI/ML** | Gemini API (Speech-to-Text), NLP Processing |
| **Database** | MongoDB |
| **Frontend** | React (Create React App), HTML5, CSS3, JavaScript |

---

## 🔄 How It Works

```
┌─────────────────────────────────────────────────────────────┐
│  1. Record Lecture Audio                                     │
│     (ESP32 Device Records Classroom Audio)                   │
└────────────────┬────────────────────────────────────────────┘
                 │
┌────────────────▼────────────────────────────────────────────┐
│  2. Upload to Server                                         │
│     (Audio File Sent to Backend)                             │
└────────────────┬────────────────────────────────────────────┘
                 │
┌────────────────▼────────────────────────────────────────────┐
│  3. Speech-to-Text Conversion                                │
│     (Audio → Transcribed Text using Gemini API)              │
└────────────────┬────────────────────────────────────────────┘
                 │
┌────────────────▼────────────────────────────────────────────┐
│  4. NLP Processing & Structuring                             │
│     (Clean, Organize, Summarize Content)                     │
└────────────────┬────────────────────────────────────────────┘
                 │
┌────────────────▼────────────────────────────────────────────┐
│  5. Store & Display Notes                                    │
│     (Save to MongoDB & Show in Web Interface)                │
└─────────────────────────────────────────────────────────────┘
```

---

## 📂 Project Structure

```
AI-speech-to-text-model/
│
├── Project/                  # Backend application
│   ├── server.js            # Express server entry point
│   ├── routes/              # API endpoints
│   ├── controllers/         # Business logic
│   ├── models/              # MongoDB schemas
│   ├── .env                 # Environment variables (DO NOT COMMIT)
│   └── package.json         # Backend dependencies
│
├── notesfrontend/           # React frontend application
│   ├── public/              # Static assets
│   ├── src/
│   │   ├── components/      # React components
│   │   ├── pages/           # Page components
│   │   ├── App.js           # Main app component
│   │   └── index.js         # React entry point
│   └── package.json         # Frontend dependencies
│
├── .env.example             # Template for environment variables
├── .gitignore              # Git ignore configuration
└── README.md               # This file
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v14.0 or higher)
- **npm** (v6.0 or higher)
- **MongoDB** (local or Atlas cloud instance)
- **Gemini API Key** (get it from [Google AI Studio](https://makersuite.google.com/app/apikey))
- **ESP32** with microphone (for hardware recording)

### Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/h00per22/AI-speech-to-text-model.git
   cd AI-speech-to-text-model
   ```

2. **Setup Backend (Node.js + Express)**
   ```bash
   cd Project
   npm install
   ```

3. **Configure Environment Variables**
   ```bash
   # Create .env file in the Project folder
   cp .env.example .env
   ```
   
   Edit `.env` with your credentials:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   MONGO_URI=your_mongodb_connection_string
   PORT=3000
   NODE_ENV=development
   ```

4. **Setup Frontend (React)**
   ```bash
   cd ../notesfrontend
   npm install
   ```

5. **Run the Application**
   
   **Terminal 1 - Backend:**
   ```bash
   cd Project
   npm start
   ```
   Backend runs on `http://localhost:3000`

   **Terminal 2 - Frontend:**
   ```bash
   cd notesfrontend
   npm start
   ```
   Frontend runs on `http://localhost:3000` (or next available port)

---

## 📖 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/upload` | Upload audio file for processing |
| `GET` | `/api/notes` | Retrieve all processed notes |
| `GET` | `/api/notes/:id` | Get a specific note by ID |
| `DELETE` | `/api/notes/:id` | Delete a note |

---

## 🔐 Environment Variables Reference

| Variable | Description | Example |
|----------|-------------|---------|
| `GEMINI_API_KEY` | API key for Google Gemini (Speech-to-Text) | `AIza...` |
| `MONGO_URI` | MongoDB connection string | `mongodb+srv://user:pass@cluster.mongodb.net/dbname` |
| `PORT` | Backend server port | `3000` |
| `NODE_ENV` | Environment type | `development` or `production` |

⚠️ **Security Warning:** Never commit `.env` file to Git. Always use `.env.example` as a template.

---

## 💡 Use Cases

- 📚 **Students** – Generate notes automatically during lectures
- 👨‍🏫 **Teachers** – Create lesson notes for students who missed class
- 📖 **Researchers** – Convert interviews or lectures into structured documents
- 🎯 **Exam Prep** – Quickly create study materials from recorded lectures
- ♿ **Accessibility** – Help students with hearing impairments access lecture content

---

## 🔮 Future Enhancements

- [ ] Multi-language support (Spanish, Mandarin, etc.)
- [ ] Real-time transcription during lectures
- [ ] Mobile application (iOS & Android)
- [ ] Cloud deployment (AWS, Google Cloud, or Heroku)
- [ ] Export notes in multiple formats (PDF, Word, etc.)
- [ ] Collaborative note-sharing between students
- [ ] AI-powered question generation for study
- [ ] Speaker identification and dialogue formatting

---

## 🐛 Troubleshooting

### "GEMINI_API_KEY is not defined"
- Ensure your `.env` file exists in the `Project` folder
- Verify the API key is correctly copied from Google AI Studio
- Restart the server after updating `.env`

### "MongoDB connection failed"
- Check your MongoDB URI in `.env`
- Verify MongoDB service is running
- Ensure IP whitelist includes your current IP (if using MongoDB Atlas)

### "Port 3000 already in use"
- Kill the process using port 3000, or
- Change `PORT` in `.env` to a different number (e.g., `3001`)

---

## 📚 Learning Resources

- [Express.js Documentation](https://expressjs.com/)
- [React Official Docs](https://react.dev/)
- [MongoDB Guide](https://docs.mongodb.com/)
- [Google Gemini API](https://ai.google.dev/)
- [ESP32 Arduino IDE Setup](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html)

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source. Feel free to use it for educational and personal projects.

---

## 👨‍💻 About

**AI SmartNotes** is a student project developed by passionate developers interested in AI, full-stack development, and educational technology.

**Developer:** Computer Science & Engineering Student  
**Focus Areas:** AI & Full Stack Development

---

## 📞 Support & Contact

For issues, questions, or suggestions:
- Open an [issue on GitHub](https://github.com/h00per22/AI-speech-to-text-model/issues)
- Reach out via GitHub profile

---

**Made with ❤️ for students, by students**