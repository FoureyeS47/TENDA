Tenda IC7-PRS Hardcoded Password Vulnerability

The firmware (version 2201101520) for the Tenda IC7-PRSV1.0 smart turret camera contains a hardcoded default password for the root user, which is stored using weak encryption. Unauthorized access—leading to a full device compromise—can be achieved by using these credentials to log in via Telnet or the UART interface and gain root-level privileges.

According to the user manual, the camera's default login IP address is 192.168.1.203.
<p align="center">
  <img src="../images/password1.png" alt="password1">
</p>
Locate the `shadow` file within the extracted firmware; it contains the hardcoded hash for the root user. Decrypting this hash reveals the password: `tdrootfs`.
<p align="center">
  <img src="../images/password2.png" alt="password2">
</p>
Scan common port numbers using nmap and observe that the Telnet service is open.
<p align="center">
  <img src="../images/password3.png" alt="password3">
</p>
Connect via MobaXterm and log in as the root user to gain full access to the device.
<p align="center">
  <img src="../images/password4.png" alt="password4">
</p>
