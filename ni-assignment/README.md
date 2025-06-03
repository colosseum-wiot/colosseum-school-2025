# NI Tutorial

## Making a Reservation on Colosseum

1. Connect to the Colosseum VPN following the instructions [here](https://colosseumwireless.readthedocs.io/en/latest/getting_started/cisco_anyconnect_remote_vpn_access.html), then log in to the [Colosseum website](https://experiments.colosseum.net).
2. Create a reservation with two SRNs using the `cast` common image. Make sure to check the **"Octoclock"** option. For detailed steps, see [Making a Reservation](https://colosseumwireless.readthedocs.io/en/latest/reservations/making_a_reservation_interactive_and_batch_mode.html).  
   - Give your reservation a meaningful name (e.g., your own name).  
   - A two-hour reservation is usually sufficient.
3. On the reservation page, find the assigned SRNs/nodes and their hostnames by hovering over the nodes.  
4. When your reservation starts, open two terminal windows and SSH into each assigned SRN as the `root` user:  

## Enabling DISPLAY Forwarding Over SSH

To use graphical applications over SSH (e.g., with GNURadio), connect using `ssh -X` or `ssh -Y`.
Make sure you have the following installed on your local machine:

* **macOS**: XQuartz
* **Linux**: `xauth` and an X server (usually included by default)
* **Windows**: An X server like Xming or VcXsrv

The password for the `cast` container is `cast123`.

## Reflashing the USRP

The installed UHD version 4.2 is incompatible with the current image on the radio. To update, run the following command:

```bash
colosseumcli usrp flash -f usrp_x310_fpga_HG_c38.bit
```

This also installs GNU Radio 4.2 along with `gr-osmosdr`, `gr-rds`, and `Gqrx`.

