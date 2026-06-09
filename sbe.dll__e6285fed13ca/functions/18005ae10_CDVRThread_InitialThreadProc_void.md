# CDVRThread::InitialThreadProc(void *)

- ea: `0x18005ae10`
- end: `0x18005ae7e`
- name: `?InitialThreadProc@CDVRThread@@SAKPEAX@Z`
- size: `110`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18005ae10`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18005ae29`
- `KERNEL32!GetModuleHandleW` at `0x18005ae29`
- `KERNEL32!GetProcAddress` at `0x18005ae3e`
- `KERNEL32!GetProcAddress` at `0x18005ae3e`
- `ole32!CoUninitialize` at `0x18005ae6b`
- `ole32!CoUninitialize` at `0x18005ae6b`

## string_xrefs

- `0x18005ae22`: `ole32.dll`

## pseudocode

```c

```
