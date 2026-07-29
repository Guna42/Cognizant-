# Week 9 (Module 9 & 10) - React SPA & Debugging Hands-on Exercises

This folder contains the solved hands-on exercises for **Module 9: React SPA** and **Module 10: Application Debugging** from the *Digital Nurture 5.0 Deep Skilling Handbook*.

## Developer Details
* **Name:** Guna Byraju
* **Email:** gunavardhan779@gmail.com
* **GitHub Repository:** https://github.com/Guna42/Cognizant-
* **Class:** Java FSE React Deepskilling Cohort

---

## Solved Exercises Included

All mandatory exercises are consolidated into a single premium React application featuring an interactive side navigation dashboard to run, inspect, and evaluate each laboratory exercise:

1. **Exercise 1: My First React (`myfirstreact`)**
   * Sets up a React environment using Vite.
   * Prints `"welcome to the first session of React"` as a main heading.

2. **Exercise 2: Student App (`StudentApp`)**
   * Creates a Student Management Portal.
   * Leverages React Class Components (`Home`, `About`, `Contact`) and renders them together.

3. **Exercise 3: Score Calculator (`scorecalculatorapp`)**
   * Creates a functional component `CalculateScore` accepting props (`Name`, `School`, `total`, `goal`).
   * Calculates the average percentage marks and applies external stylesheet styles (`mystyle.css`).

4. **Exercise 4: Blog App (`blogapp`)**
   * Implements a class component `Posts` using lifecycle hooks (`componentDidMount` and `componentDidCatch`).
   * Fetches blog posts asynchronously from the JSONPlaceholder API using the Fetch API and handles error scenarios via alert alerts.

5. **Exercise 5: Cohort Details (Styling)**
   * Styles the Cognizant Academy Cohorts Dashboard.
   * Uses CSS Modules (`CohortDetails.module.css`) to define styled box classes, tag selector properties, and dynamically colors ongoing cohorts in green and others in blue.

6. **Exercise 9: Cricket App (`cricketapp`)**
   * Implements ES6 features including `.map()` for players and scores, `.filter()` using arrow functions to show players with scores &ge; 70.
   * Uses destructuring to divide odd/even team selectors and merges T20/Ranji arrays using the Spread Operator.
   * Controls display views using state-based Flag toggles.

7. **Exercise 10: Office Space Rental App (`officespacerentalapp`)**
   * Displays office spaces at affordable ranges using JSX elements.
   * Incorporates image elements, displays details of name, rent, and address, and applies conditional inline styles to color Rent in Red (if < 60,000) or Green (if &ge; 60,000).

8. **Exercise 11: Event Examples (`eventexamplesapp`)**
   * Handles various HTML form events in React.
   * Features a Counter (Increment/Decrement) calling multiple methods (incrementing value + alert), argument passing ("Say Welcome" button), and synthetic event details.
   * Contains a Rupees to Euro currency converter sub-component.

9. **Exercise 12: Ticket Booking App (`ticketbookingapp`)**
   * Performs conditional rendering based on authentication state.
   * Shows a list of available flights for Guest view, and a ticket booking submission form for authenticated users.

10. **Exercise 13: Blogger App (`bloggerapp`)**
    * Displays three components: Book Details, Blog Details, and Course Details.
    * Implements them showing 4 different syntax styles of React conditional rendering (Switch case, Element variables, Logical && operator, and Ternary operator).

---

## How to Run & Verify

1. Open the terminal and navigate to the project directory:
   ```bash
   cd Week9_React_Debugging
   ```
2. Install npm dependencies:
   ```bash
   npm install
   ```
3. Run the application locally in development mode:
   ```bash
   npm run dev
   ```
4. Build the application for production:
   ```bash
   npm run build
   ```
