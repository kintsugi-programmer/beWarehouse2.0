# DAVP3
## Table of Contents
- [DAVP3](#davp3)
  - [Table of Contents](#table-of-contents)
  - [Digital Audio : Audio Signal Processing and Microphone Polar Patterns](#digital-audio--audio-signal-processing-and-microphone-polar-patterns)
    - [Understanding **Gain** and **Volume**](#understanding-gain-and-volume)
    - [**Compression**: Shaping Your Sound's Dynamics](#compression-shaping-your-sounds-dynamics)
    - [**Microphone Polar Patterns**: How Microphones "Hear"](#microphone-polar-patterns-how-microphones-hear)
      - [1. **Omnidirectional**](#1-omnidirectional)
      - [2. **Figure-of-8 (Bidirectional)**](#2-figure-of-8-bidirectional)
      - [3. **Cardioid (Unidirectional)**](#3-cardioid-unidirectional)
      - [4. **Supercardioid (Unidirectional)**](#4-supercardioid-unidirectional)
      - [5. **Hypercardioid (Unidirectional)**](#5-hypercardioid-unidirectional)
  - [Digital Audio : Equalization and Filters: Shaping Sound Frequencies](#digital-audio--equalization-and-filters-shaping-sound-frequencies)
    - [**Understanding Equalization**](#understanding-equalization)
    - [**Understanding Filters**](#understanding-filters)
    - [Digital Audio: EQ \& Filters - ASCII Visual Notes](#digital-audio-eq--filters---ascii-visual-notes)
      - [What is Equalization?](#what-is-equalization)
        - [Two Main Uses of EQ:](#two-main-uses-of-eq)
      - [Filter Types (The Building Blocks of EQ)](#filter-types-the-building-blocks-of-eq)
        - [1. LOW-PASS FILTER](#1-low-pass-filter)
        - [2. HIGH-PASS FILTER](#2-high-pass-filter)
        - [3. BAND-PASS FILTER](#3-band-pass-filter)
        - [4. BAND-STOP FILTER](#4-band-stop-filter)
        - [5. NOTCH FILTER](#5-notch-filter)
      - [Filter Comparison Chart](#filter-comparison-chart)
      - [Key Remember Points](#key-remember-points)
      - [Practical Application Examples](#practical-application-examples)


## Digital Audio : Audio Signal Processing and Microphone Polar Patterns
- see slides
The source provides an overview of essential audio engineering concepts, starting with a distinction between gain, which regulates the input level of an audio signal, and volume, which controls its output loudness. It then explains compression, detailing how this effect can subtly enhance sound quality and outlining its various applications in recording and mixing. Key parameters of compression are discussed, including threshold, knee, attack time, release, and ratio, alongside the function of a sidechain. Finally, the document comprehensively describes different microphone polar patterns—such as omnidirectional, figure-of-eight, cardioid, supercardioid, and hypercardioid—explaining their unique sound pickup characteristics and ideal uses.

### Understanding **Gain** and **Volume**

When you're dealing with sound equipment, you'll often hear the terms "gain" and "volume" used, and it's really important to understand that they refer to different stages of your audio signal.

*   **Gain: The Input Level**
    *   Think of **gain** as **how loud the sound is when it first enters your system**, like a channel on a mixing desk or an amplifier. It's the "input level" of the signal.
    *   The primary role of gain is to bring a signal up to a usable, recordable level *before* any major processing happens.
    *   **Example**: When you plug a microphone into a mixer, there's usually a **preamp gain** or **"trim" control**. This knob turns up the quiet signal from the microphone so that it's strong enough to work with. If the gain is too low, your signal will be weak and noisy. If it's too high, it'll distort and sound terrible!
    *   **Key takeaway**: **Gain is about the strength of the signal at the input stage, *before* it's processed or altered**.

*   **Volume: The Output Level**
    *   **Volume**, on the other hand, is **how loud the sound is *after* it has been processed** and is ready to leave the channel or amplifier. It's the "output level".
    *   This is the control you use to adjust the overall loudness of what you're hearing.
    *   **Example**: The main fader on a mixer channel or the master volume knob on your speakers controls the output volume.
    *   **A helpful distinction**: Sometimes you'll encounter a control like "makeup gain" on a compressor plugin. Even though it has "gain" in its name, it's actually acting as an output volume knob, compensating for any level reduction caused by the compression effect.
    *   **Key takeaway**: **Volume is the measurable output level of a signal *after* all processing has taken place**.

In simple terms: **Gain gets the signal *in* properly; Volume controls how loud it comes *out***.

---

### **Compression**: Shaping Your Sound's Dynamics

**Compression** is one of the most powerful and often misunderstood tools in audio production. It's used to manage the "dynamics" of a sound – meaning the difference between its loudest and quietest parts.

*   **What Compression Does (The Goal)**
    *   At its core, compression helps to **subtly balance a track**, making it sound more natural and easier to understand (intelligible).
    *   It achieves this **without adding distortion**, resulting in a song that's simply more "comfortable" to listen to. Imagine a singer who sometimes sings very loud and sometimes very quiet – a compressor can gently "tame" the loud parts and "lift" the quiet parts so the performance sounds more even.
    *   Beyond just balancing, many compressors (both physical hardware units and software plugins) have their own unique "signature sound". This means they can **inject wonderful coloration and tone** into tracks that might otherwise sound a bit lifeless.

*   **How and Where to Use a Compressor**
    You can use a compressor in several key ways:
    *   **During Recording**: You can compress an individual signal (like a vocal or bass guitar) *as it's being recorded*. This helps to capture a more controlled signal from the start.
    *   **During Mixing**: You can compress an individual signal *while you are mixing*. This is very common for instruments like drums, vocals, and guitars to help them sit better in the mix.
    *   **On the Whole Mix**: You can also compress the *entire stereo mix* during the mixing process. This is often called "master bus compression" and helps to glue all the individual tracks together and add overall punch and consistency to the final song.

*   **Key Parameters and Controls (The Knobs and Dials)**
    No matter the type of compressor, you'll encounter some common controls that dictate how the compression effect behaves:

    1.  **Threshold (The Trigger Point)**
        *   The **threshold** control sets the specific volume level at which the compressor "kicks in" or becomes active.
        *   **Only when a signal's level goes *above* this threshold will it be compressed**.
        *   If you set the threshold at, say, -10 dB, only those loud peaks that extend beyond -10 dB will be affected. Any sound below that level will pass through untouched.
        *   Think of it like a gate: once the sound gets loud enough to pass through the gate, the compressor starts working.

    2.  **Knee (The Smoothness of the Transition)**
        *   The **"knee"** describes *how* the compressor moves between the uncompressed (normal) and compressed states of an audio signal. It's about how gentle or abrupt the compression starts.
        *   Most compressors offer either a **"soft knee"** or a **"hard knee"** setting, and sometimes even allow you to choose a position in between.
        *   A **"soft knee"** allows for a **smoother and more gradual compression**. The compression effect eases in as the signal approaches the threshold, becoming progressively stronger as it passes it. This often sounds more natural.
        *   A **"hard knee"** means the compression is **much more sudden and immediate** once the signal crosses the threshold. It's an "on/off" switch for compression. This can create a more aggressive or noticeable effect.

    3.  **Attack Time (How Quickly It Reacts)**
        *   **Attack time** refers to **how long it takes for the signal to become *fully compressed* once it has exceeded the threshold level**.
        *   It's essentially the compressor's "reaction time".
        *   This setting determines how much of the initial "impact" or "transient" (the very first, usually loudest, part of a sound like a drum hit) is allowed to pass *before* the compressor clamps down.
        *   **Slow Attack**:
            *   **Pros**: Lets more of the initial impact and punchiness through. This can make drums sound punchier or vocals feel more dynamic.
            *   **Cons**: Can make uneven performance dynamics (where quiet parts are very quiet and loud parts very loud) even worse if not used carefully.
        *   **Fast Attack**:
            *   **Pros**: Quickly tightens up the initial transient, adds control, and creates a more "processed" or controlled sound.
            *   **Cons**: Can "squash" or "pull life out" of a sound by removing its initial punch.

    4.  **Release Time (How Quickly It Lets Go)**
        *   The **release control** sets the **length of time it takes for the compressor to "let go" or return to its original uncompressed state** once the signal drops back *below* the threshold.
        *   It's literally the opposite of attack time.
        *   **Example**: Imagine a compressor reducing a loud sound. Once that sound becomes quiet again, the release time dictates how quickly the compressor stops reducing the level and allows the signal to return to normal.
        *   Setting this correctly is crucial to avoid a "pumping" or unnatural breathing sound where the volume seems to fluctuate awkwardly.

    5.  **Compression Ratio (How Much It Reduces)**
        *   The **ratio** specifies **the amount of attenuation (reduction) that will be applied to the signal once it crosses the threshold**.
        *   Ratios are expressed in decibels (dB), for example, 2:1, 4:1, 8:1, etc..
        *   A **1:1 ratio** is the lowest possible and represents **"unity gain," meaning absolutely no compression or attenuation is applied**.
        *   Let's break down what the numbers mean with an example:
            *   A **2:1 ratio** indicates that if a signal exceeds the threshold by 2 dB, it will be attenuated (reduced) down to only 1 dB above the threshold. If it exceeds by 8 dB, it will be reduced to 4 dB above the threshold. Essentially, for every 2 dB *above* the threshold, only 1 dB is allowed to pass.
        *   **General Ratio Guidelines**:
            *   **1:1**: No compression.
            *   **Around 3:1**: Considered **moderate compression**. Good for gentle smoothing.
            *   **5:1**: Would be **medium compression**.
            *   **8:1**: Starts getting into **strong compression**.
            *   **20:1 through ∞:1 (infinity to one)**: This high range is considered **"limiting"**. A limiter is essentially a compressor with a very high ratio, designed to strictly prevent a signal from going above a certain level, like an absolute brick wall.

    6.  **Side Chain (Control by Another Signal)**
        *   In addition to its main audio input, a compressor often has a **side chain input**.
        *   Normally, the amount of compression applied is based directly on the dynamics (loudness changes) of the signal passing *through* the compressor itself.
        *   The **side chain allows the amount of compression on the main signal to be controlled by the dynamics of a *completely separate signal***.
        *   **Example**: A common use for side chain is "ducking." You might have music playing and a voiceover. By sending the voiceover signal to the side chain input of a compressor on the music track, the music will automatically get quieter (be compressed) *only when the voiceover is speaking*. Once the voiceover stops, the music returns to its normal volume. This creates space for the voiceover without manually riding faders.

*   **The Fundamental Principle of Compression**:
    It's crucial to understand that simply lowering the signal level using a fader is *not* compression. That's because a fader reduces *all* levels (loud and quiet) by the same amount.
    **Compression only truly happens when the loud sections of a signal are reduced in level *more* than the quiet sections**. It's about reducing the *dynamic range* (the difference between loud and quiet).

---

### **Microphone Polar Patterns**: How Microphones "Hear"

**Microphone polar patterns** are essentially a **visual map of how sensitive a microphone is to sounds coming from different directions** around its capsule. Imagine a 3D bubble around the microphone; the polar pattern shows where it "hears" best and where it's "deaf." These patterns are usually represented graphically.

Knowing these patterns is incredibly important because it helps you choose the right microphone for the job and place it effectively to capture the sound you want, while rejecting unwanted noise.

There are three main families of polar patterns:

1.  **Omnidirectional** (meaning "all directions").
2.  **Unidirectional** (meaning "one direction"), which includes **Cardioid**, **Hypercardioid**, and **Supercardioid**.
3.  **Bidirectional** (meaning "two directions"), commonly known as **Figure-of-8**.

Let's explore each in detail:

#### 1. **Omnidirectional**
*   **How it hears**: An **omnidirectional microphone** is **sensitive to sound from *all directions*, capturing sound from a full 360° radius**. It literally hears everything equally around it.
*   **Pointing not necessary**: You don't need to point these microphones in a specific direction because they pick up sound uniformly from everywhere.
*   **Best Uses**:
    *   They are **excellent for picking up ambient sound**, such as the natural acoustics of a large room.
    *   Ideal for capturing a **big, diffuse sound source** like an orchestra or a choir, where you want to hear the blend of all instruments and the room sound.
    *   Great for capturing multiple speakers in a discussion around a table.
*   **Drawbacks**:
    *   Because they pick up everything, **Omnis can produce a lot of feedback if used in a live situation**. They'll pick up background noise and monitor sound just as easily as the direct source.
*   **Sound Quality**: Their sound is often described as **open, airy, and natural**. They generally have less "proximity effect" (a boost in bass when a mic is close to a source) compared to directional mics.

#### 2. **Figure-of-8 (Bidirectional)**
*   **How it hears**: A **Figure-of-8** (or bidirectional) microphone polar pattern **captures sound primarily from the *front* (0°) and the *back* (180°)**.
*   **The "Null" Sides**: Critically, the **sides of a Figure-of-8 microphone (90° and 270°) are "null," meaning they are acoustically dead and pick up very little sound**.
*   **Best Uses**:
    *   They are **good for instrumentalists or vocalists who are facing each other**, as the mic can pick up both sources while rejecting sounds from the sides.
    *   Can also be used frequently with a single source, benefiting from the rejection of side sounds.
    *   Great for stereo miking techniques like "Blumlein pair" to capture a wide, natural stereo image.
*   **Sound Quality**: Like omnidirectional microphones, Figure-of-8 mics are described as **open and natural sounding**. Interestingly, they technically pick up a similar amount of ambient sound as Cardioid patterns, but from different directions.
*   **Important Note**: It's essential to remember that **all ribbon microphones inherently utilise the Figure-of-8 pattern** due to their design.

#### 3. **Cardioid (Unidirectional)**
*   **How it hears**: The **Cardioid** (heart-shaped) pattern is the most common **unidirectional** pattern. It **primarily picks up sound from the *front and sides*, but is *acoustically dead from the rear***.
*   **Ideal for Live and Studio**:
    *   This makes Cardioid microphones **ideal for live situations** because sound coming from behind the microphone (like stage monitors) will be largely rejected, helping to **prevent feedback**.
    *   They are also widely used for **studio sound**, frequently found on **guitars, vocals, and drums**.
*   **Proximity Effect**: A key characteristic of Cardioid microphones is the **"proximity effect"**. This phenomenon causes the **bass response (low frequencies) to increase as the microphone is moved closer to the sound source**. You can use this creatively to add warmth or fullness to a vocal or instrument.
*   **Sound Quality**: When placed close to a source (close-miked), Cardioid microphones can produce a **highly intimate, dry, and detailed direct sound transmission**.

#### 4. **Supercardioid (Unidirectional)**
*   **How it hears**: The **Supercardioid** pattern is also part of the unidirectional family and is similar to Cardioid but with a few differences.
    *   It covers a **slightly wider angle than Hypercardioid (115° as opposed to 105°)**.
    *   It features **less sensitivity in the rear** compared to Hypercardioid. You can think of it as somewhere between a standard Cardioid and a Hypercardioid.
*   **Benefits**:
    *   It provides **better ambient noise rejection than Cardioid**, making it more resistant to feedback and maintaining high directionality from the front.
*   **Placement**: Due to its precise directional characteristics, **positioning mics with this pattern must be done exactly**.
*   **Best Uses**: These microphones are commonly used for **lectures and conferences**, and also for **close-miked instruments** such as violins, violas, cellos, and mandolins, often as an alternative to using pickups.

#### 5. **Hypercardioid (Unidirectional)**
*   **How it hears**: **Hypercardioid** microphones are also unidirectional. They receive sound primarily from the **front and sides, but they have *some sensitivity in the rear*** (more than Supercardioid or Cardioid).
    *   They feature a **narrower pickup range on the sides** compared to Cardioid.
*   **Highly Directional**: This pattern is **highly directional**, meaning it's excellent for focusing on a specific sound source and rejecting off-axis sounds.
*   **Common Application**: The most common use for Hypercardioid microphones is as **"Shotgun microphones,"** which are frequently employed for sports games, conferences, and lectures where you need to pick up sound from a distance.
*   **Considerations**:
    *   While great for pointing at sources from great distances, they **can be sensitive to small movements from the source**. For instance, it's generally not recommended to use a Hypercardioid mic in front of a highly mobile singer, as their movements could cause the sound to fade in and out.
    *   Although resistant to feedback in live situations, any **monitor speakers should be placed off to the side** and *not directly behind* the microphone, due to its rear sensitivity.

---

**In summary**: Microphones are carefully designed to capture sound fields within a certain radius. A deep understanding of these **microphone polar patterns** is absolutely crucial for crafting great recordings, and it's a key part of your overall knowledge base. However, remember that other factors, like **microphone placement**, also play a significant role in achieving the desired sound.

## Digital Audio : Equalization and Filters: Shaping Sound Frequencies
- see slides
The provided text introduces the concept of equalization, explaining it as a method for adjusting frequency levels by either boosting or cutting them. It highlights two main applications: first, as a corrective tool to address issues arising from equipment, instruments, acoustics, or microphone placement, and second, for sound enhancement to achieve a desired audio quality. The text then details filters, which are presented as the most basic type of equalizer, specifically designed to remove frequency bands without boosting them. Five distinct types of filters are outlined: low-pass, which permits low frequencies while reducing high ones; high-pass, which allows high frequencies and diminishes low ones; band-pass, which attenuates both low and high frequencies while allowing mid-range frequencies through; band-stop, which lets low and high frequencies pass but attenuates a mid-band region; and finally, the notch filter, described as a very narrow band-stop filter.

Let's dive into the fascinating world of **Equalization** and **Filters**, which are essential tools in sound engineering and audio production!

### **Understanding Equalization**

At its core, **equalization** is all about **adjusting the balance of different sound frequencies** within an audio signal. Think of sound as having a wide spectrum, from very low rumbling sounds to very high piercing sounds. Equalization allows you to either **make certain frequency bands louder (boost them) or quieter (cut them)** relative to other parts of the frequency spectrum.

There are two main reasons why we use equalization:

1.  **As a Corrective Tool**: Sometimes, the sound we capture or create isn't perfect. This could be due to several issues:
    *   **Inadequate Equipment**: The gear you're using might not capture or reproduce sound perfectly evenly across all frequencies. Equalization can help balance this out.
    *   **A Less Than Satisfactory Instrument**: An instrument might naturally have too much of certain frequencies or too little of others. Equalization can help shape its sound.
    *   **Poor Acoustics**: The room where a sound is recorded or played can introduce unwanted resonances or dullness. Equalization can help compensate for these acoustic problems.
    *   **Microphone Positioning**: How a microphone is placed can drastically affect the sound it captures. Equalization can fine-tune the frequency response to get a more desirable sound.
    In essence, it helps to **fix problems** and create a more natural or balanced sound.

2.  **To Enhance the Sound**: Beyond just fixing issues, equalization is also used creatively to **make a sound more appealing or to achieve a specific artistic effect**. You can sculpt the sound to your liking, making it brighter, warmer, punchier, or clearer, depending on what you want to achieve.

### **Understanding Filters**

A **filter** is the **simplest form of an equalizer**. The key characteristic of a filter is that it **always removes (or reduces) bands of frequencies**; it **never boosts** them. Filters are designed to let certain frequencies pass through while attenuating (reducing the level of) others.

There are five principal types of filters, each designed to affect the frequency spectrum in a specific way:

1.  **Low-pass Filter**:
    *   Imagine a gate that only allows low things to pass. A **low-pass filter** does just that for sound frequencies. It allows **low frequencies to pass through relatively unaffected**, but it **reduces the level of (attenuates) high frequencies**.
    *   This is useful for removing harsh high-end noise or making a sound warmer and less bright.

2.  **High-pass Filter**:
    *   Conversely, a **high-pass filter** acts like a gate for high frequencies. It allows **high frequencies to pass through**, while **reducing the level of low frequencies**.
    *   This can be used to remove unwanted low-end rumble, hum, or muddiness from a sound, making it clearer and more defined.

3.  **Band-pass Filter**:
    *   A **band-pass filter** is like having two gates: one for the lows and one for the highs. It **reduces the level of both low and high frequencies**, allowing only a **specific range of "mid" frequencies to pass through**.
    *   This can make a sound seem like it's coming from a telephone or a small speaker, or it can isolate a particular harmonic range of an instrument.

4.  **Band-stop Filter**:
    *   The opposite of a band-pass filter, a **band-stop filter** allows **both low and high frequencies to pass through**, but it **attenuates (reduces the level of) a specific region in the mid-band**.
    *   This is useful for removing an unwanted resonant frequency or a specific unpleasant tone in the middle of the sound spectrum without affecting the extreme lows or highs.

5.  **Notch Filter**:
    *   A **notch filter** is a very specialised type of band-stop filter. What makes it unique is that it's **extremely narrow**, meaning it targets and **removes only a very small, precise range of frequencies**.
    *   This is incredibly useful for surgically removing a specific problematic frequency, such as a persistent hum from electrical equipment, a whistle, or a feedback frequency, without noticeably altering the rest of the sound.
*   

### Digital Audio: EQ & Filters - ASCII Visual Notes

#### What is Equalization?
```
FREQUENCY SPECTRUM (Before EQ)
Low ←────────────────────────────→ High
 ████████████████████████████████████
 │                                  │
Bass          Mids           Treble

AFTER EQUALIZATION (Example)
 ██████████████████████████████████████
 │      ↑               ↓            │
    Boost Bass       Cut Highs
```

##### Two Main Uses of EQ:
```
1. CORRECTIVE TOOL               2. ENHANCEMENT TOOL
   ┌─────────────────┐              ┌─────────────────┐
   │ Fix Problems:   │              │ Creative Shaping:│
   │ • Bad equipment │              │ • Warmer sound  │
   │ • Poor acoustics│              │ • Brighter tone │
   │ • Mic placement │              │ • More punch    │
   │ • Instrument    │              │ • Artistic effect│
   └─────────────────┘              └─────────────────┘
```

---

#### Filter Types (The Building Blocks of EQ)

##### 1. LOW-PASS FILTER
```
Amplitude
    │
    │████████████╲
    │            ╲╲
    │             ╲╲╲
    │              ╲╲╲╲____
    └─────────────────────────→ Frequency
     LOW                  HIGH
    PASS ✓               BLOCKED ✗

Effect: Removes harsh highs, makes sound warmer
```

##### 2. HIGH-PASS FILTER
```
Amplitude
    │
    │           ╱████████████
    │         ╱╱
    │       ╱╱╱
    │_____╱╱╱
    └─────────────────────────→ Frequency
     LOW                  HIGH
   BLOCKED ✗             PASS ✓

Effect: Removes rumble/mud, makes sound clearer
```

##### 3. BAND-PASS FILTER
```
Amplitude
    │
    │      ╱████╲
    │    ╱╱    ╲╲
    │__╱╱      ╲╲____
    └─────────────────────────→ Frequency
     LOW   MID    HIGH
   BLOCKED PASS BLOCKED
      ✗     ✓     ✗

Effect: Sounds like telephone/small speaker
```

##### 4. BAND-STOP FILTER
```
Amplitude
    │
    │████╲    ╱████
    │    ╲╲  ╱╱
    │     ╲╲╱╱
    │      ╲╱
    └─────────────────────────→ Frequency
     LOW   MID    HIGH
    PASS BLOCKED PASS
     ✓     ✗     ✓

Effect: Removes problem frequencies in middle
```

##### 5. NOTCH FILTER
```
Amplitude
    │
    │██████║██████
    │      ║
    │      ║
    │      ║  ← Very narrow cut
    └─────────────────────────→ Frequency
           │
    Specific problem frequency

Effect: Surgically removes exact frequency (hum, whistle)
```

---

#### Filter Comparison Chart
```
FILTER TYPE    │ LOWS │ MIDS │ HIGHS │ USE CASE
───────────────┼──────┼──────┼───────┼─────────────────
Low-pass       │  ✓   │  ~   │   ✗   │ Remove harshness
High-pass      │  ✗   │  ~   │   ✓   │ Remove rumble
Band-pass      │  ✗   │  ✓   │   ✗   │ Isolate midrange
Band-stop      │  ✓   │  ✗   │   ✓   │ Remove resonance
Notch          │  ✓   │  ✗*  │   ✓   │ Remove specific tone
───────────────┴──────┴──────┴───────┴─────────────────
✓ = Pass through    ✗ = Blocked/Reduced    ~ = Partially affected
* = Only very specific narrow band blocked
```

---

#### Key Remember Points
```
┌─────────────────────────────────────────────────┐
│ FILTERS vs FULL EQ:                            │
│                                                │
│ FILTERS: Only CUT/REDUCE frequencies          │
│          Never boost anything                  │
│                                                │
│ FULL EQ:  Can both CUT and BOOST             │
│          More flexible control                │
└─────────────────────────────────────────────────┘
```

---

#### Practical Application Examples
```
SCENARIO: Recording vocals with room hum and harsh sibilants

SOLUTION CHAIN:
Input → [High-pass] → [Notch] → [Low-pass] → Output
        Remove        Remove     Remove
        low rumble    60Hz hum   harsh highs

RESULT: Clean, warm vocal sound!
```