# LoadAcc(HINSTANCE__ *,void *)

- ea: `0x180053ff0`
- end: `0x180054102`
- name: `?LoadAcc@@YAPEAXPEAUHINSTANCE__@@PEAX@Z`
- size: `274`
- prototype: `void *__fastcall(HINSTANCE, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180053f10`
- `0x180053fc0`

## callees

- `0x180053ff0`
- `0x180054108`
- `0x18005413c`

## import_xrefs

- `win32u!NtUserCreateAcceleratorTable` at `0x1800540ca`
- `win32u!NtUserCreateAcceleratorTable` at `0x1800540ca`
- `ntdll!RtlEnterCriticalSection` at `0x180054020`
- `ntdll!RtlEnterCriticalSection` at `0x180054020`
- `ntdll!RtlLeaveCriticalSection` at `0x180054049`
- `ntdll!RtlLeaveCriticalSection` at `0x180054049`
- `ntdll!RtlFreeHeap` at `0x1800540df`
- `ntdll!RtlFreeHeap` at `0x1800540df`
- `ntdll!RtlAllocateHeap` at `0x18005408f`
- `ntdll!RtlAllocateHeap` at `0x18005408f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180054005`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180054005`

## pseudocode

```c

```
