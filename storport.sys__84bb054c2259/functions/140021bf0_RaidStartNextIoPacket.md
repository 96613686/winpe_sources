# RaidStartNextIoPacket

- ea: `0x140021bf0`
- end: `0x140022845`
- name: `RaidStartNextIoPacket`
- size: `3157`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140001010`
- `0x14001edc0`
- `0x14001fe50`
- `0x1400991b8`

## callees

- `0x140004cb4`
- `0x140012174`
- `0x140021bf0`
- `0x140022b10`
- `0x140022cb0`
- `0x140023058`
- `0x140023080`
- `0x14002d780`
- `0x1400313b0`
- `0x14003982c`
- `0x140039cb8`
- `0x14004a580`
- `0x140098e58`
- `0x1400bb9e0`
- `0x14014b400`
- `0x14014b440`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021d01`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021d01`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140021f36`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002203d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400223ab`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002246c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400224a6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140021f36`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002203d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400223ab`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002246c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400224a6`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140022274`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140022274`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021e45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021e45`
- `ntoskrnl!KeSetEvent` at `0x140022102`
- `ntoskrnl!KeSetEvent` at `0x140022102`
- `ntoskrnl!KeLowerIrql` at `0x140021fad`
- `ntoskrnl!KeLowerIrql` at `0x140021fad`
- `ntoskrnl!KfRaiseIrql` at `0x140021e56`
- `ntoskrnl!KfRaiseIrql` at `0x140021e56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021cb3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021cb3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140022312`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140022312`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002222b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002222b`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x140021ef4`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x140021fc2`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x140021ef4`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x140021fc2`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140021f98`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140021f98`
- `ntoskrnl!ExQueryDepthSList` at `0x140021ec4`
- `ntoskrnl!ExQueryDepthSList` at `0x14002201b`
- `ntoskrnl!ExQueryDepthSList` at `0x140021ec4`
- `ntoskrnl!ExQueryDepthSList` at `0x14002201b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140022368`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14002250d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140022368`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14002250d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14002238b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140022597`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14002238b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140022597`
- `ntoskrnl!ExRundownCompleted` at `0x1400220a0`
- `ntoskrnl!ExRundownCompleted` at `0x1400220a0`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140022090`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140022090`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002219a`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002219a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021f1c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021f1c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021ee2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021f83`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021ee2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021f83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021d81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021d81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021cdd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021cdd`

## pseudocode

```c
__int64 __fastcall RaidStartNextIoPacket(__int64 a1, int a2, int a3)
{
  char v3; // r12
  __int64 v6; // rsi
  __int64 v7; // rax
  bool v8; // r14
  __int64 v9; // r14
  unsigned __int64 v10; // rdi
  unsigned int v11; // esi
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rbx
  KIRQL v15; // bl
  __int64 v16; // rcx
  __int64 v17; // rax
  __int16 v18; // cx
  _DWORD *v19; // rcx
  _DWORD *v20; // rcx
  char v21; // bl
  signed __int64 v22; // rax
  char v23; // r15
  signed __int64 v24; // r8
  PSLIST_ENTRY v25; // rax
  signed __int64 v26; // rax
  char v27; // r14
  signed __int64 v28; // r8
  PSLIST_ENTRY v29; // rax
  signed __int64 v30; // rsi
  bool v31; // zf
  signed __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  signed __int64 v35; // rbx
  char v36; // r8
  __int64 v37; // rdx
  signed __int64 v38; // rcx
  signed __int64 v39; // rax
  signed __int64 v40; // rax
  signed __int64 v41; // rtt
  __int64 v42; // r14
  __int64 v43; // rdi
  ULONG v44; // ecx
  __int64 v45; // rbx
  unsigned int v46; // ebx
  ULONG v47; // r8d
  __int64 v48; // rbx
  int v49; // r9d
  PSLIST_ENTRY IoResource; // rdi
  __int64 *v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rbx
  _QWORD *v55; // rdx
  _QWORD *v56; // rax
  unsigned int v57; // r8d
  __int64 v58; // rax
  int v59; // r12d
  unsigned int v60; // ecx
  unsigned int v61; // r14d
  PSLIST_ENTRY v62; // rax
  __int64 *v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rax
  _QWORD *v66; // rcx
  __int64 v67; // rdx
  KSPIN_LOCK *v68; // rcx
  unsigned int v69; // esi
  __int64 i; // rbx
  unsigned int v71; // ecx
  void *v72; // rcx
  unsigned int v73; // eax
  __int64 v74; // rbx
  __int64 v75; // rdx
  KSPIN_LOCK *v76; // rcx
  bool v78; // [rsp+50h] [rbp-79h]
  KIRQL v79; // [rsp+51h] [rbp-78h]
  __m256i v81; // [rsp+60h] [rbp-69h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-49h] BYREF
  _OWORD v83[2]; // [rsp+98h] [rbp-31h] BYREF
  __int128 v84; // [rsp+B8h] [rbp-11h]
  __int64 v85; // [rsp+C8h] [rbp-1h]

  v3 = 0;
  memset(&v81, 0, 28);
  if ( a3 )
  {
    v6 = RaidNormalizeDeviceQueue(a1 + 720);
    goto LABEL_111;
  }
  v7 = *(_QWORD *)(a1 + 24);
  v8 = 0;
  v78 = 0;
  if ( v7 )
  {
    v9 = *(_QWORD *)(a1 + 560);
    if ( v9 && *(_QWORD *)(v7 + 4960) )
    {
      v10 = -1;
      v11 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( *(_DWORD *)(v9 + 8) )
      {
        do
        {
          v12 = (unsigned __int64)v11 << 6;
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v12 + v9 + 104), &LockHandle);
          v13 = v12 + v9 + 64;
          if ( *(_QWORD *)v13 != v13 && *(_QWORD *)(*(_QWORD *)v13 + 40LL) < v10 )
            v10 = *(_QWORD *)(*(_QWORD *)v13 + 40LL);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          ++v11;
        }
        while ( v11 < *(_DWORD *)(v9 + 8) );
      }
      v14 = 0;
      if ( v10 != -1 )
        v14 = v10;
      if ( v14 )
      {
        v8 = KeQueryUnbiasedInterruptTime() - v14 > *(_QWORD *)(*(_QWORD *)(a1 + 24) + 4960LL);
        v78 = v8;
      }
      else
      {
        v8 = 0;
      }
    }
    else
    {
      v8 = 0;
    }
  }
  if ( a2 )
  {
    memset(v83, 0, sizeof(v83));
    v85 = 0;
    v84 = 0;
    if ( *(_QWORD *)(a1 + 32) )
    {
      if ( (unsigned __int8)RaidIsUnitControlSupported(a1, 31) )
      {
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 32) + 24LL));
        *(_DWORD *)(*(_QWORD *)(a1 + 32) + 80LL) &= ~0x100u;
        v16 = *(_QWORD *)(a1 + 32);
        if ( (*(_DWORD *)(v16 + 80) & 0x1E0) == 0 && *(int *)(v16 + 84) <= 0 )
        {
          *(_QWORD *)&v83[0] = 0x3800000038LL;
          DWORD2(v83[0]) = 3;
          if ( (unsigned int)Feature_Servicing_perLunLockingEnable__private_IsEnabledDeviceUsageNoInline() )
          {
            v17 = *(_QWORD *)(a1 + 24);
            WORD4(v84) = 1;
            HIDWORD(v84) = 4;
            v18 = *(_WORD *)(v17 + 56);
            LOWORD(v85) = *(_WORD *)(a1 + 104);
            BYTE2(v85) = *(_BYTE *)(a1 + 106);
            WORD5(v84) = v18;
          }
          v19 = *(_DWORD **)(a1 + 24);
          if ( *v19 == 1094997074 )
          {
            v20 = v19 + 90;
          }
          else if ( *v19 == 1314275652 )
          {
            v20 = v19 + 44;
          }
          else
          {
            v20 = 0;
          }
          RaCallMiniportUnitControl(v20, 31, v83);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 32) + 24LL), v15);
      }
    }
  }
  v6 = 0;
  v79 = KfRaiseIrql(2u);
  v21 = 0;
  v22 = *(_QWORD *)(a1 + 808);
  v23 = 0;
  if ( (v22 & 1) != 0 )
    goto LABEL_58;
  while ( 1 )
  {
    LockHandle.LockQueue.Next = (_KSPIN_LOCK_QUEUE *volatile)v22;
    v24 = v22;
    if ( (unsigned int)(v22 / 0x100000000LL) )
      break;
    v22 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v22 - 4, v22);
    if ( v24 == v22 )
      goto LABEL_51;
