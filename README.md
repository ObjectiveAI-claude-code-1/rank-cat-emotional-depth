# rank-cat-emotional-depth

A vector function that ranks cat pictures by the depth of emotional feeling they provoke. This is not a cuteness detector, a humor scorer, or a measure of photographic technique. It evaluates how deeply an image of a cat can reach into the emotional interior of the person who looks at it, and how long the feeling it produces is likely to endure.

## Input

The function accepts an array of cat images (minimum 2). Each image is a photograph or picture of a cat in any context, setting, or state of being — from professional portraits to casual snapshots, kittens to elderly cats, indoor scenes to strays in the rain. No captions, titles, or metadata are considered. Every image speaks entirely for itself.

```
Input: image[]  (minItems: 2)
```

## Output

A normalized score distribution — an array of numbers (one per input image) that sum to approximately 1. Higher scores indicate greater emotional depth. The scores rank images from most emotionally shallow and transient to most deeply and lastingly affecting.

```
Output: number[]  (length matches input, sums to ~1)
```

## What It Evaluates

The function assesses each cat picture along three qualities of emotional depth:

### 1. Emotional Penetration

How far beneath the surface of a quick, automatic reaction the image reaches. A cat doing something silly provokes a laugh — that is shallow. A cat curled beside a cushion indent where someone used to sit provokes something that tightens in the chest — that is deep. This quality distinguishes between images that merely touch the outermost layer of attention and images that find their way to the tender, unguarded places where real feeling lives: love, loss, fragility, and the quiet astonishment of being alive alongside another creature.

### 2. Resonance with Universal Experience

The degree to which the image, despite being a picture of a cat, gestures toward something larger and more universally human. The most emotionally deep cat pictures are never really about cats — they are about what the cat allows the viewer to see about their own life. A kitten bewildered by snow resonates because everyone has stood at the edge of something unfamiliar. An old cat in fading afternoon light resonates because everyone has felt the ache of things that are temporary. This quality evaluates whether the image connects to shared human experience — tenderness, vulnerability, innocence, companionship, wonder, aging, solitude, trust — or remains a charming but self-contained snapshot pointing to nothing beyond itself.

### 3. Durability of Feeling

The staying power of the emotional response — its ability to outlast the moment of looking and persist in the viewer's memory. Many images are firecrackers: a dramatic cat face is hilarious for two seconds and then gone. This quality identifies images that work like embers — they may not provoke the loudest initial reaction, but what they produce continues to glow. These are the images that resurface unbidden while washing dishes, or falling asleep, or three weeks later when something in the texture of an ordinary afternoon calls the image back to mind. The ultimate test of genuine emotional depth.

## Use Cases

- **Curation**: Sift through large collections to find the images that carry real emotional freight — for books, galleries, gifts, or social posts that aspire to be more than disposable content.
- **Attention**: Use as a framework for noticing the difference between reaction and feeling, between amusement and recognition. Understand why some images land harder than others.
- **Community**: Surface quiet, profound images in sharing spaces where louder, flashier content would otherwise dominate. Advocate for the images that whisper rather than shout.

## How It Works

The function runs three independent vector completion tasks — one for each quality — each structured as a conversational prompt where the cat pictures serve as candidate responses. The tasks vary in structure:

1. **Penetration task**: A single user message requesting an image that reaches past the surface to the places where real feeling lives.
2. **Resonance task**: A developer message establishing the evaluative frame (images that transcend their subject) followed by a user message asking for an image that speaks to universal human experience.
3. **Durability task**: A multi-turn conversation (user/assistant/user) that articulates the distinction between firecrackers and embers, culminating in a request for an image the viewer will carry with them.

Scores from all three tasks are aggregated to produce the final ranking, ensuring that images must demonstrate depth across all three qualities to rank highest.