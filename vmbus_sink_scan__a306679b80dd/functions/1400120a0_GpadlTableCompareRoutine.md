# GpadlTableCompareRoutine

- ea: `0x1400120a0`
- end: `0x1400120bb`
- name: `GpadlTableCompareRoutine`
- size: `27`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400120a0`

## pseudocode

```c
__int64 __fastcall GpadlTableCompareRoutine(struct _RTL_AVL_TABLE *Table, _DWORD *FirstStruct, _DWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct >= *SecondStruct;
}

```

## disassembly

```asm
0x1400120a0  mov     ecx, [r8]
0x1400120a3  mov     r8d, [rdx]
0x1400120a6  cmp     r8d, ecx
0x1400120a9  jnz     short loc_1400120B2
0x1400120ab  mov     eax, 2
0x1400120b0  retn
0x1400120b2  xor     eax, eax
0x1400120b4  cmp     r8d, ecx
0x1400120b7  setnb   al
0x1400120ba  retn
```