LABEL_48:
    v8 = v78;
    if ( (v22 & 1) != 0 )
      goto LABEL_52;
  }
  if ( v8 )
    goto LABEL_52;
  if ( ExQueryDepthSList((PSLIST_HEADER)(a1 + 832)) )
  {
    if ( !v23 && !v21 )
    {
      if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 800)) )
        goto LABEL_58;
      v21 = 1;
    }
  }
  else
  {
    if ( !v23 )
    {
      if ( v21 )
      {
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 800));
        v21 = 0;
      }
      ExAcquireSpinLockExclusiveAtDpcLevel((PEX_SPIN_LOCK)(a1 + 792));
      v23 = 1;
      goto LABEL_47;
    }
    RiFlushDeviceLists(a1 + 720);
  }
  v25 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(a1 + 832));
  v6 = RiEntryToDeviceEntry(v25);
  if ( !v6 )
  {
LABEL_47:
    v22 = *(_QWORD *)(a1 + 808);
    goto LABEL_48;
  }
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 808), 0xFFFFFFFF00000000uLL);
  *(_BYTE *)(v6 + 20) &= 0xFCu;
LABEL_51:
  v3 = 1;
LABEL_52:
  if ( v21 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 800));
  if ( v23 )
    ExReleaseSpinLockExclusiveFromDpcLevel((PEX_SPIN_LOCK)(a1 + 792));
  if ( v3 )
  {
    KeLowerIrql(v79);
    goto LABEL_111;
  }
