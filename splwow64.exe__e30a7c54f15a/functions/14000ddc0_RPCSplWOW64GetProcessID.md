# RPCSplWOW64GetProcessID

- ea: `0x14000ddc0`
- end: `0x14000ddc7`
- name: `RPCSplWOW64GetProcessID`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000ddc0`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall RPCSplWOW64GetProcessID()
{
  return GetCurrentProcessId();
}

```

## disassembly

```asm
0x14000ddc0  jmp     cs:__imp_GetCurrentProcessId
```
