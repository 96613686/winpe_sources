# TmpTxActionDoCommit

- ea: `0x140020dd4`
- end: `0x14002107b`
- name: `TmpTxActionDoCommit`
- size: `679`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c480`
- `0x14000fed0`

## callees

- `0x14000117c`
- `0x140001f7c`
- `0x14000c010`
- `0x14000f944`
- `0x140010c70`
- `0x140015fc8`
- `0x140016604`
- `0x14001b658`
- `0x14001f3e8`
- `0x140020dd4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140020e7a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020e7a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020df5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020df5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020e19`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020e19`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoCommit(_QWORD *Object)
{
  __int64 v2; // r8
  _QWORD *v3; // r14
  _QWORD *v4; // rax
  _QWORD *v5; // rsi
  unsigned int v6; // edi

  ExAcquireFastMutex((PFAST_MUTEX)(Object[64] + 592LL));
  ++*(_QWORD *)(Object[64] + 584LL);
  ExReleaseFastMutex((PFAST_MUTEX)(Object[64] + 592LL));
  v3 = Object + 25;
  v4 = (_QWORD *)Object[25];
  v5 = Object + 30;
  if ( v4 == Object + 25 || *v5 && v4 == (_QWORD *)Object[26] )
    goto LABEL_23;
  if ( (*(_DWORD *)(Object[11] + 196LL) & 0x10000) != 0 )
  {
    KeWaitForSingleObject(&TmpTransactionThawEvent, Executive, 0, 0, 0);
    _InterlockedAnd((volatile signed __int32 *)(Object[11] + 196LL), 0xFFFEFFFF);
  }
  v6 = TmpLogTransaction((__int64)Object, 3, 1);
  if ( !v6 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_q_guid_(*((_QWORD *)WPP_GLOBAL_Control + 3), 16, v2, (_DWORD)Object, (__int64)(Object + 22));
    *((_DWORD *)Object + 48) = 5;
    *((_DWORD *)Object + 126) = 2;
    if ( (_QWORD *)*v3 == v3 || *v5 && *v3 == Object[26] )
      return (unsigned int)TmpTxActionDoCommitComplete(Object);
    else
      return (unsigned int)TmpNotifyAllEnlistmentsTransaction(Object, 4, v2, 261);
  }
  else if ( (*((_DWORD *)Object + 49) & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
      WPP_SF_q_guid_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, v2, (_DWORD)Object, (__int64)(Object + 22));
    TmpTraceTransactionRollbackLogError((__int64)Object, v6);
    TmRollbackTransactionExt((PKTRANSACTION)Object, 0);
    if ( v6 == -1072103333 && (unsigned int)(*((_DWORD *)Object + 48) - 3) <= 1 )
      TmpForgetTransaction(Object);
  }
  else if ( v6 == -1073741536 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
      WPP_SF_q_guid_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, v2, (_DWORD)Object, (__int64)(Object + 22));
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
      WPP_SF_q_guid_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, v2, Object[64], Object[64] + 112LL);
    TmpQueueOfflineTm(Object[64]);
  }
  return v6;
}

