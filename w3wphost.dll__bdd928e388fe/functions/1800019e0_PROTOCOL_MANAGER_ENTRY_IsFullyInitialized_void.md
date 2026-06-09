# PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(void)

- ea: `0x1800019e0`
- end: `0x1800019fc`
- name: `?IsFullyInitialized@PROTOCOL_MANAGER_ENTRY@@QEAAHXZ`
- size: `28`
- prototype: `__int64 __fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001970`
- `0x180009630`

## callees

- `0x1800019e0`

## pseudocode

```c
_BOOL8 __fastcall PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(PROTOCOL_MANAGER_ENTRY *this)
{
  return *((_DWORD *)this + 78) && *((int *)this + 79) >= 0;
}

```

## disassembly

```asm
0x1800019e0  mov     eax, [rcx+138h]
0x1800019e6  test    eax, eax
0x1800019e8  jz      short loc_1800019F9
0x1800019ea  cmp     dword ptr [rcx+13Ch], 0
0x1800019f1  jl      short loc_1800019F9
0x1800019f3  mov     eax, 1
0x1800019f8  retn
0x1800019f9  xor     eax, eax
0x1800019fb  retn
```
