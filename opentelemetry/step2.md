Create a file named app.py and add the following code for a simple Flask web application:
python

```
nano app.py
```{{exec}}


```
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, OpenTelemetry!"

if __name__ == "__main__":
    app.run(port=5000)
```




