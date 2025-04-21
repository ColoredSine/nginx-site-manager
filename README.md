# Nginx Site Manager (nsm)

A lightweight bash script for managing Nginx site configurations. It simplifies tasks like enabling, disabling, editing, deleting, renaming, and listing Nginx sites, as well as reloading the Nginx service.

## Features
- Enable (`e`) or disable (`d`) sites by managing symlinks between `sites-available` and `sites-enabled`.
- Edit site configurations (`ed`, `edr`) with automatic reload on changes.
- Delete single or multiple sites (`del site` or `del site1,site2`).
- Rename sites (`mv oldsite newsite`).
- List available sites with their status (`l`).
- Reload Nginx configuration (`r`).
- Navigate to Nginx config directory (`f`).

## Eximple Command
nsm e default
nsm del default

## Installation
1. Download the script:
   ```bash
   wget https://raw.githubusercontent.com/<your-username>/nginx-site-manager/main/nsm

Make it executable and move to a system path:
bash

