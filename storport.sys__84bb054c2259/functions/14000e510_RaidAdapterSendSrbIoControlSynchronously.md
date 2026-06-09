# RaidAdapterSendSrbIoControlSynchronously

- ea: `0x14000e510`
- end: `0x14000ebf6`
- name: `RaidAdapterSendSrbIoControlSynchronously`
- size: `1766`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `15`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140010488`
- `0x14002b5dc`
- `0x140086d68`
- `0x1400885b0`
- `0x1400889c8`
- `0x140088e00`
- `0x1400892b0`
- `0x1400897fc`
- `0x14008a124`
- `0x14008a930`
- `0x14008d494`
- `0x140091d5c`
- `0x140092280`
- `0x1400931b8`
- `0x1400b58d8`

## callees

- `0x14000684c`
- `0x140008258`
- `0x140008348`
- `0x140008eb0`
- `0x14000e350`
- `0x14000e510`
- `0x14000ebfc`
- `0x14000fda0`
- `0x14000ff50`
- `0x140010090`
- `0x1400290b0`
- `0x14002b518`
- `0x140030b30`
- `0x140038afc`
- `0x140040110`
- `0x140068894`
- `0x140093144`
- `0x140093e84`
- `0x1400b8cd0`
- `0x1400cf8b8`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14000e7ee`
- `ntoskrnl!PoFxIdleComponent` at `0x14000e7ee`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000ea38`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000ea38`
- `ntoskrnl!KeLowerIrql` at `0x14000ebcc`
- `ntoskrnl!KeLowerIrql` at `0x14000ebcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e898`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e898`
- `ntoskrnl!KeInitializeEvent` at `0x14000e6cb`
- `ntoskrnl!KeInitializeEvent` at `0x14000e954`
- `ntoskrnl!KeInitializeEvent` at `0x14000e6cb`
- `ntoskrnl!KeInitializeEvent` at `0x14000e954`
- `ntoskrnl!KfRaiseIrql` at `0x14000ebb4`
- `ntoskrnl!KfRaiseIrql` at `0x14000ebb4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e794`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e98d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e9d2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e794`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e98d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e9d2`
- `ntoskrnl!ExAllocatePool2` at `0x14000e5ae`
- `ntoskrnl!ExAllocatePool2` at `0x14000e5ae`
- `ntoskrnl!PoFxActivateComponent` at `0x14000e723`
- `ntoskrnl!PoFxActivateComponent` at `0x14000e723`

## pseudocode

```c
__int64 __fastcall RaidAdapterSendSrbIoControlSynchronously(
        int *a1,
        IRP *a2,
        __int64 a3,
        unsigned int a4,
        __int64 (__fastcall *a5)(_QWORD),
        char a6,
        int a7,
        unsigned int a8)
{
  _WORD *v8; // r13
  int v10; // ecx
  __int64 v12; // rdx
  __int64 v13; // r14
  __int64 v14; // rax
  unsigned int v15; // r15d
  __int64 v16; // rdx
  _WORD *Pool2; // rdi
  __int64 ContiguousIoResources; // rax
  __int64 v19; // rdx
  __int64 v20; // r15
  unsigned int v21; // ebx
  __int64 v22; // r8
  NTSTATUS v23; // r14d
  int v24; // eax
  int v25; // eax
  IRP *v26; // rax
  __int64 v27; // r8
  char v28; // r11
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  _QWORD *v36; // rcx
  __int64 Pool; // rax
  NTSTATUS v39; // eax
  bool v40; // zf
  __int64 v41; // rbx
  signed __int32 v42; // ecx
  KIRQL v43; // bl
  _BYTE *v44; // [rsp+30h] [rbp-30h]
  union _LARGE_INTEGER v45; // [rsp+38h] [rbp-28h] BYREF
  __int64 v46; // [rsp+40h] [rbp-20h]
  struct _KEVENT Event; // [rsp+48h] [rbp-18h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v49; // [rsp+B0h] [rbp+50h]
  unsigned int v50; // [rsp+B8h] [rbp+58h]

  v50 = a4;
  v49 = a3;
  v8 = 0;
  v45.QuadPart = 0;
  v10 = *a1;
  memset(&Event, 0, sizeof(Event));
  if ( v10 == 1314275652 )
  {
    v12 = (__int64)a1 + 282;
  }
  else
  {
    v12 = (__int64)a1 + 466;
    if ( v10 != 1094997074 )
      v12 = 98;
  }
  v13 = *((_QWORD *)a1 + 1);
  v44 = (_BYTE *)v12;
  v14 = 81;
  if ( v10 != 1314275652 )
    v14 = 127;
  v15 = (a1[v14] + 7) & 0xFFFFFFF8;
  if ( *(_BYTE *)v12 == 1 )
  {
    Pool = RaidAllocatePool(64, 144, 1918067026, v13);
    Pool2 = (_WORD *)Pool;
    if ( Pool )
    {
      *(_WORD *)Pool = 8;
      *(_BYTE *)(Pool + 2) = 40;
      *(_DWORD *)(Pool + 8) = 1397899864;
      *(_DWORD *)(Pool + 12) = 1;
      *(_DWORD *)(Pool + 16) = 144;
      *(_QWORD *)(Pool + 52) = 128;
      *(_DWORD *)(Pool + 20) = 2;
      *(_WORD *)(Pool + 36) = 2;
      *(_WORD *)(Pool + 128) = 1;
      *(_DWORD *)(Pool + 132) = 4;
    }
  }
  else
  {
    Pool2 = (_WORD *)ExAllocatePool2(64, 88, 1918067026);
    if ( !Pool2 && v13 )
      RaidLogAllocationFailure(v13, 64, 88, 1918067026, 0x80000000);
  }
  ContiguousIoResources = StorAllocateContiguousIoResources(v15 + 1200, v16, a1);
  v46 = ContiguousIoResources;
  if ( !Pool2 || !ContiguousIoResources )
  {
    v20 = 0;
    v23 = -1073741801;
    if ( !ContiguousIoResources )
      goto LABEL_49;
    goto LABEL_48;
  }
  v20 = ContiguousIoResources + 48;
  RaidZeroXrb(ContiguousIoResources + 48, v19, 0, 0);
  v21 = v50;
  v23 = RaidBuildMdlForXrb(v20, v49, v50);
  if ( v23 < 0 )
    goto LABEL_45;
  v24 = a7;
  if ( !a6 )
  {
    v24 = a7 | 0x102;
    if ( *((_BYTE *)Pool2 + 2) == 40 )
      Pool2[19] = 32;
    else
      *((_BYTE *)Pool2 + 9) = 32;
  }
  v25 = v24 | 1;
  if ( *v44 == 1 )
  {
    v41 = *((unsigned int *)Pool2 + 13);
    v8 = Pool2;
    *((_DWORD *)Pool2 + 5) = 2;
    *((_DWORD *)Pool2 + 6) = v25;
    if ( *a1 == 1094997074 && (*((_BYTE *)a1 + 111) & 4) != 0 )
    {
      LODWORD(v22) = HIDWORD(KeGetPcr()[1].LockArray);
      v42 = _InterlockedIncrement(*(volatile signed __int32 **)(*((_QWORD *)a1 + 779) + 8 * v22));
      *((_DWORD *)Pool2 + 11) = (unsigned __int16)v22;
    }
    else
    {
      v42 = -1;
    }
    *((_DWORD *)Pool2 + 8) = v42;
    *((_QWORD *)Pool2 + 8) = v49;
    *((_DWORD *)Pool2 + 15) = v50;
    Pool2[18] = IoGetIoPriorityHint(a2);
    *((_DWORD *)Pool2 + 10) = a1[1047];
    *((_QWORD *)Pool2 + 12) = v20;
    *((_QWORD *)Pool2 + 10) = a2;
    *(_WORD *)((char *)Pool2 + v41 + 8) = 0;
    *((_BYTE *)Pool2 + v41 + 10) = 0;
    *(_QWORD *)(v20 + 168) = Pool2;
    *(_QWORD *)(v20 + 184) = *((_QWORD *)Pool2 + 8);
    v26 = (IRP *)*((_QWORD *)Pool2 + 12);
  }
  else
  {
    *((_DWORD *)Pool2 + 3) = v25;
    *((_QWORD *)Pool2 + 3) = v49;
    *Pool2 = 88;
    *((_BYTE *)Pool2 + 2) = 2;
    *((_BYTE *)Pool2 + 8) = -1;
    *((_DWORD *)Pool2 + 4) = v21;
    *((_DWORD *)Pool2 + 5) = a1[1047];
    *((_QWORD *)Pool2 + 6) = v20;
    *(_WORD *)((char *)Pool2 + 5) = 0;
    *((_BYTE *)Pool2 + 7) = 0;
    *(_QWORD *)(v20 + 168) = Pool2;
    *(_QWORD *)(v20 + 184) = *((_QWORD *)Pool2 + 3);
    v26 = a2;
  }
  v27 = v46 + 1200;
  *(_QWORD *)(v20 + 176) = v26;
  RaSrbSetMiniportContext(a1, Pool2, v27);
  if ( a6 != v28 )
    *(_BYTE *)(v20 + 17) |= 8u;
  KeInitializeEvent((PRKEVENT)(v20 + 664), NotificationEvent, 0);
  v40 = a6 == 0;
  *(_QWORD *)(v20 + 656) = RaidXrbSignalCompletion;
  if ( !v40 )
  {
    Timeout.QuadPart = 0;
    RaidPauseAdapterQueue(a1);
    KeInitializeEvent(&Event, NotificationEvent, 0);
    StorSetIoGatewayEmptyEvent(*((_QWORD *)a1 + 128), &Event);
    Timeout.QuadPart = -1200000000;
    v39 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
    v40 = v39 == 0;
    if ( v39 >= 0 )
      v40 = (unsigned int)GatewayWaitForForwardIoWithTimeout(a1, 120000) == 0;
    if ( !v40 )
    {
      v23 = -1073741823;
      a2->IoStatus.Information = 0;
      goto LABEL_48;
    }
  }
  if ( *((_QWORD *)a1 + 628) )
  {
    if ( (a1[27] & 1) != 0 )
    {
      _InterlockedAdd64((volatile signed __int64 *)a1 + 668, 1u);
      if ( (a1[27] & 2) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)a1 + 669, 1u);
    }
    v29 = 5;
    if ( !a1[23] )
      v29 = 1;
    PoFxActivateComponent(**((_QWORD **)a1 + 628), 0, v29);
  }
  if ( *v44 == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
        v20,
        v8,
        *((_QWORD *)v8 + 13));
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      61,
      WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
      v20,
      Pool2,
      *((_QWORD *)Pool2 + 7));
  }
  if ( *((_BYTE *)a1 + 4434) )
    v30 = RaidAdapterRaiseIrqlAndExecuteXrb(a1, v20);
  else
    v30 = RaidAdapterPostScatterGatherExecute(a1, v20);
  v23 = v30;
  if ( v30 < 0 )
  {
LABEL_33:
    if ( v23 != 258 )
      goto LABEL_34;
    goto LABEL_71;
  }
  if ( a8 )
  {
    v45.QuadPart = -10000000LL * a8;
    v23 = KeWaitForSingleObject((PVOID)(v20 + 664), Executive, 0, 0, &v45);
  }
  else
  {
    KeWaitForSingleObject((PVOID)(v20 + 664), Executive, 0, 0, 0);
  }
  if ( v23 != 258 )
  {
    LOBYTE(v33) = *((_BYTE *)Pool2 + 3);
    v23 = RaidSrbStatusToNtStatus(v33, v32, v34, v35);
    goto LABEL_33;
  }
  _InterlockedIncrement(a1 + 1561);
