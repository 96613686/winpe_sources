# SclSecurityGetDescriptor

- ea: `0x180001b98`
- end: `0x180001bb7`
- name: `SclSecurityGetDescriptor`
- size: `31`
- prototype: `NTSTATUS __fastcall(void *, void *, ULONG, ULONG *LengthNeeded)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800088bc`
- `0x180008be0`
- `0x1800121d4`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x180001bac`
- `ntdll!NtQuerySecurityObject` at `0x180001bac`

## pseudocode

```c
NTSTATUS __fastcall SclSecurityGetDescriptor(void *a1, void *a2, ULONG a3, ULONG *LengthNeeded)
{
  return NtQuerySecurityObject(a1, 0x1Fu, a2, a3, LengthNeeded);
}

```

## disassembly

```asm
0x180001b98  sub     rsp, 38h
0x180001b9c  mov     [rsp+38h+LengthNeeded], r9; LengthNeeded
0x180001ba1  mov     r9d, r8d; Length
0x180001ba4  mov     r8, rdx; SecurityDescriptor
0x180001ba7  mov     edx, 1Fh; SecurityInformation
0x180001bac  call    cs:__imp_NtQuerySecurityObject
0x180001bb2  add     rsp, 38h
0x180001bb6  retn
```
