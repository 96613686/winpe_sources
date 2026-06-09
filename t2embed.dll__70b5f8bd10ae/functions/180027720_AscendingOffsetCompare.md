# AscendingOffsetCompare

- ea: `0x180027720`
- end: `0x180027733`
- name: `AscendingOffsetCompare`
- size: `19`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027720`

## pseudocode

```c
__int64 __fastcall AscendingOffsetCompare(_DWORD *a1, _DWORD *a2)
{
  unsigned int v2; // eax

  v2 = a1[2];
  if ( v2 == a2[2] )
    return 0;
  else
    return v2 < a2[2] ? -1 : 1;
}

```

## disassembly

```asm
0x180027720  mov     eax, [rcx+8]
0x180027723  cmp     eax, [rdx+8]
0x180027726  jnz     short loc_18002772B
0x180027728  xor     eax, eax
0x18002772a  retn
0x18002772b  sbb     eax, eax
0x18002772d  and     eax, 0FFFFFFFEh
0x180027730  inc     eax
0x180027732  retn
```