```

## disassembly

```asm
0x140020dd4  push    rbx
0x140020dd6  push    rsi
0x140020dd7  push    rdi
0x140020dd8  push    r14
0x140020dda  push    r15
0x140020ddc  sub     rsp, 40h
0x140020de0  mov     r15, rdx
0x140020de3  mov     rbx, rcx
0x140020de6  mov     rcx, [rcx+200h]
0x140020ded  mov     edi, 250h
0x140020df2  add     rcx, rdi; FastMutex
0x140020df5  call    cs:__imp_ExAcquireFastMutex
0x140020dfc  nop     dword ptr [rax+rax+00h]
0x140020e01  mov     rax, [rbx+200h]
0x140020e08  inc     qword ptr [rax+248h]
0x140020e0f  mov     rcx, [rbx+200h]
0x140020e16  add     rcx, rdi; FastMutex
0x140020e19  call    cs:__imp_ExReleaseFastMutex
0x140020e20  nop     dword ptr [rax+rax+00h]
0x140020e25  lea     r14, [rbx+0C8h]
0x140020e2c  mov     rax, [r14]
0x140020e2f  lea     rsi, [rbx+0F0h]
0x140020e36  cmp     rax, r14
0x140020e39  jz      loc_140020FE4
0x140020e3f  cmp     qword ptr [rsi], 0
0x140020e43  jz      short loc_140020E52
0x140020e45  cmp     rax, [rbx+0D0h]
0x140020e4c  jz      loc_140020FE4
0x140020e52  mov     rax, [rbx+58h]
0x140020e56  mov     ecx, [rax+0C4h]
0x140020e5c  bt      ecx, 10h
0x140020e60  jnb     short loc_140020E95
0x140020e62  mov     [rsp+68h+Timeout], 0; Timeout
0x140020e6b  xor     r9d, r9d; Alertable
0x140020e6e  xor     r8d, r8d; WaitMode
0x140020e71  xor     edx, edx; WaitReason
0x140020e73  lea     rcx, TmpTransactionThawEvent; Object
0x140020e7a  call    cs:__imp_KeWaitForSingleObject
0x140020e81  nop     dword ptr [rax+rax+00h]
0x140020e86  mov     rax, [rbx+58h]
0x140020e8a  lock and dword ptr [rax+0C4h], 0FFFEFFFFh
0x140020e95  mov     edx, 3
0x140020e9a  lea     r8d, [rdx-2]
0x140020e9e  mov     rcx, rbx; int
0x140020ea1  call    TmpLogTransaction
0x140020ea6  mov     edi, eax
0x140020ea8  mov     [rsp+68h+var_38], eax
0x140020eac  test    eax, eax
0x140020eae  jz      loc_140020FE4
0x140020eb4  mov     ecx, [rbx+0C4h]
0x140020eba  test    cl, 2
0x140020ebd  jz      loc_140020F43
0x140020ec3  lea     rax, WPP_GLOBAL_Control
0x140020eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ed1  cmp     rcx, rax
0x140020ed4  jz      short loc_140020EFE
0x140020ed6  mov     eax, [rcx+2Ch]
0x140020ed9  test    al, 8
0x140020edb  jz      short loc_140020EFE
0x140020edd  lea     rax, [rbx+0B0h]
0x140020ee4  mov     edx, 0Dh
0x140020ee9  mov     [rsp+68h+var_40], edi
0x140020eed  mov     [rsp+68h+Timeout], rax
0x140020ef2  mov     r9, rbx
0x140020ef5  mov     rcx, [rcx+18h]
0x140020ef9  call    WPP_SF_q_guid_D
0x140020efe  mov     edx, edi
0x140020f00  mov     rcx, rbx
0x140020f03  call    TmpTraceTransactionRollbackLogError
0x140020f08  xor     edx, edx; Wait
0x140020f0a  mov     rcx, rbx; Transaction
0x140020f0d  call    TmRollbackTransactionExt
0x140020f12  cmp     edi, 0C019005Bh
0x140020f18  jnz     loc_14002106C
0x140020f1e  mov     eax, [rbx+0C0h]
0x140020f24  sub     eax, 3
0x140020f27  cmp     eax, 1
0x140020f2a  ja      loc_14002106C
0x140020f30  mov     r8b, 1
0x140020f33  mov     dl, r8b
0x140020f36  mov     rcx, rbx; Object
0x140020f39  call    TmpForgetTransaction
0x140020f3e  jmp     loc_14002106C
0x140020f43  cmp     edi, 0C0000120h
0x140020f49  jnz     short loc_140020F97
0x140020f4b  lea     rax, WPP_GLOBAL_Control
0x140020f52  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f59  cmp     rcx, rax
0x140020f5c  jz      loc_14002106C
0x140020f62  mov     eax, [rcx+2Ch]
0x140020f65  test    al, 8
0x140020f67  jz      loc_14002106C
0x140020f6d  lea     rax, [rbx+0B0h]
0x140020f74  mov     edx, 0Eh
0x140020f79  mov     [rsp+68h+var_40], 0C0000120h
0x140020f81  mov     [rsp+68h+Timeout], rax
0x140020f86  mov     r9, rbx
0x140020f89  mov     rcx, [rcx+18h]
0x140020f8d  call    WPP_SF_q_guid_D
0x140020f92  jmp     loc_14002106C
0x140020f97  lea     rax, WPP_GLOBAL_Control
0x140020f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020fa5  cmp     rcx, rax
0x140020fa8  jz      short loc_140020FD3
0x140020faa  mov     eax, [rcx+2Ch]
0x140020fad  test    al, 8
0x140020faf  jz      short loc_140020FD3
0x140020fb1  mov     r9, [rbx+200h]
0x140020fb8  lea     rax, [r9+70h]
0x140020fbc  mov     edx, 0Fh
0x140020fc1  mov     [rsp+68h+var_40], edi
0x140020fc5  mov     [rsp+68h+Timeout], rax
0x140020fca  mov     rcx, [rcx+18h]
0x140020fce  call    WPP_SF_q_guid_D
0x140020fd3  mov     rcx, [rbx+200h]
0x140020fda  call    TmpQueueOfflineTm
0x140020fdf  jmp     loc_14002106C
0x140020fe4  lea     rax, WPP_GLOBAL_Control
0x140020feb  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ff2  cmp     rcx, rax
0x140020ff5  jz      short loc_14002101B
0x140020ff7  mov     eax, [rcx+2Ch]
0x140020ffa  test    al, 4
0x140020ffc  jz      short loc_14002101B
0x140020ffe  lea     rax, [rbx+0B0h]
0x140021005  mov     edx, 10h
0x14002100a  mov     [rsp+68h+Timeout], rax
0x14002100f  mov     r9, rbx
0x140021012  mov     rcx, [rcx+18h]
0x140021016  call    WPP_SF_q_guid_
0x14002101b  mov     dword ptr [rbx+0C0h], 5
0x140021025  mov     dword ptr [rbx+1F8h], 2
0x14002102f  mov     rax, [r14]
0x140021032  cmp     rax, r14
0x140021035  jz      short loc_14002105B
0x140021037  cmp     qword ptr [rsi], 0
0x14002103b  jz      short loc_140021046
0x14002103d  cmp     rax, [rbx+0D0h]
0x140021044  jz      short loc_14002105B
0x140021046  mov     edx, 4
0x14002104b  mov     r9d, 105h
0x140021051  mov     rcx, rbx
0x140021054  call    TmpNotifyAllEnlistmentsTransaction
0x140021059  jmp     short loc_140021066
0x14002105b  mov     rdx, r15
0x14002105e  mov     rcx, rbx; Object
0x140021061  call    TmpTxActionDoCommitComplete
0x140021066  mov     [rsp+68h+var_38], eax
0x14002106a  mov     edi, eax
0x14002106c  mov     eax, edi
0x14002106e  add     rsp, 40h
0x140021072  pop     r15
0x140021074  pop     r14
0x140021076  pop     rdi
0x140021077  pop     rsi
0x140021078  pop     rbx
0x140021079  retn
0x140021ae7  push    rbp
0x140021ae9  sub     rsp, 30h
0x140021aed  mov     rbp, rdx
0x140021af0  add     rsp, 30h
0x140021af4  pop     rbp
0x140021af5  retn
```
