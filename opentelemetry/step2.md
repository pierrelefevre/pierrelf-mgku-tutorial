Create a file named app.py and add the following code for a simple Flask web application:
python

Command for inserting the source code:
```
echo -e "from flask import Flask\n\napp = Flask(__name__)\n\n@app.route(\"/\")\ndef hello():\n    return \"Hello, OpenTelemetry\"\n\nif __name__ == \"__main__\":\n    app.run(host='0.0.0.0', port=5000 )" > app.py
```{{exec}}

To view the current file use:

```
cat app.py
```{{exec}}


And here is the source code to look at.
```
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, OpenTelemetry!"

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=5000 )
```




