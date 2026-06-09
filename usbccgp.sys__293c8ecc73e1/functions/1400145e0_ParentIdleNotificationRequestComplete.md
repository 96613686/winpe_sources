# ParentIdleNotificationRequestComplete

- ea: `0x1400145e0`
- end: `0x140014881`
- name: `ParentIdleNotificationRequestComplete`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x1400059e4`
- `0x14000773c`
- `0x140007c38`
- `0x140008230`
- `0x14000a6cc`
- `0x14000b4bc`
- `0x14000ba3c`
- `0x1400145e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400147f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147f6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001485e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001485e`
- `ntoskrnl!KeReadStateEvent` at `0x140014748`
- `ntoskrnl!KeReadStateEvent` at `0x14001475f`
- `ntoskrnl!KeReadStateEvent` at `0x140014748`
- `ntoskrnl!KeReadStateEvent` at `0x14001475f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014732`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014732`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014793`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014793`
- `ntoskrnl!KeSetEvent` at `0x140014837`
- `ntoskrnl!KeSetEvent` at `0x140014837`
- `ntoskrnl!ExAllocatePool2` at `0x1400146d8`
- `ntoskrnl!ExAllocatePool2` at `0x1400146d8`

## pseudocode

```c
__int64 __fastcall ParentIdleNotificationRequestComplete(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 v3; // rbx
  _DWORD *v4; // r15
  _QWORD *v5; // r14
  int v6; // eax
  int v7; // ebp
  int v8; // edx
  int v9; // eax
  int v10; // edx
  __int64 v11; // r8
  unsigned int v12; // edi
  __int64 Pool2; // rax
  int v14; // edx
  void *v15; // rsi
  char v16; // di
  KIRQL v17; // r14
  int Worker; // eax
  int v19; // edx

  v3 = a3;
  v4 = a2;
  v5 = (_QWORD *)(a3 + 1368);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = a2[12];
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qD(
      *v5,
      (_DWORD)a2,
      7,
      28,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      *(_QWORD *)(a3 + 32),
      v6);
  }
  v7 = v4[12];
  LOBYTE(a3) = 1;
  ChangeIdleState(v3, 3, a3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_D(*v5, v8, 7, 29, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids, *(_DWORD *)(v3 + 4));
  }
  v9 = FdoSendSetPowerRequest((POWER_STATE)1, 0);
  if ( v9 != 259 && v9 != -2147483631 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(*v5, v10, 8, 30, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids, v9);
    }
    v12 = -1073741670;
    goto LABEL_24;
  }
  Pool2 = ExAllocatePool2(64, 24, 1130525525);
  v15 = (void *)Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(*v5, v14, 8, 31, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids, 154);
    }
    goto LABEL_24;
  }
  *(_DWORD *)(Pool2 + 8) = v7;
  v16 = 0;
  *(_QWORD *)(Pool2 + 16) = v4;
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 344));
  if ( KeReadStateEvent((PRKEVENT)(v3 + 312)) )
  {
    if ( KeReadStateEvent((PRKEVENT)(v3 + 416)) )
    {
      v16 = 1;
      goto LABEL_19;
    }
    *(_DWORD *)(v3 + 1228) |= 0x20u;
  }
  else
  {
    *(_DWORD *)(v3 + 1228) |= 0x10u;
  }
  *(_QWORD *)(v3 + 1232) = v15;
  v15 = 0;
LABEL_19:
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 344), v17);
  if ( !v16 )
    return 3221225494LL;
  Worker = AllocateWorker(v3, IdleFinishCompletionWorker, v15);
  v12 = Worker;
  if ( Worker >= 0 )
    return 3221225494LL;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v3 + 1368),
      v19,
      8,
      32,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      Worker);
  }
  ExFreePoolWithTag(v15, 0x43627355u);
LABEL_24:
  if ( !*(_BYTE *)(v3 + 1362) || *(_DWORD *)(v3 + 576) == 2 )
    CompleteAllFunctionIdleIrps(v3, v12);
  LOBYTE(v11) = 1;
  ChangeIdleState(v3, 0, v11);
  KeSetEvent((PRKEVENT)(v3 + 960), 0, 0);
  UsbcReleaseRemoveLock(v3, v4);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 200), v4, 0x20u);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400145e0  push    rbx
0x1400145e2  push    rbp
0x1400145e3  push    rsi
0x1400145e4  push    rdi
0x1400145e5  push    r12
0x1400145e7  push    r13
0x1400145e9  push    r14
0x1400145eb  push    r15
0x1400145ed  sub     rsp, 48h
0x1400145f1  mov     rbx, r8
0x1400145f4  mov     r15, rdx
0x1400145f7  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400145fe  mov     esi, 7
0x140014603  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001460a  lea     r14, [r8+558h]
0x140014611  lea     r13, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140014618  jz      short loc_140014640
0x14001461a  mov     eax, [rdx+30h]
0x14001461d  lea     r9d, [rsi+15h]
0x140014621  mov     rcx, [r14]
0x140014624  mov     dl, 4
0x140014626  mov     [rsp+88h+var_58], eax
0x14001462a  mov     rax, [r8+20h]
0x14001462e  mov     r8d, esi
0x140014631  mov     [rsp+88h+var_60], rax
0x140014636  mov     [rsp+88h+var_68], r13
0x14001463b  call    WPP_RECORDER_SF_qD
0x140014640  mov     ebp, [r15+30h]
0x140014644  mov     r8b, 1
0x140014647  mov     edx, 3
0x14001464c  mov     rcx, rbx
0x14001464f  call    ChangeIdleState
0x140014654  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001465b  jz      short loc_14001467C
0x14001465d  mov     eax, [rbx+4]
0x140014660  mov     r9d, 1Dh
0x140014666  mov     rcx, [r14]
0x140014669  mov     r8d, esi
0x14001466c  mov     dword ptr [rsp+88h+var_60], eax
0x140014670  mov     dl, 4
0x140014672  mov     [rsp+88h+var_68], r13
0x140014677  call    WPP_RECORDER_SF_D
0x14001467c  xor     edx, edx; CompletionFunction
0x14001467e  mov     r9, rbx
0x140014681  xor     r8d, r8d
0x140014684  lea     ecx, [rdx+1]; PowerState
0x140014687  call    FdoSendSetPowerRequest
0x14001468c  cmp     eax, 103h
0x140014691  jz      short loc_1400146CA
0x140014693  cmp     eax, 80000011h
0x140014698  jz      short loc_1400146CA
0x14001469a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400146a1  jz      short loc_1400146C0
0x1400146a3  mov     rcx, [r14]
0x1400146a6  mov     r9d, 1Eh
0x1400146ac  mov     dword ptr [rsp+88h+var_60], eax
0x1400146b0  mov     dl, 2
0x1400146b2  mov     [rsp+88h+var_68], r13
0x1400146b7  lea     r8d, [r9-16h]
0x1400146bb  call    WPP_RECORDER_SF_d
0x1400146c0  mov     edi, 0C000009Ah
0x1400146c5  jmp     loc_140014802
0x1400146ca  mov     edx, 18h
0x1400146cf  mov     r8d, 43627355h
0x1400146d5  lea     ecx, [rdx+28h]
0x1400146d8  call    cs:__imp_ExAllocatePool2
0x1400146df  nop     dword ptr [rax+rax+00h]
0x1400146e4  mov     rsi, rax
0x1400146e7  test    rax, rax
0x1400146ea  jnz     short loc_14001471E
0x1400146ec  mov     edi, 0C000009Ah
0x1400146f1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400146f8  jz      loc_140014802
0x1400146fe  mov     rcx, [r14]
0x140014701  lea     r9d, [rax+1Fh]
0x140014705  mov     dword ptr [rsp+88h+var_60], edi
0x140014709  lea     r8d, [rax+8]
0x14001470d  mov     dl, 2
0x14001470f  mov     [rsp+88h+var_68], r13
0x140014714  call    WPP_RECORDER_SF_d
0x140014719  jmp     loc_140014802
0x14001471e  mov     [rax+8], ebp
0x140014721  xor     dil, dil
0x140014724  lea     rbp, [rbx+158h]
0x14001472b  mov     [rax+10h], r15
0x14001472f  mov     rcx, rbp; SpinLock
0x140014732  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014739  nop     dword ptr [rax+rax+00h]
0x14001473e  lea     rcx, [rbx+138h]; Event
0x140014745  mov     r14b, al
0x140014748  call    cs:__imp_KeReadStateEvent
0x14001474f  nop     dword ptr [rax+rax+00h]
0x140014754  test    eax, eax
0x140014756  jz      short loc_14001477D
0x140014758  lea     rcx, [rbx+1A0h]; Event
0x14001475f  call    cs:__imp_KeReadStateEvent
0x140014766  nop     dword ptr [rax+rax+00h]
0x14001476b  test    eax, eax
0x14001476d  jz      short loc_140014774
0x14001476f  mov     dil, 1
0x140014772  jmp     short loc_14001478D
0x140014774  or      dword ptr [rbx+4CCh], 20h
0x14001477b  jmp     short loc_140014784
0x14001477d  or      dword ptr [rbx+4CCh], 10h
0x140014784  mov     [rbx+4D0h], rsi
0x14001478b  xor     esi, esi
0x14001478d  mov     dl, r14b; NewIrql
0x140014790  mov     rcx, rbp; SpinLock
0x140014793  call    cs:__imp_KeReleaseSpinLock
0x14001479a  nop     dword ptr [rax+rax+00h]
0x14001479f  test    dil, dil
0x1400147a2  jz      loc_14001486A
0x1400147a8  mov     r8, rsi
0x1400147ab  lea     rdx, IdleFinishCompletionWorker
0x1400147b2  mov     rcx, rbx
0x1400147b5  call    AllocateWorker
0x1400147ba  mov     edi, eax
0x1400147bc  test    eax, eax
0x1400147be  jns     loc_14001486A
0x1400147c4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400147cb  jz      short loc_1400147EE
0x1400147cd  mov     rcx, [rbx+558h]
0x1400147d4  mov     r9d, 20h ; ' '
0x1400147da  mov     dword ptr [rsp+88h+var_60], eax
0x1400147de  mov     dl, 2
0x1400147e0  mov     [rsp+88h+var_68], r13
0x1400147e5  lea     r8d, [r9-18h]
0x1400147e9  call    WPP_RECORDER_SF_d
0x1400147ee  mov     edx, 43627355h; Tag
0x1400147f3  mov     rcx, rsi; P
0x1400147f6  call    cs:__imp_ExFreePoolWithTag
0x1400147fd  nop     dword ptr [rax+rax+00h]
0x140014802  cmp     byte ptr [rbx+552h], 0
0x140014809  jz      short loc_140014814
0x14001480b  cmp     dword ptr [rbx+240h], 2
0x140014812  jnz     short loc_14001481E
0x140014814  mov     edx, edi
0x140014816  mov     rcx, rbx
0x140014819  call    CompleteAllFunctionIdleIrps
0x14001481e  mov     r8b, 1
0x140014821  xor     edx, edx
0x140014823  mov     rcx, rbx
0x140014826  call    ChangeIdleState
0x14001482b  lea     rcx, [rbx+3C0h]; Event
0x140014832  xor     r8d, r8d; Wait
0x140014835  xor     edx, edx; Increment
0x140014837  call    cs:__imp_KeSetEvent
0x14001483e  nop     dword ptr [rax+rax+00h]
0x140014843  mov     rdx, r15
0x140014846  mov     rcx, rbx
0x140014849  call    UsbcReleaseRemoveLock
0x14001484e  lea     rcx, [rbx+0C8h]; RemoveLock
0x140014855  mov     r8d, 20h ; ' '; RemlockSize
0x14001485b  mov     rdx, r15; Tag
0x14001485e  call    cs:__imp_IoReleaseRemoveLockEx
0x140014865  nop     dword ptr [rax+rax+00h]
0x14001486a  mov     eax, 0C0000016h
0x14001486f  add     rsp, 48h
0x140014873  pop     r15
0x140014875  pop     r14
0x140014877  pop     r13
0x140014879  pop     r12
0x14001487b  pop     rdi
0x14001487c  pop     rsi
0x14001487d  pop     rbp
0x14001487e  pop     rbx
0x14001487f  retn
```
