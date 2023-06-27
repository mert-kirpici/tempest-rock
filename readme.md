# tempest-rock
## Quick Start
```
$ rockcraft -v
Starting Rockcraft 0.0.1.dev1
...
Entrypoint set to ['/bin/pebble', 'enter', '--verbose']                                            
Adding metadata                                                                                    
Configuring labels and annotations...                                                              
Labels and annotations set to ['org.opencontainers.image.version=30.1.0', 'org.opencontainers.image.title=tempest', 'org.opencontainers.image.ref.name=tempest', 'org.opencontainers.image.licenses=Apache-2.0', 'org.opencontainers.image.created=2023-06-27T17:30:33.720951+00:00', 'org.opencontainers.image.base.digest=2c1168b31e636c7ab22598bfaefa6de63d1806a908d0c39bd402277881356fab']                 
Setting the ROCK's Control Data                                                                    
Control data written                                                                               
Metadata added                                                                                     
Exporting to OCI archive                                                                           
Exported to OCI archive 'tempest_30.1.0_amd64.rock'

$ sudo /snap/rockcraft/current/bin/skopeo --insecure-policy copy oci-archive:tempest_30.1.0_amd64.rock docker-daemon:tempest:30.1.0
Getting image source signatures
Copying blob 6b851dcae6ca done  
Copying blob a7aa05f6406e done  
Copying blob 9970e1a8914c done  
Copying config ca598d0107 done  
Writing manifest to image destination
Storing signatures

$ docker run --rm tempest:30.1.0 exec tempest --version 2>/dev/null
tempest 30.1.0

$ docker run --rm tempest:30.1.0 exec tempest --help 2>/dev/null
usage: tempest [--version] [-v | -q] [--log-file LOG_FILE] [-h] [--debug]

Tempest cli application

options:
  --version            show program's version number and exit
  -v, --verbose        Increase verbosity of output. Can be repeated.
  -q, --quiet          Suppress output except warnings and errors.
  --log-file LOG_FILE  Specify a file to log output. Disabled by default.
  -h, --help           Show help message and exit.
  --debug              Show tracebacks on errors.

Commands:
  account-generator  Create accounts.yaml file for concurrent test runs
  cleanup        Cleanup after tempest run
  complete       print bash completion command (cliff)
  help           print detailed help for another command (cliff)
  init           Setup a local working environment for running tempest
  list-plugins   List all tempest plugins
  run            Run tempest
  subunit-describe-calls  Outputs all HTTP calls a given test made that were logged
  verify-config  Verify your current tempest configuration
  workspace list  Outputs the name and path of all known tempest workspaces
  workspace move  Changes the path of a given tempest workspace --name to --path
  workspace register  Registers a new tempest workspace via a given --name and --path
  workspace remove  Deletes the entry for a given tempest workspace --name
  workspace rename  Renames a tempest workspace from --old-name to --new-name
```
