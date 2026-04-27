# ⚡ On-Device AI Chat

> Run a language model directly on your Android phone. No internet. No cloud. 100% private.

[![React Native](https://img.shields.io/badge/React%20Native-0.74-blue)](https://reactnative.dev)
[![llama.rn](https://img.shields.io/badge/llama.rn-0.10.0-orange)](https://github.com/mybigday/llama.rn)
[![Model](https://img.shields.io/badge/Model-SmolLM2%20360M-green)](https://huggingface.co/HuggingFaceTB/SmolLM2-360M-Instruct-GGUF)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 📱 Screenshots

| App Launch | Loading Model | Model Ready | Chat |
|:---:|:---:|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/317b2e34-c298-4a14-9a82-9ad1722add73" width="200"/> | <img src="https://github.com/user-attachments/assets/a676ec5c-9bc9-48cf-89db-3e8d5c1d370a" width="200"/> | <img src="https://github.com/user-attachments/assets/945a22a3-9489-4286-a64f-5ff5261ce397" width="200"/> | <img src="https://github.com/user-attachments/assets/3e7b062a-0823-443a-969d-43f5a7cf6aa3" width="200"/> |

---

## ✨ Features

- 🔒 **100% Private** — All inference runs locally on device
- 📵 **No Internet Required** — Works completely offline
- ⚡ **Fast** — Optimized GGUF model format via llama.cpp
- 🤖 **Real LLM** — SmolLM2 360M quantized model
- 📱 **Android** — Built with React Native

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Framework | React Native 0.74 |
| LLM Runtime | llama.rn (llama.cpp bindings) |
| Model | SmolLM2 360M Q4_K_M (GGUF) |
| Language | TypeScript |
| Platform | Android |

---

## 🚀 How It Works

1. App loads a GGUF model from device storage
2. llama.rn initializes the llama.cpp context
3. User types a message
4. LLM generates response **100% on-device**
5. No data ever leaves the phone

```typescript
import { initLlama } from 'llama.rn'

const context = await initLlama({
  model: '/data/local/tmp/model.gguf',
  n_ctx: 2048,
})

const result = await context.completion({
  messages: [{ role: 'user', content: userMessage }],
  n_predict: 100,
})
```

---

## 📦 Setup

### Prerequisites
- Node.js 18+
- Android Studio
- JDK 17
- Android device or emulator (ARM recommended)

### Installation

```bash
# Clone the repo
git clone https://github.com/adityakr09/on-device-ai-chat.git
cd on-device-ai-chat

# Install dependencies
npm install

# Run on Android
npx react-native run-android

# Push model to device
adb push model.gguf /data/local/tmp/model.gguf
```

### Download Model

Download SmolLM2 360M GGUF from HuggingFace (~270MB):
```
https://huggingface.co/QuantFactory/SmolLM2-360M-GGUF
```

---

## 📁 Project Structure

```
on-device-ai-chat/
├── App.tsx          # Main app component
├── index.js         # Entry point
├── package.json     # Dependencies
└── android/         # Android native code
```

---

## ⚠️ Known Limitations

- Requires ARM device for best performance (x86 emulator has native library limitations)
- First load takes 30-60 seconds
- Requires 2GB+ RAM

---

## 👨‍💻 Built By

**Aditya Kumar**  
Backend & Full-Stack Developer learning Mobile AI Development

Django • REST APIs • React • React Native

---

## 📄 License

MIT
