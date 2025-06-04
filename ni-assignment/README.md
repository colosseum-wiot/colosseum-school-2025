# NI Tutorial

## Making a Reservation on Colosseum

1. Connect to the Colosseum VPN following the instructions [here](https://colosseumwireless.readthedocs.io/en/latest/getting_started/cisco_anyconnect_remote_vpn_access.html), then log in to the [Colosseum website](https://experiments.colosseum.net).
2. Create a reservation with two SRNs using the `ni-tutorial-2` common image.
   - Give your reservation a meaningful name (e.g., your own name).  
   - A two-hour reservation is usually sufficient.
3. On the reservation page, find the assigned SRNs/nodes and their hostnames by hovering over the nodes.  
4. When your reservation starts, open two terminal windows and SSH into each assigned SRN as the `root` user.

## Enabling DISPLAY Forwarding Over SSH

To use graphical applications over SSH (e.g., with GNU Radio), connect using `ssh -X` or `ssh -Y`.
Make sure you have the following installed on your local machine:

* **macOS**: XQuartz
* **Linux**: `xauth` and an X server (usually included by default)
* **Windows**: An X server like MobaXterm or WSL with X server support

The password for the `ni-tutorial-2` container is `cast123`.

## Reflashing the USRP

The installed UHD version 4.2 is incompatible with the current FPGA image on the radio. To update the FPGA image, run the following command:

```bash
colosseumcli usrp flash -f usrp_x310_fpga_HG_c38.bit
```

This command also installs GNU Radio 4.2 along with `gr-osmosdr`, `gr-rds`, and `Gqrx`.

## GNU Radio

You can launch the GNU Radio Companion GUI by entering:

```bash
gnuradio-companion 
```

You can then start creating your flowgraphs, generate them, and execute them on Colosseum.

## Ettus Research

[Ettus Research Tutorial](https://kb.ettus.com/Workshop_Tutorial)




