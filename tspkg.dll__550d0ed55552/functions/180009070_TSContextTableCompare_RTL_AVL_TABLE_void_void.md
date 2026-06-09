# TSContextTableCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180009070`
- end: `0x180009099`
- name: `?TSContextTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `41`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009070`

## pseudocode

```c
__int64 __fastcall TSContextTableCompare(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)
{
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // rax
  unsigned int v6; // ecx

  v3 = *(_QWORD *)(*(_QWORD *)SecondStruct + 8LL);
  v4 = *(_QWORD *)(*(_QWORD *)FirstStruct + 8LL);
  if ( v4 > v3 )
    return 1;
  v6 = 2;
  if ( v4 < v3 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180009070  mov     rax, [r8]
0x180009073  mov     r8, [rax+8]
0x180009077  mov     rax, [rdx]
0x18000907a  mov     rax, [rax+8]
0x18000907e  cmp     rax, r8
0x180009081  jbe     short loc_180009089
0x180009083  mov     eax, 1
0x180009088  retn
0x180009089  xor     edx, edx
0x18000908b  mov     ecx, 2
0x180009090  cmp     rax, r8
0x180009093  cmovb   ecx, edx
0x180009096  mov     eax, ecx
0x180009098  retn
```
