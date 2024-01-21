# Hymnal Slides Creation Project

## Overview
This project automates the process of creating Google Slides presentations for hymns. It scrapes hymnal data, processes the lyrics, and uses the Google Slides API to create individual presentations for each hymn. The presentations are organized in a folder within a Google Service Account's Drive, with functionality to share this folder with a user's primary Google Drive account.

## Features
- **Data Scraping**: Scrapes hymnal data from a website.
- **Presentation Creation**: Automates the creation of Google Slides presentations for each hymn.
- **Folder Organization**: Places all presentations in a specific folder within the service account's Google Drive.
- **Sharing Capability**: Shares the folder with presentations to a specified Google Drive account.
- **Rate Limit Handling**: Implements exponential backoff to handle Google API's rate limits.
- **Progress Tracking**: Logs the progress and any issues encountered during the process.

## Prerequisites
- Python 3.x
- Google Cloud Platform account with Google Slides and Google Drive APIs enabled.
- Service account with permissions for the Google Slides and Google Drive APIs.
- Python libraries: `google-auth`, `google-auth-oauthlib`, `google-auth-httplib2`, `google-api-python-client`, `pandas`, `splinter`, `bs4`

## Configuration and Credentials
Before running the script, you must set up a configuration file (`config.ini`) and service account credentials:

1. **Create a `config.ini` file** in the root directory with the following structure:
   ```ini
   [credentials]
   username = YOUR_HYMNAL_WEBSITE_USERNAME
   password = YOUR_HYMNAL_WEBSITE_PASSWORD
   my_email = YOUR_GOOGLE_DRIVE_EMAIL

   [Paths]
   clean_csv = PATH_TO_SAVE_CLEANED_CSV
   drive_folder = ID_OF_DRIVE_FOLDER_TO_STORE_PRESENTATIONS

   [JSON]
   location = PATH_TO_SERVICE_ACCOUNT_JSON
   ```
Replace the placeholders with your hymnal website credentials, email, and paths.

## Service Account JSON File
- Ensure you have a service account JSON file from Google Cloud Platform with the necessary permissions. Update the  `location` field in `config.ini` with the path to this file.