LABEL_58:
  ExAcquireSpinLockExclusiveAtDpcLevel((PEX_SPIN_LOCK)(a1 + 792));
  v26 = *(_QWORD *)(a1 + 808);
  v27 = 0;
  if ( (v26 & 1) != 0 )
    goto LABEL_73;
  while ( 2 )
  {
    LockHandle.LockQueue.Next = (_KSPIN_LOCK_QUEUE *volatile)v26;
    v28 = v26;
    if ( !(unsigned int)(v26 / 0x100000000LL) )
    {
      v26 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v26 - 4, v26);
      if ( v28 == v26 )
        goto LABEL_71;
      goto LABEL_68;
    }
    if ( v78 )
      goto LABEL_72;
    if ( !ExQueryDepthSList((PSLIST_HEADER)(a1 + 832)) )
      RiFlushDeviceLists(a1 + 720);
    if ( !v6 )
    {
      v29 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(a1 + 832));
      v6 = RiEntryToDeviceEntry(v29);
      if ( !v6 )
      {
        v26 = *(_QWORD *)(a1 + 808);
LABEL_68:
        if ( (v26 & 1) != 0 )
          goto LABEL_72;
        continue;
      }
    }
    break;
  }
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 808), 0xFFFFFFFF00000000uLL);
  *(_BYTE *)(v6 + 20) &= 0xFCu;
LABEL_71:
  v27 = 1;
LABEL_72:
  if ( !v27 )
  {
LABEL_73:
    v30 = *(_QWORD *)(a1 + 808);
    if ( (v30 & 1) == 0 )
    {
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 800));
      ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 800));
      do
      {
        v32 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v30 | 1, v30);
        v31 = v30 == v32;
        v30 = v32;
      }
      while ( !v31 && (v32 & 1) == 0 );
    }
    if ( a2 )
      *(_BYTE *)(a1 + 758) = 0;
    v33 = *(_DWORD *)(a1 + 748);
    if ( v33 )
      *(_DWORD *)(a1 + 748) = v33 - 1;
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 808), 0xFFFFFFFFFFFFFFFCuLL);
    if ( (((__int64)*(unsigned int *)(a1 + 808) >> 2) & 0x3FFFFFFF) == 0 && *(_DWORD *)(a1 + 760) )
      KeSetEvent((PRKEVENT)(a1 + 768), 0, 0);
    v34 = RiNormalizeDeviceQueue(a1 + 720, v78);
    v35 = *(_QWORD *)(a1 + 808);
    v36 = 0;
    v6 = v34;
    if ( (v35 & 3) != 0 )
    {
      while ( !*(_DWORD *)(a1 + 748)
           && !*(_DWORD *)(a1 + 736)
           && !*(_DWORD *)(a1 + 752)
           && !*(_BYTE *)(a1 + 757)
           && !*(_BYTE *)(a1 + 759)
           && !*(_BYTE *)(a1 + 756)
           && *(int *)(a1 + 744) <= 0
           && !*(_BYTE *)(a1 + 758) )
      {
        if ( (v35 & 1) != 0 )
        {
          if ( !v36 )
          {
            ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(a1 + 800));
            v36 = 1;
          }
          v37 = v35 ^ 1;
        }
        else
        {
          v37 = v35;
        }
        v38 = v37 ^ 2;
        if ( (v35 & 2) == 0 )
          v38 = v37;
        v39 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v38, v35);
        v31 = v35 == v39;
        v35 = v39;
        if ( v31 )
        {
          if ( *(_BYTE *)(a1 + 757) || *(_BYTE *)(a1 + 759) || *(_BYTE *)(a1 + 756) || *(int *)(a1 + 744) > 0 )
          {
            v40 = *(_QWORD *)(a1 + 808);
            if ( (v40 & 3) == 0 )
            {
              do
              {
                v41 = v40;
                v40 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v40 | 2, v40);
              }
              while ( v41 != v40 && (v40 & 3) == 0 );
            }
          }
          break;
        }
        if ( (v39 & 3) == 0 )
          break;
      }
    }
  }
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 792), v79);
LABEL_111:
  if ( !v6 )
    goto LABEL_160;
  v42 = v6 - 120;
  if ( StorEtwLoggingEnabled )
  {
    if ( byte_140177432 < 0 )
    {
      LockHandle.LockQueue = 0;
      IoGetActivityIdIrp(v6 - 120, &LockHandle);
      if ( byte_140177432 < 0 )
        McTemplateK0pquuqqd_EtwWriteTransfer(
          (*(__int64 *)(a1 + 808) >> 2) & 0x3FFFFFFF,
          *(__int64 *)(a1 + 808) >> 63,
          (unsigned int)&LockHandle,
          a1 + 720,
          ((*(_BYTE *)(v6 + 22) & 6) != 0) + 1,
          5,
          0,
          *(_BYTE *)(a1 + 736) + *(_QWORD *)(a1 + 808) / 0x100000000LL,
          *(__int64 *)(a1 + 808) >> 2);
    }
  }
  v43 = *(_QWORD *)(a1 + 728);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v44 = 0;
  v45 = *(_QWORD *)(v43 + 48);
  if ( *(_DWORD *)(v45 + 1032) > 1u )
  {
    v46 = *(_DWORD *)(v45 + 1040);
    v44 = KeGetCurrentProcessorNumberEx(0) / v46;
    v47 = *(_DWORD *)(*(_QWORD *)(v43 + 48) + 1032LL);
    if ( v44 >= v47 )
      v44 %= v47;
  }
  v48 = v43 + 320LL * v44;
  if ( v48 && *(_DWORD *)(*(_QWORD *)(v48 + 48) + 1052LL) || *(_DWORD *)(v48 + 40) )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v48, &LockHandle);
    if ( !(unsigned __int8)StorIsIoGatewayPaused(v48) && !*(_DWORD *)(v48 + 40) )
    {
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      goto LABEL_125;
    }
    v51 = *(__int64 **)(v48 + 16);
    if ( *v51 != v48 + 8 )
      __fastfail(3u);
    *(_QWORD *)v6 = v48 + 8;
    *(_QWORD *)(v6 + 8) = v51;
    *v51 = v6;
    *(_QWORD *)(v48 + 16) = v6;
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 24));
    if ( (*(_BYTE *)(v6 + 22) & 0x20) != 0 )
    {
      v52 = *(_QWORD *)(*(_QWORD *)(v6 + 64) + 8LL);
      v53 = 96;
      if ( *(_BYTE *)(v52 + 2) != 40 )
        v53 = 48;
      v54 = v48 + 264;
      v55 = *(_QWORD **)(v54 + 8);
      if ( *v55 != v54 )
        __fastfail(3u);
      v56 = (_QWORD *)(*(_QWORD *)(v52 + v53) + 24LL);
      *v56 = v54;
      v56[1] = v55;
      *v55 = v56;
LABEL_154:
      *(_QWORD *)(v54 + 8) = v56;
    }
    goto LABEL_155;
  }
