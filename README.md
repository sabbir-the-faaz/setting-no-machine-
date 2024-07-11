# setting-no-machine-

### check : https://www.nomachine.com/getting-started-with-nomachine
<div class="col-12 kb-max-width ml-2">
                <h2 id="kb-1" class="kb-content-title" style="line-height: initial; word-break: break-word;">Tips for using NoMachine on NVIDIA Jetson Nano</h2>                <div class="kb-content tableRowLast" id="kb-content">
                    <p>
	NoMachine can be installed on a Jetson Nano out-of-the-box. There are a couple of tweaks to consider if you are using your Nano as a headless server.</p>
<p>
	This article assumes that you have already installed the appropriate Ubuntu image dedicated to this device from the Nvidia website (<a href="https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit">https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit</a>) and the device is ready.</p>
<p>
	<br>
	<strong>Install NoMachine </strong></p>
<p>
	Go to the NoMachine website and download the DEB package for ARMv8:<br>
	<a href="https://www.nomachine.com/download/linux&amp;id=30&amp;s=ARM">https://www.nomachine.com/download/linux&amp;id=30&amp;s=ARM</a></p>
<p>	or download with wget command:<br>
	wget https://www.nomachine.com/free/arm/v8/deb -O nomachine.deb</p>
<p>	Then install NoMachine with the 'dpkg' command. For example if you downloaded with mentioned wget:<br>
	sudo dpkg -i nomachine.deb</p>
<p>
	<strong>IMPORTANT - For headless system users</strong></p>
<p>
	If you don't want to connect a monitor to your device and don't need to have xserver running:</p>
<p>	Disable the xserver using:<br>
	sudo systemctl disable gdm3 --now</p>
<p>	(if Xserver was disabled after NoMachine installation, you will need to restart nxserver: sudo /usr/NX/bin/nxserver --restart).</p>
<p>
	<br>
	<strong>Further considerations</strong><br>
	We suggest you install an alternative Desktop Environment (Xfce) to Unity, which is default on Jetson Nano Ubuntu. That's because on Unity there can be some minor issues, such as the blinking of the system menu.</p>
<p>
	Install Xfce4 desktop environment:<br>
	sudo apt install xfce4</p>
<p>	If you wish to continue to with XFCE as a headless machine:</p>
<p>	<strong>Step 1</strong> - Disable the xserver using:<br>
	sudo systemctl set-default multi-user.target</p>
<p>	(if Xserver was disabled after NoMachine installation, you will need to restart nxserver: sudo /usr/NX/bin/nxserver --restart).</p>
<p>	<strong>Step 2</strong> - Configure NoMachine for the Xfce desktop<br>
	Installing and using an alternative DE means that the start command for that desktop must be added to the NoMachine node configuration. Since Xfce is the chosen desktop environment:</p>
<p>	1. Edit node configuration file: sudo vim /usr/NX/etc/node.cfg<br>
	2. Find DefaultDesktopCommand key and change line to following: DefaultDesktopCommand "/usr/bin/startxfce4"<br>
	3. Save the changes.</p>
<p>	Now, go to your connecting client, install NoMachine for your OS and follow the instructions of the "Getting Started Guide". (https://www.nomachine.com/getting-started-with-nomachine)</p>
<p>	Once authenticated on your remote Nano, you should be able to create a session with the xfce4 desktop.</p>
<p>	To ensure NoMachine is ready for access, please consult the guidelines here: <a href="https://www.nomachine.com/getting-started-with-nomachine">https://www.nomachine.com/getting-started-with-nomachine</a></p>
                    <div id="kb-to-top" style="opacity: unset;" onclick="kb_to_top()"></div>
                </div>
                <div id="kb-print" style="line-height:initial;">
                    <div class="onprint_display" style="display: none; padding-left: 15px">
    <div class="container kb-left-right-0">
        <div class="onprint_display" id="no_pdf" style="display: none">
            <img style="padding-top:5px; " src="https://assets.nomachine.com/img/kb/print-logo.png">
            <hr>
            <h1 id="kb_title" class="entry-title" style="font-size: 30px">Tips for using NoMachine on NVIDIA Jetson Nano</h1>        </div>


        
      
   
<p>
	This article assumes that you have already installed the appropriate Ubuntu image dedicated to this device from the Nvidia website (<a href="https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit">https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit</a>) and the device is ready.</p>
<p>
	<br>
	<strong>Install NoMachine </strong></p>
<p>
	Go to the NoMachine website and download the DEB package for ARMv8:<br>
	<a href="https://www.nomachine.com/download/linux&amp;id=30&amp;s=ARM">https://www.nomachine.com/download/linux&amp;id=30&amp;s=ARM</a></p>
<p>	or download with wget command:<br>
	wget https://www.nomachine.com/free/arm/v8/deb -O nomachine.deb</p>
<p>	Then install NoMachine with the 'dpkg' command. For example if you downloaded with mentioned wget:<br>
	sudo dpkg -i nomachine.deb</p>
<p>
	<strong>IMPORTANT - For headless system users</strong></p>
<p>
	If you don't want to connect a monitor to your device and don't need to have xserver running:</p>
<p>	Disable the xserver using:<br>
	sudo systemctl disable gdm3 --now</p>
<p>	(if Xserver was disabled after NoMachine installation, you will need to restart nxserver: sudo /usr/NX/bin/nxserver --restart).</p>
<p>
	<br>
	<strong>Further considerations</strong><br>
	We suggest you install an alternative Desktop Environment (Xfce) to Unity, which is default on Jetson Nano Ubuntu. That's because on Unity there can be some minor issues, such as the blinking of the system menu.</p>
<p>
	Install Xfce4 desktop environment:<br>
	sudo apt install xfce4</p>
<p>	If you wish to continue to with XFCE as a headless machine:</p>
<p>	<strong>Step 1</strong> - Disable the xserver using:<br>
	sudo systemctl set-default multi-user.target</p>
<p>	(if Xserver was disabled after NoMachine installation, you will need to restart nxserver: sudo /usr/NX/bin/nxserver --restart).</p>
<p>	<strong>Step 2</strong> - Configure NoMachine for the Xfce desktop<br>
	Installing and using an alternative DE means that the start command for that desktop must be added to the NoMachine node configuration. Since Xfce is the chosen desktop environment:</p>
<p>	1. Edit node configuration file: sudo vim /usr/NX/etc/node.cfg<br>
	2. Find DefaultDesktopCommand key and change line to following: DefaultDesktopCommand "/usr/bin/startxfce4"<br>
	3. Save the changes.</p>
<p>	Now, go to your connecting client, install NoMachine for your OS and follow the instructions of the "Getting Started Guide". (https://www.nomachine.com/getting-started-with-nomachine)</p>
<p>	Once authenticated on your remote Nano, you should be able to create a session with the xfce4 desktop.</p>
<p>	To ensure NoMachine is ready for access, please consult the guidelines here: <a href="https://www.nomachine.com/getting-started-with-nomachine">https://www.nomachine.com/getting-started-with-nomachine</a></p>

</div>                </div>
            </div>
