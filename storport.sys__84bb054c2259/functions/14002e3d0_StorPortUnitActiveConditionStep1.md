# StorPortUnitActiveConditionStep1

- ea: `0x14002e3d0`
- end: `0x14002ede5`
- name: `StorPortUnitActiveConditionStep1`
- size: `2581`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x140004cb4`
- `0x14000befc`
- `0x140012174`
- `0x140022cb0`
- `0x14002e3d0`
- `0x1400313b0`
- `0x14003982c`
- `0x14004edf4`
- `0x140066a60`
- `0x1400bb9e0`
- `0x1400c5658`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002ea43`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ecf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ed34`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ea43`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ecf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ed34`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002e40d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002e833`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002e40d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002e833`
- `ntoskrnl!KeLowerIrql` at `0x14002e8df`
- `ntoskrnl!KeLowerIrql` at `0x14002ec94`
- `ntoskrnl!KeLowerIrql` at `0x14002e8df`
- `ntoskrnl!KeLowerIrql` at `0x14002ec94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e8f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e8f3`
- `ntoskrnl!KfRaiseIrql` at `0x14002e8ba`
- `ntoskrnl!KfRaiseIrql` at `0x14002ea7a`
- `ntoskrnl!KfRaiseIrql` at `0x14002e8ba`
- `ntoskrnl!KfRaiseIrql` at `0x14002ea7a`
- `ntoskrnl!IoQueueWorkItem` at `0x14002ed1f`
- `ntoskrnl!IoQueueWorkItem` at `0x14002ed1f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002e912`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002ed99`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002e912`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002ed99`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002e805`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002e805`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ec0b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ec0b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002ea95`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002ea95`
- `ntoskrnl!ExRundownCompleted` at `0x14002eac3`
- `ntoskrnl!ExRundownCompleted` at `0x14002eac3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002eab3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002eab3`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002eb7a`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002eb7a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002ea5c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002ea5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e986`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ecc0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e986`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ecc0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002e927`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002e927`

## pseudocode

```c
void __fastcall StorPortUnitActiveConditionStep1(__int64 a1, char a2)
{
  int v4; // r8d
  _DWORD *v5; // rax
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // r12
  __int64 v9; // r13
  _DWORD *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  _DWORD *v16; // r10
  unsigned int v17; // r11d
  __int64 v18; // rcx
  _DWORD *v19; // r10
  __int64 v20; // rcx
  _DWORD *v21; // r10
  __int64 v22; // rcx
  _DWORD *v23; // r10
  __int64 v24; // rcx
  _DWORD *v25; // r10
  _DWORD *v26; // rax
  _DWORD *v27; // rbx
  __int64 v28; // rcx
  _DWORD *v29; // r9
  unsigned int v30; // r11d
  __int64 v31; // rcx
  _DWORD *v32; // r9
  __int64 v33; // rcx
  _DWORD *v34; // r9
  __int64 v35; // rcx
  _DWORD *v36; // r9
  __int64 v37; // rcx
  _DWORD *v38; // r9
  __int64 v39; // rcx
  void (__fastcall *v40)(__int64, __int64, struct _KLOCK_QUEUE_HANDLE *, __int64); // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  KSPIN_LOCK *v45; // rcx
  _QWORD *v46; // rax
  _QWORD *v47; // rdi
  _QWORD *v48; // rcx
  __int64 v49; // r14
  __int64 v50; // rax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  KIRQL v55; // bl
  int v56; // r8d
  KIRQL v57; // bl
  __int64 v58; // rdx
  __int64 v59; // rax
  __int16 v60; // cx
  _DWORD *v61; // rcx
  _DWORD *v62; // rcx
  KIRQL v63; // r15
  KIRQL v64; // al
  signed __int64 v65; // r14
  KIRQL v66; // r13
  bool v67; // zf
  signed __int64 v68; // rax
  __int64 v69; // rax
  signed __int64 v70; // rbx
  char v71; // r8
  __int64 v72; // r14
  __int64 v73; // rax
  signed __int64 v74; // rdx
  signed __int64 v75; // rax
  signed __int64 v76; // rax
  signed __int64 v77; // rtt
  __int64 v78; // rdx
  KSPIN_LOCK *v79; // rcx
  __int64 v80; // rcx
  KIRQL v81; // al
  __int64 v82; // rdx
  int v83; // ecx
  int v84; // [rsp+50h] [rbp-29h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v87[2]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v88; // [rsp+90h] [rbp+17h]
  __int64 v89; // [rsp+A0h] [rbp+27h]

  if ( (*(_DWORD *)(a1 + 504) & 0x8000) == 0
    || !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864)) )
  {
    return;
  }
  if ( StorEtwLoggingEnabled && (byte_140177432 & 0x10) != 0 )
    McTemplateK0pquuuq_EtwWriteTransfer(
      *(_QWORD *)(a1 + 24),
      (unsigned int)EventUnitActiveConditionStart,
      v4,
      **(_QWORD **)(a1 + 1872),
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
      *(_BYTE *)(a1 + 104),
      *(_BYTE *)(a1 + 105),
      *(_BYTE *)(a1 + 106),
      a2);
  v84 = 1;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1872) + 32LL) & 4) != 0 )
  {
    v5 = *(_DWORD **)(a1 + 24);
    v6 = 256;
    v7 = 264;
    v8 = 272;
    v9 = 280;
    if ( *v5 == 1094997074 )
    {
      v10 = v5 + 90;
      v11 = (__int64)(v5 + 154);
      v12 = (__int64)(v5 + 156);
      v13 = (__int64)(v5 + 158);
      v14 = (__int64)(v5 + 160);
    }
    else if ( *v5 == 1314275652 )
    {
      v10 = v5 + 44;
      v11 = (__int64)(v5 + 108);
      v12 = (__int64)(v5 + 110);
      v13 = (__int64)(v5 + 112);
      v14 = (__int64)(v5 + 114);
    }
    else
    {
      v10 = 0;
      v11 = 256;
      v12 = 264;
      v13 = 272;
      v14 = 280;
    }
    if ( **((_DWORD **)v10 + 29) == 208 )
    {
      if ( (v10[62] & 0x10) == 0 )
      {
        *(_QWORD *)v11 = 0;
        *(_QWORD *)v12 = 0;
        *(_QWORD *)v13 = 0;
        *(_QWORD *)v14 = 0;
        v10[63] = 12;
        if ( (unsigned __int8)RaMiniportIsFeatureSupported(v10, 0) )
          *v16 = 13;
        if ( (unsigned __int8)RaMiniportIsFeatureSupported(v15, v17) )
          *v19 = 14;
        if ( (unsigned __int8)RaMiniportIsFeatureSupported(v18, 4) )
          *v21 = 15;
        if ( (unsigned __int8)RaMiniportIsFeatureSupported(v20, 11) )
          v10[72] = 16;
        if ( (*(_DWORD *)(*((_QWORD *)v10 + 29) + 184LL) & 0x20000) != 0 )
          *v23 = 17;
        if ( (unsigned __int8)RaMiniportIsFeatureSupported(v22, 14) )
          *v25 = 32;
        if ( (int)RaCallMiniportUnitControl(v24, 0, v25) < 0 )
          goto LABEL_53;
        v10[62] |= 0x10u;
      }
      if ( *((_BYTE *)v10 + 262) )
      {
        v26 = *(_DWORD **)(a1 + 24);
        if ( *v26 == 1094997074 )
        {
          v27 = v26 + 90;
          v6 = (__int64)(v26 + 154);
          v7 = (__int64)(v26 + 156);
          v8 = (__int64)(v26 + 158);
          v9 = (__int64)(v26 + 160);
        }
        else if ( *v26 == 1314275652 )
        {
          v27 = v26 + 44;
          v6 = (__int64)(v26 + 108);
          v7 = (__int64)(v26 + 110);
          v8 = (__int64)(v26 + 112);
          v9 = (__int64)(v26 + 114);
        }
        else
        {
          v27 = 0;
        }
        if ( **((_DWORD **)v27 + 29) == 208 )
        {
          if ( (v27[62] & 0x10) == 0 )
          {
            *(_QWORD *)v6 = 0;
            *(_QWORD *)v7 = 0;
            *(_QWORD *)v8 = 0;
            *(_QWORD *)v9 = 0;
            v27[63] = 12;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v27, 0) )
              *v29 = 13;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v28, v30) )
              *v32 = 14;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v31, 4) )
              *v34 = 15;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v33, 11) )
              v27[72] = 16;
            if ( (*(_DWORD *)(*((_QWORD *)v27 + 29) + 184LL) & 0x20000) != 0 )
              *v36 = 17;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v35, 14) )
              *v38 = 32;
            if ( (int)RaCallMiniportUnitControl(v37, 0, v38) < 0 )
              goto LABEL_53;
            v27[62] |= 0x10u;
          }
          if ( *((_BYTE *)v27 + 262) )
          {
            v39 = *(_QWORD *)(a1 + 24);
            *(_WORD *)(&LockHandle.OldIrql + 5) = 0;
            *(&LockHandle.OldIrql + 7) = 0;
            LockHandle.LockQueue.Lock = (unsigned __int64 *volatile)(a1 + 96);
            LockHandle.LockQueue.Next = (_KSPIN_LOCK_QUEUE *volatile)0x1800000001LL;
            *(_DWORD *)&LockHandle.OldIrql = 0;
            *(&LockHandle.OldIrql + 4) = 1;
            v40 = *(void (__fastcall **)(__int64, __int64, struct _KLOCK_QUEUE_HANDLE *, __int64))(*(_QWORD *)(v39 + 592)
                                                                                                 + 200LL);
            if ( v40 )
            {
              v40(*(_QWORD *)(v39 + 600) + 16LL, 6, &LockHandle, v14);
              Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v42, v41, v43, v44);
            }
          }
        }
      }
    }
  }
