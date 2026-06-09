# GetRemoteInputLanguage(ushort *,ushort *)

- ea: `0x18005fea0`
- end: `0x18005ffaf`
- name: `?GetRemoteInputLanguage@@YAHPEAG0@Z`
- size: `271`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800565e0`

## callees

- `0x18005fea0`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18005ff9d`
- `ntdll!RtlGetActiveConsoleId` at `0x18005ff9d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005fef3`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005fef3`
- `WINSTA!WinStationQueryInformationW` at `0x18005ff23`
- `WINSTA!WinStationQueryInformationW` at `0x18005ff23`

## pseudocode

```c

```
