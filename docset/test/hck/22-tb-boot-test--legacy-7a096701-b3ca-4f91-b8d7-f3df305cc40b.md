---
author: joshbax-msft
title: 2.2 TB Boot Test (Legacy)
description: 2.2 TB Boot Test (Legacy)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f16e2ee0-f5d6-44eb-809f-5df5ea1be4fd
---

# 2.2 TB Boot Test (Legacy)


This test checks the consistency of the reported disk size in a preBoot and a Windows environment. The drive size reported in the preBoot environment should match exactly the drive size reported in Windows. Because the preBoot device driver is different from the Windows device driver, the test must check for consistency of the reported drive capacity in order to ensure that disk accesses do not encounter problems caused by a variance in the reported sizes.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Storage.Controller.BootDeviceGreaterThan.BasicFunction</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows Server 2008 x64 Windows Server 2008 x86</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~10 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements for the kind of storage controller that you are testing. See. [Storage Adapter or Controller Testing Overview](storage-adapter-or-controller-testing-overview.md) for more information.

Before starting the test, you must first ensure that the boot drive is attached to the test adapter and on a machine that supports Secure Boot where Secure Boot is disabled. In Windows, the test configures the boot configuration to boot into a preOS environment during the next reboot to run the test cases. The computer reboots to the preBoot environment to allow the preBoot test cases to run. When the test cases are finished, the computer reboots back to the Windows environment to collect the logs and determine the test results.

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Storage Testing](troubleshooting-devicestorage-testing.md).

**Mismatch in preOS and Windows last block error**

The test ensures that these two values are the same. If they are different, there may be an error. Before the test restarts the machine to run the preBoot test cases, it allocates space in a file for the results from the preBoot test cases. This file is initially empty, but is filled by the preBoot test cases. If they do not run however, the file will remain empty and when it is compared against the size from windows it will report this error. The root cause is that the preBoot tests did not actually run because some component prevented them from executing. BitLocker has been observed to cause issues with running preBoot content and should be disabled before running the test.

**Could not disable the integrity check. 0xc0430002** or **Could not add the preos tool to the bootsequence. 0xc0430002**

This indicates that some component is preventing the preBoot application from being entered into the boot sequence. It is usually caused by having Secure Boot enabled. Disable Secure Boot and run the test again.

## More information


### Command usage

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TwoTBBootTest.exe /device “[DiskDeviceObjLink]”</strong></p></td>
<td><p>Configures the preBoot environment.</p>
<p>DiskDeviceObjLink example: \\.\PhysicalDrive0</p></td>
</tr>
<tr class="even">
<td><p><strong>TwoTBBootTest.exe /createlogs</strong></p></td>
<td><p>Generate the log files.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
For command-line help for this test binary, type **/?**.

 

### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TwoTBBootTest.exe</strong></p></td>
<td><p>The command line options for the test are listed below.</p></td>
</tr>
<tr class="even">
<td><p><strong>/nc</strong></p></td>
<td><p>Do not clean up the folders and BCD objects created by the tool. This switch can be used for debugging purposes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>/createLogs</strong></p></td>
<td><p>The tool needs to be run with this switch after the preOS tool has been run to create wtt log files.</p></td>
</tr>
<tr class="even">
<td><p><strong>/device</strong></p></td>
<td><p>The boot device containing the boot drive to be run against.</p></td>
</tr>
</tbody>
</table>

 

### File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TwoTBBootTest.exe</p></td>
<td><p><em>&lt;TestBinRoot&gt;\NTTest\BaseTest\boot\TwoTBBootTest\</em></p></td>
</tr>
<tr class="even">
<td><p>TwoTBBootTest.wim</p></td>
<td><p><em>&lt;TestBinRoot&gt;\NTTest\BaseTest\boot\TwoTBBootTest\</em></p></td>
</tr>
<tr class="odd">
<td><p>TwoTBBootTestPreOS.efi</p></td>
<td><p><em>&lt;TestBinRoot&gt;\NTTest\BaseTest\boot\TwoTBBootTest\</em></p></td>
</tr>
<tr class="even">
<td><p>TwoTBBootTestPreOS.exe</p></td>
<td><p><em>&lt;TestBinRoot&gt;\NTTest\BaseTest\boot\TwoTBBootTest\</em></p></td>
</tr>
</tbody>
</table>

 

 

 