LABEL_125:
  v49 = *(_DWORD *)(v48 + 128);
  if ( v49 )
  {
    v57 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v48 + 152) + 64LL) + 1040LL);
    v58 = v49 * (HIDWORD(KeGetPcr()[1].LockArray) % v57) / v57;
    v59 = v58;
    IoResource = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v48 + 64) + 8 * v58));
    if ( !IoResource )
    {
      v60 = *(_DWORD *)(v48 + 128);
      if ( v60 <= 1 )
      {
LABEL_142:
        v42 = v6 - 120;
        goto LABEL_143;
      }
      v61 = 1;
      while ( !IoResource )
      {
        v62 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v48 + 64) + 8LL * ((v61 + v59) % v60)));
        v60 = *(_DWORD *)(v48 + 128);
        ++v61;
        IoResource = v62;
        if ( v61 >= v60 )
        {
          if ( !v62 )
            goto LABEL_142;
          break;
        }
      }
    }
    LODWORD(IoResource->Next) = v59;
    goto LABEL_142;
  }
  IoResource = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v48 + 64));
LABEL_143:
  if ( IoResource
    || *(_DWORD *)(v48 + 136) < *(_DWORD *)(v48 + 144)
    && (RaAttemptHighWaterMarkIncrease((PVOID)v48), (IoResource = (PSLIST_ENTRY)RaAllocateIoResource(v48 + 64)) != 0) )
  {
    v71 = *(_DWORD *)(v48 + 36);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v48 + 192)) >= v71 )
      *(_DWORD *)(v48 + 36) = *(_DWORD *)(v48 + 192);
    v81.m256i_i64[2] = (__int64)&IoResource[3];
    v81.m256i_i64[3] = (__int64)&IoResource[59];
    v81.m256i_i64[1] = (__int64)&IoResource[75];
    v72 = (void *)*((_QWORD *)&IoResource[50].Next + 1);
    v73 = *((_DWORD *)&IoResource[49].Next + 2);
    LOBYTE(IoResource[4].Next) &= 0x9Cu;
    v74 = *((_QWORD *)&IoResource[52].Next + 1);
    LODWORD(IoResource[3].Next) = 523124044;
    *((_QWORD *)&IoResource[3].Next + 1) = 0;
    WORD2(IoResource[4].Next) = -1;
    BYTE6(IoResource[4].Next) = -1;
    *((_DWORD *)&IoResource[4].Next + 2) = 0;
    *((_QWORD *)&IoResource[9].Next + 1) = 0;
    IoResource[10].Next = 0;
    *((_QWORD *)&IoResource[11].Next + 1) = 0;
    *((_QWORD *)&IoResource[12].Next + 1) = 0;
    IoResource[12].Next = 0;
    IoResource[15].Next = 0;
    IoResource[13].Next = 0;
    *((_QWORD *)&IoResource[13].Next + 1) = 0;
    *((_QWORD *)&IoResource[16].Next + 1) = 0;
    IoResource[17].Next = 0;
    *((_QWORD *)&IoResource[10].Next + 1) = 0;
    *((_QWORD *)&IoResource[46].Next + 1) = 0;
    IoResource[47].Next = 0;
    *((_QWORD *)&IoResource[47].Next + 1) = 0;
    IoResource[48].Next = 0;
    *((_DWORD *)&IoResource[49].Next + 2) = v73;
    *((_QWORD *)&IoResource[50].Next + 1) = v72;
    if ( v72 )
      memset_0(v72, 0, v73);
    LOBYTE(IoResource[4].Next) &= ~0x80u;
    BYTE1(IoResource[4].Next) &= 0x70u;
    LODWORD(IoResource[53].Next) = -1;
    IoResource[51].Next = 0;
    *((_DWORD *)&IoResource[49].Next + 3) = 0;
    *((_DWORD *)&IoResource[51].Next + 2) = 0;
    *((_QWORD *)&IoResource[52].Next + 1) = v74;
    *((_WORD *)&IoResource[51].Next + 6) = -1;
    IoResource[52].Next = 0;
    *((_DWORD *)&IoResource[53].Next + 2) = 0;
    LODWORD(IoResource[54].Next) = 0;
    *((_QWORD *)&IoResource[54].Next + 1) = 0;
    IoResource[55] = 0;
    IoResource[56].Next = 0;
    *((_QWORD *)&IoResource[56].Next + 1) = 0;
    IoResource[57].Next = 0;
    *((_QWORD *)&IoResource[57].Next + 1) = 0;
    LODWORD(IoResource[58].Next) = -1;
    (*(void (__fastcall **)(_QWORD, __int64, __m256i *, _QWORD))(a1 + 712))(*(_QWORD *)(a1 + 704), v42, &v81, 0);
    v69 = 1;
  }
  else
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v48, &LockHandle);
    v63 = *(__int64 **)(v48 + 16);
    if ( *v63 != v48 + 8 )
      __fastfail(3u);
    *(_QWORD *)v6 = v48 + 8;
    *(_QWORD *)(v6 + 8) = v63;
    *v63 = v6;
    *(_QWORD *)(v48 + 16) = v6;
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 24));
    *(_DWORD *)(v48 + 40) = 1699901262;
    if ( (*(_BYTE *)(v6 + 22) & 0x20) != 0 )
    {
      v64 = *(_QWORD *)(*(_QWORD *)(v6 + 64) + 8LL);
      v65 = 96;
      if ( *(_BYTE *)(v64 + 2) != 40 )
        v65 = 48;
      v54 = v48 + 264;
      v66 = *(_QWORD **)(v54 + 8);
      if ( *v66 != v54 )
        __fastfail(3u);
      v56 = (_QWORD *)(*(_QWORD *)(v65 + v64) + 24LL);
      *v56 = v54;
      v56[1] = v66;
      *v66 = v56;
      goto LABEL_154;
    }
