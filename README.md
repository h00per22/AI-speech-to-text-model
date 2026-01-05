# AI SmartNotes – Lecture Capture & Study Assistant

AI SmartNotes is an intelligent system that records classroom lectures and automatically converts them into clean, structured, and easy-to-study notes using Speech-to-Text and NLP techniques.

---

## 🚀 Features

- 🎙️ Records classroom audio using an ESP32-based device  
- 📝 Converts speech to text using AI  
- 🧠 Uses NLP to clean, organize, and summarize content  
- 📚 Generates structured notes with headings and bullet points  
- 🌐 Web interface for uploading audio and viewing notes  

---

## 🛠️ Tech Stack

- **Hardware**: ESP32, I2S Microphone  
- **Backend**: Node.js, Express  
- **AI / NLP**: Speech-to-Text APIs, NLP processing  
- **Database**: MongoDB  
- **Frontend**: HTML, CSS, JavaScript  

---

## ⚙️ How It Works

1. ESP32 records classroom audio  
2. Audio is uploaded to the backend server  
3. Speech-to-Text converts audio into text  
4. NLP cleans and structures the content  
5. Final notes are generated and stored  

---

## 📂 Project Structure

```
AI-speech-to-text-model/
│
├── Project/              # Backend source code
├── notesfrontend/        # Frontend UI
├── .env.example          # Environment variable template
├── README.md             # Project documentation
```

---

## 🔐 Environment Variables

Create a `.env` file inside the `Project` folder:

```
GEMINI_API_KEY=your_api_key_here
MONGO_URI=your_mongodb_connection_string
PORT=3000
```

⚠️ Do NOT upload `.env` to GitHub.  
Use `.env.example` instead.

---

## ▶️ Run the Project (Optional)

```
npm install
npm start
```

> Running the project is optional.  
This repository is mainly for project demonstration and learning.

---

## 🎯 Use Cases

- Automatic lecture note generation  
- Faster exam revision  
- Helps students who miss classes  
- AI-powered study assistant  

---

## 🔮 Future Enhancements

- Multi-language support  
- Real-time transcription  
- Mobile application  
- Cloud deployment  

ience & Engineering  
AI & Full Stack Developer  
