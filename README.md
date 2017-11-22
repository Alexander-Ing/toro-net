# Toro Net
## Getting
Fork the repo then clone it to your local machine.
```
git clone https://github.com/<your username>/toro-net.git
```

Fork the repo then clone it to your local machine.

```bash
$ git clone https://github.com/<github-user>/toro-net.git [<repo-name>]
```

We assume that `$TOPDIR` is relative to the `toro-net` directory and all script executions are done in the `$TOPDIR` location.

```bash
$ cd toro-net
```

## Dependencies

Install application dependencies, e.g. mongo and nodejs.

```bash
$ bash bin/install.sh
```

Install node packages with `npm`.

```bash
$ npm install
``` 

Additionally, you will need to install Neo4j as well as Java 8 in order to run Toro-net. 

## Customizations

Update your environment settings by creating a file `.env` as below:

```
PORT=3000
MONGO_URI=mongodb://127.0.0.1:27017/toro-net
GITHUB_ID=233245n234566kjh243f
GITHUB_SECRET=k2hj432kjgjkh2g34kj2g4jkh23g4jk2342jhg34
APP_URL=http://127.0.0.1:3000/
NEO4J_PROTOCOL=http
NEO4J_HOST=127.0.0.1
NEO4J_PORT=7474
NEO4J_USERNAME=neo4j
NEO4J_PASSWORD=neo4j
```
---
## Virtual Box Setup Instructions
### To use Vagrant, get started [here](#vagrant-setup-instructions)
Install dependencies (mongo, node, npm packages).  
```
bash dev-env.sh
```

## Deploying a Development Environment

Run mongo as a service.  

```bash
$ ./bin/init-db.sh
```

```bash
$ ./bin/run-back-end.sh &
$ ./bin/run-front-end.sh &
```

Log files will be created in `var/log/*.log`.  Note that you can monitor the log file with the `tail` command. For example:

```bash
$ tail -f var/log/frontend.log
```

## View the Application

Open `http://localhost:3000` in any web browser.
