# CTrace::TraceInternalV(ulong,ushort const *,ushort const *,ushort const *,char *)

- ea: `0x180010b40`
- end: `0x180010ff6`
- name: `?TraceInternalV@CTrace@@AEAAXKPEBG00PEAD@Z`
- size: `1206`
- prototype: `void __usercall(CTrace *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, char *)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180010b00`
- `0x180011000`
- `0x180011050`
- `0x180011060`

## callees

- `0x18000179c`
- `0x180006ffc`
- `0x1800104a0`
- `0x180010b40`
- `0x18001144c`
- `0x180011530`
- `0x180011640`
- `0x18002e468`
- `0x18002f3ba`
- `0x18002f3e0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180010bdc`
- `msvcrt!_vsnwprintf` at `0x180010bdc`
- `msvcrt!wprintf` at `0x180010f8c`
- `msvcrt!wprintf` at `0x180010f8c`
- `KERNEL32!OutputDebugStringW` at `0x180010fa1`
- `KERNEL32!OutputDebugStringW` at `0x180010fb8`
- `KERNEL32!OutputDebugStringW` at `0x180010fa1`
- `KERNEL32!OutputDebugStringW` at `0x180010fb8`

## pseudocode

```c

```
