# AI Chat Open External (IntelliJ IDEA Plugin)

`idea-plugin-aichat-openextern` is an IntelliJ IDEA plugin designed to quickly and seamlessly open the Markdown transcript (`transcript.md`) of the currently visible or most recent AI chat in an external editor (e.g., **Typora**, **VS Code**, **Obsidian**, **Neovim**). It also supports optional cleanup or filtering of the content.

## Overview and User Perspective

### Problem and Benefits

Documenting or further processing long chat histories within an IDE’s built-in AI chat can be cumbersome, as standard UI copy functions typically only capture individual responses. However, the IDE stores complete Markdown transcripts of all sessions at `~/.junie/sessions/<session_id>/transcript.md`.

This plugin bridges that gap: with a single click or keyboard shortcut, it identifies the transcript for the currently focused chat tab and opens it directly in your preferred external application.

### Key Features

- **Active Chat Detection:** Identifies the title of the chat tab currently open in the editor and maps it to the corresponding session ID via `~/.junie/sessions/index.jsonl`. 

    > [!note]
    >
    > Currently, detection of the specific chat being viewed only works if the chat is open within an editor tab. If you are using only the "AI Chat View" panel, this is not possible; in such cases, the most recent chat will be opened instead.

- **Automatic Fallback:** If no specific chat tab is in focus, the plugin automatically opens the most recent transcript for the current project.

- **Configurable External Application:** You can easily specify the name or path of your preferred external application within the IDE settings (default: `typora`).

- **Menu integration:** Available in the `Tools` menu.

## Configuration in the IDE

1. Open the IDE settings via `File -> Settings` (on macOS: `IntelliJ IDEA -> Settings`) or by pressing `Ctrl+Alt+S`.
2. Go to **Tools -> AI Chat Open External**.
3. In the **External Program (binary or path)** field, enter the desired command:

   - `typora` (default)

   - `code` (for Visual Studio Code)

   - or the absolute path, e.g., `/usr/bin/typora` or `/opt/typora/Typora`
4. Click **Apply** or **OK**.
