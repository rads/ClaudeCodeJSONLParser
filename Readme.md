# JSONL Log Viewer

A simple HTML tool for viewing and analyzing Claude Code JSONL log files in a human-readable format.

## Usage

1. Open `log_viewer.html` in your web browser
2. Click "Choose File" and select your Claude Code JSONL log file (usually in ~.claude/projects/ and then choose the appropriate project and whichever session you want to look at -- or make a file that is a concatenation of all sessions)
3. Navigate through sessions using the Table of Contents
4. Click on session headers to expand/collapse
5. Use "Show actions" to view assistant responses and tool calls
6. Use "Raw JSON" to see the original log data

## Message Types

- **Blue**: User messages
- **Green**: Assistant responses
- **Light Green**: Assistant tool calls
- **Orange**: Tool results
- **Gray**: Session summaries
- **Red**: Special actions (like continuation markers)

## File Support

Supports `.jsonl` files containing JSON Lines format logs from Claude Code.

---