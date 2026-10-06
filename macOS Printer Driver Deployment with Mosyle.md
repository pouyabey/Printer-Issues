## macOS Printer Driver Deployment with Mosyle

### Problem

Network printers were successfully added to managed Macs through Mosyle, but the manufacturer-specific printer drivers were not available.

As a result, some printers were using generic drivers and advanced features such as color options, duplex printing, paper trays, and finishing settings were unavailable.

### Root Cause

Deploying the printer configuration alone was not sufficient. The correct manufacturer driver package and PPD needed to be installed and associated with the printer configuration.

### Resolution

1. Downloaded the official macOS printer driver package (`.pkg`) from the manufacturer.
2. Installed the driver on a test Mac.
3. Located the correct PPD file under:

   `/Library/Printers/PPDs/Contents/Resources/`

4. Added the driver package and PPD path to the Mosyle **Custom Printer Configuration**.
5. Deployed the configuration to managed Macs.
6. Verified that printers were using the manufacturer driver instead of a generic driver.

### Result

Printers can now be deployed automatically through MDM with the correct driver and full printer functionality, eliminating the need for manual driver installation on each Mac.
