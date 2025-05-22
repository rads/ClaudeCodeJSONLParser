# Claude Code JSONL Log Viewer with Git Integration

A comprehensive HTML tool for viewing and analyzing Claude Code JSONL log files alongside Git repository history in a human-readable, chronological timeline.

NB: This was made with heavy help from ChatGPT o3 and Claude 4 Sonnet and should not be relied on in any way.

## Features

- **JSONL Log Parsing**: View Claude Code conversation logs in an organized, collapsible format
- **Git Repository Integration**: Upload and analyze Git repositories to see commits interleaved with log entries
- **Chronological Timeline**: When both logs and Git repo are loaded, displays a combined timeline sorted by timestamp
- **Detailed Git Analysis**: Shows file changes, additions, deletions, modifications with line counts and diffs
- **Interactive UI**: Collapsible sections, expandable details, and raw JSON viewing
- **Visual Design**: Modern, gradient-based design with color-coded message types

## Usage

### Basic Log Viewing
1. Open `combined-log-viewer.html` in your web browser
2. Click "Choose File" under "Upload Log File" and select your Claude Code JSONL log file
   - Usually found in `~/.claude/projects/[project-name]/[session-id].jsonl`
   - You can concatenate multiple session files for comprehensive viewing
3. Navigate through sessions using the Table of Contents
4. Click on session headers to expand/collapse
5. Use "Show actions" on user messages to view assistant responses and tool calls
6. Use "Raw JSON" to see the original log data for any entry

### Git Repository Integration
1. Click "Choose Directory" under "Upload Git Repository (Optional)"
2. Select a Git repository folder (must contain `.git` directory)
3. The tool will analyze all commits and calculate:
   - Files added, modified, and deleted per commit
   - Line changes (additions and deletions)
   - Change percentage relative to total repository size
   - Basic text diffs for modified files
4. View detailed changes by clicking "Details" on any commit

### Combined Timeline View
When both a log file and Git repository are loaded:
- All entries are merged into a single "Combined Log and Git Timeline"
- Events are sorted chronologically, showing code changes alongside conversations
- Perfect for understanding how your codebase evolved during development sessions

## Message Types

- **Blue (Primary)**: User messages
- **Purple**: Assistant responses
- **Light Purple**: Assistant tool calls
- **Orange/Yellow**: Tool results and actions
- **Gray**: Session summaries and metadata
- **Green**: Git commits with change statistics

## Change Indicators

Git commits show color-coded change percentages:
- **Green badge**: Low change impact (< 20%)
- **Yellow badge**: Medium change impact (20-50%)
- **Red badge**: High change impact (> 50%)

## Browser Compatibility

- **Full support**: Chrome 86+, Edge 86+ (supports directory picker API)
- **Partial support**: Other modern browsers (manual file selection for directories)

## Technical Details

- Uses isomorphic-git for Git repository analysis
- Uses LightningFS for in-browser filesystem operations
- Calculates simple text diffs for file modifications
- Supports both File System Access API and legacy webkitdirectory

## File Support

- **Log files**: `.jsonl`, `.log`, `.txt` containing JSON Lines format
- **Git repositories**: Any valid Git repository with `.git` directory

---
