## Command description
This operation will test a physical device for its read capabilities. If the media is removable, it will ask you to insert different media on it, as read capabilities vary with different media. The report will be saved in the executing directory, and sent to us. Shared reports can be seen in https://www.aaru.app

## Command usage

```aaru -d [true/false] -v [true/false] device-report -h [true/false] <device-path/aaru-remote-host>```

```-d, --debug [true/false]``` shows debug output *(default false)*

```-v, --verbose [true/false]``` shows verbose output *(default false)*

```-h, --help [true/false]``` shows help screen for the command instead of running it, ignores all other switches *(default false)*

```<aaru-remote-host>``` connects to an Aaru Remote Host with ```aaru://<IP ADDRESS>/<DEVICE PATH>```

## Example
FreeBSD: ```aaru device-report /dev/cd0```

Linux: ```aaru device-report /dev/sdb```

Windows: ```aaru device-report \\.\PhysicalDrive3```

## Operating system support
|Device type|FreeBSD|macOS|Linux|Windows|
|---|---|---|---|---|
|SCSI Block device|Yes|No(1)|Yes|Yes|
|SCSI MultiMedia device|Yes|Not yet(2)|Yes|Yes|
|SCSI Streaming device|Yes|No(1)|Yes|Yes|
|Parallel ATA|No(3)|No(1)|Yes|Yes|
|Serial ATA|Yes|No(1)|Yes|Yes|
|USB|Partial(4)|Partial(5)|Yes|Yes|
|FireWire|Partial(6)|Partial(5)|Yes|Partial(6)|
|PCMCIA|Partial(7)|Partial(5)|Yes|Partial(7)|
|SecureDigital / MultiMediaCard|Not yet(8)|No(1)|Yes|Untested(9)|

1. macOS only allows talking with MultiMedia devices
2. Support for MultiMedia devices in macOS will be added if users require it
3. Not supported due to upstream bug
4. USB descriptors are not retrieved
5. Only MultiMedia devices can be supported and descriptors will not be retrieved
6. FireWire descriptors are not retrieved
7. PCMCIA CIS is not retrieved 
8. Support will come with FreeBSD 12-RELEASE
9. Should work, untested due to not available hardware