LABEL_71:
  RaidAdapterResetBus(a1, 0);
LABEL_34:
  if ( a6 )
  {
    v43 = KfRaiseIrql(2u);
    RaidResumeAndRestartAdapterQueues(a1);
    KeLowerIrql(v43);
  }
  if ( (*(_BYTE *)(v20 + 17) & 1) != 0 )
  {
    RaidAdapterPoFxIdleComponentFromMiniport(a1, *(unsigned int *)(v20 + 748), v31);
    *(_BYTE *)(v20 + 17) &= ~1u;
  }
  v36 = (_QWORD *)*((_QWORD *)a1 + 628);
  if ( v36 )
  {
    PoFxIdleComponent(*v36, 0, 0);
    v36 = (_QWORD *)*(unsigned int *)(*((_QWORD *)a1 + 628) + 20LL);
  }
  if ( v23 >= 0 )
  {
    if ( v23 == 258 )
    {
LABEL_46:
      v23 = -1073741643;
      goto LABEL_48;
    }
    if ( !a5 || (v23 = a5(*(unsigned int *)(v49 + 20)), v23 >= 0) )
    {
      LOBYTE(v36) = *((_BYTE *)Pool2 + 3);
      v23 = PortSrbTranslateSrbToNtStatus(v36);
    }
  }
