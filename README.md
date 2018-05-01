# L4-Bootable-Miner
Bootable Linux image already configured to mine Cryptonight (and all variants) while taking advantage of CPUs with eDRAM (L4 Cache).  FAQ will be underneath instructions.

Software/Hardware/Settings needed:
- Rufus:  https://rufus.akeo.ie/downloads/rufus-2.18.exe
- A USB stick larger than 3 GB
- UEFI enabled in the BIOS on the machine you will be using to boot into linux

Media Creation Instructions (in Windows):

1.  Unzip the miner.zip file, which should leave you with an ISO file.
2.  Insert your USB drive and open Rufus. For Partition Scheme select (GPT Partition scheme for EUFI).  Toward the bottom of the window look for the checkbox that says "create a bottable disk using"  Click the the cd-rom icon and browse to where the ISO file is.  After selecting it, the option should say "DD Image"
3.  Click Start, the image will be written to the USB drive.


Usage:

On the host computer, insert the USB drive and turn on the computer.  Different computer models will vary, but generally hitting f12 at startup will take you to the boot options screen which will allow you to boot into Ubuntu on the USB stick.

Login Credentials:
username: miner
password: 23Miner80

In the default directory after logging in, there will be 2 directories:  XMR-Stak and XMRig.  Both programs have already been configured to take advantage of the extra L4 cache and also huge pages.  I recommend using XMRig, but it is technically in Beta so I also included XMR-Stak.

To use XMRig:

1.  Type cd xmrig-2.6.0-beta3\build
2.  to edit the configuration type: nano config.json   (after making changes or to close the program hit CTRL-X)
3.  To run type ./xmrig
4.  CTRL-C  will stop the miner
5.  To retun to the main directory:  cd /home/miner

to use XMR-Stak
1.  type:  cd xmr-stak/build/bin
2.  To edit the config file type:  nano config.txt
3.  To start the miner type: ./xmr-stak (CTRL-C will stop the miner)

To change computer name:  https://www.cyberciti.biz/faq/ubuntu-change-hostname-command/

To find out current ip address type: ifconfig



F.A.Q.

Q.  What processors have this extra eDRAM or L4 Cache?

A.  Any processor that has an Intel Iris Pro GPU embedded on the chip.  To see a list:  https://en.wikipedia.org/wiki/List_of_Intel_graphics_processing_units

Q.  Why did you create this Portable Ubuntu miner?

A.  While discussing mining cryptonight with these processors on Bitcointalk it became apparent that many of the people wanting to take advantage of the extra cache knew very little about Linux and were using Windows.  I believe the overhead of windows negatively affects hashrate so I tried to make this as simple as possible.

Q.  Are there any known issues?

A.  XMR-Stak will eventually drop the hashrate to half (restarting the miner fixes this).  I believe there is a bug in their software and that is why I recommend XMRig.
