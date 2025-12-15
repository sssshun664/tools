# HN Best Comments Viewer

A single-file HTML tool for viewing and sorting the best comments from Hacker News.

## Description

This tool fetches and displays the best-rated comments from Hacker News using the hnrss.org RSS feed. It provides a clean, mobile-friendly interface for browsing top comments with features like auto-refresh, sorting, and easy copying.

## Features

- **Real-time Updates**: Auto-refresh every 5 minutes with countdown timer
- **Flexible Sorting**: Toggle between newest-first and oldest-first views
- **Easy Copying**: One-click copy button for each comment
- **Direct Links**: Click any comment to open the original HN thread
- **Offline Support**: Comments cached in localStorage for offline viewing
- **Mobile Optimized**: Responsive design with good tap targets
- **Clean UI**: Card-based layout with HN's signature orange (#ff6600) accent
- **Metadata Display**: Shows author, points, and relative timestamps
- **Error Handling**: Graceful fallback to cached data if fetch fails

## Technical Details

- **No dependencies**: Pure vanilla JavaScript, HTML, and CSS
- **Single file**: Complete application in under 400 lines
- **RSS Source**: https://hnrss.org/bestcomments
- **Storage**: Uses localStorage for caching and persistence
- **CORS-friendly**: Works with the CORS-enabled hnrss.org API

## Usage

Simply open `hn-best-comments.html` in any modern web browser. No server or build process required.

## References

- [hnrss.org Documentation](https://hnrss.org/) - RSS feeds for Hacker News
- [Hacker News](https://news.ycombinator.com/) - Official Hacker News site

## Development

This tool was created as part of the tools repository. For implementation details and conversation history, see the original development discussion.

## File Information

- **Filename**: `hn-best-comments.html`
- **Size**: ~10KB
- **Lines**: 361
- **Created**: 2025-12-15
