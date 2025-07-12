# Background and Motivation

The user wants to create a web app that illustrates concepts from the article 'The Jackpot Age' and introduces the Kelly Criterion. The app should allow users to adjust bet sizes in a coin flip simulation and visualize the net PNL over time through graphs/charts to demonstrate the importance of proper bet sizing.

Key elements from the article:
- Coin flip game: 50% chance +100% gain, 50% chance -60% loss on net worth.
- Positive arithmetic mean but negative geometric mean leading to likely ruin.
- Wealth preferences: log (risk-averse), linear, exponential (risk-seeking).
- Jackpot Paradox: Chasing high EV but rare jackpots often leads to zero.

The app will simulate multiple paths of coin flips with variable bet sizes, showing how different sizing (including Kelly optimal) affects long-term outcomes. This will visually teach why log wealth maximization (Kelly) is superior for compounded returns.

# Key Challenges and Analysis

## Mandatory Data Inventory (Before Any Solution)
1. List ALL existing data structures/tables/collections in the system: None - this is a new empty project.
2. For each data structure, write what data it contains: N/A.
3. What data do I already have that relates to this problem? None, as the project is starting from scratch.
4. Can I solve this by combining/querying existing data differently? No, we need to build the simulation and UI from the ground up.
5. If database exists and problem is about duplicates/persistence: No database exists yet; the problem is about simulation visualization, not persistence initially. If needed for user data, we can add later, but keep simple.

## Required Format Before Solution
1. **EXISTING DATA CHECK**: "No, there is no existing system or data; this is a new web app."
2. **5-MINUTE FIX**: "If I had 5 minutes, I would sketch a simple HTML page with JavaScript to run a basic coin flip simulation and plot a line chart using a library like Chart.js."
3. **DUMBEST SOLUTION**: "The most boring/obvious approach is to create a static web page that runs Monte Carlo simulations in the browser based on user-input bet size and displays the results in a chart."
4. **BASIC OPERATION**: "This is just a simple JavaScript simulation with user inputs and chart rendering."

## Key Challenges
- Simulating multiple paths of coin flips accurately, handling multiplicative returns.
- Implementing Kelly Criterion calculation for optimal bet size.
- Visualizing multiple simulation paths (e.g., wealth over flips) in an interactive chart.
- Ensuring the app is educational: Explain concepts, show arithmetic vs geometric means.
- Keep it simple: Client-side only, no backend unless necessary.
- Potential integration: Consider if it should be a Farcaster mini app given the rules, but user specified web app - confirm with user if needed.
- Performance: Running many simulations in browser without lag.

## Analysis
The core is a Monte Carlo simulation:
- Parameters: Initial wealth (e.g., 1), number of flips, number of paths, bet fraction (user adjustable), win prob=0.5, win multiplier=2 (100% gain), loss multiplier=0.4 (-60% loss).
- For each path, simulate flips, update wealth multiplicatively.
- Compute stats: Arithmetic mean, geometric mean, median outcome.
- Kelly fraction for this bet: f = (p*(b+1) - 1)/b, where p=0.5, b=1 (odds), but adjust for asymmetric.
- For asymmetric: Kelly f = (p*gain - q*loss)/(gain*loss), but research exact formula.
- Use Chart.js for visualization.
- Framework: Simple React app for interactivity.
- No database needed; all client-side.

# High-level Task Breakdown

Breakdown into small tasks with success criteria:

1. Set up project structure: Initialize a basic React app with Vite or Create React App.
   - Success: App runs locally with 'npm run dev', shows hello world page.

2. Implement core simulation function: Write a JS function to run one path of coin flips.
   - Success: Unit test passes for a fixed seed, wealth matches expected multiplicative calculation.

3. Add Monte Carlo wrapper: Function to run multiple paths.
   - Success: Test generates array of paths, computes correct mean/median/geometric mean.

4. Integrate Kelly Criterion calculation.
   - Success: Function returns correct optimal fraction (for this bet, Kelly f=0.25 or calculate properly).

5. Create UI components: Inputs for bet size, num flips, num paths; button to run sim.
   - Success: Form renders, values update state.

6. Integrate chart: Use Chart.js to plot wealth paths, means.
   - Success: Chart displays after simulation, shows multiple lines.

7. Add explanations: Text sections explaining concepts from article.
   - Success: Content matches article key points, readable.

8. Style and polish: Basic CSS for usability.
   - Success: App looks clean, responsive.

9. Deploy: To Vercel or similar.
   - Success: Live URL works.

Confirm with user before proceeding to Executor mode.

# Project Status Board

- [ ] 1. Set up project structure
- [ ] 2. Implement core simulation function
- [ ] 3. Add Monte Carlo wrapper
- [ ] 4. Integrate Kelly Criterion calculation
- [ ] 5. Create UI components
- [ ] 6. Integrate chart
- [ ] 7. Add explanations
- [ ] 8. Style and polish
- [ ] 9. Deploy

# Executor's Feedback or Assistance Requests

(None yet)

# Lessons

(None yet) 