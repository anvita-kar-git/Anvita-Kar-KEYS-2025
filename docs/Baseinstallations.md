# Base installations in a VScode server for smooth sailing code. MCP Installation Guide: File System and Fetch

This guide will walk you through installing and configuring the File System and Fetch MCPs (Model Context Protocols) in VS Code using the Cline extension. These are the 2 basic MCPs all users should have installed in their CyVerse VScode Server, so as to not create more errors while working on any complex project.


### Step 1: Update System and Install Dependencies
Open VS Code Server and open a bash terminal in VS Code (Terminal → New Terminal)

Update your system:
   ```bash
   sudo apt update
   ```
Install Node.js and npm:
   ```bash
   sudo apt install nodejs npm
   ```
Wait for about 30 secs as your system finishes all installations.

### Step 2: Install Cline Extension
<img width="48" alt="image" src="https://github.com/user-attachments/assets/70682bbd-8b92-4398-a46e-96d64c6d8732" />
Go to the Extensions panel in VS Code (Ctrl+Shift+X)

Search for "Cline"

Install the Cline extension

Enter your API key when prompted

### Step 3: Initial Configuration
In the taskbar on top of the cline logo, click the icon that looks like 3 books stacked on top of each other

<img width="253" alt="image" src="https://github.com/user-attachments/assets/471f2efd-b1ce-47a3-ac4c-1fa38df16c90" />

Then go to *Installed* and click the *Configure MCP Servers* button.

Replace all the code in the `cline_mcp_settings.json` with this code from the [official MCP server github repository](https://github.com/modelcontextprotocol/servers). I edited their code after taking the base code from this [README.md](https://github.com/modelcontextprotocol/servers/blob/main/src/filesystem/README.md).

```
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/home/vscode",
        "/config"
      ],
      "disabled": false,
      "autoApprove": [
        "read_file"
      ]
    },
    "github.com/zcaceres/fetch-mcp": {
      "command": "node",
      "args": [
        "/config/Cline/MCP/fetch-mcp/dist/index.js"
      ],
      "disabled": false,
      "autoApprove": []
    }
  }
}

```

### Step 4: Create File path
The code that you copied into your `cline_mcp_settings.json` just now is the completed code for both Filesystem and Fetch to be installed automatically. But since we didn't follow the traditional method of installing both MCPs throught Cline (which takes waaaayy longer), some file paths are missing and have to be manually created.

Enter this code into your bash terminal

   ```bash
   mkdir -p /config/Desktop
   ```

### Step 5: Check if MCPs were installed correctly
To check if you were succesful in taking the shortcut, go to 'Installed' under 'MCP Servers' in cline again.
Both Filesystem and Fetch should show
   - No error messages
   - Green "ON" button indicating it's active

<img width="523" alt="image" src="https://github.com/user-attachments/assets/1c5e3dd4-508e-4d00-9c7c-bc640b74d9e8" />

## If that's what you see then congratulations, you are ready to start any project without base errors. Good Job!



### If instead you see something like this, do not panic. You just have to take the long way around.

![image](https://github.com/user-attachments/assets/8a7ae083-bbab-456a-8cd0-1ae53d7b83d4)

### Step 3: Different Initial Configuration
For this method, you still have to follow the first two steps, but instead of adding the previously mentioned code to your `cline_mcp_settings.json` you will now add this one. This is a basic version of the code directly from the [official MCP server github repository](https://github.com/modelcontextprotocol/servers), and will later be edited by Cline.

```
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/home/vscode",
        "/config"
      ],
      "disabled": false,
      "autoApprove": [
        "read_file"
      ]
    }
  }
}
```

### Step 4: Create File path
This code in your `cline_mcp_settings.json` is the code for only Filesystem's installation since CyVerse VScode pulls its data automatically. Right now only one file path is missing and to account for it we manually add a folder.

Enter this code into your bash terminal

   ```bash
   mkdir -p /config/Desktop
   ```

### Step 5: Checking for File System MCP

To check if you were succesful in installing Filesystem, go to 'Installed' under 'MCP Servers' in cline again.

The Filesystem button should show
   - No error messages
   - Green "ON" button indicating it's active


### Step 6: Install Fetch MCP
Return to the *Marketplace* tab in Cline
Search for and install **Fetch** MCP
During installation:
   - Click **Allow** for all permission requests
   - Ignore any error messages that pop up
   - Allow Cline to manage the installation process

Just wait for the installation to complete

### Step 7: Final Verification
Go to **Installed MCP Servers** one last time
Confirm both MCPs are properly installed:
   - **File System**: Shows green "ON" button, no errors
   - **Fetch**: Shows green "ON" button, no errors

## You have again successfully installed and configured both File System and Fetch MCPs! Your VS Code server is now ready to work smoothly with these Model Context Protocols.

## Troubleshooting Tips

- **Error messages during installation**: These are normal and expected - Cline will resolve them automatically
- **Permission prompts**: Always click "Allow" to ensure proper functionality
- **Installation not showing**: Refresh the Installed MCP Servers tab
- **Services not starting**: Check that the green "ON" button is enabled for both services

# Your development environment is now enhanced with File System and Fetch capabilities through the MCP protocol!
