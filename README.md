# Nginx Site Manager (nsm) 🚀

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub release](https://img.shields.io/github/v/release/ColoredSine/nginx-site-manager)](https://github.com/ColoredSine/nginx-site-manager/releases)

**Nginx Site Manager (nsm)** is a lightweight and powerful bash script designed to streamline the management of Nginx site configurations. It simplifies common tasks for system administrators, such as enabling, disabling, editing, deleting, renaming, and listing Nginx sites, as well as reloading the Nginx service. Whether you're managing a single site or multiple sites, `nsm` offers an intuitive CLI interface to save time and reduce errors.

Built with simplicity and efficiency in mind, `nsm` works with the standard Nginx `sites-available` and `sites-enabled` structure, commonly used in Debian/Ubuntu environments. It's perfect for sysadmins, DevOps engineers, and anyone who wants to manage Nginx configurations with ease.

## Key Features 🌟

- **Enable/Disable Sites**: Use `e` to enable or `d` to disable sites by managing symlinks between `sites-available` and `sites-enabled`. Add `r` (e.g., `er`, `dr`) to automatically reload Nginx.
- **Edit Configurations**: Edit site configurations with `ed` (creates new if not exists) or `edr` to edit and reload Nginx if changes are saved. Smart change detection ensures reloads only when necessary.
- **Delete Sites**: Delete a single site (`del <site>`) or multiple sites (`del "site1,site2"`) in one command, with optional automatic Nginx reload.
- **Rename Sites**: Rename sites with `mv <old> <new>`, automatically updating symlinks if the site is enabled.
- **List Sites**: View all available sites and their status (`enabled` or not) with `l`.
- **Reload Nginx**: Reload Nginx configuration with `r`, including a syntax check before reload.
- **Navigate Easily**: Jump to the Nginx config directory (`/etc/nginx`) with `f` for quick manual edits.

## Example Commands and Outputs 📋

Here are some practical examples to show how `nsm` works:

### Listing Sites
```bash
nsm l
```
**Output**:
```
Available sites (/etc/nginx/sites-available):
  default [enabled]
  site1
  site2 [enabled]
```

### Enabling a Site
```bash
nsm e site1
```
**Output**:
```
Site 'site1' enabled successfully
Run 'nsm r' to apply changes
```

### Deleting Multiple Sites
```bash
nsm del "site1,site2"
```
**Output**:
```
Site 'site1' configuration deleted successfully
Symlink for site 'site2' removed
Site 'site2' configuration deleted successfully
Nginx reloaded successfully
```

### Editing a Site Configuration
```bash
nsm ed default
```
**Output (after saving changes in vim)**:
```
Changes saved for site 'default'
Run 'nsm r' to apply changes if you modified/saved the configuration
```

## Installation 🛠️

Follow these steps to install `nsm` on your system:

1. **Download the Script**:
   ```bash
   wget https://raw.githubusercontent.com/ColoredSine/nginx-site-manager/main/nsm
   ```

2. **Make it Executable**:
   ```bash
   chmod +x nsm
   ```

3. **Move to a System Path**:
   ```bash
   sudo mv nsm /usr/local/bin/
   ```

4. **Verify Installation**:
   ```bash
   nsm -h
   ```
   This will display the help message with all available commands.

## Requirements 📦

- **Bash**: The script runs in any standard bash environment.
- **Nginx**: Must be installed and configured with `sites-available` and `sites-enabled` directories (common in Debian/Ubuntu).

## Usage 📖

```bash
nsm [command] [site_name] [options]
```

### Available Commands
| Command          | Description                                      | Example                     |
|------------------|--------------------------------------------------|-----------------------------|
| `e <site>`       | Enable a site (create symlink)                  | `nsm e default`            |
| `d <site>`       | Disable a site (remove symlink)                 | `nsm d default`            |
| `er`/`re <site>` | Enable a site and reload Nginx                  | `nsm er default`           |
| `dr`/`rd <site>` | Disable a site and reload Nginx                 | `nsm dr default`           |
| `ed <site>`      | Edit site configuration (create if not exists)  | `nsm ed default`           |
| `edr <site>`     | Edit and reload Nginx if saved                  | `nsm edr default`          |
| `l`              | List available sites with status                | `nsm l`                    |
| `r`              | Reload Nginx configuration                      | `nsm r`                    |
| `f`              | Navigate to `/etc/nginx` directory              | `nsm f`                    |
| `mv <old> <new>` | Rename a site configuration                     | `nsm mv oldsite newsite`   |
| `del <site> \| "<site1,site2,...>"` | Delete one or multiple sites        | `nsm del "site1,site2"`    |
| `-h`             | Show help message                               | `nsm -h`                   |

## Contributing 🤝

We welcome contributions to improve `nsm`! Here's how you can help:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Make your changes and commit (`git commit -m "Add feature"`).
4. Push to your branch (`git push origin feature-name`).
5. Open a pull request.

If you find a bug or have a feature request, please open an issue on GitHub.

## License 📜

This project is licensed under the [MIT License](LICENSE).

## Acknowledgements 🙌

Built with 💙 by [ColoredSine](https://github.com/ColoredSine) for the sysadmin community.
