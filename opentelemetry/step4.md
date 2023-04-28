Modify app.py to use OpenTelemetry instrumentation:

```
echo -e "from flask import Flask\nfrom opentelemetry.instrumentation.flask import FlaskInstrumentor\nfrom trace import get_tracer\n\napp = Flask(__name__)\nFlaskInstrumentor().instrument_app(app)\ntracer = get_tracer()\n\n@app.route(\"/\")\ndef hello():\n    with tracer.start_as_current_span(\"hello-span\"):\n        return \"Hello, OpenTelemetry\"\n\nif __name__ == \"__main__\":\n    app.run(host='0.0.0.0', port=5000)" > app.py
```{{exec}}


Here is the source code to look at.
```
from flask import Flask
from opentelemetry.instrumentation.flask import FlaskInstrumentor
from trace import get_tracer

app = Flask(__name__)
FlaskInstrumentor().instrument_app(app)
tracer = get_tracer()

@app.route("/")
def hello():
    with tracer.start_as_current_span("hello-span"):
        return "Hello, OpenTelemetry!"

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=5000)

```
