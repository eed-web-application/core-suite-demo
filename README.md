![logo](./logos/SLAC-lab-hires.png)

# Core SUITE demo


## SLAC National Accelerator Laboratory
The SLAC National Accelerator Laboratory is operated by Stanford University for the US Departement of Energy.  
[DOE/Stanford Contract](https://legal.slac.stanford.edu/sites/default/files/Conformed%20Prime%20Contract%20DE-AC02-76SF00515%20as%20of%202022.10.01.pdf)

## License
Copyright (c) 2017-2023, The Board of Trustees of the Leland Stanford Junior University, through SLAC National Accelerator Laboratory... the complete license is [here](LICENSE.md)

## Overview
this ia comprenhensive package that permit to spinup a new slac core-suit software. It's a simpel docker compose file that include nginx reverse proxy to export into unique url the backend. The below command is for startup the demo.
``` bash
docker compose --profile all-service up
```
it expose on port 80 the backend on the following URI:
```bash
http://localhost/api/cwm => core work management backend
as test can be used the command  curl http://localhost/api/cwm/actuator/info that will show the applcaition version
```
```bash
http://localhost/api/cis => core inventory system
as test can be used the command  curl http://localhost/api/cis/actuator/info that will show the applcaition version
```
```bash
http://localhost/api/elog => elog system
as test can be used the command  curl http://localhost/api/elog/actuator/info that will show the applcaition version
```

## Special startup
The docker compose file containe 4 profile
- cis
- cwm
- elog
- all-service

each or multiple can be used to startup the desidere backend ad example:
```bash
docker compose --profile cis up
```
or
```bash
docker compose --profile elog up
```
or can also be used more that one profile
```bash
docker compose --profile cis --profile elog up
```