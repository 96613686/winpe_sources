# TmpTxActionDoPrepareComplete

- ea: `0x14000c480`
- end: `0x14000c57d`
- name: `TmpTxActionDoPrepareComplete`
- size: `253`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c3c4`

## callees

- `0x140001f7c`
- `0x14000c480`
- `0x14000f944`
- `0x140010c70`
- `0x140011300`
- `0x14001f3e8`
- `0x140020dd4`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoPrepareComplete(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  int v4; // edi
  void *v6; // rcx

  if ( !*(_QWORD *)(a1 + 240) || (*(_DWORD *)(a1 + 196) & 2) != 0 )
  {
    *(_DWORD *)(a1 + 192) = 3;
    return TmpTxActionDoCommit((_QWORD *)a1);
  }
  else
  {
    v2 = a1 + 200;
    v3 = *(_QWORD *)(a1 + 200);
    if ( v3 == v2 || *(_QWORD *)(a1 + 240) && v3 == *(_QWORD *)(a1 + 208) || (v4 = TmpLogTransaction(a1, 2, 1), v4 >= 0) )
    {
      v6 = *(void **)(a1 + 240);
      *(_DWORD *)(a1 + 192) = 3;
      return TmpNotifyEnlistment(v6, 258);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_q_guid_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, a1 + 176, a1, a1 + 176);
      TmpTraceTransactionRollbackLogError(a1, v4);
      TmRollbackTransactionExt((PKTRANSACTION)a1, 0);
      return (unsigned int)v4;
    }
  }
}

```

## disassembly

```asm
0x14000c480  mov     [rsp+arg_0], rbx
0x14000c485  push    rdi
0x14000c486  sub     rsp, 40h
0x14000c48a  cmp     qword ptr [rcx+0F0h], 0
0x14000c492  mov     rbx, rcx
0x14000c495  jz      loc_14000C562
0x14000c49b  mov     eax, [rcx+0C4h]
0x14000c4a1  test    al, 2
0x14000c4a3  jnz     loc_14000C562
0x14000c4a9  lea     rax, [rcx+0C8h]
0x14000c4b0  mov     rcx, [rax]
0x14000c4b3  cmp     rcx, rax
0x14000c4b6  jz      short loc_14000C536
0x14000c4b8  cmp     qword ptr [rbx+0F0h], 0
0x14000c4c0  jz      short loc_14000C4CB
0x14000c4c2  cmp     rcx, [rbx+0D0h]
0x14000c4c9  jz      short loc_14000C536
0x14000c4cb  mov     edx, 2
0x14000c4d0  mov     rcx, rbx; int
0x14000c4d3  lea     r8d, [rdx-1]
0x14000c4d7  call    TmpLogTransaction
0x14000c4dc  mov     edi, eax
0x14000c4de  test    eax, eax
0x14000c4e0  jns     short loc_14000C536
0x14000c4e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4e9  lea     rax, WPP_GLOBAL_Control
0x14000c4f0  cmp     rcx, rax
0x14000c4f3  jz      short loc_14000C51E
0x14000c4f5  mov     edx, [rcx+2Ch]
0x14000c4f8  test    dl, 8
0x14000c4fb  jz      short loc_14000C51E
0x14000c4fd  mov     rcx, [rcx+18h]
0x14000c501  lea     r8, [rbx+0B0h]
0x14000c508  mov     edx, 0Ch
0x14000c50d  mov     [rsp+48h+var_20], edi
0x14000c511  mov     r9, rbx
0x14000c514  mov     qword ptr [rsp+48h+var_28], r8
0x14000c519  call    WPP_SF_q_guid_D
0x14000c51e  mov     edx, edi
0x14000c520  mov     rcx, rbx
0x14000c523  call    TmpTraceTransactionRollbackLogError
0x14000c528  xor     edx, edx; Wait
0x14000c52a  mov     rcx, rbx; Transaction
0x14000c52d  call    TmRollbackTransactionExt
0x14000c532  mov     eax, edi
0x14000c534  jmp     short loc_14000C571
0x14000c536  mov     rcx, [rbx+0F0h]; Object
0x14000c53d  mov     r9b, 1
0x14000c540  mov     dl, r9b
0x14000c543  mov     dword ptr [rbx+0C0h], 3
0x14000c54d  mov     r8d, 20h ; ' '
0x14000c553  mov     [rsp+48h+var_28], 102h; int
0x14000c55b  call    TmpNotifyEnlistment
0x14000c560  jmp     short loc_14000C571
0x14000c562  mov     dword ptr [rcx+0C0h], 3
0x14000c56c  call    TmpTxActionDoCommit
0x14000c571  mov     rbx, [rsp+48h+arg_0]
0x14000c576  add     rsp, 40h
0x14000c57a  pop     rdi
0x14000c57b  retn
```
