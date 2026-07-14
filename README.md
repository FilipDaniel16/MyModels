# My Models List

A comprehensive collection of AI models with detailed information and usage guides.

---

## 📹 Video Generation Models

### Sora 2 (OpenAI)
**Standard Video Generation Model**

| Property | Details |
|----------|---------|
| **Model ID** | `sora-2` |
| **Type** | Text-to-Video / Image-to-Video |
| **Resolution** | Up to 720p (1280x720) |
| **Max Duration** | 12 seconds per video |
| **Price** | $0.10 per second |
| **Best For** | Social media content, drafts, fast iteration |
| **Features** | Text prompts, image references, synchronized audio |
| **Status** | Production-ready ✅ |
| **Documentation** | [OpenAI Video Generation Docs](https://developers.openai.com/api/docs/guides/video-generation) |

#### Key Capabilities:
- ✅ Generate videos from text descriptions
- ✅ Generate videos from reference images
- ✅ Automatic audio synchronization
- ✅ Multiple aspect ratios supported
- ✅ Up to 12 seconds of video content

#### Usage Example:
```python
from openai import OpenAI

client = OpenAI(api_key="your-api-key")

response = client.videos.create(
    model="sora-2",
    prompt="A cat playing piano under spotlights on a stage",
    seconds=8,
    size="1280x720"
)

video_id = response.id
```

---

### Sora 2 Pro (OpenAI)
**Professional Video Generation Model**

| Property | Details |
|----------|---------|
| **Model ID** | `sora-2-pro` |
| **Type** | Text-to-Video / Image-to-Video |
| **Resolution** | Up to 1080p (1920x1080) |
| **Max Duration** | 12 seconds (up to 20 seconds with extensions) |
| **Price** | $0.30/sec (720p), $0.50/sec (1024p), $0.70/sec (1080p) |
| **Best For** | Commercial projects, cinematic quality, high-detail scenes |
| **Features** | Advanced physics, better lighting, detailed faces, smooth motion |
| **Status** | Production-ready ✅ |
| **Documentation** | [OpenAI Video Generation Docs](https://developers.openai.com/api/docs/guides/video-generation) |

#### Key Capabilities:
- ✅ Cinematic quality videos
- ✅ Advanced physics simulation
- ✅ High-resolution output (1080p)
- ✅ Better lighting and shadow rendering
- ✅ More detailed facial expressions
- ✅ Smoother motion and transitions
- ✅ Character consistency across scenes
- ✅ Video extension/continuation

#### Usage Example:
```python
from openai import OpenAI

client = OpenAI(api_key="your-api-key")

response = client.videos.create(
    model="sora-2-pro",
    prompt="A futuristic city skyline at sunset with flying cars and neon lights",
    seconds=12,
    size="1920x1080"
)

video_id = response.id
```

---

## 📊 Comparison Table

| Feature | Sora 2 | Sora 2 Pro |
|---------|--------|-----------|
| Max Resolution | 720p | 1080p |
| Max Duration | 12 sec | 12-20 sec |
| Price/Second | $0.10 | $0.30-$0.70 |
| Video Quality | Standard | Cinematic |
| Physics | Basic | Advanced |
| Lighting | Standard | Enhanced |
| Use Case | Drafts, Social | Commercial, Studio |
| Character Consistency | Limited | Yes |
| Audio Sync | Yes | Yes |

---

## 🔗 API Endpoints

### Generate Video
```
POST /v1/videos
```

### Extend/Continue Video
```
POST /v1/videos/extensions
```

### Edit Video
```
POST /v1/videos/{video_id}/edits
```

### Get Video Status
```
GET /v1/videos/{video_id}
```

---

## 💰 Pricing Guide

### Sora 2 (Standard)
- **720p video at 12 seconds:** $1.20
- **720p video at 8 seconds:** $0.80
- **720p video at 4 seconds:** $0.40

### Sora 2 Pro
- **720p video at 12 seconds:** $3.60
- **1024p video at 12 seconds:** $6.00
- **1080p video at 12 seconds:** $8.40

---

## 🚀 Getting Started

1. **Get API Access:** https://platform.openai.com/docs/api-reference/videos
2. **Authenticate:** Use your OpenAI API key
3. **Choose Model:** `sora-2` for speed, `sora-2-pro` for quality
4. **Create Video:** Send prompt via API and receive video ID
5. **Poll Status:** Check generation progress
6. **Download:** Get MP4 file when ready

---

## ⚠️ Important Notes

- **Deprecation:** Sora 2 models are scheduled for deprecation on **September 24, 2026**
- **Content Moderation:** Strict moderation for photorealistic content of real people
- **Rate Limits:** Scale with your usage tier
- **Async Processing:** Video generation is asynchronous (not instant)
- **Audio:** Automatic audio generation included in all outputs

---

## 📚 Resources

- [OpenAI Video Generation Guide](https://developers.openai.com/api/docs/guides/video-generation)
- [Sora 2 Model Details](https://developers.openai.com/api/docs/models/sora-2)
- [Sora 2 Pro Model Details](https://developers.openai.com/api/docs/models/sora-2-pro)
- [OpenAI API Documentation](https://platform.openai.com/docs/api-reference)

---

**Last Updated:** July 14, 2026  
**Models Included:** Sora 2, Sora 2 Pro
