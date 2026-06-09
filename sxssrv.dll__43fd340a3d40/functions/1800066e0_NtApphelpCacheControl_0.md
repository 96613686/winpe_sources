# NtApphelpCacheControl_0

- ea: `0x1800066e0`
- end: `0x1800066e6`
- name: `NtApphelpCacheControl_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(APPHELPCACHESERVICECLASS Service, PAPPHELP_CACHE_SERVICE_LOOKUP ServiceData)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `ntdll!NtApphelpCacheControl` at `0x1800066e0`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtApphelpCacheControl_0(APPHELPCACHESERVICECLASS Service, PAPPHELP_CACHE_SERVICE_LOOKUP ServiceData)
{
  return NtApphelpCacheControl(Service, ServiceData);
}

```

## disassembly

```asm
0x1800066e0  jmp     cs:__imp_NtApphelpCacheControl
```
