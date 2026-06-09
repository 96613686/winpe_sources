# DescendingStringLengthCompare

- ea: `0x18001be50`
- end: `0x18001be65`
- name: `DescendingStringLengthCompare`
- size: `21`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001be50`

## pseudocode

```c
__int64 __fastcall DescendingStringLengthCompare(_WORD *a1, _WORD *a2)
{
  unsigned __int16 v2; // ax

  v2 = a1[1];
  if ( v2 == a2[1] )
    return 0;
  else
    return v2 < a2[1] ? 1 : -1;
}

```

## disassembly

```asm
0x18001be50  movzx   eax, word ptr [rcx+2]
0x18001be54  cmp     ax, [rdx+2]
0x18001be58  jnz     short loc_18001BE5D
0x18001be5a  xor     eax, eax
0x18001be5c  retn
0x18001be5d  sbb     eax, eax
0x18001be5f  and     eax, 2
0x18001be62  dec     eax
0x18001be64  retn
```
