# Necesse dedicated server in Docker


## Quick Start

Run `docker-compose up -d` from this directory.

Default server password is `password123`.


### Key files
* save-data/cfg/server.cfg
* save-data/saves/default-world/worldSettings.cfg
* .env
    * Update the server by changing the URL in this file to the latest Linux version [found here](https://necessegame.com/server)

Remember to forward port 14159 to your game server on your router.


## Updating the server

Go to the [Necesse server download page](https://necessegame.com/server) and locate the URL for the Linux64 version. Right click and copy the link. Paste the new url as the value for `SERVER_DOWNLOAD_URL` in the `.env` file.


## Can I host this on a Raspberry Pi?

### Short answer
Yes!

### Slightly longer answer
If you have a 64-bit operating system, you should be able to use this compose file as-is. If, however, you are using a 32-bit operating system and receive an error when you try to build the docker images saying something about linux/arm/v7, you'll need to switch to the 32-bit version.

To do this, change which `JAVA_VERSION` line is active in the .env file. The line that has arm32v7 in it should be active (should not start with a #).


## Troubleshooting

> "required variable ... is missing a value... Please set ... in the .env file"

If you have already set the values in the .env file or you haven't changed anything, you may be using an old version of docker compose. Try including `--project-directory .` to your up command, e.g.:

`docker-compose --project-directory . up -d`
