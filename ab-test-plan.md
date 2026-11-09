# A/B Test Plan: Haven Pilates Studio

## 1. Page and Element Changes
* **Page:** Haven Pilates Studio Home (`https://fbahwell.github.io/form-flow-pilates/`)
* **Element:** The primary hero section Call-to-Action (CTA) button.
* **Control (A):** Button text reads `"Explore beginner Pilates"`.
* **Variant (B):** Button text reads `"Start Your Free Routine"`.

## 2. Hypothesis and Reasoning
* **Hypothesis:** Changing the hero CTA button from a passive exploratory phrase ("Explore beginner Pilates") to an action-oriented, benefit-driven phrase ("Start Your Free Routine") will increase simulated user conversion intent. This prediction could turn out wrong if users feel pressured or skeptical by "Free" text on a simple static concept page, preferring low-pressure exploration instead.
* **Reasoning:** Fitness consumers, especially beginners looking for home workouts, respond better to direct, low-friction commitments that tell them exactly what action comes next.

## 3. Model, Persona, Prompt, and Assignment
* **Model:** `gpt-4o` (or specify your chosen LLM)
* **Persona:** "A 32-year-old desk worker who sits all day, feels stiff, and is looking for a gentle, approachable home fitness routine that requires zero equipment and minimal intimidation."
* **Exact Prompt:** 
  > "You are [Persona Description]. You have landed on the Haven Pilates Studio website. You see a hero button offering: '[INSERT BUTTON TEXT A OR B]'. On a scale of 1 to 5 (where 1 is completely uninterested and 5 is immediately ready to click and commit), how likely are you to click this button and engage with the routine? Output your score followed by a one-sentence rationale."
* **Assignment Mechanism:** Trial assignment is handled pseudo-randomly using a 50/50 split (e.g., using a hash of the trial ID or Python's `random.choice(['A', 'B'])`).

## 4. Primary Outcome and Measurement
* **Primary Outcome:** Simulated user intent score (ranging from 1 to 5).
* **How it is Measured:** The numerical score parsed from the LLM persona's response during each automated trial run.

## 5. Sample Size and Timeline
* **Sample Size:** $N = 100$ total trials ($50$ trials for Control A, $50$ trials for Variant B).
* **Expected Completion Date:** November 9, 2026.

## 6. Comparison and Success Criteria
* **Comparison:** We will compare the mean intent score of Variant B against Control A using an independent two-sample t-test.
* **Support for Hypothesis:** If Variant B yields a statistically significantly higher mean intent score ($p < 0.05$) than Control A, it will count as support for the hypothesis.
