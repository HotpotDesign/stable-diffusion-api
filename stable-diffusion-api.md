# Stable Diffusion API

## Stable Diffusion Overview

Stable Diffusion is a popular text-to-image model created by Stability.ai, the Ludwig Maximilian University machine learning research group, and contributions from AI artists and enthusiasts. Of note, researchers from NVIDIA kickstarted the trend toward modern image AI architectures with an influential paper on score-based generative modeling in latent space.

## Stable Diffusion Versions

Hotpot.ai offers multiple versions of Stable Diffusion, each catering to different needs and budgets.

- **Stable Diffusion Normal**: applies proprietary optimizations to vanilla Stable Diffusion for improved quality and latency. Runs on Hotpot standard servers.

- **Stable Diffusion Premium**: applies additional optimizations to **Stable Diffusion Normal**, with higher quality and the lowest latency. Runs on A100 servers.

- **Stable Diffusion Budget**: optimizes Stable Diffusion for lowest possible cost.

- **Hotpot Image Generator**: premium image generation, offering maximum quality and the same styles and proprietary model powering the [AI Image Generator](https://hotpot.ai/art-generator) from Hotpot.ai.

These Stable Diffusion API versions are based on Stable Diffusion XL. Stable Diffusion 2.1 and Stable Diffusion 1.5 are available upon request.

## API Reliability

The Hotpot.ai API powers millions of image generation requests each month from Fortune 500 enterprises, consumers, and small businesses around the world. The API infrastructure is built on enterprise-grade servers from leading cloud platforms, not decentralized consumer GPUs that form an unreliable mesh network.

## Stable Diffusion Pricing

Hotpot offers flexible, pay-as-you-go pricing based on each image generated, not server time.

Free credits are given to new users for testing, no credit card required.

## How to Get Started With Stable Diffusion

Follow these steps to start building with Stable Diffusion and integrate advanced image generation capabilities:

1. Get API key from [Stable Diffusion API] (https://hotpot.ai/stable-diffusion-api).
2. Each API key comes with free credits, no credit card required.
3. Try the cURL and Python code examples below, or review the [Hotpot.ai API docs](https://hotpot.ai/docs/api).

## Stable Diffusion Code Examples

Listed below are simple code examples for generating images from text with Stable Diffusion.

### cURL Example

```bash
curl -H 'Authorization: YOUR_API_KEY' \
     -F 'inputText=An astronaut riding a horse on Mars' \
     -F 'guidanceScale=10' \
     -o 'astronaut_on_mars.jpg' \
     https://api.hotpot.ai/stable-diffusion-normal
```

### Python Example

```python
import requests

# API Key and Endpoint
api_key = 'your_hotpot_ai_api_key'
api_endpoint = 'https://api.hotpot.ai/stable-diffusion-normal'

# Request Headers and Data
headers = {'Authorization': api_key}
data = {
    'inputText': 'An astronaut riding a horse on Mars',
    'guidanceScale': 10,
}

# Make API Request
response = requests.post(api_endpoint, headers=headers, files=data)
if response.status_code == 200:
    with open('astronaut_on_mars.jpg', 'wb') as f:
        f.write(response.content)
    print('Image generated and saved.')
else:
    print(f'Error: {response.status_code}, message: {response.text}')
```
