# CipCompareCatalogListEntryByID

- ea: `0x18004430c`
- end: `0x18004431e`
- name: `CipCompareCatalogListEntryByID`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004439c`

## callees

- `0x18004430c`

## pseudocode

```c
__int64 __fastcall CipCompareCatalogListEntryByID(unsigned __int64 a1, __int64 a2)
{
  if ( a1 == *(_QWORD *)(a2 - 8) )
    return 0;
  else
    return a1 < *(_QWORD *)(a2 - 8) ? -1 : 1;
}

```

## disassembly

```asm
0x18004430c  cmp     rcx, [rdx-8]
0x180044310  jnz     short loc_180044316
0x180044312  xor     eax, eax
0x180044314  retn
0x180044316  sbb     eax, eax
0x180044318  and     eax, 0FFFFFFFEh
0x18004431b  inc     eax
0x18004431d  retn
```
