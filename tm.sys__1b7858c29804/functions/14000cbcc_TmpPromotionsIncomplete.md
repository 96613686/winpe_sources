# TmpPromotionsIncomplete

- ea: `0x14000cbcc`
- end: `0x14000cbf0`
- name: `TmpPromotionsIncomplete`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c3c4`
- `0x1400110f4`

## callees

- `0x14000cbcc`

## pseudocode

```c
char __fastcall TmpPromotionsIncomplete(__int64 a1)
{
  char v1; // dl
  _QWORD **v2; // rcx
  _QWORD *v3; // rax

  v1 = 0;
  v2 = (_QWORD **)(a1 + 256);
  v3 = *v2;
  while ( v3 != v2 )
  {
    if ( !*(v3 - 2) )
      return 1;
    v3 = (_QWORD *)*v3;
    v1 = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x14000cbcc  xor     dl, dl
0x14000cbce  add     rcx, 100h
0x14000cbd5  mov     rax, [rcx]
0x14000cbd8  cmp     rax, rcx
0x14000cbdb  jz      short loc_14000CBED
0x14000cbdd  cmp     qword ptr [rax-10h], 0
0x14000cbe2  jz      short loc_14000CBEB
0x14000cbe4  mov     rax, [rax]
0x14000cbe7  xor     dl, dl
0x14000cbe9  jmp     short loc_14000CBD8
0x14000cbeb  mov     dl, 1
0x14000cbed  mov     al, dl
0x14000cbef  retn
```
