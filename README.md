#GlobalGameManager Script
The GlobalGameManager script is a versatile and reusable component designed to manage the core lifecycle and state of a game in Unity. This script acts as a singleton, ensuring that only one instance exists across all scenes, providing centralized control over game states, data persistence, audio management, and more.

#Features
Singleton Pattern: Ensures a single instance of the GlobalGameManager exists, making it accessible globally across all scenes.
Persistent Data Management: Saves and loads essential game data such as points and coins to/from persistent storage using PlayerPrefs.
Event Management: Custom events for game lifecycle states (OnGameStart, OnGameComplete, OnGameOver, OnGamePause, OnGameResume) allowing for easy subscription and invocation.
Scene Management: Includes methods to reload the current scene and load specific levels while preserving player progress.
Game Control Methods: Methods to start, pause, resume, and end the game, managing the game's time scale and invoking corresponding events.
