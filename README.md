# ze-fluentd-plugin
Zebrium's command line interface for uploading log events from files or streams, viewing log events and the definitions of event types in the database.
## Features
##### upload
Upload log event data to your Zebrium instance from a file or stream (stdin) with appropriate meta data.
##### def
Show the event-type (eType) definition for structured events in the database.
##### cat
Show events from the database by: meta-data, eType, time range, or first occurrence in CSV, JSON, pretty-print or raw format.
## Getting Started
##### Prerequisites
* Perl
* cURL
* API token from Zebrium
* URL to your instance of Zebrium
##### Installing
* `git clone https://github.com/zebrium/ze-cli.git`
* move `bin/ze` to appropriate bin directory in your PATH
## Configuration
No configuration is required. All options can be specified as command line arguments. However, see **Setup** section below for information on configuring your .zerc file.
##### Setup
For convenience, your API token and your Zebrium instance URL can be specified in your $HOME/.zerc file.

Example .zerc file:
```
auth=YOUR_API_TOKEN
url=https://YOUR_ZE_API_INSTANCE_NAME.zebrium.com
```
##### Environment Variables
None
## Usage
Use `ze help` for a complete list of command operations and options.
```
ze help
```
## Testing your installation
Use `ze up` to ingest log events into your Zebrium instance.
```
ze up --file=/var/log/messages --node=server01 --log=varlogmsgs
```
Use `ze cat` to show events already ingested into your Zebrium instance.
```
ze cat --lim=20 --fmt=pp
```
## Contributors
* Larry Lancaster (Zebrium)
* Dara Hazeghi (Zebrium)
* Rod Bagg (Zebrium)
