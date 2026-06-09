# TimeZoneSyncTask.Data.SYSTEMTIME::IsValid

- ea: `0xfa00`
- end: `0xfb16`
- name: `TimeZoneSyncTask.Data.SYSTEMTIME::IsValid`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0xfe80`

## callees

- `0xce30`
- `0xfa00`
- `0xfb20`

## pseudocode

```c

```

## disassembly

```asm
0xfa00  ldarg.0
0xfa01  call     instance bool TimeZoneSyncTask.Data.SYSTEMTIME::IsAllZero()
0xfa06  brtrue   loc_FB14
0xfa0b  ldarg.0
0xfa0c  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xfa11  ldc.i4.0
0xfa12  blt.s    loc_FA23
0xfa14  ldarg.0
0xfa15  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xfa1a  ldc.i4.s 0x17
0xfa1c  cgt
0xfa1e  ldc.i4.0
0xfa1f  ceq
0xfa21  br.s     loc_FA24
0xfa23  ldc.i4.0
0xfa24  ldstr    aExpectingWhour// "expecting wHour in range [0, 23]"
0xfa29  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfa2e  ldarg.0
0xfa2f  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMinute
0xfa34  ldc.i4.0
0xfa35  blt.s    loc_FA46
0xfa37  ldarg.0
0xfa38  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xfa3d  ldc.i4.s 0x3B
0xfa3f  cgt
0xfa41  ldc.i4.0
0xfa42  ceq
0xfa44  br.s     loc_FA47
0xfa46  ldc.i4.0
0xfa47  ldstr    aExpectingWminu// "expecting wMinute in range [0, 59]"
0xfa4c  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfa51  ldarg.0
0xfa52  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wSecond
0xfa57  ldc.i4.0
0xfa58  blt.s    loc_FA69
0xfa5a  ldarg.0
0xfa5b  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xfa60  ldc.i4.s 0x3B
0xfa62  cgt
0xfa64  ldc.i4.0
0xfa65  ceq
0xfa67  br.s     loc_FA6A
0xfa69  ldc.i4.0
0xfa6a  ldstr    aExpectingWseco// "expecting wSecond in range [0, 59]"
0xfa6f  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfa74  ldarg.0
0xfa75  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMilliseconds
0xfa7a  ldc.i4.0
0xfa7b  blt.s    loc_FA8F
0xfa7d  ldarg.0
0xfa7e  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMilliseconds
0xfa83  ldc.i4   0x3E7
0xfa88  cgt
0xfa8a  ldc.i4.0
0xfa8b  ceq
0xfa8d  br.s     loc_FA90
0xfa8f  ldc.i4.0
0xfa90  ldstr    aExpectingWmill// "expecting wMilliseconds in range [0, 99"...
0xfa95  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfa9a  ldarg.0
0xfa9b  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wYear
0xfaa0  ldc.i4.0
0xfaa1  ceq
0xfaa3  ldstr    aExpectingRelat// "expecting relative SYSTEMTIME"
0xfaa8  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfaad  ldarg.0
0xfaae  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0xfab3  ldc.i4.1
0xfab4  blt.s    loc_FAC5
0xfab6  ldarg.0
0xfab7  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0xfabc  ldc.i4.s 0xC
0xfabe  cgt
0xfac0  ldc.i4.0
0xfac1  ceq
0xfac3  br.s     loc_FAC6
0xfac5  ldc.i4.0
0xfac6  ldstr    aExpectingWmont// "expecting wMonth in range [1, 12]"
0xfacb  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfad0  ldarg.0
0xfad1  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDay
0xfad6  ldc.i4.1
0xfad7  blt.s    loc_FAE7
0xfad9  ldarg.0
0xfada  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDay
0xfadf  ldc.i4.5
0xfae0  cgt
0xfae2  ldc.i4.0
0xfae3  ceq
0xfae5  br.s     loc_FAE8
0xfae7  ldc.i4.0
0xfae8  ldstr    aExpectingWdayI// "expecting wDay in range [first, last]"
0xfaed  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfaf2  ldarg.0
0xfaf3  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDayOfWeek
0xfaf8  ldc.i4.0
0xfaf9  blt.s    loc_FB09
0xfafb  ldarg.0
0xfafc  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDayOfWeek
0xfb01  ldc.i4.6
0xfb02  cgt
0xfb04  ldc.i4.0
0xfb05  ceq
0xfb07  br.s     loc_FB0A
0xfb09  ldc.i4.0
0xfb0a  ldstr    aExpectingWdayo// "expecting wDayOfWeek in range [Sun, Sat"...
0xfb0f  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfb14  ldc.i4.1
0xfb15  ret
```
