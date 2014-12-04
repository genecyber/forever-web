forever-web [![NPM version](https://badge.fury.io/js/forever-web.svg)](http://badge.fury.io/js/forever-web)
===========
An elegant web interface for Nodejitsi/forever.

# Guide
- [Installation](#ins)
- [CLI](#cli)
  - [Run Web Interface](#cli_web)
  - [Configurations](#cli_confs)
- [Features](#feats)
- [Cautions](#cauts)
- [UI/UX](#ui)
- [TODO](#todo)


<a name="ins" />
# Installation
```
$ npm install -g forever-web
```

<a name="cli" />
# CLI
```bash
  Usage: fw [cmd] [file|name]

  Commands:

    start [options] [port]  Launch the web server, port default by 8088
    config                  show all configs
    set <key> <value>       set config by key-value pairs
    rm <key>                remove config by key

  Options:

    -h, --help     output usage information
    -v, --version  output the version number

  Basic Examples:

    Start the web server, by default port (8088):
    $ fw start

    Start the web server, by specific port (8090):
    $ fw start 8090

```

<a name="cli_web" />
## Run Web Interface
```bash
  Usage: start [options] [port]

  Options:

    -h, --help  output usage information
    --no-debug  hide stdout/stderr information
```

<a name="cli_confs" />
## Configurations
```
refresh: 	3000
manipulation: 	true
forever: 	~/.forever
```

- **refresh** The heartbeat duration of monitor (backend), `5000` by default.
- **manupulation** A value indicates whether the client has permission to restart/stop processes, `true` by default.
- **forever** Root directory of nodejitsu/forever, `~/.forever` by default.

<a name="feats" />
# Feature
- All the heartbeats - including **monitor** and **tail (logs)** are automatic destroyed.
- The `forever` processes are watched by a FSWatcher ([chokidar](https://www.npmjs.org/package/chokidar)), but not manually polling.
- Communicated with `forever` through [NSSocket](https://www.npmjs.org/package/nssocket) directly, but not `forever` programmatic API.
- Socket.io between client and server.
- Monitor CPU and Memory usage of server in a real-time.
- Monitor `forever` processes in a real-time.

<a name="cauts" />
# Cautions
- Web Interface is wrote by CSS3 && HTML5, so view it with the latest version of the browser (WebGL, Animation, WebSocket supports), e.g. Chrome, Safari and Firefox.
- I've never test it on Internet Explorer.
- I've never test it on Windows.
- Nodejitsu/forever has problem with `STOPPED` process, so if there is a `STOPPED` process, however, it can create instability, you'd better refresh the page manually (F5 / COMMAND + R).

<a name="ui" />
# UI/UX
- Amazing and smooth animations.
- High performance.

Backend (without `--no-debug` option):

![shot](screenshots/backend.jpg)

Home

![shot](screenshots/home.jpg)

Empty List

![shot](screenshots/no-proc.jpg)

Processes

![shot](screenshots/procs.jpg)

Describe Complete Information

![shot](screenshots/info.jpg)

Tail Logs

![shot](screenshots/tail-logs.jpg)

<a name="todo" />
# TODO
- Implement restart/stop
- Test on Windows (need environment).
- Need feedback.


## License
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