LABEL_155:
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    v67 = *(_QWORD *)(a1 + 728);
    if ( (*(_BYTE *)(*(_QWORD *)(v67 + 48) + 112LL) & 4) != 0
      && *(_DWORD *)(v67 + 40) == 1699901262
      && *(_DWORD *)(v67 + 24)
      && !*(_DWORD *)(v67 + 192) )
    {
      v68 = *(KSPIN_LOCK **)(a1 + 728);
      *(_DWORD *)(v67 + 40) = 0;
      RaidAdapterRestartGateway(v68);
    }
LABEL_160:
    v69 = 0;
  }
  if ( a2 )
  {
    for ( i = RaidNormalizeDeviceQueue(a1 + 720); i; i = RaidNormalizeDeviceQueue(a1 + 720) )
    {
      if ( (unsigned __int8)StorSubmitIoGatewayItem(*(_QWORD *)(a1 + 728), i, &v81) )
      {
        v75 = *(_QWORD *)(a1 + 728);
        if ( (*(_BYTE *)(*(_QWORD *)(v75 + 48) + 112LL) & 4) != 0
          && *(_DWORD *)(v75 + 40) == 1699901262
          && *(_DWORD *)(v75 + 24)
          && !*(_DWORD *)(v75 + 192) )
        {
          v76 = *(KSPIN_LOCK **)(a1 + 728);
          *(_DWORD *)(v75 + 40) = 0;
          RaidAdapterRestartGateway(v76);
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, __int64, __m256i *, _QWORD))(a1 + 712))(*(_QWORD *)(a1 + 704), i - 120, &v81, 0);
      }
    }
  }
  return v69;
}

