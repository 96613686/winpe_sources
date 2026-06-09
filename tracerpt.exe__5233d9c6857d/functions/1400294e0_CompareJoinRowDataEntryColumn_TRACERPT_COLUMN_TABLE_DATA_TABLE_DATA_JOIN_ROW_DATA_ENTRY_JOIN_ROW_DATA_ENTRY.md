# CompareJoinRowDataEntryColumn(_TRACERPT_COLUMN *,_TABLE_DATA *,_TABLE_DATA *,_JOIN_ROW_DATA_ENTRY *,_JOIN_ROW_DATA_ENTRY *)

- ea: `0x1400294e0`
- end: `0x140029565`
- name: `?CompareJoinRowDataEntryColumn@@YAJPEAU_TRACERPT_COLUMN@@PEAU_TABLE_DATA@@1PEAU_JOIN_ROW_DATA_ENTRY@@2@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct _TRACERPT_COLUMN *, struct _TABLE_DATA *, struct _TABLE_DATA *, struct _JOIN_ROW_DATA_ENTRY *, struct _JOIN_ROW_DATA_ENTRY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002c76c`

## callees

- `0x1400294e0`
- `0x14002da1c`

## pseudocode

```c
int __fastcall CompareJoinRowDataEntryColumn(
        struct _TRACERPT_COLUMN *a1,
        struct _TABLE_DATA *a2,
        struct _TABLE_DATA *a3,
        struct _JOIN_ROW_DATA_ENTRY *a4,
        struct _JOIN_ROW_DATA_ENTRY *a5)
{
  __int64 v6; // r11
  __int64 v7; // r10
  __int64 v8; // rdx
  __int64 v9; // rcx

  v6 = *((_QWORD *)a2 + 1);
  v7 = 32LL * (unsigned int)(*((_DWORD *)a1 + 90) + 1);
  v8 = *(_QWORD *)(32LL * *((unsigned int *)a4 + 4) + v6 + 8);
  if ( !*(_DWORD *)(v7 + v8 + 16) )
    v8 = *(_QWORD *)(32LL * *((unsigned int *)a4 + 5) + *((_QWORD *)a3 + 1) + 8);
  v9 = *(_QWORD *)(32LL * *((unsigned int *)a5 + 4) + v6 + 8);
  if ( !*(_DWORD *)(v7 + v9 + 16) )
    v9 = *(_QWORD *)(32LL * *((unsigned int *)a5 + 5) + *((_QWORD *)a3 + 1) + 8);
  return SortCompareItemData(
           (struct _ITEM_DATA *)(v7 + v8),
           (struct _ITEM_DATA *)(v7 + v9),
           (*((_BYTE *)a1 + 353) & 2) != 0);
}

```

## disassembly

```asm
0x1400294e0  push    rbx
0x1400294e2  mov     r10d, [rcx+168h]
0x1400294e9  mov     rbx, rcx
0x1400294ec  mov     eax, [r9+10h]
0x1400294f0  inc     r10d
0x1400294f3  mov     r11, [rdx+8]
0x1400294f7  shl     rax, 5
0x1400294fb  shl     r10, 5
0x1400294ff  mov     rdx, [rax+r11+8]
0x140029504  cmp     dword ptr [r10+rdx+10h], 0
0x14002950a  ja      short loc_14002951D
0x14002950c  mov     ecx, [r9+14h]
0x140029510  mov     rax, [r8+8]
0x140029514  shl     rcx, 5
0x140029518  mov     rdx, [rcx+rax+8]
0x14002951d  lea     r9, [r10+rdx]
0x140029521  mov     rdx, [rsp+8+arg_20]
0x140029526  mov     eax, [rdx+10h]
0x140029529  shl     rax, 5
0x14002952d  mov     rcx, [rax+r11+8]
0x140029532  cmp     dword ptr [r10+rcx+10h], 0
0x140029538  ja      short loc_14002954A
0x14002953a  mov     edx, [rdx+14h]
0x14002953d  mov     rax, [r8+8]
0x140029541  shl     rdx, 5
0x140029545  mov     rcx, [rdx+rax+8]
0x14002954a  mov     r8b, [rbx+161h]
0x140029551  lea     rdx, [r10+rcx]; struct _ITEM_DATA *
0x140029555  shr     r8b, 1
0x140029558  mov     rcx, r9; struct _ITEM_DATA *
0x14002955b  and     r8b, 1; unsigned __int8
0x14002955f  pop     rbx
0x140029560  jmp     ?SortCompareItemData@@YAJPEAU_ITEM_DATA@@0E@Z; SortCompareItemData(_ITEM_DATA *,_ITEM_DATA *,uchar)
```
