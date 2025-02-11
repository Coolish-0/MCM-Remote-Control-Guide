# MCM-Remote-Control-Guide
Step by step guide on using Remote Control in Microsoft Configuration Manager (MCM) for IT support and troubleshooting.
Remote Control in Microsoft Configuration Manager (MCM) allows IT administrators to remotely troubleshoot and assit users on Windows client machines. This improves efficiency by reducing downtime and eliminating the need for physical access to a device.

Step One: Enable Remote Control in MCM
- On the management PC, open Configuratino Manager Console.
  - Go to Administration>Client Settings.
    - Open Default Client Settings. Or you can create a test client settings.

- Select Remote Tools
  - Select Configure Settings.
    - Check Enalbe Remote Control on client computers.
       - Check Domain, and Private, then select OK.
          - Observe the Device Settings menu and change any selection you see fit.

Step Two: Check Firewall Rules
- Press Windows + R and type wf.msc on the Managment PC.
  - Go to Inbound Rules.
    - Select New Rule.
       - Check Port, then select Next.
          - Choose TCP and enter 2701 in the "Specific local ports" box.
            - Click Next.
              - Select Allow the Connection then click next.
                 - Cheack all porfiles (Domain, Private, Public).
                    - Click Next.
                       - Name the rule "SCCM Remote Control" and click finish.

Step 3: Enable Remote access on the Client (If not already enabled)
- On client PC Press Windows + R and type sysdm.cpl
  - In the properties tab select Remote on the top bar.
    - Under Remote Desktop check "Allow remote connections to this computer".
      - Click Applt and OK

Step 4: Remote Connect to Client PC
- On the Managment PC go back into Microsoft Configuration Manager (MCM)
  - Select Assets and Compliance> Overview> Devices
    - Find Client PC that has remote access allowed from Previous step.
       - Right Click and select Start> Remote Desktop Client
          - Enter Admin Password and login
    
