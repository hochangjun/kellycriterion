# v0 Prompt for Jackpot Paradox UI

Create a modern, interactive web app UI for a coin flip game that demonstrates the "Jackpot Paradox" - how positive expected value can still lead to ruin.

## Design Requirements:

1. **Hero Section**
   - Title: "The Jackpot Paradox"
   - Subtitle explaining the concept
   - Dark theme with neon accents to give a casino/risk feeling

2. **Game Configuration Panel**
   - Sliders/inputs for:
     - Heads probability (0-100%)
     - Tails probability (auto-calculated to sum to 100%)
     - Heads outcome multiplier (e.g., 2.0x for +100%)
     - Tails outcome multiplier (e.g., 0.4x for -60%)
   - Real-time calculation display showing:
     - Expected value per flip
     - Geometric mean per flip
     - Break-even point (how many heads needed out of 1000 flips)

3. **Interactive Single Player Game**
   - Large coin flip animation (3D coin that spins)
   - Current wealth display with animated number changes
   - Flip button with satisfying hover effects
   - Win/loss streak counter
   - History of last 10 flips as visual chips (green/red)
   - Bankruptcy animation when wealth < $0.01

4. **Simulation Controls**
   - Number of players (slider: 100-25,000)
   - Number of flips (slider: 10-1,000)
   - Betting strategy dropdown:
     - "YOLO Mode" (bet 100%)
     - "Kelly Criterion" (optimal bet sizing)
     - "Conservative" (fixed 25% bets)
   - Large "Run Simulation" button

5. **Results Dashboard**
   - Animated counters for key metrics:
     - Survival rate (% with > $1)
     - Median wealth
     - Mean wealth
     - Jackpot winners (> $1M)
   - Interactive chart showing wealth paths over time
   - Distribution histogram of final wealths
   - Toggle between linear and log scale

6. **Educational Section**
   - Tabs explaining:
     - The math behind the paradox
     - Real-world applications
     - Wealth preference types (log, linear, exponential)
   - Interactive examples showing different betting strategies

## Visual Style:
- Dark background (#0a0a0a) with neon accents
- Green (#00ff88) for wins, Red (#ff0044) for losses
- Smooth animations and transitions
- Mobile-responsive design
- Use Framer Motion for animations
- Chart.js or Recharts for visualizations
- Modern typography (Inter or similar)

## Key Interactions:
- Hovering over math formulas shows explanations
- Clicking on wealth paths highlights that player's journey
- Dragging sliders shows real-time EV calculations
- Sound effects for coin flips (optional toggle)

Make it feel like a high-stakes casino game while being educational. The UI should make users want to keep flipping while learning why they shouldn't.