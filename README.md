# 📦 Flask File Server

<div align="center">

![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.7+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

*A lightweight Flask-based file server for uploading, downloading, and managing files via HTTP API*

</div>

---

## 📖 Overview

Flask File Server is a simple and efficient RESTful API server built with Flask that allows you to upload, download, and list files through HTTP requests. Perfect for quick file sharing, testing, or as a backend component for file management systems.

## ✨ Features

- 📤 **File Upload**: Upload single or multiple files simultaneously
- 📥 **File Download**: Download files by filename
- 📋 **File Listing**: List all available files on the server
- 🔒 **Safe Storage**: Files are stored in a dedicated `uploads` directory
- 🚀 **RESTful API**: Clean and intuitive API endpoints
- ⚡ **Lightweight**: Minimal dependencies, fast performance

## 🛠️ Installation

### Prerequisites
- Python 3.7 or higher
- pip package manager

### Quick Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/ernakkc/flask-file-server.git
   cd flask-file-server
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the server**:
   ```bash
   python app.py
   ```

The server will start on `http://localhost:5000`

## 🚀 Usage

<ol>
  <li><strong>Run the server:</strong></li>
  <pre><code>python app.py
</code></pre>

  <li><strong>Upload files using the <code>/upload</code> endpoint:</strong></li>
  <pre><code>import requests

url = 'http://localhost:5000/upload'
files = {'files': open('path/to/your/file', 'rb')}
response = requests.post(url, files=files)
print(response.json())
</code></pre>

  <li><strong>List uploaded files using the <code>/files</code> endpoint:</strong></li>
  <pre><code>import requests

response = requests.get('http://localhost:5000/files')
print(response.json())
</code></pre>

  <li><strong>Download a file using the <code>/download/&lt;filename&gt;</code> endpoint:</strong></li>
  <pre><code>import requests

response = requests.get('http://localhost:5000/download/yourfile.txt')
with open('yourfile.txt', 'wb') as f:
    f.write(response.content)
</code></pre>
</ol>

