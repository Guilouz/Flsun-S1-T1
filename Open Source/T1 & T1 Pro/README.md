# FLSUN T1 & T1 Pro

<img width="900" src="https://github.com/user-attachments/assets/3d38a152-6b93-4812-94ee-6f0f924a9fef">

<br /><br />

This exploit allows to free SSH access on **T1** and **T1 Pro**.

<br />

> [!CAUTION]  
> **FLSUN does not oﬀer any system restore images, do this only if you know what you are doing.**<br />
> **Neither I nor FLSUN will be held responsible if something goes wrong.**

<br />

This exploit has been confirmed to work on the following firmware versions:
  - T1 → 1.0.8.7
  - T1 Pro → 1.0.0.11

<br />

### TABLE OF CONTENTS:

- :zap: [HOW TO USE EXPLOIT](#zap-how-to-use-exploit)
- :link: [CONNECT TO SSH](#link-connect-to-ssh)
- :earth_americas: [BLOCK / RESTORE OTA UPDATES](#earth_americas-block--restore-ota-updates)
- :question: [QUESTIONS / ANSWERS](#question-questions--answers)

<br /><br />

## :zap: HOW TO USE EXPLOIT

<br />

- Download and unzip [SSH Access - T1 & T1 Pro.zip](https://github.com/Guilouz/Flsun-S1-T1/raw/refs/heads/main/Open%20Source/T1%20&%20T1%20Pro/SSH%20Access%20-%20T1%20&%20T1%20Pro.zip)

- Go to your **Mainsail** Web interface from your Web browser then select the **`MACHINE`** tab on the left side and drag and drop **`plr.sh`**, **`ssh.sh`** and **`ssh.cfg`** files from **`files`** folder.

- Open **`printer.cfg`** file and add this line at the top:
   
    ```
    [include ssh.cfg]
    ```

- Once done, click on **`SAVE & RESTART`** button at the top right to save the file.

- Select the **`CONSOLE`** tab on the left and run this command to backup original file:

    ```
    SSH_STEP_1
    ```

- Then run this command to copy modified file to the dedicated folder:

    ```
    SSH_STEP_2
    ```

- Then run this command to start the process:

    ```
    SSH_STEP_3
    ```

- Then run this command to restore original file:

    ```
    SSH_STEP_4
    ```

- You must have this:

   <img width="1000" src="https://github.com/user-attachments/assets/9f6de695-2a4f-4826-9a79-37a3b7e9f853">

- Then run this command to restart the printer:

    ```
    SSH_STEP_5
    ```

- After the printer restarts, the process will start. It takes few minutes. Do not do anything on the machine and just wait for it to restart.

<br />

**_Note:_** A log file **`ssh_log.txt`** will be created in **`/home/pi/printer_data/config`** to ensure everything worked as expected.

<br /><br />

## :link: CONNECT TO SSH

<br />

- Download and install latest **MobaXterm** software here: [https://mobaxterm.mobatek.net/download-home-edition.html](https://mobaxterm.mobatek.net/download-home-edition.html)

- Launch it then click on the **`Session`** icon:

    <img width="1000" src="https://github.com/user-attachments/assets/a5a213e3-98bf-4205-90dd-1d0663d1f7e7">

- Then on then **`SSH`** icon and enter the IP address of your machine in the **`Remote host`** field, check the **`Specify username`** box and enter the username **`pi`** in the field then click on **`OK`**:

    <img width="700" alt="Sans titre" src="https://github.com/user-attachments/assets/36ae1420-c466-401f-bdbc-31cff2673dda">

- At the connection, you will be asked for a password: **`flsun`**

- You now have SSH access to your machine with these credentials:

   User: **`pi`** <br />
   Password: **`flsun`**
   <br /><br />
   User: **`root`** <br />
   Password: **`flsun`**

- Enjoy :smiley:

    <img width="1000" alt="Capture d’écran 2024-12-05 à 20 24 43" src="https://github.com/user-attachments/assets/ac98efd1-7b5c-4396-a5fd-2a55aa28ac2f">

- I recommend first making a backup of the **`/home/pi`** folder in case of issues.

<br /><br />

## :earth_americas: BLOCK / RESTORE OTA UPDATES

<br />

**If you want to block OTA updates:**

- Connect to SSH and enter these commands (one at time):

    ```
    echo "0.0.0.0       flsun-hk-t1.oss-cn-hongkong.aliyuncs.com" | sudo tee -a /etc/hosts
    ```
    
    ```
    echo "::0           flsun-hk-t1.oss-cn-hongkong.aliyuncs.com" | sudo tee -a /etc/hosts
    ```

    ```
    echo "0.0.0.0       api.flsunworld.com" | sudo tee -a /etc/hosts
    ```

    ```
    echo "::0           api.flsunworld.com" | sudo tee -a /etc/hosts
    ```
   	
<br />

**If you want to restore OTA updates:**

- Connect to SSH and enter these commands (one at time):

    ```
    sed -i '/flsun-hk-t1.oss-cn-hongkong.aliyuncs.com/d' /etc/hosts
    ```

    ```
    sed -i '/api.flsunworld.com/d' /etc/hosts
    ```

<br /><br />

## :question: QUESTIONS / ANSWERS

<br />

- **What I can do with SSH access?**

    - This allows you to have full access to the system, to install new things (Spoolman for example), to be free to do what you want on the machine. Many of the elements used on the printer are open source, so they should be easily accessible.

- **Can I update when a new firmware is available?**

    - Yes it is possible but the exploit will have to be redone (provided it is not fixed in future updates, I added an exit door just in case).

- **If I'm not comfortable with Linux, should I do this?**

    - If you don't know and at least understand what you are doing, there is no interest to access to SSH. FLSUN doesn't distribute any recovery image to restore the system in case of a problem, so you have to be careful with what you do or you will render the printer unusable.

- **Can I install Kiauh?**

    - Yes you can. Kiauh is a script that assists you in installing many things on your printer.

- **Can I update Mainsail without issue?**

    - Yes you can. Mainsail is the popular web interface for managing and controlling 3D printers with Klipper.

- **Can I update Moonraker without issue?**

    - Yes you can. Moonraker is a Python 3 based web server that exposes APIs with which client applications may use to interact with Klipper firmware.

- **Can I update Klipper without issue?**

    - It's possible but the old version used by FLSUN has several modifications to support some features (some changes need to be added to the official Klipper version) and the motherboard firmware also needs to be updated.

- **Can I install Moonraker Timalapse?**

    - Yes you can. Moonraker Timelapse is a 3rd party Moonraker component to create timelapse of 3D prints.
