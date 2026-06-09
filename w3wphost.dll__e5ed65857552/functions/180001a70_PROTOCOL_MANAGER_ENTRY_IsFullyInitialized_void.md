# PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(void)

- ea: `0x180001a70`
- end: `0x180001a8d`
- name: `?IsFullyInitialized@PROTOCOL_MANAGER_ENTRY@@QEAAHXZ`
- size: `29`
- prototype: `__int64 __fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800019f0`
- `0x18000a0f4`

## callees

- `0x180001a70`

## pseudocode

```c
_BOOL8 __fastcall PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(PROTOCOL_MANAGER_ENTRY *this)
{
  return *((_DWORD *)this + 78) && *((int *)this + 79) >= 0;
}

```

## disassembly

```asm
0x180001a70  mov     eax, [rcx+138h]
0x180001a76  test    eax, eax
0x180001a78  jz      short loc_180001A8A
0x180001a7a  cmp     dword ptr [rcx+13Ch], 0
0x180001a81  jl      short loc_180001A8A
0x180001a83  mov     eax, 1
0x180001a88  retn
0x180001a8a  xor     eax, eax
0x180001a8c  retn
```
