# InstallServicePerfCounter(ServiceSetupInfo *)

- ea: `0x180039b1c`
- end: `0x180039d06`
- name: `?InstallServicePerfCounter@@YAJPEAUServiceSetupInfo@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct ServiceSetupInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18004086c`

## callees

- `0x180007824`
- `0x180037df0`
- `0x180039b1c`
- `0x180040248`
- `0x18004d030`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180039ca0`
- `KERNEL32!lstrlenW` at `0x180039ca0`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x180039bd8`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x180039bd8`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039cc1`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039cc1`

## pseudocode

```c

```
