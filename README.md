# Kadomaru Frenzy - Card Clicker Game

Kadomaru Frenzy is a fast-paced and engaging web-based game where players test their speed and accuracy by clicking the corners of appearing cards. The game features various card types, increasing difficulty with levels, and several customization options to enhance the player experience. This project is based on the `redesign.html` file, which includes updated visuals and features.

## Gameplay Mechanics

The core objective of Kadomaru Frenzy is to "complete" cards by clicking all four of their corners before they expire.

*   **Playing the Game**:
    *   Cards appear at random positions within the game area.
    *   Players must click on each of the four corners of a card. Each successful click on a corner visually "rounds" that corner of the card.
    *   Once all four corners are clicked, the card is considered "completed," and points are awarded.

*   **Card Types**:
    *   **Regular Cards**: Standard cards that appear. Completing them awards points. If a regular card expires before being completed, the player loses a life.
    *   **Special Cards**: These cards have a distinct glow and appear occasionally (one per regular level, 30% chance). Completing them awards bonus points (3 points). If a special card expires, the player loses 6 points but does not lose a life.
    *   **Boss Cards**: Every 3rd level is a Boss Level. A single, larger, moving Boss Card appears.
        *   Each corner of a Boss Card requires multiple clicks (currently `BOSS_CLICKS_PER_CORNER = 2` clicks).
        *   Each click on a boss card corner awards 1 point.
        *   Successfully completing a Boss Card awards a significant point bonus (`BOSS_COMPLETION_BONUS = 10` points) and grants additional lives based on the current boss level tier (e.g., `lives += Math.floor(level / 3)`).
        *   If a Boss Card expires, the player loses points (`BOSS_EXPIRATION_PENALTY = 10` points) and one life.

*   **Scoring**:
    *   Players earn 1 point for each successfully clicked corner on any card.
    *   Bonus points are awarded for completing Special Cards and Boss Cards as described above.
    *   **Streak Bonus**: Completing 4 regular cards consecutively (a streak) awards an additional 5 bonus points. Losing a life or a special card expiring resets the streak.

*   **Lives**:
    *   Players start with 10 lives.
    *   A life is lost if a regular card expires before being completed or if a Boss Card expires.
    *   Losing all lives results in a "Game Over."

*   **Level Progression**:
    *   Levels advance automatically after a set duration (`LEVEL_DURATION = 10 seconds`).
    *   With each regular level, the game's difficulty increases: cards spawn more frequently (`currentSpawnDelay` decreases) and their on-screen lifetime (`cardLifetime`) becomes shorter.
    *   Boss levels pause the regular level timer and card spawning. Defeating the boss or having it expire will advance to the next regular level.

*   **Level 10 Mastery & Continuation**:
    *   Upon completing Level 10, the game pauses to celebrate the player's "mastery."
    *   Players are then given the option to "Continue Game," starting from Level 11 with their current score and lives, facing progressively harder challenges.

## Key Features

Kadomaru Frenzy offers a variety of features to create an enjoyable and customizable gaming experience:

*   **Dynamic Game Titles**: The game title changes randomly on each load from a predefined list (e.g., "Round Rush," "Corner Cruncher," "Kadomaru Frenzy"), adding a fresh touch each time you play.
*   **Custom Card Backgrounds**: Players can upload their own images (up to 10) to be used as backgrounds for the cards. If no images are uploaded, cards will have vibrant, randomly selected solid colors (in `redesign.html`).
*   **Sound Effects**: Engaging sound effects, powered by Tone.js, provide auditory feedback for actions like clicking corners, completing cards, leveling up, losing a life, and game over. A toggle switch allows players to enable or disable sounds.
*   **Switchable Themes**:
    *   **Dark Mode ("Lava Lamp")**: A cool, immersive theme with deep indigo and purple hues, accented by vibrant corals and oranges. (Default theme)
    *   **Light Mode ("Citrus Splash")**: A bright and energetic theme featuring pale yellows, peaches, and whites, with pops of orange and green.
    *   A toggle switch allows players to easily switch between themes.
*   **High Score Persistence**: The game saves the player's highest score locally in the browser (using localStorage), so you can compete against your personal best.
*   **Responsive Design**: The game interface is designed to be responsive and playable across different screen sizes, from desktops to mobile devices.
*   **Mobile-Specific Enhancements**:
    *   **Collapsible Stats Panel**: On mobile and tablet devices, the game statistics panel can be toggled (shown/hidden) to maximize screen space for gameplay.
*   **Developer Feature - Start Level Input**:
    *   A hidden input field allows developers or testers to start the game from a specific level.
    *   **How to Toggle**: Triple-click the main game title rapidly to reveal or hide this input field within the stats panel.

## Visual Themes

The game offers two distinct visual themes, allowing players to choose their preferred aesthetic:

*   **"Lava Lamp" (Dark Mode - Default)**:
    *   This theme provides an immersive experience with a darker palette. It features deep indigos (`#1c1c2e`) and purple-blues (`#2a2a45`) for backgrounds, complemented by light lavender (`#f0f0ff`) and soft violet (`#c0c0e0`) text.
    *   Accents are provided by vibrant coral (`#ff6b6b`) for titles and highlights, and bright orange (`#ff9f43`) for primary UI elements, creating a visually engaging "lava lamp" feel.

*   **"Citrus Splash" (Light Mode)**:
    *   This theme offers a bright, clean, and energetic look. Backgrounds use pale yellow (`#fef9e7`) and white (`#ffffff`), with text in dark (`#3d2c24`) and medium browns (`#7a5c4f`).
    *   Bright orange (`#fa8231`) and vibrant green (`#20bf6b`) are used for accents and UI elements, giving it a refreshing "citrus splash" vibe.

Players can easily switch between these themes using the theme toggle switch located in the stats panel.

## How to Run the Game

This game is built with HTML, CSS, and JavaScript and can be run directly in a modern web browser.

1.  **Ensure you have the game files**:
    *   If you've downloaded the project as a ZIP, extract it to a folder on your computer.
    *   If you've cloned the repository, navigate to the project directory.
2.  **Open `redesign.html`**:
    *   Locate the `redesign.html` file in the project folder.
    *   Double-click the file, or right-click and choose "Open with" your preferred web browser (e.g., Chrome, Firefox, Safari, Edge).
3.  **Start Playing**:
    *   The game should load in your browser. Click the "Start Game" button on the overlay to begin!

## Technologies Used

*   **HTML5**: For the basic structure and content of the game.
*   **CSS3**: For styling the game, including the visual themes and responsive design.
    *   **Tailwind CSS**: Utilized for utility classes to speed up the styling process, though much of the core styling is custom CSS within the `<style>` tags in `redesign.html`.
*   **JavaScript (ES6+)**: For all game logic, interactivity, DOM manipulation, and managing game state.
*   **Tone.js**: A Web Audio framework used to create and manage the sound effects in the game.
*   **Google Fonts**: For importing the "Fredoka One" and "Poppins" fonts used in the `redesign.html` version.
*   **Local Storage**: Used by the browser to persist the high score and user preferences for sound and theme.

## Possible Future Enhancements

*   **Activate Social Media Links**: The game interface includes placeholders for social media icons. These could be linked to actual social media profiles or share functionality.
*   **More Card Types/Mechanics**: Introduce new card types with different behaviors or scoring rules to add more variety.
*   **Power-ups**: Implement temporary power-ups that players can collect (e.g., slow down time, auto-complete a card, score multiplier).
*   **Online Leaderboard**: Instead of just local high scores, implement a global leaderboard.
