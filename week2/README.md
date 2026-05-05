## Overview

A VM instance was created on Google Compute Engine and configured using the provided `supera.sh` startup script. After the VM finished setting up, the deployment was checked using the provided gate script.

## VM Details

<img width="1637" height="181" alt="vm instance - regiano-vm" src="https://github.com/user-attachments/assets/b5a145d1-c1e8-4044-bef1-790091d42145" />

- **VM name:** `regiano-vm`
- **Zone:** `europe-west1-c`
- **External IP:** `104.155.61.31`
- **Startup script:** `supera.sh`
- **Gate script:** `gate_gcp_vm_http_ok.sh`

## What Was Tested

The gate script checked that:

- The homepage was reachable over HTTP
- The `/healthz` endpoint returned `ok`
- The `/metadata` endpoint returned valid JSON
- The metadata included the instance name
- The metadata included the region

## Result

The deployment passed all checks.

<img width="577" height="175" alt="gate_gcp_vm_http_ok sh result vm - regiano" src="https://github.com/user-attachments/assets/b4e7197d-fb47-433b-8412-01756945390b" />

## Notes

The VM is running successfully and the required HTTP endpoints are responding as expected.
