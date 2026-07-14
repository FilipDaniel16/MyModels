# Models Help Guide

Complete guide to using OpenAI's Sora 2 and Sora 2 Pro video generation models.

---

## 🎬 Quick Start Guide

### 1. Setup Your Environment

#### Install Required Libraries
```bash
pip install openai python-dotenv
```

#### Set Your API Key
```bash
# Create a .env file
echo "OPENAI_API_KEY=your-api-key-here" > .env
```

#### Verify Installation
```python
from openai import OpenAI
print("OpenAI library installed successfully!")
```

---

## 📝 Basic Usage

### Generate a Video with Sora 2 (Standard)

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

# Load environment variables
load_dotenv()

# Initialize client
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Generate video
response = client.videos.create(
    model="sora-2",
    prompt="A golden retriever playing fetch in a sunny park",
    seconds=8,
    size="1280x720"
)

# Get video ID
video_id = response.id
print(f"Video ID: {video_id}")
print(f"Status: {response.status}")
```

### Generate a Video with Sora 2 Pro (Professional)

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

# Load environment variables
load_dotenv()

# Initialize client
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Generate high-quality video
response = client.videos.create(
    model="sora-2-pro",
    prompt="A futuristic city skyline at sunset with flying cars and neon lights",
    seconds=12,
    size="1920x1080"
)

# Get video ID
video_id = response.id
print(f"Video ID: {video_id}")
print(f"Status: {response.status}")
```

---

## ✅ Checking Video Status

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

load_dotenv()
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Check video generation status
video_id = "your-video-id"
status_response = client.videos.retrieve(video_id)

print(f"Status: {status_response.status}")
print(f"Created at: {status_response.created_at}")

# Status values:
# - "pending" = Still generating
# - "completed" = Ready to download
# - "failed" = Generation failed

if status_response.status == "completed":
    print(f"Video URL: {status_response.url}")
```

---

## 🎯 Advanced Examples

### Example 1: Generate and Poll Until Complete

```python
import os
import time
from openai import OpenAI
from dotenv import load_dotenv

load_dotenv()
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Create video
response = client.videos.create(
    model="sora-2",
    prompt="A astronaut walking on the moon with Earth in the background",
    seconds=10,
    size="1280x720"
)

video_id = response.id
print(f"Creating video {video_id}...")

# Poll for completion
max_attempts = 60  # Poll for up to 5 minutes (60 * 5 seconds)
attempt = 0

while attempt < max_attempts:
    status = client.videos.retrieve(video_id)
    print(f"Attempt {attempt + 1}: Status = {status.status}")
    
    if status.status == "completed":
        print(f"✅ Video completed! URL: {status.url}")
        break
    elif status.status == "failed":
        print(f"❌ Video generation failed!")
        break
    
    time.sleep(5)  # Wait 5 seconds before checking again
    attempt += 1

if attempt == max_attempts:
    print("⏱️ Polling timeout - video is still processing")
```

### Example 2: Using Image Reference

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

load_dotenv()
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Generate video from image reference
response = client.videos.create(
    model="sora-2-pro",
    prompt="Transform this into an animated scene with the character dancing",
    image="path/to/your/image.jpg",  # Reference image
    seconds=8,
    size="1280x720"
)

print(f"Video ID: {response.id}")
```

### Example 3: Extend an Existing Video

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

load_dotenv()
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Extend video (continue from where it ended)
extension_response = client.videos.create_extension(
    model="sora-2-pro",
    video_id="your-existing-video-id",
    prompt="Continue the scene with the character walking into a building"
)

print(f"Extended video ID: {extension_response.id}")
```

### Example 4: Edit Existing Video

```python
import os
from openai import OpenAI
from dotenv import load_dotenv

load_dotenv()
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Edit specific parts of a video
edit_response = client.videos.create_edit(
    model="sora-2-pro",
    video_id="your-existing-video-id",
    prompt="Change the background to a snowy mountain landscape"
)

print(f"Edited video ID: {edit_response.id}")
```

---

## 🎨 Writing Effective Prompts

### ✅ Good Prompts (Specific & Detailed)
```
"A chef preparing a gourmet pasta dish in a modern kitchen, with steam 
rising from the pan, shot in cinematic style with warm lighting"

"A young girl running through a golden wheat field at sunset, with a 
golden retriever following her, slow motion, cinematic camera"

