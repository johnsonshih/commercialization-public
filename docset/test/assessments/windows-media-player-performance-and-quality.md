---
title: Windows Media Player Performance and Quality
description: Windows Media Player Performance and Quality
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0c0c1485-ab34-42a4-bcc7-690b09b51347
ms.prod: W10
ms.mktglfcycl: plan
ms.sitesec: msdn
---

# Windows Media Player Performance and Quality


The Windows Media Player Performance and Quality assessment starts Windows Media Player and plays multiple media clips one after another. The focus of this assessment is on the quality and performance of steady-state playback in Windows Media Player, which mimics the workload of a user watching a movie. The results produced by this assessment can help you assess media playing capabilities and performance and quality issues. This assessment does not evaluate any seeking or pausing functionality. For more information about the results that are produced by this assessment, see [Results for the Windows Media Player Performance and Quality Assessment](results-for-the-windows-media-player-performance-and-quality-assessment.md).

The following graphic illustrates the assessment process.

![workflow graphic for windows media player p & q](images/dep-win8-8-techref-wmpassessmentflow.jpg)

In this topic:

-   [System Requirements](#bkmk-systemrequirements)

-   [Settings](#assesssettings)

## <a href="" id="bkmk-systemrequirements"></a>System Requirements


When running this assessment on Windows 8.1, make sure the **Collect Analysis Trace** setting is unchecked when assessing expected battery life. When checked, this option will produce an incorrect estimation.

Enable analysis trace collection only when you need additional information to investigate other energy-related problems.

You can run this assessment on the following operating systems:

-   Windows 8

-   Windows 10

Supported architectures include x86-based and x64-based systems.

## <a href="" id="assesssettings"></a>Settings


By default, this assessment uses the recommended settings. Microsoft defines these settings so that you can compare the results across multiple computer configurations or over time on the same computer. When you review the results, the run information includes metadata that indicates whether the assessment used the recommended settings.

The following table describes the assessment settings, recommended values, and alternative values for each setting.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Use recommended settings</p></td>
<td><p>Specifies whether the assessment uses the recommended settings. By default, this check box is selected. To change the settings for this assessment, you must first clear this check box.</p></td>
</tr>
<tr class="even">
<td><p>Content path</p></td>
<td><p>Specifies the source folder for the media files. By default, the folder is located at <code>..\Content\Streaming Media Assessment</code>. You can use the media files in the default location or specify a different folder. If you supply your own media files, the assessment supports the use of a network folder.</p></td>
</tr>
<tr class="odd">
<td><p>Test pass type</p></td>
<td><p>Specifies a power option for the assessment. Select one of the following options from the drop-down list. By default, the power option on a laptop is <strong>Tests on AC and DC</strong>.</p>
<ul>
<li><p><strong>Tests on AC and DC</strong></p></li>
<li><p><strong>Tests on AC only</strong></p></li>
<li><p><strong>Tests on DC only</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## Related topics


[Windows Assessment Toolkit](windows-assessment-toolkit-technical-reference.md)

[Assessments](assessments.md)

[Results for the Windows Media Player Performance and Quality Assessment](results-for-the-windows-media-player-performance-and-quality-assessment.md)

[Media Transcoding Performance](media-transcoding-performance.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_assessments\p_assessments%5D:%20Windows%20Media%20Player%20Performance%20and%20Quality%20%20RELEASE:%20%285/3/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




