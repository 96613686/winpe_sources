# FindKeyInFilterHashTable

- ea: `0x14000a994`
- end: `0x14000aa2a`
- name: `FindKeyInFilterHashTable`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b160`
- `0x14000b418`

## callees

- `0x140001118`
- `0x14000a994`
- `0x14000aa30`

## pseudocode

```c
char __fastcall FindKeyInFilterHashTable(__int64 a1, __int64 a2, _QWORD *a3)
{
  PVOID v3; // rsi
  char TableEntryInFilterHashTable; // di
  __int64 v7; // r8
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = a1;
  v3 = P;
  TableEntryInFilterHashTable = 0;
  DbgTrace(2, "UevFilter.FindKeyInFilterHashTable: Entry\n", (__int64)a3);
  if ( a3 )
    *a3 = 0;
  if ( v3 )
  {
    v9 = 0;
    TableEntryInFilterHashTable = FindTableEntryInFilterHashTable(v3, a2, &v9, 0);
    if ( TableEntryInFilterHashTable )
    {
      if ( v9 && a3 )
        *a3 = *(_QWORD *)(v9 + 16);
    }
  }
  DbgTrace(2, "UevFilter.FindKeyInFilterHashTable: Exit\n", v7);
  return TableEntryInFilterHashTable;
}

```

## disassembly

```asm
0x14000a994  mov     [rsp+arg_0], rcx
0x14000a999  push    rbx
0x14000a99a  push    rbp
0x14000a99b  push    rsi
0x14000a99c  push    rdi
0x14000a99d  sub     rsp, 28h
0x14000a9a1  mov     rsi, cs:P
0x14000a9a8  mov     rbp, rdx
0x14000a9ab  lea     rdx, aUevfilterFindk_0; "UevFilter.FindKeyInFilterHashTable: Ent"...
0x14000a9b2  mov     ecx, 2
0x14000a9b7  mov     rbx, r8
0x14000a9ba  xor     dil, dil
0x14000a9bd  call    DbgTrace
0x14000a9c2  test    rbx, rbx
0x14000a9c5  jz      short loc_14000A9CE
0x14000a9c7  mov     qword ptr [rbx], 0
0x14000a9ce  test    rsi, rsi
0x14000a9d1  jz      short loc_14000AA0C
0x14000a9d3  xor     r9d, r9d
0x14000a9d6  mov     [rsp+48h+arg_0], 0
0x14000a9df  lea     r8, [rsp+48h+arg_0]
0x14000a9e4  mov     rdx, rbp
0x14000a9e7  mov     rcx, rsi
0x14000a9ea  call    FindTableEntryInFilterHashTable
0x14000a9ef  mov     dil, al
0x14000a9f2  test    al, al
0x14000a9f4  jz      short loc_14000AA0C
0x14000a9f6  mov     rdx, [rsp+48h+arg_0]
0x14000a9fb  test    rdx, rdx
0x14000a9fe  jz      short loc_14000AA0C
0x14000aa00  test    rbx, rbx
0x14000aa03  jz      short loc_14000AA0C
0x14000aa05  mov     rdx, [rdx+10h]
0x14000aa09  mov     [rbx], rdx
0x14000aa0c  lea     rdx, aUevfilterFindk; "UevFilter.FindKeyInFilterHashTable: Exi"...
0x14000aa13  mov     ecx, 2
0x14000aa18  call    DbgTrace
0x14000aa1d  mov     al, dil
0x14000aa20  add     rsp, 28h
0x14000aa24  pop     rdi
0x14000aa25  pop     rsi
0x14000aa26  pop     rbp
0x14000aa27  pop     rbx
0x14000aa28  retn
```
