# AscendingRecordIndexCompare

- ea: `0x18001b9f0`
- end: `0x18001ba03`
- name: `AscendingRecordIndexCompare`
- size: `19`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b9f0`

## pseudocode

```c
__int64 __fastcall AscendingRecordIndexCompare(_WORD *a1, _WORD *a2)
{
  if ( *a1 == *a2 )
    return 0;
  else
    return *a1 < *a2 ? -1 : 1;
}

```

## disassembly

```asm
0x18001b9f0  movzx   eax, word ptr [rcx]
0x18001b9f3  cmp     ax, [rdx]
0x18001b9f6  jnz     short loc_18001B9FB
0x18001b9f8  xor     eax, eax
0x18001b9fa  retn
0x18001b9fb  sbb     eax, eax
0x18001b9fd  and     eax, 0FFFFFFFEh
0x18001ba00  inc     eax
0x18001ba02  retn
```
