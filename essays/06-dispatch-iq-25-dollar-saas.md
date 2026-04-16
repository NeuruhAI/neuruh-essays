# I Turned a $25 Radio Scanner Into a $985/mo SaaS Business

**The insight:** police and fire radio is a public signal. Anyone can listen. Almost nobody monetizes it.

Roofers, plumbers, tow truck operators, insurance adjusters, restoration crews — the first one to arrive wins the job 80% of the time. A 2-hour head start is the entire business.

## The 7-layer pipeline

```
1. Capture         — Broadcastify Calls API (or RTL-SDR dongle, ~$25)
2. Transcribe      — Deepgram Nova-2
3. Analyze         — Groq llama-3.1-70b (JSON: category + priority + summary)
4. Geocode         — Google Maps
5. Score           — proximity + priority thresholding
6. Alert           — subscriber match (tier → min_priority)
7. Deliver         — Twilio SMS
```

## Unit economics

- **Cost per alert:** under $0.05 (Deepgram + Groq + Twilio combined)
- **Pricing:** $97 / $197 / $397 per month
- **Break-even:** 5 Basic subs = **$985 MRR**

## The pitch

> A roofer who arrives two hours first gets the job 80% of the time. DISPATCH-IQ texts you storm damage, structure fires, and hail events the moment they come over the radio. $97/mo.

## Source

Private repo at `NeuruhAI/neuruh-dispatch-iq`. Happy to white-label it for agencies selling to service contractors.