LABEL_53:
  v45 = (KSPIN_LOCK *)(*(_QWORD *)(a1 + 1872) + 96LL);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock(v45, &LockHandle);
  *(_DWORD *)(*(_QWORD *)(a1 + 1872) + 32LL) |= 2u;
  if ( (*(_DWORD *)(a1 + 504) & 0x8000) != 0
    && ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864)) )
  {
    while ( 1 )
    {
      v46 = (_QWORD *)(*(_QWORD *)(a1 + 1872) + 80LL);
      if ( (_QWORD *)*v46 == v46 )
        break;
      v47 = *(_QWORD **)(*(_QWORD *)(a1 + 1872) + 88LL);
      if ( (_QWORD *)*v47 != v46 || (v48 = (_QWORD *)v47[1], (_QWORD *)*v48 != v47) )
        __fastfail(3u);
      *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 88LL) = v48;
      *v48 = v46;
      v49 = v47[2];
      v50 = *(_QWORD *)(*(_QWORD *)(v49 + 184) + 8LL);
      if ( *(_BYTE *)(v50 + 2) == 40 )
        v51 = *(_DWORD *)(v50 + 20);
      else
        v51 = *(unsigned __int8 *)(v50 + 2);
      v52 = v51 - 16;
      if ( !v52 || (v53 = v52 - 2) == 0 || (v54 = v53 - 1) == 0 || v54 == 13 )
      {
        v55 = KfRaiseIrql(2u);
        RaUnitStartResetIo(*(_QWORD *)(a1 + 8), v49, a1 + 1824);
        KeLowerIrql(v55);
      }
      ExFreePoolWithTag(v47, 0x4F506152u);
    }
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( *(_BYTE *)(a1 + 759) )
  {
    *(_BYTE *)(a1 + 759) = 0;
    memset(v87, 0, sizeof(v87));
    v89 = 0;
    v88 = 0;
    if ( *(_QWORD *)(a1 + 32) && (unsigned __int8)RaidIsUnitControlSupported(a1, 31) )
    {
      v57 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 32) + 24LL));
      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 80LL) &= ~0x40u;
      v58 = *(_QWORD *)(a1 + 32);
      if ( (*(_DWORD *)(v58 + 80) & 0x1E0) == 0 && *(int *)(v58 + 84) <= 0 )
      {
        *(_QWORD *)&v87[0] = 0x3800000038LL;
        DWORD2(v87[0]) = 3;
        if ( (unsigned int)Feature_Servicing_perLunLockingEnable__private_IsEnabledDeviceUsageNoInline() )
        {
          v59 = *(_QWORD *)(a1 + 24);
          WORD4(v88) = 1;
          HIDWORD(v88) = 4;
          v60 = *(_WORD *)(v59 + 56);
          LOWORD(v89) = *(_WORD *)(a1 + 104);
          BYTE2(v89) = *(_BYTE *)(a1 + 106);
          WORD5(v88) = v60;
        }
        v61 = *(_DWORD **)(a1 + 24);
        if ( *v61 == 1094997074 )
        {
          v62 = v61 + 90;
        }
        else if ( *v61 == 1314275652 )
        {
          v62 = v61 + 44;
        }
        else
        {
          v62 = 0;
        }
        RaCallMiniportUnitControl(v62, 31, v87);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 32) + 24LL), v57);
    }
    memset(v87, 0, 28);
    if ( KeGetCurrentIrql() == 2 )
    {
      v63 = 0;
    }
    else
    {
      v84 = 0;
      v63 = KfRaiseIrql(2u);
    }
    v64 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 792));
    v65 = *(_QWORD *)(a1 + 808);
    v66 = v64;
    if ( (v65 & 1) == 0 )
    {
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 800));
      ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 800));
      do
      {
        v68 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v65 | 1, v65);
        v67 = v65 == v68;
        v65 = v68;
      }
      while ( !v67 && (v68 & 1) == 0 );
    }
    v69 = RiNormalizeDeviceQueue(a1 + 720, 0);
    v70 = *(_QWORD *)(a1 + 808);
    v71 = 0;
    v72 = v69;
    if ( (v70 & 3) != 0 )
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
        if ( (v70 & 1) != 0 )
        {
          if ( !v71 )
          {
            ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(a1 + 800));
            v71 = 1;
          }
          v73 = v70 ^ 1;
        }
        else
        {
          v73 = v70;
        }
        v74 = v73 ^ 2;
        if ( (v70 & 2) == 0 )
          v74 = v73;
        v75 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v74, v70);
        v67 = v70 == v75;
        v70 = v75;
        if ( v67 )
        {
          if ( *(_BYTE *)(a1 + 757) || *(_BYTE *)(a1 + 759) || *(_BYTE *)(a1 + 756) || *(int *)(a1 + 744) > 0 )
          {
            v76 = *(_QWORD *)(a1 + 808);
            if ( (v76 & 3) == 0 )
            {
              do
              {
                v77 = v76;
                v76 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 808), v76 | 2, v76);
              }
              while ( v77 != v76 && (v76 & 3) == 0 );
            }
          }
          break;
        }
        if ( (v75 & 3) == 0 )
          break;
      }
    }
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 792), v66);
    if ( v72 )
    {
      if ( (unsigned __int8)StorSubmitIoGatewayItem(*(_QWORD *)(a1 + 728), v72, v87) )
      {
        v78 = *(_QWORD *)(a1 + 728);
        if ( (*(_BYTE *)(*(_QWORD *)(v78 + 48) + 112LL) & 4) != 0
          && *(_DWORD *)(v78 + 40) == 1699901262
          && *(_DWORD *)(v78 + 24)
          && !*(_DWORD *)(v78 + 192) )
        {
          v79 = *(KSPIN_LOCK **)(a1 + 728);
          *(_DWORD *)(v78 + 40) = 0;
          RaidAdapterRestartGateway(v79);
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, __int64, _OWORD *, _QWORD))(a1 + 712))(*(_QWORD *)(a1 + 704), v72 - 120, v87, 0);
      }
    }
    if ( !v84 )
      KeLowerIrql(v63);
    if ( !*(_BYTE *)(a1 + 759) )
    {
      v80 = *(_QWORD *)(a1 + 32);
      if ( v80 )
      {
        v81 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v80 + 24));
        v82 = *(_QWORD *)(a1 + 32);
        v83 = *(_DWORD *)(v82 + 80);
        if ( (v83 & 8) != 0 )
        {
          *(_DWORD *)(v82 + 80) = v83 & 0xFFFFFFF7;
          *(_DWORD *)(*(_QWORD *)(a1 + 32) + 80LL) |= 0x10u;
          KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 32) + 24LL), v81);
          *(_QWORD *)(*(_QWORD *)(a1 + 32) + 72LL) = 0;
          IoQueueWorkItem(
            *(PIO_WORKITEM *)(*(_QWORD *)(a1 + 32) + 64LL),
            RaAcquirePowerRefWorkRoutine,
            CriticalWorkQueue,
            (PVOID)(*(_QWORD *)(a1 + 32) + 64LL));
        }
        else
        {
          KeReleaseSpinLock((PKSPIN_LOCK)(v82 + 24), v81);
        }
      }
    }
  }
  if ( StorEtwLoggingEnabled && (byte_140177432 & 0x10) != 0 )
    McTemplateK0pquuuq_EtwWriteTransfer(
      *(_QWORD *)(a1 + 24),
      (unsigned int)EventUnitActiveConditionStop,
      v56,
      **(_QWORD **)(a1 + 1872),
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
      *(_BYTE *)(a1 + 104),
      *(_BYTE *)(a1 + 105),
      *(_BYTE *)(a1 + 106),
      a2);
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
}

