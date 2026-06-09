# ReadMSDTCEnabledOnWCOWFabricProperty(bool &)

- ea: `0x100424800`
- end: `0x100424979`
- name: `?ReadMSDTCEnabledOnWCOWFabricProperty@@YAJAEA_N@Z`
- size: `377`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100425030`

## callees

- `0x100423970`
- `0x100424800`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10042495e`
- `KERNEL32!HeapFree` at `0x10042495e`
- `KERNEL32!GetProcessHeap` at `0x10042489b`
- `KERNEL32!GetProcessHeap` at `0x100424950`
- `KERNEL32!GetProcessHeap` at `0x10042489b`
- `KERNEL32!GetProcessHeap` at `0x100424950`
- `KERNEL32!HeapAlloc` at `0x1004248ac`
- `KERNEL32!HeapAlloc` at `0x1004248ac`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x100424860`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x100424907`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x100424860`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x100424907`
- `hostregdll!HostReg_GetApplicationName` at `0x100424827`
- `hostregdll!HostReg_GetApplicationName` at `0x1004248cd`
- `hostregdll!HostReg_GetApplicationName` at `0x100424827`
- `hostregdll!HostReg_GetApplicationName` at `0x1004248cd`

## string_xrefs

- `0x10042491d`: `Failed reading MSDTCEnabled fabric property.\n`
- `0x10042493e`: `MSDTCEnabled fabric property successfully read. Setting MSDTC Enabled value to %d.\n`

## pseudocode

```c

```
