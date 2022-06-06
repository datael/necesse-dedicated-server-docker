# Necesse dedicated server in Docker

## Quick Start

* Key files
    * save-data/cfg/server.cfg
    * save-data/saves/default-server/worlsSettings.cfg
    * .env
        * Update the server by changing the URL in this file to the latest Linux version [found here](https://necessegame.com/server)
* Remember to forward port 14159 to your server


## Updating the server

Go to the [Necesse server download page](https://necessegame.com/server) and locate the URL for the Linux64 version. Right click and copy the link. Paste the new url as the value for `SERVER_DOWNLOAD_URL` in the `.env` file.
