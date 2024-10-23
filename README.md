

Here is a sample markdown based readme file based on the provided information:

# LogicMonitor Datamart in Docker using Compose

This repository contains the files needed to run the Panoramic Data [LogicMonitor Datamart](https://github.com/panoramicdata/LogicMonitor.Datamart?tab=readme-ov-file#introduction) using Docker Compose. The Datamart allows you to create a copy of your LogicMonitor system in a SQL Server or PostgreSQL database. 

Running the datamart in Docker Compose allows turn-key setup and installation of all the required components, including the PostgreSQL database and [Adminer](https://hub.docker.com/_/adminer), a popular web-based SQL database client. 
Adminer is no longer maintained and can be removed from the docker-compose.yml definition. Alternatively, you can use other clients like [Dockette's Adminer](https://hub.docker.com/r/dockette/adminer). 

## Features

* **Dimension data:** Get a snapshot of your LogicMonitor devices, groups, and other configuration items.
* **Alert history:** Keep a historical record of all alerts generated in your LogicMonitor system.
* **Audit log history:** Track changes made to your LogicMonitor configuration.
* **Time Series data aggregations:** Analyze performance trends over time.

## Prerequisites

Before you begin, ensure you have the following:

* **LogicMonitor Account:** You'll need a LogicMonitor account and the ability to generate an API key and ID.
  * Create these under Settings > Users > API Tokens in the LogicMonitor UI.
  *  The API user requires full read permissions, including LogicModule access.
* **Docker Environment:** You'll need a working Docker environment. The instructions provided assume you're using Docker Desktop on Windows. 

## Setup

1. **Clone this repository:**
   ```bash
   git clone https://github.com/sweenig/panoramic_datamart_docker_compose.git
   ```
2. **Navigate to the directory:**
   ```bash
   cd panoramic_datamart_docker_compose
   ```
3. **Update the .env file:**
   ```
   lm_account=your-logicmonitor-account
   lm_accessid=your-logicmonitor-api-access-id
   lm_accesskey=your-logicmonitor-api-access-key
   dbpassword=your-database-password
   ```
4. **Start the containers:**
   ```bash
   docker-compose up -d
   ```

## Accessing the Datamart

Once the containers are running, you can access the datamart by going to `http://your-docker-server:8080`. Use the credentials you specified in the .env file:
* System: `PostgreSQL`
* Server: `datamart_db`
* Username: `pdata`
* Password: configured in your `.env` file
* Database: `logicmonitor`

## Configuration

You can customize the datamart's behavior by modifying the `appsettings.json` file located in the root of this repository. Refer to the [full configuration file documentation](https://panoramicdata.com/open-source/logicmonitor-datamart/) for available options.

## Support

* For assistance with the datamart, consider contacting Panoramic Data's Professional Services Team if you have an active project with available hours.
* Free support is also available in the Panoramic Data Community. 

## Contributing

Contributions are welcome! Help improve the LogicMonitor Datamart on GitHub!