```

## disassembly

```asm
0x14002e3d0  push    rbp
0x14002e3d2  push    rbx
0x14002e3d3  push    rsi
0x14002e3d4  lea     rbp, [rsp-47h]
0x14002e3d9  sub     rsp, 0C0h
0x14002e3e0  mov     rax, cs:__security_cookie
0x14002e3e7  xor     rax, rsp
0x14002e3ea  mov     [rbp+57h+var_28], rax
0x14002e3ee  mov     eax, [rcx+1F8h]
0x14002e3f4  mov     ebx, edx
0x14002e3f6  mov     [rbp+57h+var_7C], edx
0x14002e3f9  mov     rsi, rcx
0x14002e3fc  bt      eax, 0Fh
0x14002e400  jnb     loc_14002EDCD
0x14002e406  mov     rcx, [rcx+748h]; RunRefCacheAware
0x14002e40d  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002e414  nop     dword ptr [rax+rax+00h]
0x14002e419  test    al, al
0x14002e41b  jz      loc_14002EDCD
0x14002e421  cmp     cs:StorEtwLoggingEnabled, 0
0x14002e428  jz      short loc_14002E470
0x14002e42a  test    cs:byte_140177432, 10h
0x14002e431  jz      short loc_14002E470
0x14002e433  movzx   eax, byte ptr [rsi+6Ah]
0x14002e437  lea     rdx, EventUnitActiveConditionStart
0x14002e43e  mov     rcx, [rsi+18h]
0x14002e442  mov     r9, [rsi+750h]
0x14002e449  mov     [rsp+0D0h+var_90], ebx
0x14002e44d  mov     [rsp+0D0h+var_98], al
0x14002e451  movzx   eax, byte ptr [rsi+69h]
0x14002e455  mov     r9, [r9]
0x14002e458  mov     [rsp+0D0h+var_A0], al
0x14002e45c  movzx   eax, byte ptr [rsi+68h]
0x14002e460  mov     [rsp+0D0h+var_A8], al
0x14002e464  mov     eax, [rcx+38h]
0x14002e467  mov     [rsp+0D0h+var_B0], eax
0x14002e46b  call    McTemplateK0pquuuq_EtwWriteTransfer
0x14002e470  mov     rax, [rsi+750h]
0x14002e477  mov     r11d, 1
0x14002e47d  mov     [rsp+0D0h+arg_8], rdi
0x14002e485  mov     [rsp+0D0h+arg_10], r12
0x14002e48d  mov     [rsp+0D0h+arg_18], r13
0x14002e495  mov     ecx, [rax+20h]
0x14002e498  mov     [rsp+0D0h+var_18], r14
0x14002e4a0  mov     [rsp+0D0h+var_20], r15
0x14002e4a8  mov     [rbp+57h+var_80], r11d
0x14002e4ac  test    cl, 4
0x14002e4af  jz      loc_14002E7E6
0x14002e4b5  mov     rax, [rsi+18h]
0x14002e4b9  xor     edi, edi
0x14002e4bb  mov     r14d, 100h
0x14002e4c1  mov     r15d, 108h
0x14002e4c7  mov     r12d, 110h
0x14002e4cd  mov     r13d, 118h
0x14002e4d3  mov     ecx, [rax]
0x14002e4d5  cmp     ecx, 41445452h
0x14002e4db  jnz     short loc_14002E502
0x14002e4dd  lea     rbx, [rax+168h]
0x14002e4e4  lea     rcx, [rax+268h]
0x14002e4eb  lea     rdx, [rax+270h]
0x14002e4f2  lea     r8, [rax+278h]
0x14002e4f9  lea     r9, [rax+280h]
0x14002e500  jmp     short loc_14002E53E
0x14002e502  cmp     ecx, 4E564144h
0x14002e508  jnz     short loc_14002E52F
0x14002e50a  lea     rbx, [rax+0B0h]
0x14002e511  lea     rcx, [rax+1B0h]
0x14002e518  lea     rdx, [rax+1B8h]
0x14002e51f  lea     r8, [rax+1C0h]
0x14002e526  lea     r9, [rax+1C8h]
0x14002e52d  jmp     short loc_14002E53E
0x14002e52f  mov     rbx, rdi
0x14002e532  mov     rcx, r14
0x14002e535  mov     rdx, r15
0x14002e538  mov     r8, r12
0x14002e53b  mov     r9, r13
0x14002e53e  mov     rax, [rbx+0E8h]
0x14002e545  cmp     dword ptr [rax], 0D0h
0x14002e54b  jnz     loc_14002E7E6
0x14002e551  mov     eax, [rbx+0F8h]
0x14002e557  test    al, 10h
0x14002e559  jnz     loc_14002E61C
0x14002e55f  mov     [rcx], rdi
0x14002e562  lea     r10, [rbx+0FCh]
0x14002e569  mov     [rdx], rdi
0x14002e56c  mov     rcx, rbx
0x14002e56f  mov     [r8], rdi
0x14002e572  xor     edx, edx
0x14002e574  mov     [r9], rdi
0x14002e577  mov     dword ptr [r10], 0Ch
0x14002e57e  call    RaMiniportIsFeatureSupported
0x14002e583  test    al, al
0x14002e585  jz      short loc_14002E58E
0x14002e587  mov     dword ptr [r10], 0Dh
0x14002e58e  mov     edx, r11d
0x14002e591  call    RaMiniportIsFeatureSupported
0x14002e596  test    al, al
0x14002e598  jz      short loc_14002E5A1
0x14002e59a  mov     dword ptr [r10], 0Eh
0x14002e5a1  mov     edx, 4
0x14002e5a6  call    RaMiniportIsFeatureSupported
0x14002e5ab  test    al, al
0x14002e5ad  jz      short loc_14002E5B6
0x14002e5af  mov     dword ptr [r10], 0Fh
0x14002e5b6  mov     edx, 0Bh
0x14002e5bb  call    RaMiniportIsFeatureSupported
0x14002e5c0  test    al, al
0x14002e5c2  jz      short loc_14002E5CE
0x14002e5c4  mov     dword ptr [rbx+120h], 10h
0x14002e5ce  mov     rax, [rbx+0E8h]
0x14002e5d5  test    dword ptr [rax+0B8h], 20000h
0x14002e5df  jz      short loc_14002E5E8
0x14002e5e1  mov     dword ptr [r10], 11h
0x14002e5e8  mov     edx, 0Eh
0x14002e5ed  call    RaMiniportIsFeatureSupported
0x14002e5f2  test    al, al
0x14002e5f4  jz      short loc_14002E5FD
0x14002e5f6  mov     dword ptr [r10], 20h ; ' '
0x14002e5fd  mov     r8, r10
0x14002e600  xor     edx, edx
0x14002e602  call    RaCallMiniportUnitControl
0x14002e607  test    eax, eax
0x14002e609  js      loc_14002E7DF
0x14002e60f  or      dword ptr [rbx+0F8h], 10h
0x14002e616  mov     r11d, 1
0x14002e61c  mov     edi, 106h
0x14002e621  mov     eax, edi
0x14002e623  cmp     byte ptr [rbx+rax], 0
0x14002e627  jz      loc_14002E7DF
0x14002e62d  mov     rax, [rsi+18h]
0x14002e631  mov     ecx, [rax]
0x14002e633  cmp     ecx, 41445452h
0x14002e639  jnz     short loc_14002E660
0x14002e63b  lea     rbx, [rax+168h]
0x14002e642  lea     r14, [rax+268h]
0x14002e649  lea     r15, [rax+270h]
0x14002e650  lea     r12, [rax+278h]
0x14002e657  lea     r13, [rax+280h]
0x14002e65e  jmp     short loc_14002E68F
0x14002e660  cmp     ecx, 4E564144h
0x14002e666  jnz     short loc_14002E68D
0x14002e668  lea     rbx, [rax+0B0h]
0x14002e66f  lea     r14, [rax+1B0h]
0x14002e676  lea     r15, [rax+1B8h]
0x14002e67d  lea     r12, [rax+1C0h]
0x14002e684  lea     r13, [rax+1C8h]
0x14002e68b  jmp     short loc_14002E68F
0x14002e68d  xor     ebx, ebx
0x14002e68f  mov     rax, [rbx+0E8h]
0x14002e696  cmp     dword ptr [rax], 0D0h
0x14002e69c  jnz     loc_14002E7DF
0x14002e6a2  mov     eax, [rbx+0F8h]
0x14002e6a8  test    al, 10h
0x14002e6aa  jnz     loc_14002E775
0x14002e6b0  mov     qword ptr [r14], 0
0x14002e6b7  lea     r9, [rbx+0FCh]
0x14002e6be  mov     qword ptr [r15], 0
0x14002e6c5  xor     edx, edx
0x14002e6c7  mov     qword ptr [r12], 0
0x14002e6cf  mov     rcx, rbx
0x14002e6d2  mov     qword ptr [r13+0], 0
0x14002e6da  mov     dword ptr [r9], 0Ch
0x14002e6e1  call    RaMiniportIsFeatureSupported
0x14002e6e6  test    al, al
0x14002e6e8  jz      short loc_14002E6F1
0x14002e6ea  mov     dword ptr [r9], 0Dh
0x14002e6f1  mov     edx, r11d
0x14002e6f4  call    RaMiniportIsFeatureSupported
0x14002e6f9  test    al, al
0x14002e6fb  jz      short loc_14002E704
0x14002e6fd  mov     dword ptr [r9], 0Eh
0x14002e704  mov     edx, 4
0x14002e709  call    RaMiniportIsFeatureSupported
0x14002e70e  test    al, al
0x14002e710  jz      short loc_14002E719
0x14002e712  mov     dword ptr [r9], 0Fh
0x14002e719  mov     edx, 0Bh
0x14002e71e  call    RaMiniportIsFeatureSupported
0x14002e723  test    al, al
0x14002e725  jz      short loc_14002E731
0x14002e727  mov     dword ptr [rbx+120h], 10h
0x14002e731  mov     rax, [rbx+0E8h]
0x14002e738  test    dword ptr [rax+0B8h], 20000h
0x14002e742  jz      short loc_14002E74B
0x14002e744  mov     dword ptr [r9], 11h
0x14002e74b  mov     edx, 0Eh
0x14002e750  call    RaMiniportIsFeatureSupported
0x14002e755  test    al, al
0x14002e757  jz      short loc_14002E760
0x14002e759  mov     dword ptr [r9], 20h ; ' '
0x14002e760  mov     r8, r9
0x14002e763  xor     edx, edx
0x14002e765  call    RaCallMiniportUnitControl
0x14002e76a  test    eax, eax
0x14002e76c  js      short loc_14002E7DF
0x14002e76e  or      dword ptr [rbx+0F8h], 10h
0x14002e775  movzx   eax, byte ptr [rdi+rbx]
0x14002e779  mov     edi, 1
0x14002e77e  test    al, al
0x14002e780  jz      short loc_14002E7E9
0x14002e782  mov     rcx, [rsi+18h]
0x14002e786  xor     eax, eax
0x14002e788  mov     word ptr [rbp+57h+LockHandle+15h], ax
0x14002e78c  mov     byte ptr [rbp+57h+LockHandle+17h], al
0x14002e78f  lea     rax, [rsi+60h]
0x14002e793  mov     [rbp+57h+LockHandle.LockQueue.Lock], rax
0x14002e797  mov     dword ptr [rbp+57h+LockHandle.LockQueue.Next], edi
0x14002e79a  mov     dword ptr [rbp+57h+LockHandle.LockQueue.Next+4], 18h
0x14002e7a1  mov     dword ptr [rbp+57h+LockHandle.OldIrql], 0
0x14002e7a8  mov     byte ptr [rbp+57h+LockHandle+14h], dil
0x14002e7ac  mov     rax, [rcx+250h]
0x14002e7b3  mov     rax, [rax+0C8h]
0x14002e7ba  test    rax, rax
0x14002e7bd  jz      short loc_14002E7E9
0x14002e7bf  mov     rcx, [rcx+258h]
0x14002e7c6  lea     r8, [rbp+57h+LockHandle]
0x14002e7ca  add     rcx, 10h
0x14002e7ce  mov     edx, 6
0x14002e7d3  call    _guard_dispatch_icall
0x14002e7d8  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x14002e7dd  jmp     short loc_14002E7E9
0x14002e7df  mov     edi, 1
0x14002e7e4  jmp     short loc_14002E7E9
0x14002e7e6  mov     edi, r11d
0x14002e7e9  mov     rcx, [rsi+750h]
0x14002e7f0  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14002e7f4  xorps   xmm0, xmm0
0x14002e7f7  xor     eax, eax
0x14002e7f9  add     rcx, 60h ; '`'; SpinLock
0x14002e7fd  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14002e801  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14002e805  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002e80c  nop     dword ptr [rax+rax+00h]
0x14002e811  mov     rax, [rsi+750h]
0x14002e818  or      dword ptr [rax+20h], 2
0x14002e81c  mov     eax, [rsi+1F8h]
0x14002e822  bt      eax, 0Fh
0x14002e826  jnb     loc_14002E923
0x14002e82c  mov     rcx, [rsi+748h]; RunRefCacheAware
0x14002e833  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002e83a  nop     dword ptr [rax+rax+00h]
0x14002e83f  test    al, al
0x14002e841  jz      loc_14002E923
0x14002e847  nop     word ptr [rax+rax+00000000h]
0x14002e850  mov     rax, [rsi+750h]
0x14002e857  add     rax, 50h ; 'P'
0x14002e85b  cmp     [rax], rax
0x14002e85e  jz      loc_14002E90B
0x14002e864  mov     rdi, [rax+8]
0x14002e868  cmp     [rdi], rax
0x14002e86b  jnz     loc_14002E904
0x14002e871  mov     rcx, [rdi+8]
0x14002e875  cmp     [rcx], rdi
0x14002e878  jnz     loc_14002E904
0x14002e87e  mov     [rax+8], rcx
0x14002e882  mov     [rcx], rax
0x14002e885  mov     r14, [rdi+10h]
0x14002e889  mov     rax, [r14+0B8h]
0x14002e890  mov     rax, [rax+8]
0x14002e894  movzx   ecx, byte ptr [rax+2]
0x14002e898  cmp     cl, 28h ; '('
0x14002e89b  jnz     short loc_14002E8A2
0x14002e89d  mov     eax, [rax+14h]
0x14002e8a0  jmp     short loc_14002E8A4
0x14002e8a2  mov     eax, ecx
0x14002e8a4  sub     eax, 10h
0x14002e8a7  jz      short loc_14002E8B8
0x14002e8a9  sub     eax, 2
0x14002e8ac  jz      short loc_14002E8B8
0x14002e8ae  sub     eax, 1
0x14002e8b1  jz      short loc_14002E8B8
0x14002e8b3  cmp     eax, 0Dh
0x14002e8b6  jnz     short loc_14002E8EB
0x14002e8b8  mov     cl, 2; NewIrql
0x14002e8ba  call    cs:__imp_KfRaiseIrql
0x14002e8c1  nop     dword ptr [rax+rax+00h]
0x14002e8c6  mov     rcx, [rsi+8]
0x14002e8ca  lea     r8, [rsi+720h]
0x14002e8d1  mov     rdx, r14
0x14002e8d4  movzx   ebx, al
0x14002e8d7  call    RaUnitStartResetIo
0x14002e8dc  movzx   ecx, bl; NewIrql
0x14002e8df  call    cs:__imp_KeLowerIrql
0x14002e8e6  nop     dword ptr [rax+rax+00h]
0x14002e8eb  mov     edx, 4F506152h; Tag
0x14002e8f0  mov     rcx, rdi; P
0x14002e8f3  call    cs:__imp_ExFreePoolWithTag
0x14002e8fa  nop     dword ptr [rax+rax+00h]
0x14002e8ff  jmp     loc_14002E850
0x14002e904  mov     ecx, 3
0x14002e909  int     29h; Win8: RtlFailFast(ecx)
0x14002e90b  mov     rcx, [rsi+748h]; RunRefCacheAware
0x14002e912  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002e919  nop     dword ptr [rax+rax+00h]
0x14002e91e  mov     edi, 1
0x14002e923  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14002e927  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002e92e  nop     dword ptr [rax+rax+00h]
0x14002e933  movzx   eax, byte ptr [rsi+2F7h]
0x14002e93a  test    al, al
  ... truncated ...
```
