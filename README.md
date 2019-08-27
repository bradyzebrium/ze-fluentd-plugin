# ze-fluentd-plugin
Zebrium's fluentd output plugin sends the logs you collect with Fluentd to Zebrium for automated Anomaly detection.
## Features
##### upload
Upload log event data to your Zebrium instance from a file or stream (stdin) with appropriate meta data.
##### def
Show the event-type (eType) definition for structured events in the database.
##### cat
Show events from the database by: meta-data, eType, time range, or first occurrence in CSV, JSON, pretty-print or raw format.
## Getting Started
##### Prerequisites
* Fluentd
##### Installing
1. Install [Fluentd](https://www.fluentd.org/download).

2. Download/copy Zebrium output plugin package fluent-plugin-zebrium_output-1.0.0.gem
   1. git clone https://github.com/zebrium/ze-fluentd-plugin.git
   2. copy pkgs/fluent-plugin-zebrium_output-1.0.0.gem to a new directory
3. Run the following command in the same directory where fluent-plugin-zebrium_output-1.0.0.gem was copied/saved
   1. Run the following command in the same directory where  fluent-plugin-zebrium_output-1.0.0.gem is saved
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