"A sleek silver sports car driving through a futuristic neon-lit city 
at night, with dynamic camera angles and reflections on wet streets"
```

### ❌ Vague Prompts (Too Generic)
```
"A car"
"A person"
"Something interesting"
```

### Tips for Better Prompts:
1. **Be Specific:** Include details about the subject, setting, and style
2. **Add Context:** Describe the scene, lighting, and atmosphere
3. **Include Camera Movement:** Mention static shots, pans, zooms, etc.
4. **Use Adjectives:** Add color, texture, and mood descriptions
5. **Specify Duration:** Consider what can happen in 12 seconds
6. **Think Cinematically:** Use film/photography terms (cinematic, slow-motion, etc.)

---

## 💡 Choosing the Right Model

### Use **Sora 2** When:
- ✅ Creating quick drafts or prototypes
- ✅ Making social media content
- ✅ Cost is a priority ($0.10/second)
- ✅ You don't need 1080p quality
- ✅ Fast turnaround is important
- ✅ Content is for web/mobile

### Use **Sora 2 Pro** When:
- ✅ Creating commercial content
- ✅ Quality is critical
- ✅ You need 1080p resolution
- ✅ Character consistency matters
- ✅ Cinematic quality is required
- ✅ Professional presentation needed
- ✅ Client deliverables

---

## 🔧 Troubleshooting

### Issue: "Authentication Error"
```
Solution: 
1. Check your API key is correct
2. Verify API key has video generation access
3. Ensure .env file is in correct location
4. Try recreating your API key on platform.openai.com
```

### Issue: "Invalid Prompt"
```
Solution:
1. Prompts must be 1-4096 characters
2. Avoid asking for illegal or explicit content
3. Cannot generate photorealistic celebrities
4. Keep descriptions realistic and feasible
```

### Issue: "Video Generation Failed"
```
Solution:
1. Try a simpler prompt
2. Reduce complexity (fewer characters, simpler scenes)
3. Check prompt for content policy violations
4. Wait a moment and try again
5. Contact OpenAI support if persists
```

### Issue: "Rate Limit Exceeded"
```
Solution:
1. Wait before making new requests
2. Upgrade your OpenAI plan for higher limits
3. Implement exponential backoff in your code
```

---

## 📊 Cost Estimation

### Sora 2 (Standard - $0.10/second)
| Duration | 720p Cost |
|----------|-----------|
| 4 seconds | $0.40 |
| 8 seconds | $0.80 |
| 12 seconds | $1.20 |

### Sora 2 Pro
| Duration | 720p | 1024p | 1080p |
|----------|------|-------|-------|
| 4 seconds | $1.20 | $2.00 | $2.80 |
| 8 seconds | $2.40 | $4.00 | $5.60 |
| 12 seconds | $3.60 | $6.00 | $8.40 |

---

## 🚀 Best Practices

1. **Test with Sora 2 First:** Get feedback before upgrading to Pro
2. **Batch Similar Videos:** Generate multiple videos together for efficiency
3. **Monitor Costs:** Track spending to stay within budget
4. **Use Image References:** Helps maintain consistency across videos
5. **Iterate Gradually:** Small edits are better than complete regeneration
6. **Save Video URLs:** Store URLs before they expire
7. **Document Prompts:** Keep records of what worked well
8. **Plan Content:** Outline scenes before generating

---

## 📚 API Parameters Reference

### Video Creation Parameters
```python
client.videos.create(
    model="sora-2" or "sora-2-pro",        # Required: Model choice
    prompt="Your prompt here",              # Required: Video description
    seconds=8,                              # Optional: Duration (4, 8, 12, 16, 20)
    size="1280x720"                        # Optional: Resolution
)
```

### Supported Sizes
- `1280x720` (16:9 landscape, default)
- `720x1280` (9:16 portrait)
- `1024x1024` (1:1 square)
- `1920x1080` (16:9, Sora 2 Pro only)

### Response Fields
```python
response.id              # Video ID for tracking
response.status         # "pending", "completed", or "failed"
response.created_at     # Timestamp
response.url            # Download URL (when completed)
response.expires_at     # URL expiration time
```

---

## 🔐 Security & Best Practices

1. **Never commit API keys:** Use environment variables
2. **Rotate keys regularly:** Update on platform.openai.com
3. **Use .gitignore:** Exclude .env files from git
4. **Monitor usage:** Check API dashboard for unusual activity
5. **Use specific keys:** Create separate keys for different projects
6. **Rate limit:** Implement backoff strategies

---

## 📞 Getting Help

- **Official Docs:** https://developers.openai.com/api/docs/guides/video-generation
- **API Reference:** https://platform.openai.com/docs/api-reference/videos
- **Status Page:** https://status.openai.com
- **Community:** https://community.openai.com

---

## 📅 Important Dates

- **Sora 2 Deprecation Date:** September 24, 2026
- **Last Day to Use:** September 23, 2026
- **Plan Migration:** Start preparing before this date

---

**Last Updated:** July 14, 2026  
**Version:** 1.0
