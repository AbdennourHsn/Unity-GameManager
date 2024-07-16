# Global Game Manager for Unity

This Unity script provides a centralized manager for handling core game lifecycle events, data persistence, audio management, and more. It follows the Singleton pattern to ensure only one instance of the manager exists throughout the game.

## Features

- **Singleton Pattern**: Ensures a single instance of `GlobalGameManager` exists.
- **Persistent Data Management**: Saves and loads game data such as points and coins.
- **Event Management**: Custom events for game lifecycle states (`OnGameStart`, `OnGameComplete`, `OnGameOver`, `OnGamePause`, `OnGameResume`).
- **Scene Management**: Methods to reload the current scene and load specific levels.
- **Game Control Methods**: Methods to start, pause, resume, and end the game.
- **Custom Attributes**: Easily extend the class with custom attributes based on specific game requirements.

## Usage

### Initialization

1. **Ensure a single instance**:
    ```csharp
    private void Awake()
    {
        if (instance != null && instance != this)
        {
            Destroy(gameObject);
            return;
        }
        instance = this;
        DontDestroyOnLoad(gameObject);
        LoadGameData();
    }
    ```

2. **Start the game**:
    ```csharp
    GlobalGameManager.instance.StartGame();
    ```

### Event Management

- **OnGameStart**: Called when the game starts.
- **OnGameComplete**: Called when the game is completed.
- **OnGameOver**: Called when the game is over.
- **OnGamePause**: Called when the game is paused.
- **OnGameResume**: Called when the game resumes.

### Game Control Methods

- **Start the game**:
    ```csharp
    GlobalGameManager.instance.StartGame();
    ```

- **End the game**:
    ```csharp
    GlobalGameManager.instance.GameOver();
    ```

- **Complete the game**:
    ```csharp
    GlobalGameManager.instance.GameComplete();
    ```

- **Pause the game**:
    ```csharp
    GlobalGameManager.instance.PauseGame();
    ```

- **Resume the game**:
    ```csharp
    GlobalGameManager.instance.ResumeGame();
    ```

- **Reload the current scene**:
    ```csharp
    GlobalGameManager.instance.ReloadScene();
    ```

### Data Management

- **Set Points**:
    ```csharp
    GlobalGameManager.instance.SetPoints(int value);
    ```

- **Set Coins**:
    ```csharp
    GlobalGameManager.instance.SetCoins(int value);
    ```

- **Add Coins**:
    ```csharp
    GlobalGameManager.instance.AddCoins(int value);
    ```

### Scene Management

- **Load Level**:
    ```csharp
    GlobalGameManager.instance.LoadLevel(int level);
    ```

### Audio Management

- **Play Sound Effect**:
    ```csharp
    GlobalGameManager.instance.PlaySoundEffect(int index);
    ```

- **Stop Sound Effect**:
    ```csharp
    GlobalGameManager.instance.StopSoundEffect(int index);
    ```

- **Toggle Background Music**:
    ```csharp
    GlobalGameManager.instance.ToggleBackgroundMusic(bool play);
    ```

## Extending the Manager

You can extend the `GlobalGameManager` class with custom attributes and methods as per your game's requirements.

### Example

```csharp
// Custom attributes
public int playerHealth;
public int playerLives;

// Method to decrease player health
public void DecreaseHealth(int amount)
{
    playerHealth -= amount;
    if (playerHealth <= 0)
    {
        GameOver();
    }
}
