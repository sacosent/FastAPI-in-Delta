
# Deploy a FastAPI App to Deta Space with PHIRO 🔥🔥

We're excited to share our first open project on GitHub, a FastAPI application deployed on a public server in Deta Space. Whether you're a seasoned developer or a passionate newcomer, this guide will help you deploy your own FastAPI app effortlessly. Let's turn your innovative ideas into reality! 🔥

## Why Deta Space? 🔥

In the spirit of PHIRO's mission, we're always on the lookout for accessible and sustainable tech solutions. Deta Space offers a free and reliable platform to deploy your applications, perfect for those late-night ideas when you just have to build one more to-do app. No more worrying about Heroku's pricing changes—Deta Space has got you covered.

## Setting Up Deta Space 🔥

First, you'll need to install the [Space CLI](https://deta.space/docs/en/build/fundamentals/space-cli/).

Next, log in to Deta Space to get your access token:

```bash
space login
```

Create a new project (we're calling it _fast-api-sample_ for this example):

```bash
space new
```

## Creating the Spacefile 🔥

Your \`Spacefile\` is the blueprint for your project. It should look something like this:

```yaml
v: 0
app_name: "FAPI SAMPLE"
micros:
  - name: fastapi-sample
    src: ./
    engine: python3.9
    dev: .venv/bin/uvicorn main:app --reload
```

Note that \`main:app\` refers to the \`main.py\` file and the \`app\` instance within it.

## Building Your FastAPI App 🔥

Here's a simple FastAPI app to get you started:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}
```

Ensure you have a \`requirements.txt\` file listing your dependencies. For this basic app, it should include:

```
fastapi
```

## Deploying Your App 🔥

With everything set up, you can deploy your app with a simple push command:

```bash
space push
```

If everything is configured correctly, you'll see a message like this:

```
🎉  Successfully pushed your code and updated your Builder instance!
Builder instance: <https://fastapisample-1-p5210071.deta.app>
```

And just like that, your API is live on the web! ⛅

## Join the PHIRO Community

<div align="center" style="display: flex; justify-content: center; align-items: center; height: 100vh;">
  <img src="https://github.com/sacosent/fastapi-in-delta/assets/72815091/edc344b3-b01c-4f4c-a627-2e59d0e46b1c" width="30%" height="30%">
</div>

At PHIRO, every project is a collaborative effort, driven by passion and innovation. Join us in creating technology that makes a difference. Dive into this project, contribute, and share your feedback. Together, we can build something amazing.

🔥 Ignite Inovation 🔥
