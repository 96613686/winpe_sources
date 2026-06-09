# PgmSendRequestFromClient

- ea: `0x140019424`
- end: `0x140019f68`
- name: `PgmSendRequestFromClient`
- size: `2884`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007d90`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400052e4`
- `0x1400054d0`
- `0x140005524`
- `0x1400067f4`
- `0x140007524`
- `0x140009f50`
- `0x140019424`
- `0x14001b398`
- `0x14001cdf0`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140019d7e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140019dfb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140019d7e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140019dfb`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001991f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140019a18`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001991f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140019a18`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400195cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001964a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400195cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001964a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019668`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019877`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001988e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019cf5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019d3f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019668`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019877`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001988e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019cf5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019d3f`
- `ntoskrnl!KeStackAttachProcess` at `0x1400197db`
- `ntoskrnl!KeStackAttachProcess` at `0x1400197db`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140019838`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400198f7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140019838`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400198f7`
- `ntoskrnl!ZwClose` at `0x1400198e2`
- `ntoskrnl!ZwClose` at `0x1400198e2`
- `ntoskrnl!KeInitializeTimer` at `0x1400199b0`
- `ntoskrnl!KeInitializeTimer` at `0x1400199b0`
- `ntoskrnl!KeInitializeDpc` at `0x1400199d0`
- `ntoskrnl!KeInitializeDpc` at `0x1400199d0`
- `ntoskrnl!KeSetTimer` at `0x1400199e9`
- `ntoskrnl!KeSetTimer` at `0x1400199e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019795`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019795`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400197aa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400197aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019852`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019e84`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019852`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019e84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001985e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019e90`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001985e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019e90`
- `ntoskrnl!KeSetEvent` at `0x140019e53`
- `ntoskrnl!KeSetEvent` at `0x140019e53`
- `ntoskrnl!PsCreateSystemThread` at `0x140019819`
- `ntoskrnl!PsCreateSystemThread` at `0x140019819`
- `ntoskrnl!KeGetCurrentIrql` at `0x140019779`
- `ntoskrnl!KeGetCurrentIrql` at `0x140019779`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400197be`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400197be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001973e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019756`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001976d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019f29`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001973e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019756`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001976d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019f29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001948b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019592`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400195b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001990a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019933`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001994a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001948b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019592`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400195b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001990a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019933`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001994a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a43`

## pseudocode

