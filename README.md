<h1>Flask File Server</h1>

<p>This is a simple Flask server for uploading and downloading files.</p>

<h2>Installation</h2>

<ol>
  <li><strong>Clone the repository:</strong></li>
  <pre><code>git clone git@github.com:ernakkc/flask-file-server.git
cd flask-file-server
</code></pre>

  <li><strong>Install the required packages:</strong></li>
  <pre><code>pip install -r requirements.txt
</code></pre>
</ol>

<h2>Usage</h2>

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

<h2>License</h2>

<p>This project is licensed under the <a href="https://opensource.org/licenses/MIT">MIT License</a>.</p>
