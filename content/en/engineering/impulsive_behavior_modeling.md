---
title: "Impulse in the Clickstream -Behavioral Insights from Browsing History"
date: 2025-11-19
draft: false
description: "An empirical study of impulsive clicking behavior using real-world browser history data to enable adaptive, behavior-aware cybersecurity defenses."
featured_image: "/images/research_images/impulsive_modeling.png"
tags: ["cybersecurity", "user-behavior-analytics", "phishing", "browser-telemetry", "adaptive-security"]
---

### 🚩 Can we detect risky user behavior before a phishing attack succeeds?  
This paper tackles a fundamental but often overlooked problem in modern AI pipelines: annotation errors and their cascading impact on model training, evaluation, and human-in-the-loop data cleaning systems.    
In this research, we introduce a behavioral framework to detect and quantify impulsive clicks at the session level, revealing when users are momentarily vulnerable and how that vulnerability evolves across browsing contexts.

### 📄 Work Overview <a href="https://doi.org/10.1145/3719027.3760725" target="_blank" rel="noopener">🔗</a>
**Venue**: ACM CCS 2025  
**Focus**: User behavior modeling, phishing susceptibility, adaptive security

Phishing attacks continue to succeed not because of missing technical defenses, but because attackers exploit human cognitive vulnerabilities. Among these, impulsivity plays a critical role—yet it has been poorly operationalized in real-world systems.  
This paper bridges that gap by showing how browser interaction data alone can surface actionable impulsivity signals.

### 🎯 The Core Idea
Instead of treating impulsivity as a fixed personality trait, this work demonstrates that:  
> Impulsive clicking is transient, session-dependent, and context-driven.  

By shifting the unit of analysis from users to browsing sessions, we can detect short-lived periods of elevated risk—precisely when adaptive defenses matter most.
This tool represents a significant advancement in construction technology, combining several cutting-edge features:

### 🧠 Behavioral Modeling Framework  
The proposed framework models impulsivity using fine-grained browser telemetry, structured into three stages:
1. **Session-Level Behavioral Signals**  
   Browsing activity is segmented into sessions based on inactivity gaps. Within each session, multiple dimensions of behavior are captured:
   - **Engagement Duration**: How long users actively attend to pages
   - **Navigation Intent**: Typed vs. link-based transitions
   - **Tab & Window Churn**: Frequency of context switching
   - **Website Familiarity**: Prior exposure to domains and pages
   - **Topical Diversity**: Breadth of browsing intent via cluster entropy

   These signals move beyond raw clicks to reflect attention, deliberation, and cognitive load.

2. **Composite Impulsivity Scoring**  
   A composite impulsivity score integrates multiple normalized indicators:  
   Higher impulsivity when:
   - Engagement time is short
   - Clicking is link-driven rather than intentional
   - Tab/window switching is frequent

   Sessions above a high-percentile threshold are flagged as **impulsive sessions**, rather than labeling users as impulsive.

3. **Behavioral Session Profiles**  
   Impulsive and non-impulsive sessions are further categorized into interpretable behavioral profiles:
   - **Risky Impulsive**: High impulsivity + low site familiarity
   - **Deliberate Impulsive**: High impulsivity + familiar contexts
   - **Exploratory**: Moderate impulsivity + unfamiliar domains
   - **Focused Non-Impulsive**: Low impulsivity + narrow topics
   - **Distracted Non-Impulsive**: Low impulsivity + high entropy

This profiling reveals how and why impulsivity manifests, not just that it exists.

### 📊 Key Findings

🔹 **Impulsivity Is Situational**  
Users frequently alternate between impulsive and deliberate sessions. Even the same user can exhibit:
   - Highly impulsive behavior late at night or during task overload
   - Focused, low-risk behavior during goal-driven work

🔹 **Context Switching Is a Major Risk Signal**  
High impulsivity correlates strongly with:
   - Frequent tab/window switching
   - Authentication and email workflows
   - Security- and credential-related pages
These moments create attack windows where phishing links are more likely to succeed.

🔹 **Impulsivity ≠ Exploration**  
High topical diversity does not necessarily imply impulsivity. Some users explore broadly but deliberately, highlighting the need to model entropy and impulsivity separately.

### 🛡️ Implications for Adaptive Cybersecurity

This research enables a shift from static defenses to **behavior-aware security controls**, such as:
- Context-sensitive URL reputation checks
- Step-up authentication during impulsive sessions
- Dynamic friction when impulsive patterns intersect with sensitive workflows
- Personalized security nudges based on session state, not user stereotypes
- Rather than blocking users, defenses can **adapt to momentary vulnerability**.

### 🧩 Conclusion

This work demonstrates that browser history is not just a log; it is a behavioral sensor. By modeling impulsive clicking as a dynamic, session-level phenomenon, we open the door to more precise, humane, and effective cybersecurity defenses.

If you're interested in user behavior analytics, phishing resilience, or adaptive security systems, this paper offers both methodological insights and practical implications.