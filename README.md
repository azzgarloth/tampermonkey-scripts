# Userscripts Repository

This repository contains two Tampermonkey userscripts:

1. **Pepper Keyword Filter Prioritizer UI (Responsive)** – Customize and prioritize forum threads on [Pepper.pl](https://www.pepper.pl/).  
2. **Hide Videos & Shorts Menu & Channels & Shorts Shelf** – Filter unwanted videos and Shorts on YouTube.

---

## 1. Pepper Keyword Filter Prioritizer UI (Responsive)

![Tampermonkey](https://img.shields.io/badge/Tampermonkey-compatible-brightgreen)  
![Pepper.pl](https://img.shields.io/badge/Platform-Pepper.pl-orange)  
![Version](https://img.shields.io/badge/Version-10.7-blue)

### Description

A Tampermonkey userscript that allows:

- Filtering out threads by specific keywords.
- Prioritizing certain keywords to display threads at the top.
- Dynamic, responsive UI to add, remove, and reorder priority keywords.
- Loading all threads automatically and sorting them.

### Features

- **Hide keywords:** Any thread containing a `hideKeywords` term is hidden.  
- **Priority keywords:** Threads containing these keywords are moved to the top.  
- **Responsive UI:** Add, remove, and reorder priority keywords directly on the page.  
- **Load & sort:** Button on the page triggers scrolling through all threads and sorting them in real-time.  

### Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/) in your browser.  
2. Create a new userscript and paste the `Pepper Keyword Filter Prioritizer UI Responsive` code.  
3. Save and open [Pepper.pl](https://www.pepper.pl/).  
4. Wait 2 seconds for the UI to appear in the bottom-right corner.

### Configuration

- **hideKeywords:** Array of keywords to automatically hide threads.  
- **priorityKeywords:** Array of keywords to prioritize in sorting.  

The UI allows you to dynamically add, remove, and reorder priority keywords without editing the code.  

### Example Usage

1. Open Pepper.pl.  
2. Add a keyword `"laptop"` in the UI.  
3. Click **Load All & Sort** to fetch all threads and prioritize those containing `"laptop"` while hiding unwanted threads.

---

## 2. Hide Videos & Shorts Menu & Channels & Shorts Shelf

![Tampermonkey](https://img.shields.io/badge/Tampermonkey-compatible-brightgreen)  
![YouTube](https://img.shields.io/badge/Platform-YouTube-red)  
![Version](https://img.shields.io/badge/Version-1.6-blue)

### Description

A Tampermonkey userscript that hides:

- Videos containing a specific keyword (`"value 2"` by default).  
- Shorts menu from the sidebar.  
- Videos from specific blocked channels.  
- Shorts shelves from the homepage feed.  

### Features

- Keyword-based filtering for video titles.  
- Channel-specific filtering.  
- Hides UI elements like the **Shorts menu** and **Shorts shelves**.  
- Dynamic updates using a `MutationObserver` for content loaded after scrolling.  

### Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/).  
2. Create a new userscript and paste the `Hide Videos, Shorts Menu, Channels array, and Shorts Shelf` code.  
3. Save and visit [YouTube](https://www.youtube.com/).  

### Configuration

- **blockedChannels:** Array of channel names to hide videos from:

```javascript
const blockedChannels = [
    'channelNameToBlock',
    'AnotherChannel'
];
```

- **Video keyword**: The regex /value\s*2/i filters videos containing "value 2". Modify as needed.

### Usage

- The script runs **automatically**.
- Hidden elements are only **visually removed** (display: none) but not deleted.
- **Works with dynamic content loading (infinite scroll)**.

### Contributing

- Adjust selectors if YouTube or Pepper.pl updates their DOM structure.
- Add additional keyword matching rules.
- Report issues or submit pull requests to improve filtering performance.

### License

- MIT License
