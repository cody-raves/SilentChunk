# SilentChunk

SilentChunk is a lightweight Skript designed to optimize server performance by automatically managing Chunky generation based on player activity. When the first player joins the server, SilentChunk pauses Chunky generation, and when no players remain online, it resumes generation. This smart automation helps conserve server resources and ensures smoother gameplay.

## Features

- **Automatic Chunk Management**
  - **Pause Generation:**  
    When the first player joins, SilentChunk broadcasts a message, waits a configurable amount of time, and then executes the `/chunky pause` command to stop chunk generation.
  - **Resume Generation:**  
    When the last player leaves, after a short delay, the script executes the `/chunky continue` command to resume chunk generation.

- **Customizable Timing:**  
  Adjust the wait times for pausing and resuming generation to suit your server's needs.

- **Simple Setup:**  
  Just drop the Skript into your Skript folder, and SilentChunk will start managing Chunky generation based on player join/quit events.

## How It Works

SilentChunk listens for player join and quit events:

- **On Join:**  
  When a player joins and becomes the only player online, the script:
  1. Broadcasts a message indicating that Chunky generation will be paused.
  2. Waits for a set duration (e.g., 20 seconds).
  3. Re-checks if there is still only one player online.
  4. Executes `/chunky pause` to pause chunk generation and notifies players via broadcast.

- **On Quit:**  
  When a player quits, the script waits for a short period (e.g., 10 seconds) and checks if no players are online. If true, it:
  1. Broadcasts a message indicating that Chunky generation will be resumed.
  2. Executes `/chunky continue` to resume chunk generation.
  3. Broadcasts a confirmation that generation has resumed.

## Requirements

- A Minecraft server running a compatible version.
- The [Chunky plugin](https://www.spigotmc.org/resources/chunky.12345/) (or a similar plugin) installed and configured.
- The [Skript plugin](https://github.com/SkriptLang/Skript) installed on your server.

## Installation

1. Download the SilentChunk Skript file.
2. Place the file into your server's `plugins/Skript/scripts/` folder.
3. Reload Skript using the command:
