# UmpoPowerRequestCompare

- ea: `0x18000b590`
- end: `0x18000b5ab`
- name: `UmpoPowerRequestCompare`
- size: `27`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, _DWORD *FirstStruct, _DWORD *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b590`

## pseudocode

```c
__int64 __fastcall UmpoPowerRequestCompare(struct _RTL_AVL_TABLE *Table, _DWORD *FirstStruct, _DWORD *SecondStruct)
{
  int v3; // r9d
  int v4; // eax

  v3 = SecondStruct[8];
  v4 = FirstStruct[8];
  if ( v4 < v3 )
    return 0;
  else
    return (unsigned int)(v4 <= v3) + 1;
}

```

## disassembly

```asm
0x18000b590  mov     r9d, [r8+20h]
0x18000b594  mov     eax, [rdx+20h]
0x18000b597  cmp     eax, r9d
0x18000b59a  jl      short loc_18000B5A8
0x18000b59c  xor     ecx, ecx
0x18000b59e  cmp     eax, r9d
0x18000b5a1  setle   cl
0x18000b5a4  lea     eax, [rcx+1]
0x18000b5a7  retn
0x18000b5a8  xor     eax, eax
0x18000b5aa  retn
```
