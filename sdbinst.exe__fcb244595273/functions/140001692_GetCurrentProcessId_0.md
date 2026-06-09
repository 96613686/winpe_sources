# GetCurrentProcessId_0

- ea: `0x140001692`
- end: `0x140001698`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14000b574`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140001692`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetCurrentProcessId_0()
{
  return GetCurrentProcessId();
}

```

## disassembly

```asm
0x140001692  jmp     cs:__imp_GetCurrentProcessId
```
