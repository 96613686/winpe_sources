# SQLStartupShutdownControl::WaitForComponentsInitialized(void)

- ea: `0x10041a550`
- end: `0x10041a5bb`
- name: `?WaitForComponentsInitialized@SQLStartupShutdownControl@@EEAAXXZ`
- size: `107`
- prototype: `void __fastcall(SQLStartupShutdownControl *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10041a550`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10041a573`
- `KERNEL32!WaitForSingleObject` at `0x10041a573`
- `sqldk!?SOS_OS_BootEvent@@3PEAXEA` at `0x10041a564`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10041a5b0`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10041a5b0`
- `sqldk!?SOS_OS_sm_osProcessStatus@@3KA` at `0x10041a554`

## pseudocode

```c

```