LABEL_45:
  if ( v23 == 258 )
    goto LABEL_46;
LABEL_48:
  RaidXrbDeallocateResources(v20, 0);
  StorFreeContiguousIoResources(a1, v46);
LABEL_49:
  if ( Pool2 )
  {
    if ( *v44 == 1 )
    {
      if ( !v8 )
        v8 = Pool2;
      *((_QWORD *)v8 + 10) = 0;
      *((_QWORD *)v8 + 13) = 0;
    }
    else
    {
      *((_QWORD *)Pool2 + 6) = 0;
      *((_QWORD *)Pool2 + 7) = 0;
    }
    ExFreePoolWithTag(Pool2, 0x72536152u);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14000e510  mov     [rsp-38h+arg_8], rbx
0x14000e515  mov     [rsp-38h+arg_18], r9d
0x14000e51a  mov     [rsp-38h+arg_10], r8
0x14000e51f  push    rbp
0x14000e520  push    rsi
0x14000e521  push    rdi
0x14000e522  push    r12
0x14000e524  push    r13
0x14000e526  push    r14
0x14000e528  push    r15
0x14000e52a  mov     rbp, rsp
0x14000e52d  sub     rsp, 60h
0x14000e531  xor     r13d, r13d
0x14000e534  xor     eax, eax
0x14000e536  mov     rsi, rcx
0x14000e539  mov     qword ptr [rbp+var_28], r13
0x14000e53d  mov     ecx, [rcx]
0x14000e53f  mov     r9d, 4E564144h
0x14000e545  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14000e549  xorps   xmm0, xmm0
0x14000e54c  mov     r12, rdx
0x14000e54f  movups  xmmword ptr [rbp+Event.Header.___u0], xmm0
0x14000e553  cmp     ecx, r9d
0x14000e556  jz      loc_14000E8CA
0x14000e55c  lea     rdx, [rsi+1D2h]
0x14000e563  cmp     ecx, 41445452h
0x14000e569  jnz     loc_14000EAE1
0x14000e56f  mov     r14, [rsi+8]
0x14000e573  cmp     ecx, r9d
0x14000e576  mov     r8d, 1FCh
0x14000e57c  mov     [rbp+var_30], rdx
0x14000e580  mov     eax, 144h
0x14000e585  cmovnz  eax, r8d
0x14000e589  mov     r8d, 72536152h
0x14000e58f  mov     r15d, [rax+rsi]
0x14000e593  add     r15d, 7
0x14000e597  and     r15d, 0FFFFFFF8h
0x14000e59b  cmp     byte ptr [rdx], 1
0x14000e59e  jz      loc_14000E8D6
0x14000e5a4  mov     edx, 58h ; 'X'
0x14000e5a9  lea     ebx, [rdx-18h]
0x14000e5ac  mov     ecx, ebx
0x14000e5ae  call    cs:__imp_ExAllocatePool2
0x14000e5b5  nop     dword ptr [rax+rax+00h]
0x14000e5ba  mov     rdi, rax
0x14000e5bd  test    rax, rax
0x14000e5c0  jz      loc_14000EAF6
0x14000e5c6  mov     r8, rsi
0x14000e5c9  lea     ecx, [r15+4B0h]
0x14000e5d0  call    StorAllocateContiguousIoResources
0x14000e5d5  mov     [rbp+var_20], rax
0x14000e5d9  test    rdi, rdi
0x14000e5dc  jz      loc_14000E84A
0x14000e5e2  test    rax, rax
0x14000e5e5  jz      loc_14000E84A
0x14000e5eb  lea     r15, [rax+30h]
0x14000e5ef  xor     r9d, r9d
0x14000e5f2  mov     rcx, r15
0x14000e5f5  xor     r8d, r8d
0x14000e5f8  call    RaidZeroXrb
0x14000e5fd  mov     ebx, [rbp+arg_18]
0x14000e600  mov     rcx, r15
0x14000e603  mov     rdx, [rbp+arg_10]
0x14000e607  mov     r8d, ebx
0x14000e60a  call    RaidBuildMdlForXrb
0x14000e60f  xor     r11d, r11d
0x14000e612  mov     r14d, eax
0x14000e615  test    eax, eax
0x14000e617  js      loc_14000E839
0x14000e61d  mov     eax, [rbp+arg_30]
0x14000e620  cmp     [rbp+arg_28], r11b
0x14000e624  jnz     short loc_14000E639
0x14000e626  or      eax, 102h
0x14000e62b  cmp     byte ptr [rdi+2], 28h ; '('
0x14000e62f  jz      loc_14000EAEB
0x14000e635  mov     byte ptr [rdi+9], 20h ; ' '
0x14000e639  mov     r14, [rbp+var_30]
0x14000e63d  mov     r9d, 1
0x14000e643  or      eax, r9d
0x14000e646  cmp     [r14], r9b
0x14000e649  jz      loc_14000EA02
0x14000e64f  mov     [rdi+0Ch], eax
0x14000e652  mov     rax, [rbp+arg_10]
0x14000e656  mov     [rdi+18h], rax
0x14000e65a  mov     word ptr [rdi], 58h ; 'X'
0x14000e65f  mov     byte ptr [rdi+2], 2
0x14000e663  mov     byte ptr [rdi+8], 0FFh
0x14000e667  mov     [rdi+10h], ebx
0x14000e66a  mov     eax, [rsi+105Ch]
0x14000e670  mov     [rdi+14h], eax
0x14000e673  mov     [rdi+30h], r15
0x14000e677  mov     [rdi+5], r11w
0x14000e67c  mov     [rdi+7], r11b
0x14000e680  mov     [r15+0A8h], rdi
0x14000e687  mov     rax, [rdi+18h]
0x14000e68b  mov     [r15+0B8h], rax
0x14000e692  mov     rax, r12
0x14000e695  mov     r8, [rbp+var_20]
0x14000e699  mov     rdx, rdi
0x14000e69c  add     r8, 4B0h
0x14000e6a3  mov     [r15+0B0h], rax
0x14000e6aa  mov     rcx, rsi
0x14000e6ad  call    RaSrbSetMiniportContext
0x14000e6b2  cmp     [rbp+arg_28], r11b
0x14000e6b6  jnz     loc_14000EB23
0x14000e6bc  lea     rbx, [r15+298h]
0x14000e6c3  xor     r8d, r8d; State
0x14000e6c6  mov     rcx, rbx; Event
0x14000e6c9  xor     edx, edx; Type
0x14000e6cb  call    cs:__imp_KeInitializeEvent
0x14000e6d2  nop     dword ptr [rax+rax+00h]
0x14000e6d7  cmp     [rbp+arg_28], 0
0x14000e6db  lea     rax, RaidXrbSignalCompletion
0x14000e6e2  mov     [r15+290h], rax
0x14000e6e9  jnz     loc_14000E93B
0x14000e6ef  xor     r12d, r12d
0x14000e6f2  cmp     [rsi+13A0h], r12
0x14000e6f9  jz      short loc_14000E739
0x14000e6fb  lea     ecx, [r12+1]
0x14000e700  test    [rsi+6Ch], cl
0x14000e703  jnz     loc_14000EAC2
0x14000e709  cmp     [rsi+5Ch], r12d
0x14000e70d  mov     r8d, 5
0x14000e713  cmovbe  r8d, ecx
0x14000e717  mov     rcx, [rsi+13A0h]
0x14000e71e  xor     edx, edx
0x14000e720  mov     rcx, [rcx]
0x14000e723  call    cs:__imp_PoFxActivateComponent
0x14000e72a  nop     dword ptr [rax+rax+00h]
0x14000e72f  mov     rax, [rsi+13A0h]
0x14000e736  mov     ecx, [rax+14h]
0x14000e739  cmp     byte ptr [r14], 1
0x14000e73d  jz      loc_14000EB41
0x14000e743  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e74a  lea     rax, WPP_GLOBAL_Control
0x14000e751  cmp     rcx, rax
0x14000e754  jnz     loc_14000EB85
0x14000e75a  mov     rdx, r15
0x14000e75d  mov     rcx, rsi
0x14000e760  cmp     [rsi+1152h], r12b
0x14000e767  jz      loc_14000E8C0
0x14000e76d  call    RaidAdapterRaiseIrqlAndExecuteXrb
0x14000e772  mov     r14d, eax
0x14000e775  test    eax, eax
0x14000e777  js      short loc_14000E7B8
0x14000e779  mov     eax, [rbp+arg_38]
0x14000e77c  xor     r9d, r9d; Alertable
0x14000e77f  xor     r8d, r8d; WaitMode
0x14000e782  xor     edx, edx; WaitReason
0x14000e784  test    eax, eax
0x14000e786  jnz     loc_14000E9BB
0x14000e78c  mov     rcx, rbx; Object
0x14000e78f  mov     [rsp+60h+Timeout], r12; Timeout
0x14000e794  call    cs:__imp_KeWaitForSingleObject
0x14000e79b  nop     dword ptr [rax+rax+00h]
0x14000e7a0  cmp     r14d, 102h
0x14000e7a7  jz      loc_14000EA82
0x14000e7ad  mov     cl, [rdi+3]
0x14000e7b0  call    RaidSrbStatusToNtStatus
0x14000e7b5  mov     r14d, eax
0x14000e7b8  cmp     r14d, 102h
0x14000e7bf  jz      loc_14000EA89
0x14000e7c5  cmp     [rbp+arg_28], r12b
0x14000e7c9  jnz     loc_14000EBB2
0x14000e7cf  test    byte ptr [r15+11h], 1
0x14000e7d4  jnz     loc_14000EBDD
0x14000e7da  mov     rcx, [rsi+13A0h]
0x14000e7e1  test    rcx, rcx
0x14000e7e4  jz      short loc_14000E804
0x14000e7e6  mov     rcx, [rcx]
0x14000e7e9  xor     r8d, r8d
0x14000e7ec  xor     edx, edx
0x14000e7ee  call    cs:__imp_PoFxIdleComponent
0x14000e7f5  nop     dword ptr [rax+rax+00h]
0x14000e7fa  mov     rax, [rsi+13A0h]
0x14000e801  mov     ecx, [rax+14h]
0x14000e804  test    r14d, r14d
0x14000e807  js      short loc_14000E839
0x14000e809  cmp     r14d, 102h
0x14000e810  jz      short loc_14000E842
0x14000e812  mov     rax, [rbp+arg_20]
0x14000e816  test    rax, rax
0x14000e819  jz      short loc_14000E82E
0x14000e81b  mov     rcx, [rbp+arg_10]
0x14000e81f  mov     ecx, [rcx+14h]
0x14000e822  call    _guard_dispatch_icall
0x14000e827  mov     r14d, eax
0x14000e82a  test    eax, eax
0x14000e82c  js      short loc_14000E839
0x14000e82e  mov     cl, [rdi+3]
0x14000e831  call    PortSrbTranslateSrbToNtStatus
0x14000e836  mov     r14d, eax
0x14000e839  cmp     r14d, 102h
0x14000e840  jnz     short loc_14000E858
0x14000e842  mov     r14d, 0C00000B5h
0x14000e848  jmp     short loc_14000E858
0x14000e84a  xor     r15d, r15d
0x14000e84d  mov     r14d, 0C0000017h
0x14000e853  test    rax, rax
0x14000e856  jz      short loc_14000E86E
0x14000e858  xor     edx, edx
0x14000e85a  mov     rcx, r15
0x14000e85d  call    RaidXrbDeallocateResources
0x14000e862  mov     rdx, [rbp+var_20]
0x14000e866  mov     rcx, rsi
0x14000e869  call    StorFreeContiguousIoResources
0x14000e86e  test    rdi, rdi
0x14000e871  jz      short loc_14000E8A4
0x14000e873  mov     rax, [rbp+var_30]
0x14000e877  cmp     byte ptr [rax], 1
0x14000e87a  jz      loc_14000E9E6
0x14000e880  mov     qword ptr [rdi+30h], 0
0x14000e888  mov     qword ptr [rdi+38h], 0
0x14000e890  mov     edx, 72536152h; Tag
0x14000e895  mov     rcx, rdi; P
0x14000e898  call    cs:__imp_ExFreePoolWithTag
0x14000e89f  nop     dword ptr [rax+rax+00h]
0x14000e8a4  mov     rbx, [rsp+60h+arg_8]
0x14000e8ac  mov     eax, r14d
0x14000e8af  add     rsp, 60h
0x14000e8b3  pop     r15
0x14000e8b5  pop     r14
0x14000e8b7  pop     r13
0x14000e8b9  pop     r12
0x14000e8bb  pop     rdi
0x14000e8bc  pop     rsi
0x14000e8bd  pop     rbp
0x14000e8be  retn
0x14000e8c0  call    RaidAdapterPostScatterGatherExecute
0x14000e8c5  jmp     loc_14000E772
0x14000e8ca  lea     rdx, [rsi+11Ah]
0x14000e8d1  jmp     loc_14000E56F
0x14000e8d6  mov     r9, r14
0x14000e8d9  mov     r14d, 90h
0x14000e8df  mov     edx, r14d
0x14000e8e2  lea     ecx, [r14-50h]
0x14000e8e6  call    RaidAllocatePool
0x14000e8eb  mov     rdi, rax
0x14000e8ee  test    rax, rax
0x14000e8f1  jz      loc_14000E5C6
0x14000e8f7  mov     word ptr [rax], 8
0x14000e8fc  mov     byte ptr [rax+2], 28h ; '('
0x14000e900  mov     dword ptr [rax+8], 53524258h
0x14000e907  mov     eax, 1
0x14000e90c  mov     [rdi+0Ch], eax
0x14000e90f  mov     [rdi+10h], r14d
0x14000e913  mov     qword ptr [rdi+34h], 80h
0x14000e91b  lea     ecx, [rax+1]
0x14000e91e  mov     [rdi+14h], ecx
0x14000e921  mov     [rdi+24h], cx
0x14000e925  mov     [rdi+80h], ax
0x14000e92c  mov     dword ptr [rdi+84h], 4
0x14000e936  jmp     loc_14000E5C6
0x14000e93b  mov     rcx, rsi
0x14000e93e  mov     qword ptr [rbp+arg_0], 0
0x14000e946  call    RaidPauseAdapterQueue
0x14000e94b  xor     r8d, r8d; State
0x14000e94e  lea     rcx, [rbp+Event]; Event
0x14000e952  xor     edx, edx; Type
0x14000e954  call    cs:__imp_KeInitializeEvent
0x14000e95b  nop     dword ptr [rax+rax+00h]
0x14000e960  mov     rcx, [rsi+400h]
0x14000e967  lea     rdx, [rbp+Event]
0x14000e96b  call    StorSetIoGatewayEmptyEvent
0x14000e970  lea     rax, [rbp+arg_0]
0x14000e974  mov     qword ptr [rbp+arg_0], 0FFFFFFFFB8797400h
0x14000e97c  xor     r9d, r9d; Alertable
0x14000e97f  mov     [rsp+60h+Timeout], rax; Timeout
0x14000e984  xor     r8d, r8d; WaitMode
0x14000e987  lea     rcx, [rbp+Event]; Object
0x14000e98b  xor     edx, edx; WaitReason
0x14000e98d  call    cs:__imp_KeWaitForSingleObject
0x14000e994  nop     dword ptr [rax+rax+00h]
0x14000e999  test    eax, eax
0x14000e99b  jns     loc_14000EB2D
0x14000e9a1  jz      loc_14000E6EF
0x14000e9a7  mov     r14d, 0C0000001h
0x14000e9ad  mov     qword ptr [r12+38h], 0
0x14000e9b6  jmp     loc_14000E858
0x14000e9bb  imul    rcx, rax, 0FFFFFFFFFF676980h
0x14000e9c2  lea     rax, [rbp+var_28]
0x14000e9c6  mov     qword ptr [rbp+var_28], rcx
0x14000e9ca  mov     rcx, rbx; Object
0x14000e9cd  mov     [rsp+60h+Timeout], rax; Timeout
0x14000e9d2  call    cs:__imp_KeWaitForSingleObject
0x14000e9d9  nop     dword ptr [rax+rax+00h]
0x14000e9de  mov     r14d, eax
0x14000e9e1  jmp     loc_14000E7A0
0x14000e9e6  test    r13, r13
0x14000e9e9  cmovz   r13, rdi
0x14000e9ed  mov     qword ptr [r13+50h], 0
0x14000e9f5  mov     qword ptr [r13+68h], 0
0x14000e9fd  jmp     loc_14000E890
0x14000ea02  mov     ebx, [rdi+34h]
0x14000ea05  mov     r13, rdi
0x14000ea08  mov     dword ptr [rdi+14h], 2
0x14000ea0f  mov     [rdi+18h], eax
0x14000ea12  cmp     dword ptr [rsi], 41445452h
0x14000ea18  jnz     short loc_14000EA21
0x14000ea1a  mov     al, [rsi+6Fh]
  ... truncated ...
```
