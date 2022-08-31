# NoNahimic
Disable the A-Volute/Nahimic "audio effects service" auto-installed with Realtek audio drivers on certain PCs. 

## Confirmed Devices
* Dell G7 7590
* MSI GS65 Stealth Thin 8RF
* MSI GP73 Leopard 8RE

Pull requests are welcome if different devices have different hardware IDs for this service.

## How to check your Device Hardware IDs
There are two different devices to check.
1. Open Device Manager (WinKey + X, M)
2. Select "Sound, video and game controllers"
3. Do shared steps below for "Nahimic mirroring device"
4. Select "Software components"
5. Do shared steps below for "A-Volute *" device (for example, A-Volute Nh3 Audio Effects Component)

### Shared Steps
1. Find nahimic/a-volute related device
2. Double Click or Right Click->Properties the entry
3. Select "Details" Tab, Click "Property" drop down, then pick "Hardware Ids"
4. The value shown is a hardware ID to block

## Currently Blocked Hardware IDs
* ROOT\Nahimic_Mirroring
* SWC\VEN_AVOL&AID_0300
* SWC\VEN_AVOL&AID_0400

## Next Steps (WIP)
If the above was not done on a fresh Windows installation before Internet was connected, you likely will already have nahimic components installed.

1. Uninstall Nahimic Companion
2. Uninstall Nahimic App
3. Stop NahimicService from running in Task Manager, there is likely 32-bit and 64-bit service both running.
4. Open Services (can be done from Task Manager), Find NahimicService(s), and set them to "Disabled" instead of "Automatic" 
5. Remove Nahimic/A-Volute tasks under Task Scheduler -> Task Scheduler Library
6. Remove Nahimic/A-Volute AppData
7. Delete System32/A-Volute and System32/NahimicService EXEs

## Why remove Nahimic?
* Adversely affects audio capture- 'muffling' the recorded desktop audio
* "Privacy" Policy https://www.nahimic.com/privacy-policy-apps/ and https://www.nahimic.com/privacy-policy-gdpr/
* Can interfere with other post processing applications
* Performance

