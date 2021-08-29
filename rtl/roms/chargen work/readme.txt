1. The binary file is not in the proper format for Quartus and needs to be converted to a memory intialization file (MIF).  For that I used srec_cat.exe available from https://sourceforge.net/projects/srecord/files/srecord-win32/

The command line for srec_cat.exe I used was:

srec_cat.exe charset.bin -binary -output chargen.mif -Memory_Initialization_File

2. Now the file is converted to MIF format that Quartus can understand.  Open up the Quartus project of C64_MiSTer and edit the file rom_C64.vhd

3. Look for the reference to the MIF file in fpga64_buslogic.vhd and change it to suit the filename you used for your new chargen MIF file.

4. Compile and you should be good to go.  Your output RBF file should be in the output_files folder.  Copy that to your SD card, rename it if you want.
