# TcpTcbReceive

- ea: `0x140031340`
- end: `0x14003312d`
- name: `TcpTcbReceive`
- size: `7661`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, _QWORD *, _QWORD *, int *, _QWORD *)`
- caller_count: `3`
- callee_count: `46`
- tags: `installer_update`

## callers

- `0x140030160`
- `0x1400fba9c`
- `0x1400fc7b8`

## callees

- `0x140009590`
- `0x14000cbf0`
- `0x14000de40`
- `0x14000ec08`
- `0x14000f128`
- `0x14000f4f0`
- `0x1400121c0`
- `0x140014420`
- `0x140018578`
- `0x14002fe38`
- `0x140030fdc`
- `0x140031160`
- `0x140031300`
- `0x140031340`
- `0x140033140`
- `0x140034500`
- `0x14003dabc`
- `0x14003de94`
- `0x140040ca0`
- `0x140040d18`
- `0x140041ce0`
- `0x14005d040`
- `0x14007ef10`
- `0x1400a136c`
- `0x1400a2910`
- `0x1400a2980`
- `0x1400a2d20`
- `0x1400a3020`
- `0x1400a4bc0`
- `0x1400a5500`
- `0x1400b85e0`
- `0x1400b8d90`
- `0x1400b8df8`
- `0x1400dd1f0`
- `0x14010af14`
- `0x14011368c`
- `0x14012af14`
- `0x140134d40`
- `0x1401529c8`
- `0x140152a44`
- `0x14015362c`
- `0x140153938`
- `0x140154f10`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!PsUpdateNetworkCounters` at `0x140031729`
- `ntoskrnl!PsUpdateNetworkCounters` at `0x140031729`
- `ntoskrnl!KeBugCheck` at `0x140031667`
- `ntoskrnl!KeBugCheck` at `0x140031667`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140031815`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140031815`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140031709`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140031c4d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140031709`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140031c4d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031875`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031875`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003236b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400324ac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400326be`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003273e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003236b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400324ac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400326be`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003273e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400323e6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003252f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140032694`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140032714`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140032dab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400323e6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003252f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140032694`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140032714`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140032dab`
- `NETIO!WfpStreamInspectReceive` at `0x140032913`
- `NETIO!WfpStreamInspectReceive` at `0x140032913`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x1400323c3`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x14003250c`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140032d88`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x1400323c3`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x14003250c`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140032d88`
- `NETIO!RtlResumeTimerWheel` at `0x1400323b0`
- `NETIO!RtlResumeTimerWheel` at `0x1400324f9`
- `NETIO!RtlResumeTimerWheel` at `0x140032d71`
- `NETIO!RtlResumeTimerWheel` at `0x1400323b0`
- `NETIO!RtlResumeTimerWheel` at `0x1400324f9`
- `NETIO!RtlResumeTimerWheel` at `0x140032d71`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140032399`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400324e3`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140032d5a`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140032399`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400324e3`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140032d5a`
- `HAL!KeQueryPerformanceCounter` at `0x14003241c`
- `HAL!KeQueryPerformanceCounter` at `0x14003241c`

## pseudocode

```c

```
