# Out Of Ordinary Journal - GitHub Data Sync

This guide explains how to sync your journal data with your GitHub repository at `https://github.com/ooo-journal/cn`.

## 1. Export Data from Local Storage

### Method 1: Using Browser Console
1. Open any page of the journal website (e.g., `index.html`)
2. Open the browser console (F12)
3. Run the following commands:

   ```javascript
   // Initialize database
   await window.ooodb.init();
   
   // Export all data
   await window.ooodb.exportData();
   
   // Or export only accepted articles
   await window.ooodb.exportAcceptedArticles();
   ```

### Method 2: Using Author Dashboard
1. Open `author-dashboard.html`
2. Look for the "Export Data" button (if available)
3. Click it to download the data files

## 2. Upload Data to GitHub

1. **Clone your GitHub repository** (if not already cloned):
   ```bash
   git clone https://github.com/ooo-journal/cn.git
   cd cn
   ```

2. **Create a `data` directory** (if not already exists):
   ```bash
   mkdir -p data
   ```

3. **Move the exported JSON file** to the data directory:
   - If you exported all data: move `ooo-journal-data.json` to `data/`
   - If you exported only accepted articles: move `ooo-accepted-articles.json` to `data/`

4. **Commit and push the changes**:
   ```bash
   git add data/
   git commit -m "Update journal data"
   git push origin main
   ```

## 3. Import Data from GitHub

### Method 1: Manual Import
1. **Download the JSON file** from GitHub:
   - Go to `https://github.com/ooo-journal/cn/blob/main/data/ooo-journal-data.json`
   - Click "Raw" and save the file

2. **Import the data**:
   - Open any page of the journal website
   - Open the browser console
   - Run the following commands:

     ```javascript
     // Read the JSON file content (replace with actual content)
     const jsonData = '{"manuscripts": {...}, "acceptedArchive": {...}}';
     
     // Import the data
     await window.ooodb.importData(jsonData);
     ```

### Method 2: Automated Import (Future Feature)
A future update will include automatic data syncing with GitHub using the GitHub API.

## 4. Data Structure

### Full Data Export (`ooo-journal-data.json`)
```json
{
  "manuscripts": {
    "MS_12345": {
      "id": "MS_12345",
      "title": "Article Title",
      "authors": "Author Name",
      "abstract": "Article abstract",
      "content": "Article content",
      "status": "Accepted",
      "statusHistory": [...],
      "submittedDate": "2026-04-21T12:00:00Z"
    }
  },
  "acceptedArchive": {
    "MS_12345": {
      "id": "MS_12345",
      "title": "Article Title",
      "authors": "Author Name",
      "abstract": "Article abstract",
      "content": "Article content",
      "acceptedDate": "2026-04-21T12:00:00Z",
      "publicationDate": "2026-04-21T12:00:00Z"
    }
  },
  "exportedAt": "2026-04-21T12:00:00Z"
}
```

### Accepted Articles Export (`ooo-accepted-articles.json`)
```json
{
  "acceptedArticles": {
    "MS_12345": {
      "id": "MS_12345",
      "title": "Article Title",
      "authors": "Author Name",
      "abstract": "Article abstract",
      "content": "Article content",
      "acceptedDate": "2026-04-21T12:00:00Z",
      "publicationDate": "2026-04-21T12:00:00Z"
    }
  },
  "exportedAt": "2026-04-21T12:00:00Z"
}
```

## 5. Best Practices

1. **Regular Backups**: Export data regularly to GitHub to prevent data loss
2. **Consistent Workflow**: Always export data after making changes
3. **Branch Strategy**: Consider using branches for major updates
4. **Documentation**: Keep this README updated with any changes to the sync process

## 6. Troubleshooting

### Common Issues
- **File not found**: Ensure the `js/db.js` file is properly loaded
- **Data not saving**: Check browser localStorage permissions
- **GitHub push failed**: Ensure you have write access to the repository

### Debugging
- Open browser console and check for error messages
- Verify that `window.ooodb` is defined
- Check localStorage in browser dev tools (Application tab)

## 7. Future Enhancements

- [ ] Automatic GitHub sync using GitHub API
- [ ] Webhook integration for real-time updates
- [ ] Data validation and conflict resolution
- [ ] User-friendly export/import UI

For questions or issues, please contact the editorial board.