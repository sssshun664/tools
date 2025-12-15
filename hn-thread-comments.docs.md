# HN Thread Comments Viewer

A single-file HTML tool for viewing the top 5 comments from specific Hacker News threads.

## Description

This tool allows you to view the best comments from any Hacker News story or discussion thread. Simply enter a thread URL or ID, and it will fetch all comments, rank them by score (points), and display the top 5 in a clean, readable format.

## Features

- **Thread Input**: Supports both HN URLs and direct thread IDs
- **Smart Parsing**: Automatically extracts thread ID from full URLs
- **Recursive Fetching**: Retrieves all comments including nested replies
- **Score-Based Ranking**: Sorts comments by points to show the most valuable contributions
- **Top 5 Display**: Focuses on the highest-quality comments
- **Rich Metadata**: Shows author, score, and posting time for each comment
- **Direct Links**: One-click access to view comments on Hacker News
- **Copy Function**: Easy one-click copying of comment text
- **URL Parameters**: Support for `?id=12345678` for direct linking
- **Mobile Optimized**: Responsive design with good tap targets
- **Clean UI**: Card-based layout with numbered ranking badges

## Technical Details

- **No dependencies**: Pure vanilla JavaScript, HTML, and CSS
- **Single file**: Complete application in under 400 lines
- **API**: HackerNews Official API (Firebase-hosted)
  - `https://hacker-news.firebaseio.com/v0/item/{id}.json`
- **CORS-friendly**: Direct API access without proxy
- **Recursive fetching**: Retrieves nested comments up to 10 levels deep
- **Performance**: Parallel API requests using Promise.all()

## Usage

### Basic Usage

1. Open `hn-thread-comments.html` in any modern web browser
2. Enter a Hacker News thread URL or ID:
   - Full URL: `https://news.ycombinator.com/item?id=12345678`
   - Direct ID: `12345678`
3. Click "Load Thread" or press Enter
4. View the top 5 comments ranked by score

### Direct Linking

You can link directly to a thread by using URL parameters:

```
hn-thread-comments.html?id=12345678
```

This will automatically load the specified thread on page load.

### Finding Thread IDs

Thread IDs can be found in the URL of any Hacker News story or discussion:
- Story: `https://news.ycombinator.com/item?id=39511676`
- The ID is: `39511676`

## How It Works

1. **Input Parsing**: Extracts thread ID from URL or direct input
2. **Thread Fetching**: Retrieves thread metadata (title, author, score)
3. **Comment Fetching**: Recursively fetches all comments and nested replies
4. **Ranking**: Sorts all comments by score (points)
5. **Display**: Shows top 5 comments with full metadata and formatting

## Example Use Cases

- **Research**: Quickly find the most insightful comments on technical discussions
- **Learning**: Identify expert opinions and valuable insights
- **Curation**: Find the best responses to a particular topic
- **Analysis**: Study high-quality contributions to HN threads

## API Reference

This tool uses the official Hacker News API:

- **Item endpoint**: `GET /v0/item/{id}.json`
- **Response fields**:
  - `id`: Item ID
  - `type`: "story", "comment", "poll", etc.
  - `by`: Author username
  - `time`: Unix timestamp
  - `text`: Comment HTML
  - `score`: Points/upvotes
  - `kids`: Array of child comment IDs

## Limitations

- Only shows top 5 comments (by design for focused reading)
- Requires active internet connection (no offline mode)
- Large threads (1000+ comments) may take a few seconds to load
- Dead or deleted comments are filtered out
- Maximum recursion depth of 10 levels for nested comments

## Browser Compatibility

Works in all modern browsers that support:
- ES6+ JavaScript (async/await, arrow functions)
- Fetch API
- CSS Flexbox
- Clipboard API (for copy function)

Tested on:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Android)

## File Information

- **Filename**: `hn-thread-comments.html`
- **Size**: ~14KB
- **Lines**: ~380
- **Created**: 2025-12-15

## References

- [Hacker News Official API](https://github.com/HackerNews/API) - API documentation
- [Hacker News](https://news.ycombinator.com/) - Official Hacker News site

## Development

This tool was created as part of the tools repository following the established template and design guidelines. For implementation details, see the original development discussion.