```

## disassembly

```asm
0x140021bf0  push    rbp
0x140021bf2  push    rbx
0x140021bf3  push    rsi
0x140021bf4  push    rdi
0x140021bf5  push    r12
0x140021bf7  push    r13
0x140021bf9  push    r14
0x140021bfb  push    r15
0x140021bfd  lea     rbp, [rsp-1Fh]
0x140021c02  sub     rsp, 0E8h
0x140021c09  mov     rax, cs:__security_cookie
0x140021c10  xor     rax, rsp
0x140021c13  mov     [rbp+57h+var_50], rax
0x140021c17  xorps   xmm0, xmm0
0x140021c1a  mov     [rbp+57h+var_C8], edx
0x140021c1d  xor     r12d, r12d
0x140021c20  xor     eax, eax
0x140021c22  mov     [rbp+57h+var_CC], r12d
0x140021c26  mov     r15d, edx
0x140021c29  mov     r13, rcx
0x140021c2c  mov     esi, 1
0x140021c31  mov     ebx, 0FFFFFFFFh
0x140021c36  movups  [rbp+57h+var_C0], xmm0
0x140021c3a  movups  [rbp+57h+var_C0+0Ch], xmm0
0x140021c3e  test    r8d, r8d
0x140021c41  jz      short loc_140021C57
0x140021c43  add     rcx, 2D0h
0x140021c4a  call    RaidNormalizeDeviceQueue
0x140021c4f  mov     rsi, rax
0x140021c52  jmp     loc_14002223F
0x140021c57  mov     rax, [rcx+18h]
0x140021c5b  xor     r14b, r14b
0x140021c5e  mov     [rbp+57h+var_D0], r14b
0x140021c62  test    rax, rax
0x140021c65  jz      loc_140021D35
0x140021c6b  mov     r14, [rcx+230h]
0x140021c72  test    r14, r14
0x140021c75  jz      loc_140021D28
0x140021c7b  cmp     [rax+1360h], r12
0x140021c82  jbe     loc_140021D28
0x140021c88  xor     eax, eax
0x140021c8a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140021c91  mov     esi, r12d
0x140021c94  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140021c98  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140021c9c  cmp     [r14+8], eax
0x140021ca0  jbe     short loc_140021CF1
0x140021ca2  mov     ebx, esi
0x140021ca4  lea     rcx, [r14+68h]
0x140021ca8  shl     rbx, 6
0x140021cac  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140021cb0  add     rcx, rbx; SpinLock
0x140021cb3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140021cba  nop     dword ptr [rax+rax+00h]
0x140021cbf  lea     rax, [r14+40h]
0x140021cc3  add     rax, rbx
0x140021cc6  mov     rcx, [rax]
0x140021cc9  cmp     rcx, rax
0x140021ccc  jz      short loc_140021CD9
0x140021cce  mov     rax, [rcx+28h]
0x140021cd2  cmp     rax, rdi
0x140021cd5  cmovb   rdi, rax
0x140021cd9  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140021cdd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140021ce4  nop     dword ptr [rax+rax+00h]
0x140021ce9  inc     esi
0x140021ceb  cmp     esi, [r14+8]
0x140021cef  jb      short loc_140021CA2
0x140021cf1  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140021cf5  mov     rbx, r12
0x140021cf8  cmovnz  rbx, rdi
0x140021cfc  test    rbx, rbx
0x140021cff  jz      short loc_140021D2D
0x140021d01  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140021d08  nop     dword ptr [rax+rax+00h]
0x140021d0d  mov     rcx, rax
0x140021d10  mov     rax, [r13+18h]
0x140021d14  sub     rcx, rbx
0x140021d17  cmp     rcx, [rax+1360h]
0x140021d1e  setnbe  r14b
0x140021d22  mov     [rbp+57h+var_D0], r14b
0x140021d26  jmp     short loc_140021D30
0x140021d28  xor     r14b, r14b
0x140021d2b  jmp     short loc_140021D35
0x140021d2d  xor     r14b, r14b
0x140021d30  mov     esi, 1
0x140021d35  lea     rdi, [r13+2D0h]
0x140021d3c  test    r15d, r15d
0x140021d3f  jz      loc_140021E51
0x140021d45  xorps   xmm0, xmm0
0x140021d48  xor     eax, eax
0x140021d4a  movups  [rbp+57h+var_88], xmm0
0x140021d4e  mov     [rbp+57h+var_58], rax
0x140021d52  movups  [rbp+57h+var_78], xmm0
0x140021d56  movups  [rbp+57h+var_68], xmm0
0x140021d5a  cmp     [r13+20h], rax
0x140021d5e  jz      loc_140021E51
0x140021d64  mov     edx, 1Fh
0x140021d69  mov     rcx, r13
0x140021d6c  call    RaidIsUnitControlSupported
0x140021d71  test    al, al
0x140021d73  jz      loc_140021E51
0x140021d79  mov     rcx, [r13+20h]
0x140021d7d  add     rcx, 18h; SpinLock
0x140021d81  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140021d88  nop     dword ptr [rax+rax+00h]
0x140021d8d  movzx   ebx, al
0x140021d90  mov     rax, [r13+20h]
0x140021d94  and     dword ptr [rax+50h], 0FFFFFEFFh
0x140021d9b  mov     rcx, [r13+20h]
0x140021d9f  test    dword ptr [rcx+50h], 1E0h
0x140021da6  jnz     loc_140021E3A
0x140021dac  cmp     [rcx+54h], r12d
0x140021db0  jg      loc_140021E3A
0x140021db6  mov     dword ptr [rbp+57h+var_88], 38h ; '8'
0x140021dbd  mov     dword ptr [rbp+57h+var_88+4], 38h ; '8'
0x140021dc4  mov     dword ptr [rbp+57h+var_88+8], 3
0x140021dcb  call    Feature_Servicing_perLunLockingEnable__private_IsEnabledDeviceUsageNoInline
0x140021dd0  test    eax, eax
0x140021dd2  jz      short loc_140021E03
0x140021dd4  mov     rax, [r13+18h]
0x140021dd8  mov     word ptr [rbp+57h+var_68+8], si
0x140021ddc  mov     dword ptr [rbp+57h+var_68+0Ch], 4
0x140021de3  movzx   ecx, word ptr [rax+38h]
0x140021de7  movzx   eax, byte ptr [r13+68h]
0x140021dec  mov     byte ptr [rbp+57h+var_58], al
0x140021def  movzx   eax, byte ptr [r13+69h]
0x140021df4  mov     byte ptr [rbp+57h+var_58+1], al
0x140021df7  movzx   eax, byte ptr [r13+6Ah]
0x140021dfc  mov     byte ptr [rbp+57h+var_58+2], al
0x140021dff  mov     word ptr [rbp+57h+var_68+0Ah], cx
0x140021e03  mov     rcx, [r13+18h]
0x140021e07  mov     eax, [rcx]
0x140021e09  cmp     eax, 41445452h
0x140021e0e  jnz     short loc_140021E19
0x140021e10  add     rcx, 168h
0x140021e17  jmp     short loc_140021E2C
0x140021e19  cmp     eax, 4E564144h
0x140021e1e  jnz     short loc_140021E29
0x140021e20  add     rcx, 0B0h
0x140021e27  jmp     short loc_140021E2C
0x140021e29  mov     rcx, r12
0x140021e2c  lea     r8, [rbp+57h+var_88]
0x140021e30  mov     edx, 1Fh
0x140021e35  call    RaCallMiniportUnitControl
0x140021e3a  mov     rcx, [r13+20h]
0x140021e3e  movzx   edx, bl; NewIrql
0x140021e41  add     rcx, 18h; SpinLock
0x140021e45  call    cs:__imp_KeReleaseSpinLock
0x140021e4c  nop     dword ptr [rax+rax+00h]
0x140021e51  mov     cl, 2; NewIrql
0x140021e53  mov     rsi, r12
0x140021e56  call    cs:__imp_KfRaiseIrql
0x140021e5d  nop     dword ptr [rax+rax+00h]
0x140021e62  mov     [rbp+57h+var_CF], al
0x140021e65  xor     bl, bl
0x140021e67  mov     rax, [rdi+58h]
0x140021e6b  xor     r15b, r15b
0x140021e6e  test    al, 1
0x140021e70  jnz     loc_140021FBE
0x140021e76  nop     word ptr [rax+rax+00000000h]
0x140021e80  mov     [rbp+57h+LockHandle.LockQueue.Next], rax
0x140021e84  mov     r8, rax
0x140021e87  cqo
0x140021e89  mov     ecx, 0FFFFFFFFh
0x140021e8e  and     rdx, rcx
0x140021e91  add     rax, rdx
0x140021e94  sar     rax, 20h
0x140021e98  test    eax, eax
0x140021e9a  jnz     short loc_140021EB7
0x140021e9c  lea     rcx, [r8-4]
0x140021ea0  mov     rax, r8
0x140021ea3  lock cmpxchg [rdi+58h], rcx
0x140021ea9  cmp     r8, rax
0x140021eac  jz      loc_140021F78
0x140021eb2  jmp     loc_140021F56
0x140021eb7  test    r14b, r14b
0x140021eba  jnz     loc_140021F7B
0x140021ec0  lea     rcx, [rdi+70h]; SListHead
0x140021ec4  call    cs:__imp_ExQueryDepthSList
0x140021ecb  nop     dword ptr [rax+rax+00h]
0x140021ed0  test    ax, ax
0x140021ed3  jnz     short loc_140021F0F
0x140021ed5  test    r15b, r15b
0x140021ed8  jnz     short loc_140021F05
0x140021eda  test    bl, bl
0x140021edc  jz      short loc_140021EF0
0x140021ede  lea     rcx, [rdi+50h]; RunRef
0x140021ee2  call    cs:__imp_ExReleaseRundownProtection
0x140021ee9  nop     dword ptr [rax+rax+00h]
0x140021eee  xor     bl, bl
0x140021ef0  lea     rcx, [rdi+48h]; SpinLock
0x140021ef4  call    cs:__imp_ExAcquireSpinLockExclusiveAtDpcLevel
0x140021efb  nop     dword ptr [rax+rax+00h]
0x140021f00  mov     r15b, 1
0x140021f03  jmp     short loc_140021F52
0x140021f05  mov     rcx, rdi
0x140021f08  call    RiFlushDeviceLists
0x140021f0d  jmp     short loc_140021F32
0x140021f0f  test    r15b, r15b
0x140021f12  jnz     short loc_140021F32
0x140021f14  test    bl, bl
0x140021f16  jnz     short loc_140021F32
0x140021f18  lea     rcx, [rdi+50h]; RunRef
0x140021f1c  call    cs:__imp_ExAcquireRundownProtection
0x140021f23  nop     dword ptr [rax+rax+00h]
0x140021f28  test    al, al
0x140021f2a  jz      loc_140021FBE
0x140021f30  mov     bl, 1
0x140021f32  lea     rcx, [rdi+70h]; ListHead
0x140021f36  call    cs:__imp_ExpInterlockedPopEntrySList
0x140021f3d  nop     dword ptr [rax+rax+00h]
0x140021f42  mov     rcx, rax
0x140021f45  call    RiEntryToDeviceEntry
0x140021f4a  mov     rsi, rax
0x140021f4d  test    rax, rax
0x140021f50  jnz     short loc_140021F65
0x140021f52  mov     rax, [rdi+58h]
0x140021f56  movzx   r14d, [rbp+57h+var_D0]
0x140021f5b  test    al, 1
0x140021f5d  jz      loc_140021E80
0x140021f63  jmp     short loc_140021F7B
0x140021f65  mov     rax, 0FFFFFFFF00000000h
0x140021f6f  lock add [rdi+58h], rax
0x140021f74  and     byte ptr [rsi+14h], 0FCh
0x140021f78  mov     r12b, 1
0x140021f7b  test    bl, bl
0x140021f7d  jz      short loc_140021F8F
0x140021f7f  lea     rcx, [rdi+50h]; RunRef
0x140021f83  call    cs:__imp_ExReleaseRundownProtection
0x140021f8a  nop     dword ptr [rax+rax+00h]
0x140021f8f  test    r15b, r15b
0x140021f92  jz      short loc_140021FA4
0x140021f94  lea     rcx, [rdi+48h]; SpinLock
0x140021f98  call    cs:__imp_ExReleaseSpinLockExclusiveFromDpcLevel
0x140021f9f  nop     dword ptr [rax+rax+00h]
0x140021fa4  test    r12b, r12b
0x140021fa7  jz      short loc_140021FBE
0x140021fa9  movzx   ecx, [rbp+57h+var_CF]; NewIrql
0x140021fad  call    cs:__imp_KeLowerIrql
0x140021fb4  nop     dword ptr [rax+rax+00h]
0x140021fb9  jmp     loc_140022237
0x140021fbe  lea     rcx, [rdi+48h]; SpinLock
0x140021fc2  call    cs:__imp_ExAcquireSpinLockExclusiveAtDpcLevel
0x140021fc9  nop     dword ptr [rax+rax+00h]
0x140021fce  mov     rax, [rdi+58h]
0x140021fd2  xor     r14b, r14b
0x140021fd5  movzx   r15d, [rbp+57h+var_D0]
0x140021fda  test    al, 1
0x140021fdc  jnz     loc_140022082
0x140021fe2  mov     [rbp+57h+LockHandle.LockQueue.Next], rax
0x140021fe6  mov     r8, rax
0x140021fe9  cqo
0x140021feb  mov     ecx, 0FFFFFFFFh
0x140021ff0  and     rdx, rcx
0x140021ff3  add     rax, rdx
0x140021ff6  sar     rax, 20h
0x140021ffa  test    eax, eax
0x140021ffc  jnz     short loc_140022012
0x140021ffe  lea     rcx, [r8-4]
0x140022002  mov     rax, r8
0x140022005  lock cmpxchg [rdi+58h], rcx
0x14002200b  cmp     r8, rax
0x14002200e  jz      short loc_140022076
0x140022010  jmp     short loc_14002205D
0x140022012  test    r15b, r15b
0x140022015  jnz     short loc_140022079
0x140022017  lea     rcx, [rdi+70h]; SListHead
0x14002201b  call    cs:__imp_ExQueryDepthSList
0x140022022  nop     dword ptr [rax+rax+00h]
0x140022027  test    ax, ax
0x14002202a  jnz     short loc_140022034
0x14002202c  mov     rcx, rdi
0x14002202f  call    RiFlushDeviceLists
0x140022034  test    rsi, rsi
0x140022037  jnz     short loc_140022063
0x140022039  lea     rcx, [rdi+70h]; ListHead
0x14002203d  call    cs:__imp_ExpInterlockedPopEntrySList
0x140022044  nop     dword ptr [rax+rax+00h]
0x140022049  mov     rcx, rax
0x14002204c  call    RiEntryToDeviceEntry
0x140022051  mov     rsi, rax
0x140022054  test    rax, rax
0x140022057  jnz     short loc_140022063
0x140022059  mov     rax, [rdi+58h]
0x14002205d  test    al, 1
0x14002205f  jz      short loc_140021FE2
0x140022061  jmp     short loc_140022079
0x140022063  mov     rax, 0FFFFFFFF00000000h
0x14002206d  lock add [rdi+58h], rax
0x140022072  and     byte ptr [rsi+14h], 0FCh
0x140022076  mov     r14b, 1
0x140022079  test    r14b, r14b
0x14002207c  jnz     loc_140022223
0x140022082  mov     rsi, [rdi+58h]
0x140022086  test    sil, 1
0x14002208a  jnz     short loc_1400220C9
0x14002208c  lea     rcx, [rdi+50h]; RunRef
0x140022090  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140022097  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