```c
__int64 __fastcall PgmSendRequestFromClient(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 StartContext; // r13
  __int64 v7; // r12
  KIRQL v8; // al
  KIRQL v9; // r14
  __int64 v10; // r14
  unsigned int v11; // ebx
  _DWORD *v12; // rsi
  KIRQL v13; // dl
  _QWORD *v14; // r15
  int v15; // ebx
  unsigned int v16; // ebx
  KIRQL v18; // dl
  int v19; // ebx
  char v20; // bl
  NTSTATUS SystemThread; // edi
  KIRQL v22; // al
  __int64 v23; // r9
  int v24; // r8d
  unsigned int v25; // ecx
  unsigned int v26; // eax
  unsigned int v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // r8
  _QWORD *v31; // rax
  unsigned int v32; // eax
  _QWORD *v33; // rax
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  KIRQL v40; // [rsp+40h] [rbp-98h]
  KIRQL v41; // [rsp+40h] [rbp-98h]
  KIRQL Irql; // [rsp+41h] [rbp-97h] BYREF
  KIRQL NewIrql; // [rsp+42h] [rbp-96h]
  KIRQL v44; // [rsp+43h] [rbp-95h]
  KIRQL v45; // [rsp+44h] [rbp-94h]
  unsigned int v46; // [rsp+48h] [rbp-90h]
  __int64 v47; // [rsp+50h] [rbp-88h]
  PKSPIN_LOCK SpinLock; // [rsp+58h] [rbp-80h]
  PKSPIN_LOCK v49; // [rsp+60h] [rbp-78h]
  __int64 v50; // [rsp+68h] [rbp-70h]
  struct _KAPC_STATE ApcState; // [rsp+70h] [rbp-68h] BYREF

  v3 = *(_QWORD *)(a3 + 48);
  v50 = a3;
  v47 = a2;
  Irql = 0;
  v4 = a3;
  StartContext = *(_QWORD *)(v3 + 24);
  memset(&ApcState, 0, sizeof(ApcState));
  v7 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
  v40 = v8;
  v9 = v8;
  if ( !StartContext )
    goto LABEL_107;
  if ( *(_DWORD *)(StartContext + 16) != 1397966163 )
    goto LABEL_107;
  v7 = *(_QWORD *)(StartContext + 24);
  if ( !v7 )
    goto LABEL_107;
  v10 = *(_QWORD *)(StartContext + 40);
  if ( !*(_QWORD *)(v10 + 304) || *(_DWORD *)(v7 + 16) != 1380205633 || (*(_DWORD *)(StartContext + 32) & 0x6000) != 0 )
  {
    v9 = v8;
LABEL_107:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        101,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        StartContext,
        v7);
    KeReleaseSpinLock(&::SpinLock, v9);
    return 3221225480LL;
  }
  if ( (*(_DWORD *)(v7 + 56) & 1) != 0 )
  {
    v9 = v8;
    goto LABEL_107;
  }
  if ( !*(_DWORD *)(v10 + 40) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, StartContext);
    v11 = -1073741305;
    goto LABEL_32;
  }
  if ( !*(_DWORD *)(v4 + 8) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        a2,
        StartContext);
    v11 = 0;
    goto LABEL_32;
  }
  v49 = (PKSPIN_LOCK)(v7 + 424);
  Irql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 424));
  SpinLock = (PKSPIN_LOCK)(StartContext + 360);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 360));
  v12 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576));
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
    v13 = NewIrql;
LABEL_31:
    KeReleaseSpinLock(SpinLock, v13);
    KeReleaseSpinLock(v49, Irql);
    v11 = -1073741670;
LABEL_32:
    KeReleaseSpinLock(&::SpinLock, v40);
    return v11;
  }
  v14 = 0;
  v15 = *(_DWORD *)(v10 + 208);
  if ( v15 )
  {
    v16 = v15 - *(_DWORD *)(v10 + 212);
    v46 = v16;
    if ( v16 )
    {
      if ( v16 < *(_DWORD *)(v4 + 8) )
      {
        v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576));
        if ( !v14 )
        {
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576), v12);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
          }
          v13 = NewIrql;
          goto LABEL_31;
        }
      }
    }
  }
  else
  {
    v46 = 0;
  }
  memset(v12 + 4, 0, 0x90u);
  *((_QWORD *)v12 + 1) = v12;
  *(_QWORD *)v12 = v12;
  if ( v14 )
  {
    memset(v14 + 2, 0, 0x90u);
    v14[1] = v14;
    *v14 = v14;
  }
  v18 = NewIrql;
  v19 = *(_DWORD *)(StartContext + 32) & 8;
  ++*(_DWORD *)(StartContext + 20);
  KeReleaseSpinLock((PKSPIN_LOCK)(StartContext + 360), v18);
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 424), Irql);
  KeReleaseSpinLock(&::SpinLock, v40);
  if ( KeGetCurrentIrql() )
  {
    NewIrql = 0;
  }
  else
  {
    NewIrql = 1;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v10 + 736), 1u);
  }
  if ( v19 )
  {
    if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
    {
      v20 = 0;
    }
    else
    {
      KeStackAttachProcess(PgmStaticConfig, &ApcState);
      v20 = 1;
    }
    SystemThread = PsCreateSystemThread(
                     (PHANDLE)(v10 + 728),
                     0x1FFFFFu,
                     0,
                     0,
                     0,
                     SenderWorkerThread,
                     (PVOID)StartContext);
    if ( SystemThread < 0 )
    {
      if ( v20 )
        KeUnstackDetachProcess(&ApcState);
      if ( NewIrql )
      {
        ExReleaseResourceLite((PERESOURCE)(v10 + 736));
        KeLeaveCriticalRegion();
      }
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576), v12);
      if ( v14 )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576), v14);
      PgmDereferenceSessionCommon(StartContext);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          106,
          WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
          (unsigned int)SystemThread);
      return (unsigned int)SystemThread;
    }
    ZwClose(*(HANDLE *)(v10 + 728));
    if ( v20 )
      KeUnstackDetachProcess(&ApcState);
    v45 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
    IoAcquireCancelSpinLock(&Irql);
    v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 424));
    v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 360));
    *(_DWORD *)(StartContext + 32) &= ~8u;
    *(_QWORD *)(v10 + 32) = v7;
    *(_DWORD *)(v10 + 156) = -1;
    v12[15] |= 0x20u;
    v12[16] += 4;
    ++*(_DWORD *)(StartContext + 20);
    ++*(_DWORD *)(v7 + 20);
    v41 = v22;
    *(_QWORD *)(v10 + 280) = MEMORY[0xFFFFF78000000008];
    *(_QWORD *)(v10 + 288) = 200000;
    *(_QWORD *)(v10 + 296) = 1;
    KeInitializeTimer((PKTIMER)(StartContext + 232));
    KeInitializeDpc((PRKDPC)(StartContext + 296), SendSessionTimeout, (PVOID)StartContext);
    KeSetTimer((PKTIMER)(StartContext + 232), (LARGE_INTEGER)-200000LL, (PKDPC)(StartContext + 296));
    v4 = v50;
  }
  else
  {
    v45 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
    IoAcquireCancelSpinLock(&Irql);
    v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 424));
    v41 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(StartContext + 360));
  }
  v23 = v47;
  *((_QWORD *)v12 + 3) = v47;
  *((_QWORD *)v12 + 4) = v23;
  v12[14] = 0;
  *((_QWORD *)v12 + 5) = StartContext;
  v12[4] = (*(_DWORD *)(v10 + 104))++;
  v12[29] = *(_DWORD *)(v10 + 112);
  v12[15] |= *(_DWORD *)(v10 + 200);
  v12[16] += *(_DWORD *)(v10 + 204);
  *((_QWORD *)v12 + 18) = -1;
  v24 = *(_DWORD *)(v10 + 208);
  if ( v24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_dddd(
        WPP_GLOBAL_Control->AttachedDevice,
        107,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned int)v12[4],
        v24,
        *(_DWORD *)(v10 + 212),
        *(_DWORD *)(v4 + 8));
      v23 = v47;
    }
    v12[17] = *(_DWORD *)(v10 + 208);
    v12[18] = *(_DWORD *)(v10 + 212);
    if ( v14 )
    {
      v25 = v46;
      v12[25] = v46;
      *((_QWORD *)v12 + 4) = 0;
      v14[5] = StartContext;
      v14[3] = v23;
      v14[4] = v23;
      *((_DWORD *)v14 + 4) = (*(_DWORD *)(v10 + 104))++;
      *((_DWORD *)v14 + 29) = *(_DWORD *)(v10 + 112);
      *((_DWORD *)v14 + 15) |= *(_DWORD *)(v10 + 200);
      *((_DWORD *)v14 + 16) += *(_DWORD *)(v10 + 204);
      v14[18] = -1;
      v26 = *(_DWORD *)(v4 + 8) - v25;
      *((_DWORD *)v14 + 14) = v25;
      *((_DWORD *)v14 + 17) = v26;
      *((_DWORD *)v14 + 25) = v26;
    }
    else
    {
      v12[25] = *(_DWORD *)(v4 + 8);
    }
    *(_DWORD *)(v10 + 212) += v12[25];
    if ( *(_DWORD *)(v10 + 212) == *(_DWORD *)(v10 + 208) )
      *(_QWORD *)(v10 + 208) = 0;
  }
  else
  {
    v12[17] = *(_DWORD *)(v4 + 8);
    v12[25] = *(_DWORD *)(v4 + 8);
  }
  v27 = v12[17];
  v28 = v12[25];
  if ( v27 > v12[29] || v27 > v28 )
  {
    v12[15] |= 1u;
    v12[16] += 16;
    v29 = (*(_DWORD *)(v10 + 112) + v28 - 1) / *(_DWORD *)(v10 + 112);
  }
  else
  {
    v29 = 1;
  }
  v12[19] = v29;
  *(_DWORD *)(v10 + 188) += v29;
  if ( v12[15] )
    v12[16] += 4;
  v30 = v10 + 248;
  v12[26] = v12[25];
  v31 = *(_QWORD **)(v10 + 256);
  if ( *v31 != v10 + 248 )
    goto LABEL_104;
  *(_QWORD *)v12 = v30;
  *((_QWORD *)v12 + 1) = v31;
  *v31 = v12;
  *(_QWORD *)(v10 + 256) = v12;
  ++*(_DWORD *)(v10 + 144);
  if ( v14 )
  {
    v14[10] = v12;
    *((_QWORD *)v12 + 10) = v14;
    ++*(_DWORD *)(StartContext + 20);
    if ( *((_DWORD *)v14 + 17) <= v12[29] )
    {
      v32 = 1;
    }
    else
    {
      *((_DWORD *)v14 + 15) |= 1u;
      *((_DWORD *)v14 + 16) += 16;
      v32 = (unsigned int)(*(_DWORD *)(v10 + 112) + *((_DWORD *)v14 + 25) - 1) / *(_DWORD *)(v10 + 112);
    }
    *((_DWORD *)v14 + 19) = v32;
    *(_DWORD *)(v10 + 188) += v32;
    if ( *((_DWORD *)v14 + 15) )
      *((_DWORD *)v14 + 16) += 4;
    *((_DWORD *)v14 + 26) = *((_DWORD *)v14 + 25);
    v33 = *(_QWORD **)(v10 + 256);
    if ( *v33 != v30 )
      goto LABEL_104;
    *v14 = v30;
    v14[1] = v33;
    *v33 = v14;
    *(_QWORD *)(v10 + 256) = v14;
    ++*(_DWORD *)(v10 + 144);
  }
  LOBYTE(v30) = 1;
  if ( (int)PgmCheckSetCancelRoutine(v23, PgmCancelSendIrp, v30) < 0 )
  {
    *(_DWORD *)(StartContext + 32) |= 0x4000u;
    --*(_DWORD *)(v10 + 144);
    *(_DWORD *)(v10 + 188) -= v12[19];
    v34 = *(_QWORD *)v12;
    if ( *(_DWORD **)(*(_QWORD *)v12 + 8LL) == v12 )
    {
      v35 = (_QWORD *)*((_QWORD *)v12 + 1);
      if ( (_DWORD *)*v35 == v12 )
      {
        *v35 = v34;
        *(_QWORD *)(v34 + 8) = v35;
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576), v12);
        if ( !v14 )
        {
LABEL_90:
          KeReleaseSpinLock((PKSPIN_LOCK)(StartContext + 360), v41);
          KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 424), v44);
          IoReleaseCancelSpinLock(Irql);
          KeReleaseSpinLock(&::SpinLock, v45);
          PgmDereferenceSessionCommon(StartContext);
          if ( v14 )
            PgmDereferenceSessionCommon(StartContext);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_qqq(
              WPP_GLOBAL_Control->AttachedDevice,
              108,
              WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
              v47,
              StartContext,
              v7);
          }
          return 3221225760LL;
        }
        --*(_DWORD *)(v10 + 144);
        *(_DWORD *)(v10 + 188) -= *((_DWORD *)v14 + 19);
        v36 = *v14;
        if ( *(_QWORD **)(*v14 + 8LL) == v14 )
        {
          v37 = (_QWORD *)v14[1];
          if ( (_QWORD *)*v37 == v14 )
          {
            *v37 = v36;
            *(_QWORD *)(v36 + 8) = v37;
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576), v14);
            goto LABEL_90;
          }
        }
      }
    }
LABEL_104:
    __fastfail(3u);
  }
  IoReleaseCancelSpinLock(v41);
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 424), v44);
  KeReleaseSpinLock(&::SpinLock, Irql);
  if ( *(_DWORD *)(v10 + 408) >= *(_DWORD *)(v7 + 248) )
    KeSetEvent((PRKEVENT)(v10 + 704), 0, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(StartContext + 360), v45);
  if ( NewIrql )
  {
    ExReleaseResourceLite((PERESOURCE)(v10 + 736));
    KeLeaveCriticalRegion();
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_dqqq(WPP_GLOBAL_Control->AttachedDevice, v38, v39, (unsigned int)v12[4], v47, v12, v14);
  return 259;
}

```

