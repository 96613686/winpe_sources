# TmpRequestOutcomeTransaction

- ea: `0x1400108c0`
- end: `0x140010981`
- name: `TmpRequestOutcomeTransaction`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010500`
- `0x1400161c0`

## callees

- `0x140001e84`
- `0x14000f82c`
- `0x1400108c0`
- `0x140011300`
- `0x140011ab4`

## pseudocode

```c
__int64 __fastcall TmpRequestOutcomeTransaction(__int64 a1, __int64 a2, int a3)
{
  int v4; // ecx
  void *v6; // r10

  v4 = *(_DWORD *)(a1 + 192);
  if ( v4 == 2 )
    return TmpTxActionDoRollback(a1, a2, a3);
  if ( (_BYTE)a2 && (unsigned int)(v4 - 3) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
      WPP_SF_qq_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        11,
        (unsigned int)WPP_9112add83f5b3bede8aeac5f64c7907b_Traceguids,
        *(_QWORD *)(a1 + 512),
        a1,
        a1 + 176);
    TmpTraceTransactionHeuristicCorruption(a1);
    _InterlockedOr((volatile signed __int32 *)(a1 + 196), 0x8000000u);
    return TmpTxActionDoRollback(a1, a2, a3);
  }
  v6 = *(void **)(a1 + 240);
  if ( v6 && (unsigned int)(v4 - 3) <= 1 )
    return TmpNotifyEnlistment(v6, 0);
  else
    return 3222863891LL;
}

```

## disassembly

```asm
0x1400108c0  push    rbx
0x1400108c2  sub     rsp, 40h
0x1400108c6  mov     rbx, rcx
0x1400108c9  mov     ecx, [rcx+0C0h]
0x1400108cf  cmp     ecx, 2
0x1400108d2  jz      short loc_14001093A
0x1400108d4  test    dl, dl
0x1400108d6  jz      short loc_140010944
0x1400108d8  lea     eax, [rcx-3]
0x1400108db  cmp     eax, 1
0x1400108de  ja      short loc_140010944
0x1400108e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400108e7  lea     rax, WPP_GLOBAL_Control
0x1400108ee  cmp     rcx, rax
0x1400108f1  jz      short loc_140010927
0x1400108f3  mov     eax, [rcx+2Ch]
0x1400108f6  test    al, 8
0x1400108f8  jz      short loc_140010927
0x1400108fa  mov     r9, [rbx+200h]
0x140010901  lea     rax, [rbx+0B0h]
0x140010908  mov     rcx, [rcx+18h]
0x14001090c  lea     r8, WPP_9112add83f5b3bede8aeac5f64c7907b_Traceguids
0x140010913  mov     [rsp+48h+var_20], rax
0x140010918  mov     edx, 0Bh
0x14001091d  mov     qword ptr [rsp+48h+var_28], rbx
0x140010922  call    WPP_SF_qq_guid_
0x140010927  mov     rcx, rbx
0x14001092a  call    TmpTraceTransactionHeuristicCorruption
0x14001092f  lock or dword ptr [rbx+0C4h], 8000000h
0x14001093a  mov     rcx, rbx
0x14001093d  call    TmpTxActionDoRollback
0x140010942  jmp     short loc_14001097A
0x140010944  mov     r10, [rbx+0F0h]
0x14001094b  test    r10, r10
0x14001094e  jz      short loc_140010975
0x140010950  lea     eax, [rcx-3]
0x140010953  cmp     eax, 1
0x140010956  ja      short loc_140010975
0x140010958  xor     r9d, r9d
0x14001095b  mov     [rsp+48h+var_28], 0; int
0x140010963  mov     r8d, 20000000h
0x140010969  mov     dl, 1
0x14001096b  mov     rcx, r10; Object
0x14001096e  call    TmpNotifyEnlistment
0x140010973  jmp     short loc_14001097A
0x140010975  mov     eax, 0C0190013h
0x14001097a  add     rsp, 40h
0x14001097e  pop     rbx
0x14001097f  retn
```
