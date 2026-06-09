# TmpHeuristicAbortTransactionAfterCheckpoint

- ea: `0x1400161c0`
- end: `0x1400162db`
- name: `TmpHeuristicAbortTransactionAfterCheckpoint`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001e84`
- `0x14000221c`
- `0x14000f82c`
- `0x1400108c0`
- `0x140011ab4`
- `0x1400161c0`
- `0x14001b338`

## import_xrefs

- `CLFS!ClfsLsnLess` at `0x1400161ef`
- `CLFS!ClfsLsnLess` at `0x1400161ef`
- `ntoskrnl!KeReleaseMutex` at `0x1400162c1`
- `ntoskrnl!KeReleaseMutex` at `0x1400162c1`

## pseudocode

```c
__int64 __fastcall TmpHeuristicAbortTransactionAfterCheckpoint(const CLFS_LSN *a1, const CLFS_LSN *a2)
{
  int v4; // r8d
  __int64 v5; // rdx

  TmpAcquireTransactionMutex(a1);
  if ( (a1[24].offset.cidContainer & 0x800000) != 0 && ClfsLsnLess(a1 + 31, a2) )
  {
    if ( (int)TmpRequestOutcomeTransaction(a1, 0) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_qq_guid_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          15,
          (unsigned int)WPP_f4159a977dea3a818e35a78ee98eeba7_Traceguids,
          a1[64].ullOffset,
          (_DWORD)a1,
          (__int64)&a1[22]);
    }
    else
    {
      TmpTraceTransactionHeuristicCorruption((__int64)a1);
      v5 = (__int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v5 = *((unsigned int *)WPP_GLOBAL_Control + 11);
        if ( (v5 & 8) != 0 )
          WPP_SF_qq_guid_D(*((_QWORD *)WPP_GLOBAL_Control + 3), v5, v4, a1[64].ullOffset, (_DWORD)a1, (__int64)&a1[22]);
      }
      _InterlockedOr((volatile signed __int32 *)&a1[24].offset.cidContainer, 0x8000000u);
      TmpTxActionDoRollback((__int64)a1, v5, v4);
    }
  }
  KeReleaseMutex((PRKMUTEX)(a1[11].ullOffset + 32), 0);
  return 0;
}

```

## disassembly

```asm
0x1400161c0  mov     [rsp+arg_0], rbx
0x1400161c5  push    rdi
0x1400161c6  sub     rsp, 40h
0x1400161ca  mov     rdi, rdx
0x1400161cd  mov     rbx, rcx
0x1400161d0  call    TmpAcquireTransactionMutex
0x1400161d5  mov     eax, [rbx+0C4h]
0x1400161db  bt      eax, 17h
0x1400161df  jnb     loc_1400162B7
0x1400161e5  lea     rcx, [rbx+0F8h]; plsn1
0x1400161ec  mov     rdx, rdi; plsn2
0x1400161ef  call    cs:__imp_ClfsLsnLess
0x1400161f6  nop     dword ptr [rax+rax+00h]
0x1400161fb  test    al, al
0x1400161fd  jz      loc_1400162B7
0x140016203  xor     edx, edx
0x140016205  mov     rcx, rbx
0x140016208  call    TmpRequestOutcomeTransaction
0x14001620d  mov     edi, eax
0x14001620f  test    eax, eax
0x140016211  jns     short loc_140016270
0x140016213  mov     rcx, rbx
0x140016216  call    TmpTraceTransactionHeuristicCorruption
0x14001621b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016222  lea     rdx, WPP_GLOBAL_Control
0x140016229  cmp     rcx, rdx
0x14001622c  jz      short loc_14001625B
0x14001622e  mov     edx, [rcx+2Ch]
0x140016231  test    dl, 8
0x140016234  jz      short loc_14001625B
0x140016236  mov     r9, [rbx+200h]
0x14001623d  lea     rax, [rbx+0B0h]
0x140016244  mov     rcx, [rcx+18h]
0x140016248  mov     [rsp+48h+var_18], edi
0x14001624c  mov     [rsp+48h+var_20], rax
0x140016251  mov     [rsp+48h+var_28], rbx
0x140016256  call    WPP_SF_qq_guid_D
0x14001625b  lock or dword ptr [rbx+0C4h], 8000000h
0x140016266  mov     rcx, rbx
0x140016269  call    TmpTxActionDoRollback
0x14001626e  jmp     short loc_1400162B7
0x140016270  mov     rcx, cs:WPP_GLOBAL_Control
0x140016277  lea     rdx, WPP_GLOBAL_Control
0x14001627e  cmp     rcx, rdx
0x140016281  jz      short loc_1400162B7
0x140016283  mov     eax, [rcx+2Ch]
0x140016286  test    al, 8
0x140016288  jz      short loc_1400162B7
0x14001628a  mov     r9, [rbx+200h]
0x140016291  lea     rax, [rbx+0B0h]
0x140016298  mov     rcx, [rcx+18h]
0x14001629c  lea     r8, WPP_f4159a977dea3a818e35a78ee98eeba7_Traceguids
0x1400162a3  mov     [rsp+48h+var_20], rax
0x1400162a8  mov     edx, 0Fh
0x1400162ad  mov     [rsp+48h+var_28], rbx
0x1400162b2  call    WPP_SF_qq_guid_
0x1400162b7  mov     rcx, [rbx+58h]
0x1400162bb  xor     edx, edx; Wait
0x1400162bd  add     rcx, 20h ; ' '; Mutex
0x1400162c1  call    cs:__imp_KeReleaseMutex
0x1400162c8  nop     dword ptr [rax+rax+00h]
0x1400162cd  mov     rbx, [rsp+48h+arg_0]
0x1400162d2  xor     eax, eax
0x1400162d4  add     rsp, 40h
0x1400162d8  pop     rdi
0x1400162d9  retn
```