## disassembly

```asm
0x140019424  mov     r11, rsp
0x140019427  mov     [r11+8], rbx
0x14001942b  mov     [r11+20h], rsi
0x14001942f  push    rdi
0x140019430  push    r12
0x140019432  push    r13
0x140019434  push    r14
0x140019436  push    r15
0x140019438  sub     rsp, 0B0h
0x14001943f  mov     rax, cs:__security_cookie
0x140019446  xor     rax, rsp
0x140019449  mov     [rsp+0D8h+var_38], rax
0x140019451  mov     rax, [r8+30h]
0x140019455  lea     rcx, SpinLock; SpinLock
0x14001945c  xorps   xmm0, xmm0
0x14001945f  mov     [rsp+0D8h+var_70], r8
0x140019464  xor     ebx, ebx
0x140019466  mov     [rsp+0D8h+var_88], rdx
0x14001946b  mov     [rsp+0D8h+Irql], bl
0x14001946f  mov     rdi, r8
0x140019472  mov     r13, [rax+18h]
0x140019476  mov     r15, rdx
0x140019479  movups  xmmword ptr [rsp+0D8h+ApcState.ApcListHead.Flink], xmm0
0x14001947e  mov     r12d, ebx
0x140019481  movups  xmmword ptr [r11-58h], xmm0
0x140019486  movups  xmmword ptr [r11-48h], xmm0
0x14001948b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019492  nop     dword ptr [rax+rax+00h]
0x140019497  mov     [rsp+0D8h+var_98], al
0x14001949b  mov     r14b, al
0x14001949e  test    r13, r13
0x1400194a1  jz      loc_140019EE8
0x1400194a7  cmp     dword ptr [r13+10h], 53534553h
0x1400194af  jnz     loc_140019EE8
0x1400194b5  mov     r12, [r13+18h]
0x1400194b9  test    r12, r12
0x1400194bc  jz      loc_140019EE8
0x1400194c2  mov     r14, [r13+28h]
0x1400194c6  cmp     [r14+130h], rbx
0x1400194cd  jz      loc_140019EE5
0x1400194d3  cmp     dword ptr [r12+10h], 52444441h
0x1400194dc  jnz     loc_140019EE5
0x1400194e2  test    dword ptr [r13+20h], 6000h
0x1400194ea  jnz     loc_140019EE5
0x1400194f0  mov     eax, [r12+38h]
0x1400194f5  test    al, 1
0x1400194f7  jnz     loc_140019EDE
0x1400194fd  cmp     [r14+28h], ebx
0x140019501  jnz     short loc_14001953F
0x140019503  mov     rcx, cs:WPP_GLOBAL_Control
0x14001950a  lea     rbx, WPP_GLOBAL_Control
0x140019511  cmp     rcx, rbx
0x140019514  jz      short loc_140019535
0x140019516  mov     eax, [rcx+2Ch]
0x140019519  test    al, 2
0x14001951b  jz      short loc_140019535
0x14001951d  mov     rcx, [rcx+18h]
0x140019521  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140019528  mov     edx, 66h ; 'f'
0x14001952d  mov     r9, r13
0x140019530  call    WPP_SF_q
0x140019535  mov     ebx, 0C0000207h
0x14001953a  jmp     loc_1400196D1
0x14001953f  cmp     [rdi+8], ebx
0x140019542  jnz     short loc_140019582
0x140019544  mov     rcx, cs:WPP_GLOBAL_Control
0x14001954b  lea     rbx, WPP_GLOBAL_Control
0x140019552  cmp     rcx, rbx
0x140019555  jz      short loc_14001957B
0x140019557  mov     eax, [rcx+2Ch]
0x14001955a  test    al, 4
0x14001955c  jz      short loc_14001957B
0x14001955e  mov     rcx, [rcx+18h]
0x140019562  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140019569  mov     edx, 67h ; 'g'
0x14001956e  mov     [rsp+0D8h+ClientId], r13
0x140019573  mov     r9, r15
0x140019576  call    WPP_SF_qq
0x14001957b  xor     ebx, ebx
0x14001957d  jmp     loc_1400196D1
0x140019582  lea     rax, [r12+1A8h]
0x14001958a  mov     rcx, rax; SpinLock
0x14001958d  mov     [rsp+0D8h+var_78], rax
0x140019592  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019599  nop     dword ptr [rax+rax+00h]
0x14001959e  mov     [rsp+0D8h+Irql], al
0x1400195a2  lea     rax, [r13+168h]
0x1400195a9  mov     rcx, rax; SpinLock
0x1400195ac  mov     [rsp+0D8h+SpinLock], rax
0x1400195b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400195b8  nop     dword ptr [rax+rax+00h]
0x1400195bd  lea     rcx, [r14+240h]; Lookaside
0x1400195c4  mov     [rsp+0D8h+NewIrql], al
0x1400195c8  mov     r15b, al
0x1400195cb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400195d2  nop     dword ptr [rax+rax+00h]
0x1400195d7  mov     rsi, rax
0x1400195da  test    rax, rax
0x1400195dd  jnz     short loc_140019614
0x1400195df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195e6  lea     rbx, WPP_GLOBAL_Control
0x1400195ed  cmp     rcx, rbx
0x1400195f0  jz      short loc_14001960C
0x1400195f2  mov     eax, [rcx+2Ch]
0x1400195f5  test    al, 2
0x1400195f7  jz      short loc_14001960C
0x1400195f9  mov     rcx, [rcx+18h]
0x1400195fd  lea     edx, [rsi+68h]
0x140019600  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140019607  call    WPP_SF_
0x14001960c  mov     dl, r15b
0x14001960f  jmp     loc_1400196A6
0x140019614  mov     r15, rbx
0x140019617  mov     ebx, [r14+0D0h]
0x14001961e  test    ebx, ebx
0x140019620  jz      loc_1400196EF
0x140019626  sub     ebx, [r14+0D4h]
0x14001962d  mov     [rsp+0D8h+var_90], ebx
0x140019631  jz      loc_1400196F4
0x140019637  cmp     ebx, [rdi+8]
0x14001963a  jnb     loc_1400196F4
0x140019640  lea     rbx, [r14+240h]
0x140019647  mov     rcx, rbx; Lookaside
0x14001964a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140019651  nop     dword ptr [rax+rax+00h]
0x140019656  mov     r15, rax
0x140019659  test    rax, rax
0x14001965c  jnz     loc_1400196F4
0x140019662  mov     rdx, rsi; Entry
0x140019665  mov     rcx, rbx; Lookaside
0x140019668  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001966f  nop     dword ptr [rax+rax+00h]
0x140019674  mov     rcx, cs:WPP_GLOBAL_Control
0x14001967b  lea     rbx, WPP_GLOBAL_Control
0x140019682  cmp     rcx, rbx
0x140019685  jz      short loc_1400196A2
0x140019687  mov     eax, [rcx+2Ch]
0x14001968a  test    al, 2
0x14001968c  jz      short loc_1400196A2
0x14001968e  mov     rcx, [rcx+18h]
0x140019692  lea     edx, [r15+69h]
0x140019696  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x14001969d  call    WPP_SF_
0x1400196a2  mov     dl, [rsp+0D8h+NewIrql]; NewIrql
0x1400196a6  mov     rcx, [rsp+0D8h+SpinLock]; SpinLock
0x1400196ab  call    cs:__imp_KeReleaseSpinLock
0x1400196b2  nop     dword ptr [rax+rax+00h]
0x1400196b7  mov     dl, [rsp+0D8h+Irql]; NewIrql
0x1400196bb  mov     rcx, [rsp+0D8h+var_78]; SpinLock
0x1400196c0  call    cs:__imp_KeReleaseSpinLock
0x1400196c7  nop     dword ptr [rax+rax+00h]
0x1400196cc  mov     ebx, 0C000009Ah
0x1400196d1  mov     dl, [rsp+0D8h+var_98]; NewIrql
0x1400196d5  lea     rcx, SpinLock; SpinLock
0x1400196dc  call    cs:__imp_KeReleaseSpinLock
0x1400196e3  nop     dword ptr [rax+rax+00h]
0x1400196e8  mov     eax, ebx
0x1400196ea  jmp     loc_140019F3A
0x1400196ef  mov     [rsp+0D8h+var_90], r15d
0x1400196f4  mov     ebx, 90h
0x1400196f9  lea     rcx, [rsi+10h]; void *
0x1400196fd  mov     r8d, ebx; Size
0x140019700  xor     edx, edx; Val
0x140019702  call    memset
0x140019707  mov     [rsi+8], rsi
0x14001970b  mov     [rsi], rsi
0x14001970e  test    r15, r15
0x140019711  jz      short loc_140019728
0x140019713  lea     rcx, [r15+10h]; void *
0x140019717  mov     r8d, ebx; Size
0x14001971a  xor     edx, edx; Val
0x14001971c  call    memset
0x140019721  mov     [r15+8], r15
0x140019725  mov     [r15], r15
0x140019728  mov     ebx, [r13+20h]
0x14001972c  lea     rcx, [r13+168h]; SpinLock
0x140019733  mov     dl, [rsp+0D8h+NewIrql]; NewIrql
0x140019737  and     ebx, 8
0x14001973a  inc     dword ptr [r13+14h]
0x14001973e  call    cs:__imp_KeReleaseSpinLock
0x140019745  nop     dword ptr [rax+rax+00h]
0x14001974a  mov     dl, [rsp+0D8h+Irql]; NewIrql
0x14001974e  lea     rcx, [r12+1A8h]; SpinLock
0x140019756  call    cs:__imp_KeReleaseSpinLock
0x14001975d  nop     dword ptr [rax+rax+00h]
0x140019762  mov     dl, [rsp+0D8h+var_98]; NewIrql
0x140019766  lea     rcx, SpinLock; SpinLock
0x14001976d  call    cs:__imp_KeReleaseSpinLock
0x140019774  nop     dword ptr [rax+rax+00h]
0x140019779  call    cs:__imp_KeGetCurrentIrql
0x140019780  nop     dword ptr [rax+rax+00h]
0x140019785  test    al, al
0x140019787  jz      short loc_140019790
0x140019789  mov     [rsp+0D8h+NewIrql], 0
0x14001978e  jmp     short loc_1400197B6
0x140019790  mov     [rsp+0D8h+NewIrql], 1
0x140019795  call    cs:__imp_KeEnterCriticalRegion
0x14001979c  nop     dword ptr [rax+rax+00h]
0x1400197a1  lea     rcx, [r14+2E0h]; Resource
0x1400197a8  mov     dl, 1; Wait
0x1400197aa  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400197b1  nop     dword ptr [rax+rax+00h]
0x1400197b6  test    ebx, ebx
0x1400197b8  jz      loc_1400199FC
0x1400197be  call    cs:__imp_PsGetCurrentProcess
0x1400197c5  nop     dword ptr [rax+rax+00h]
0x1400197ca  mov     rcx, cs:PgmStaticConfig; PROCESS
0x1400197d1  cmp     rax, rcx
0x1400197d4  jz      short loc_1400197EB
0x1400197d6  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x1400197db  call    cs:__imp_KeStackAttachProcess
0x1400197e2  nop     dword ptr [rax+rax+00h]
0x1400197e7  mov     bl, 1
0x1400197e9  jmp     short loc_1400197ED
0x1400197eb  xor     bl, bl
0x1400197ed  lea     rcx, SenderWorkerThread
0x1400197f4  mov     [rsp+0D8h+StartContext], r13; StartContext
0x1400197f9  mov     [rsp+0D8h+StartRoutine], rcx; StartRoutine
0x1400197fe  xor     r9d, r9d; ProcessHandle
0x140019801  lea     rcx, [r14+2D8h]; ThreadHandle
0x140019808  mov     [rsp+0D8h+ClientId], 0; ClientId
0x140019811  xor     r8d, r8d; ObjectAttributes
0x140019814  mov     edx, 1FFFFFh; DesiredAccess
0x140019819  call    cs:__imp_PsCreateSystemThread
0x140019820  nop     dword ptr [rax+rax+00h]
0x140019825  mov     edi, eax
0x140019827  test    eax, eax
0x140019829  jns     loc_1400198DB
0x14001982f  test    bl, bl
0x140019831  jz      short loc_140019844
0x140019833  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x140019838  call    cs:__imp_KeUnstackDetachProcess
0x14001983f  nop     dword ptr [rax+rax+00h]
0x140019844  cmp     [rsp+0D8h+NewIrql], 0
0x140019849  jz      short loc_14001986A
0x14001984b  lea     rcx, [r14+2E0h]; Resource
0x140019852  call    cs:__imp_ExReleaseResourceLite
0x140019859  nop     dword ptr [rax+rax+00h]
0x14001985e  call    cs:__imp_KeLeaveCriticalRegion
0x140019865  nop     dword ptr [rax+rax+00h]
0x14001986a  lea     rbx, [r14+240h]
0x140019871  mov     rdx, rsi; Entry
0x140019874  mov     rcx, rbx; Lookaside
0x140019877  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001987e  nop     dword ptr [rax+rax+00h]
0x140019883  test    r15, r15
0x140019886  jz      short loc_14001989A
0x140019888  mov     rdx, r15; Entry
0x14001988b  mov     rcx, rbx; Lookaside
0x14001988e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019895  nop     dword ptr [rax+rax+00h]
0x14001989a  mov     rcx, r13
0x14001989d  call    PgmDereferenceSessionCommon
0x1400198a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400198a9  lea     rbx, WPP_GLOBAL_Control
0x1400198b0  cmp     rcx, rbx
0x1400198b3  jz      short loc_1400198D4
0x1400198b5  mov     eax, [rcx+2Ch]
0x1400198b8  test    al, 2
0x1400198ba  jz      short loc_1400198D4
0x1400198bc  mov     rcx, [rcx+18h]
0x1400198c0  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400198c7  mov     edx, 6Ah ; 'j'
0x1400198cc  mov     r9d, edi
0x1400198cf  call    WPP_SF_d
0x1400198d4  mov     eax, edi
0x1400198d6  jmp     loc_140019F3A
0x1400198db  mov     rcx, [r14+2D8h]; Handle
0x1400198e2  call    cs:__imp_ZwClose
0x1400198e9  nop     dword ptr [rax+rax+00h]
0x1400198ee  test    bl, bl
0x1400198f0  jz      short loc_140019903
0x1400198f2  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x1400198f7  call    cs:__imp_KeUnstackDetachProcess
0x1400198fe  nop     dword ptr [rax+rax+00h]
0x140019903  lea     rcx, SpinLock; SpinLock
0x14001990a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019911  nop     dword ptr [rax+rax+00h]
0x140019916  lea     rcx, [rsp+0D8h+Irql]; Irql
0x14001991b  mov     [rsp+0D8h+var_94], al
0x14001991f  call    cs:__imp_IoAcquireCancelSpinLock
0x140019926  nop     dword ptr [rax+rax+00h]
0x14001992b  lea     rcx, [r12+1A8h]; SpinLock
0x140019933  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001993a  nop     dword ptr [rax+rax+00h]
0x14001993f  lea     rcx, [r13+168h]; SpinLock
0x140019946  mov     [rsp+0D8h+var_95], al
0x14001994a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019951  nop     dword ptr [rax+rax+00h]
0x140019956  and     dword ptr [r13+20h], 0FFFFFFF7h
0x14001995b  lea     rdi, [r13+0E8h]
0x140019962  mov     [r14+20h], r12
0x140019966  mov     rcx, rdi; Timer
0x140019969  mov     dword ptr [r14+9Ch], 0FFFFFFFFh
0x140019974  or      dword ptr [rsi+3Ch], 20h
0x140019978  add     dword ptr [rsi+40h], 4
0x14001997c  inc     dword ptr [r13+14h]
0x140019980  inc     dword ptr [r12+14h]
0x140019985  mov     [rsp+0D8h+var_98], al
0x140019989  mov     rax, ds:0FFFFF78000000008h
  ... truncated ...
```
