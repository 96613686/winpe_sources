# TmCommitTransactionExt

- ea: `0x14001a2e0`
- end: `0x14001a56f`
- name: `TmCommitTransactionExt`
- size: `655`
- prototype: `NTSTATUS __stdcall(PKTRANSACTION Transaction, BOOLEAN Wait)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000fed0`
- `0x14001a240`

## callees

- `0x14000117c`
- `0x14000c140`
- `0x1400110f4`
- `0x140011d48`
- `0x14001a2e0`
- `0x14001b338`
- `0x14001dbb0`
- `0x14001eb30`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001a4d4`
- `ntoskrnl!KeReleaseMutex` at `0x14001a558`
- `ntoskrnl!KeReleaseMutex` at `0x14002139f`
- `ntoskrnl!KeReleaseMutex` at `0x14001a4d4`
- `ntoskrnl!KeReleaseMutex` at `0x14001a558`
- `ntoskrnl!KeReleaseMutex` at `0x14002139f`
- `ntoskrnl!KeSetEvent` at `0x14001a410`
- `ntoskrnl!KeSetEvent` at `0x14001a410`
- `ntoskrnl!DbgPrintEx` at `0x14001a313`
- `ntoskrnl!DbgPrintEx` at `0x14001a313`

## string_xrefs

- `0x14001a302`: `KTM:  TmCommitTransactionExt for tx %lx\n`

## pseudocode

```c
NTSTATUS __stdcall TmCommitTransactionExt(PKTRANSACTION Transaction, BOOLEAN Wait)
{
  NTSTATUS v4; // edi
  int v5; // r8d
  int v6; // eax

  v4 = -1072103405;
  DbgPrintEx(0x6Cu, 0x80000020, "KTM:  TmCommitTransactionExt for tx %lx\n", (_DWORD)Transaction);
  TmpAcquireTransactionMutex(Transaction);
  if ( *((_QWORD *)Transaction + 30)
    && (*((_DWORD *)Transaction + 49) & 2) == 0
    && (*((_DWORD *)Transaction + 49) & 0x1000) == 0 )
  {
    v4 = -1072103406;
    goto LABEL_21;
  }
  v6 = *((_DWORD *)Transaction + 126);
  if ( v6 == 3 )
    goto LABEL_20;
  if ( v6 == 2 )
  {
    v4 = -1072103402;
    goto LABEL_21;
  }
  if ( (*((_DWORD *)Transaction + 49) & 0x1000) != 0 && (*((_DWORD *)Transaction + 49) & 2) == 0 )
  {
    v4 = TmpForwardCommitTransaction(Transaction);
    goto LABEL_21;
  }
  _InterlockedOr((volatile signed __int32 *)Transaction + 49, 2u);
  if ( *((_DWORD *)Transaction + 48) != 1 )
    goto LABEL_21;
  if ( *((_QWORD *)Transaction + 64) )
  {
    v4 = TmpTxActionTrySinglePhase(Transaction);
    if ( v4 < 0 )
      goto LABEL_21;
    _InterlockedOr((volatile signed __int32 *)Transaction + 49, 4u);
    v4 = TmpTxActionDoPrePrepare((int)Transaction);
    if ( *((_DWORD *)Transaction + 48) != 6 && *((_DWORD *)Transaction + 126) != 3 )
      goto LABEL_21;
LABEL_20:
    v4 = -1072103403;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q_guid_(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, v5, (_DWORD)Transaction, (__int64)Transaction + 176);
  *((_DWORD *)Transaction + 48) = 9;
  *((_DWORD *)Transaction + 126) = 2;
  KeSetEvent((PRKEVENT)Transaction, 0, 0);
  TmpFinalizeTransaction(Transaction);
  v4 = 0;
LABEL_21:
  if ( v4 != 259 || !Wait )
  {
    *((_DWORD *)Transaction + 2 * (*((_DWORD *)Transaction + 152) % 0xAu) + 132) = 1;
    *((_DWORD *)Transaction + 2 * (*((_DWORD *)Transaction + 152) % 0xAu) + 133) = v4;
    ++*((_DWORD *)Transaction + 152);
  }
  KeReleaseMutex((PRKMUTEX)(*((_QWORD *)Transaction + 11) + 32LL), 0);
  if ( v4 == 259 && Wait )
  {
    v4 = TmpWaitForTransactionOutcome(Transaction, 2);
    TmpAcquireTransactionMutex(Transaction);
    *((_DWORD *)Transaction + 2 * (*((_DWORD *)Transaction + 152) % 0xAu) + 132) = 1;
    *((_DWORD *)Transaction + 2 * (*((_DWORD *)Transaction + 152) % 0xAu) + 133) = v4;
    ++*((_DWORD *)Transaction + 152);
    KeReleaseMutex((PRKMUTEX)(*((_QWORD *)Transaction + 11) + 32LL), 0);
  }
  return v4;
}

```

## disassembly

```asm
0x14001a2e0  mov     [rsp+arg_8], dl
0x14001a2e4  mov     [rsp+arg_0], rcx
0x14001a2e9  push    rbx
0x14001a2ea  push    rsi
0x14001a2eb  push    rdi
0x14001a2ec  sub     rsp, 40h
0x14001a2f0  mov     sil, dl
0x14001a2f3  mov     rbx, rcx
0x14001a2f6  mov     edi, 0C0190013h
0x14001a2fb  mov     [rsp+58h+var_28], edi
0x14001a2ff  mov     r9, rcx
0x14001a302  lea     r8, Format; "KTM:  TmCommitTransactionExt for tx %lx"...
0x14001a309  mov     edx, 80000020h; Level
0x14001a30e  mov     ecx, 6Ch ; 'l'; ComponentId
0x14001a313  call    cs:__imp_DbgPrintEx
0x14001a31a  nop     dword ptr [rax+rax+00h]
0x14001a31f  mov     rcx, rbx
0x14001a322  call    TmpAcquireTransactionMutex
0x14001a327  nop
0x14001a328  cmp     qword ptr [rbx+0F0h], 0
0x14001a330  jz      short loc_14001A352
0x14001a332  mov     eax, [rbx+0C4h]
0x14001a338  test    al, 2
0x14001a33a  jnz     short loc_14001A352
0x14001a33c  mov     eax, [rbx+0C4h]
0x14001a342  bt      eax, 0Ch
0x14001a346  jb      short loc_14001A352
0x14001a348  mov     edi, 0C0190012h
0x14001a34d  jmp     loc_14001A473
0x14001a352  mov     eax, [rbx+1F8h]
0x14001a358  cmp     eax, 3
0x14001a35b  jz      loc_14001A46E
0x14001a361  cmp     eax, 2
0x14001a364  jnz     short loc_14001A370
0x14001a366  mov     edi, 0C0190016h
0x14001a36b  jmp     loc_14001A473
0x14001a370  mov     eax, [rbx+0C4h]
0x14001a376  bt      eax, 0Ch
0x14001a37a  jnb     short loc_14001A399
0x14001a37c  mov     eax, [rbx+0C4h]
0x14001a382  test    al, 2
0x14001a384  jnz     short loc_14001A399
0x14001a386  mov     rcx, rbx; Transaction
0x14001a389  call    TmpForwardCommitTransaction
0x14001a38e  mov     edi, eax
0x14001a390  mov     [rsp+58h+var_28], eax
0x14001a394  jmp     loc_14001A477
0x14001a399  lock or dword ptr [rbx+0C4h], 2
0x14001a3a1  cmp     dword ptr [rbx+0C0h], 1
0x14001a3a8  jnz     loc_14001A473
0x14001a3ae  mov     [rsp+58h+arg_10], 0
0x14001a3b3  cmp     qword ptr [rbx+200h], 0
0x14001a3bb  jnz     short loc_14001A428
0x14001a3bd  lea     rax, WPP_GLOBAL_Control
0x14001a3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3cb  cmp     rcx, rax
0x14001a3ce  jz      short loc_14001A3F4
0x14001a3d0  mov     eax, [rcx+2Ch]
0x14001a3d3  test    al, 4
0x14001a3d5  jz      short loc_14001A3F4
0x14001a3d7  lea     rax, [rbx+0B0h]
0x14001a3de  mov     edx, 0Ah
0x14001a3e3  mov     [rsp+58h+var_38], rax
0x14001a3e8  mov     r9, rbx
0x14001a3eb  mov     rcx, [rcx+18h]
0x14001a3ef  call    WPP_SF_q_guid_
0x14001a3f4  mov     dword ptr [rbx+0C0h], 9
0x14001a3fe  mov     dword ptr [rbx+1F8h], 2
0x14001a408  xor     r8d, r8d; Wait
0x14001a40b  xor     edx, edx; Increment
0x14001a40d  mov     rcx, rbx; Event
0x14001a410  call    cs:__imp_KeSetEvent
0x14001a417  nop     dword ptr [rax+rax+00h]
0x14001a41c  mov     rcx, rbx; Object
0x14001a41f  call    TmpFinalizeTransaction
0x14001a424  xor     edi, edi
0x14001a426  jmp     short loc_14001A473
0x14001a428  lea     rdx, [rsp+58h+arg_10]
0x14001a42d  mov     rcx, rbx; Transaction
0x14001a430  call    TmpTxActionTrySinglePhase
0x14001a435  mov     edi, eax
0x14001a437  mov     [rsp+58h+var_28], eax
0x14001a43b  test    eax, eax
0x14001a43d  js      short loc_14001A477
0x14001a43f  cmp     [rsp+58h+arg_10], 0
0x14001a444  jnz     short loc_14001A45C
0x14001a446  lock or dword ptr [rbx+0C4h], 4
0x14001a44e  mov     rcx, rbx; int
0x14001a451  call    TmpTxActionDoPrePrepare
0x14001a456  mov     edi, eax
0x14001a458  mov     [rsp+58h+var_28], eax
0x14001a45c  cmp     dword ptr [rbx+0C0h], 6
0x14001a463  jz      short loc_14001A46E
0x14001a465  cmp     dword ptr [rbx+1F8h], 3
0x14001a46c  jnz     short loc_14001A477
0x14001a46e  mov     edi, 0C0190015h
0x14001a473  mov     [rsp+58h+var_28], edi
0x14001a477  cmp     edi, 103h
0x14001a47d  jnz     short loc_14001A484
0x14001a47f  test    sil, sil
0x14001a482  jnz     short loc_14001A4CA
0x14001a484  mov     ecx, [rbx+260h]
0x14001a48a  mov     eax, 0CCCCCCCDh
0x14001a48f  mul     ecx
0x14001a491  shr     edx, 3
0x14001a494  lea     eax, [rdx+rdx*4]
0x14001a497  add     eax, eax
0x14001a499  sub     ecx, eax
0x14001a49b  mov     dword ptr [rbx+rcx*8+210h], 1
0x14001a4a6  mov     ecx, [rbx+260h]
0x14001a4ac  mov     eax, 0CCCCCCCDh
0x14001a4b1  mul     ecx
0x14001a4b3  shr     edx, 3
0x14001a4b6  lea     eax, [rdx+rdx*4]
0x14001a4b9  add     eax, eax
0x14001a4bb  sub     ecx, eax
0x14001a4bd  mov     [rbx+rcx*8+214h], edi
0x14001a4c4  inc     dword ptr [rbx+260h]
0x14001a4ca  mov     rcx, [rbx+58h]
0x14001a4ce  add     rcx, 20h ; ' '; Mutex
0x14001a4d2  xor     edx, edx; Wait
0x14001a4d4  call    cs:__imp_KeReleaseMutex
0x14001a4db  nop     dword ptr [rax+rax+00h]
0x14001a4e0  cmp     edi, 103h
0x14001a4e6  jnz     short loc_14001A564
0x14001a4e8  test    sil, sil
0x14001a4eb  jz      short loc_14001A564
0x14001a4ed  mov     edx, 2
0x14001a4f2  mov     rcx, rbx
0x14001a4f5  call    TmpWaitForTransactionOutcome
0x14001a4fa  mov     edi, eax
0x14001a4fc  mov     rcx, rbx
0x14001a4ff  call    TmpAcquireTransactionMutex
0x14001a504  mov     r8d, [rbx+260h]
0x14001a50b  mov     eax, 0CCCCCCCDh
0x14001a510  mul     r8d
0x14001a513  shr     edx, 3
0x14001a516  lea     ecx, [rdx+rdx*4]
0x14001a519  add     ecx, ecx
0x14001a51b  sub     r8d, ecx
0x14001a51e  mov     dword ptr [rbx+r8*8+210h], 1
0x14001a52a  mov     ecx, [rbx+260h]
0x14001a530  mov     eax, 0CCCCCCCDh
0x14001a535  mul     ecx
0x14001a537  shr     edx, 3
0x14001a53a  lea     eax, [rdx+rdx*4]
0x14001a53d  add     eax, eax
0x14001a53f  sub     ecx, eax
0x14001a541  mov     [rbx+rcx*8+214h], edi
0x14001a548  inc     dword ptr [rbx+260h]
0x14001a54e  mov     rcx, [rbx+58h]
0x14001a552  add     rcx, 20h ; ' '; Mutex
0x14001a556  xor     edx, edx; Wait
0x14001a558  call    cs:__imp_KeReleaseMutex
0x14001a55f  nop     dword ptr [rax+rax+00h]
0x14001a564  mov     eax, edi
0x14001a566  add     rsp, 40h
0x14001a56a  pop     rdi
0x14001a56b  pop     rsi
0x14001a56c  pop     rbx
0x14001a56d  retn
0x14002131b  push    rbp
0x14002131d  sub     rsp, 30h
0x140021321  mov     rbp, rdx
0x140021324  mov     r9d, [rbp+30h]
0x140021328  cmp     r9d, 103h
0x14002132f  jnz     short loc_14002133D
0x140021331  cmp     byte ptr [rbp+68h], 0
0x140021335  jz      short loc_14002133D
0x140021337  mov     r8, [rbp+60h]
0x14002133b  jmp     short loc_140021395
0x14002133d  mov     r8, [rbp+60h]
0x140021341  mov     ecx, [r8+260h]
0x140021348  mov     eax, 0CCCCCCCDh
0x14002134d  mul     ecx
0x14002134f  shr     edx, 3
0x140021352  lea     eax, [rdx+rdx*4]
0x140021355  add     eax, eax
0x140021357  sub     ecx, eax
0x140021359  mov     dword ptr [r8+rcx*8+210h], 1
0x140021365  mov     ecx, [r8+260h]
0x14002136c  mov     eax, 0CCCCCCCDh
0x140021371  mul     ecx
0x140021373  shr     edx, 3
0x140021376  lea     eax, [rdx+rdx*4]
0x140021379  add     eax, eax
0x14002137b  sub     ecx, eax
0x14002137d  mov     [r8+rcx*8+214h], r9d
0x140021385  mov     eax, [r8+260h]
0x14002138c  inc     eax
0x14002138e  mov     [r8+260h], eax
0x140021395  mov     rcx, [r8+58h]
0x140021399  add     rcx, 20h ; ' '; Mutex
0x14002139d  xor     edx, edx; Wait
0x14002139f  call    cs:__imp_KeReleaseMutex
0x1400213a6  nop     dword ptr [rax+rax+00h]
0x1400213ab  nop
0x1400213ac  add     rsp, 30h
0x1400213b0  pop     rbp
0x1400213b1  retn
```
