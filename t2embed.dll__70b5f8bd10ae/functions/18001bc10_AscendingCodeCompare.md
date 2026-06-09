# AscendingCodeCompare

- ea: `0x18001bc10`
- end: `0x18001bc23`
- name: `AscendingCodeCompare`
- size: `19`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001bc10`

## pseudocode

```c
__int64 __fastcall AscendingCodeCompare(_WORD *a1, _WORD *a2)
{
  if ( *a1 == *a2 )
    return 0;
  else
    return *a1 < *a2 ? -1 : 1;
}

```

## disassembly

```asm
0x18001bc10  movzx   eax, word ptr [rcx]
0x18001bc13  cmp     ax, [rdx]
0x18001bc16  jz      short loc_18001BC20
0x18001bc18  sbb     eax, eax
0x18001bc1a  and     eax, 0FFFFFFFEh
0x18001bc1d  inc     eax
0x18001bc1f  retn
0x18001bc20  xor     eax, eax
0x18001bc22  retn
```
