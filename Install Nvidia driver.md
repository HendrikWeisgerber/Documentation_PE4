# How to install the right Nvidia driver

1. Check wich driver you need. Either with ubuntu-drivers devices or on the Nvidia Website. For that find out Which GPU you have (ZBook: Quadro P1000) https://www.nvidia.co.uk/Download/index.aspx?lang=en-uk
2. Follow this tutorial on youtube: https://www.youtube.com/watch?v=GljujCLixzE
3. In case it didnt work, I also did the following but dont believe its necessary:
   https://wiki.debian.org/KernelModuleBlacklisting
   https://askubuntu.com/questions/841876/how-to-disable-nouveau-kernel-driver


# Further Information

Find out your GPUs
lspci -nnk | grep -i VGA -A2
	01:00.0 VGA compatible controller [0300]: NVIDIA Corporation GP107GLM [Quadro P1000 Mobile] [10de:1cbb] (rev a1)
	Subsystem: Hewlett-Packard Company Device [103c:842c]
	Kernel modules: nvidiafb, nouveau

sudo lshw -c video
  *-display                 
       Beschreibung: VGA compatible controller
       Produkt: GP107GLM [Quadro P1000 Mobile]
       Hersteller: NVIDIA Corporation
       Physische ID: 0
       Bus-Informationen: pci@0000:01:00.0
       Version: a1
       Breite: 64 bits
       Takt: 33MHz
       Fähigkeiten: pm msi pciexpress vga_controller bus_master cap_list rom
       Konfiguration: driver=nouveau latency=0
       Ressourcen: irq:159 memory:e8000000-e8ffffff memory:a0000000-afffffff memory:b0000000-b1ffffff ioport:4000(Größe=128) memory:e9080000-e90fffff




The version of the kernel your system is running 
uname -r
5.4.0-87-generic


To monitor your GPU
nvidia-smi -l 1

## The following steps should be executet with in yout virtual enviroment (maskrcnn)
# Cuda
Check which one you need: https://www.tensorflow.org/install/source#linux
To check wich versions there are through conda
conda search cudatoolkit
To install: 
conda install cudatoolkit==10.0.130

# Cudnn
Log in here and Download runtimlib developerlib and codesample + user guide cudnn 7.4.2 Ubuntu 18.04
https://developer.nvidia.com/rdp/cudnn-archive

# Step by Step tutorial for the right version for cuda & cudnn 
https://gist.github.com/matheustguimaraes/43e0b65aa534db4df2918f835b9b361d
!!!!!!!!!!Important, dont follow the driver installation instructions though
