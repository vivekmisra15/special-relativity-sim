# 🧠 AI Prompt Engineering

This simulation was built using a series of detailed architectural prompts with AI (Claude and Gemini). Rather than asking for the entire simulation at once, the project was guided by setting strict physics constraints, building a state machine, and explicitly designing the visual solutions.

Below are the 3 key structural prompts used to generate the core engine and learning flow. There were iterative modifications in the prompting process.

## 1. The Genesis Prompt (Claude)
*This was the initial zero-shot prompt used to generate the foundation of the project. It established the core visual metaphor (Einstein's train), the strict physics requirement (0.999c), and the HTML5 Canvas technical stack.*

> **Prompt:** "I want to build an interactive HTML5 Canvas simulation demonstrating Einstein's Special Relativity, specifically Time Dilation and Length Contraction. 
>
> **Technical Stack:** A single file containing HTML, CSS, and Vanilla JavaScript. No external libraries. Clean, modern, high-contrast UI.
> 
> **The Setup:** > * Create a scene with two observers. Observer 1 is standing perfectly still on the ground. Observer 2 is standing at the rear of a very long train. 
> * The train is moving at v = 0.999c. 
> * There is a lamp at the very front of the train. The lamp will fire a beam of light backward toward Observer 2.
>
> **The UI:**
> Include two large digital clocks on the screen. One represents Observer 1's time (ground frame), and the other represents Observer 2's time (train frame). The clocks must update live based on the Lorentz factor (γ) for 0.999c. 
>
> **The Execution:**
> Build a Javascript state machine (`requestAnimationFrame`) to animate the train moving right, and the light beam moving left. Do not fake the math—calculate the pixel positions dynamically based on the exact time dilation and length contraction formulas."

## 2. The Master Architecture & Physics Prompt (Gemini)
*This prompt was used to establish the visual aesthetic, the strict mathematical constraints (origin synchronization), and the phase-based tutorial state machine.*

> **Prompt:** "You are an expert physics educator and senior frontend developer. We are building an interactive Special Relativity HTML5/JS/CSS animation. 
> 
> **1. What Stays the Same (CRITICAL):**
> * **The Design & Aesthetics:** Keep the CSS for the background, train, observers, stopwatches, and overall styling.
> * **The Physics & Math:** Keep all existing relativistic calculations exactly the same (Lorentz factor γ ≈ 22.37 for v = 0.999c). The time dilation formula t' = t / γ remains. 
> 
> **2. The Physical Setup & Scale:**
> * **Origin Synchronization (x=0, t=0):** At the start of the simulation, Observer 1 (on the ground) and Observer 2 (at the rear of the train) must be stationed at the exact same horizontal position. The lamp fires at this exact millisecond.
> * **The Distance Brackets:** Add dynamic "CAD-style" dimension brackets to the canvas. The train gets a fixed bracket showing its rest length. The ground gets a dynamic bracket that tracks the light's travel from the emission point to the impact point.
> 
> **3. The Interactive Sequence (State Machine):**
> Implement a guided narrative sequence with the following phases using centered pop-up modals during auto-pauses:
> * **Phase 1: Length Contraction** (Paused before movement). Explain what Observer 1 sees vs Observer 2.
> * **Phase 2: The Race** (Slow-motion). The light fires left at 1c, train moves right at 0.999c.
> * **Phase 3: The Conclusion & Math** (Auto-pause on impact). Provide the exact math calculation in an accordion UI.
> * **Phase 4: Free Play Mode**. Reveal standard Play/Pause/Reset controls."

## 3. The Scale & "Circular Math" Correction Prompt
*Early versions used a 1000 light-hour train, which created a confusing numerical coincidence (Lorentz factor = 22.37, Final time = 22.36 hours). This prompt broke that coincidence.*

> **Prompt:** "In Phase 1, the contracted length is calculated as: `1000 lh / 22.37 = 44.7 lh`. But then we use 44.7 lh to calculate the time as 22.36 hours. This is not self-explanatory at all; it looks like a circular reference because the Lorentz factor and the Final Time are almost the exact same number. 
> 
> Let's change the scale to break the coincidence. Change the train length to **200 light-hours**. Update the physics engine so the numbers cascade cleanly:
> * Warp Factor = 22.37
> * Contracted Length = 200 / 22.37 = 8.94 lh
> * Time to Impact = 8.94 / 1.999c = 4.47 hours. 
> Now the numbers are distinct and the math progression is clear to the user."