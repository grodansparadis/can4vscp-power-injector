

Here the events sent by the module is described.

<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="http://www.vscp.org/docs/vscpspec/doku.php?id=class1.data#type_6_0x06_count_value">CLASS1.DATA (15) Type=6, Count Value</a></td>
<td>Count data steam event sent on regular intervals if activated. Coding: Integer. Unit: none.<br />
<br />
<strong><span class="underline">Byte 0</span></strong><br />
<a href="http://www.vscp.org/docs/vscpspec/doku.php?id=data_coding">Datacoding:</a> 0b<span class="underline">011</span>00<span class="underline">xxx</span> where xxx is the counter (0-3/4-7)<br />
<br />
<strong>0x60</strong> - Counter 0<br />
<strong>0x61</strong> - Counter 1<br />
<strong>0x62</strong> - Counter 2<br />
<strong>0x63</strong> - Counter 3<br />
<br />
<strong><span class="underline">Byte 1-4</span></strong><br />
Counter value MSB in first byte.</td>
</tr>
<tr class="even">
<td><a href="http://www.vscp.org/docs/vscpspec/doku.php?id=class1.alarm&amp;#type_2_0x02_alarm_occurred">CLASS1.ALARM (1) Type=1, Alarm occurred</a></td>
<td>If an alarm is armed this event is sent when it occurs and the corresponding alarm bit is set in the alarm register.<br />
<br />
<strong>Byte 0</strong> - Channel 0-3 for counter, channel 4-6 for frequency low, channel 7-9 for frequency high.<br />
<strong>Byte 1</strong> - Zone for module.<br />
<strong>Byte 2</strong> - Sub zone for channel.<br />
</td>
</tr>
<tr class="odd">
<td><a href="http://www.vscp.org/docs/vscpspec/doku.php?id=class1.measurement#type_9_0x09_frequency">CLASS1.MEASUREMENT (10) Type=9, Frequency</a></td>
<td>Frequency measurement event sent on regular intervals if activated. Coding: 32-bit integer. Unit: Hertz.<br />
<br />
<strong><span class="underline">Byte 0</span></strong><br />
<a href="http://www.vscp.org/docs/vscpspec/doku.php?id=data_coding">Datacoding:</a> 0b<span class="underline">011</span>00<span class="underline">xxx</span> where xxx is the counter (0-3)<br />
<br />
<strong>0x60</strong> - Counter 0<br />
<strong>0x61</strong> - Counter 1<br />
<strong>0x62</strong> - Counter 2<br />
<strong>0x63</strong> - Counter 3<br />
<br />
<strong><span class="underline">Byte 1-4</span></strong><br />
Frequency value as 32-bit floating point value with MSB in first byte.</td>
</tr>
<tr class="even">
<td><a href="http://www.vscp.org/docs/vscpspec/doku.php?id=class1.measurement">CLASS1.MEASUREMENT (10) Type=x</a></td>
<td>Measurement values of all kinds can be sent as a result of linearization. For example can an input counting S0 pulses be translated to KWh and watt<br />
<br />
The data is always a 32-bit floating point value and the and the counter is in the sensor index bits of the data coding byte. Unit and measurement type is configurable.</td>
</tr>
</tbody>
</table>

  
[filename](./bottom-copyright.md ':include')
