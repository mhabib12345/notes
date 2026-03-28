+++
date = '2025-04-27T21:19:55+07:00'
draft = true
title = 'Setting Up Printer'
+++

First, install cups needed packaged

{{< code lang="bash" >}}
sudo pacman -S cups cups-dinit
{{< /code >}}

enable the cups service (Here, we use dinit version)

{{< code lang="bash" >}}
sudo dinitctl start cupsd
{{< /code >}}

Check output lsusb (make sure package usbutils installed)

Open browser and go to http://localhost:631/admin . It will prompt pop-up admin+pass.
Then select Administration -> Add Printer, select your printer that should be recognized on the network, select the drivers and your model that should be present too, and finish by selecting Add printer at the bottom.

Lets get the necessary printer drivers!  