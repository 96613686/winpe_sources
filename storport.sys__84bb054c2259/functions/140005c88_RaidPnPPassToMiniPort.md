# RaidPnPPassToMiniPort

- ea: `0x140005c88`
- end: `0x140006846`
- name: `RaidPnPPassToMiniPort`
- size: `3006`
- prototype: ``
- caller_count: `6`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x140004a10`
- `0x140075420`
- `0x14018e72c`
- `0x14018ed38`
- `0x1401a8f14`
- `0x1401bcb90`

## callees

- `0x1400016cc`
- `0x140003df0`
- `0x140005984`
- `0x140005c50`
- `0x140005c88`
- `0x14000684c`
- `0x140008210`
- `0x140008348`
- `0x140008eb0`
- `0x140031f60`
- `0x140040110`
- `0x14004a0a8`
- `0x140071618`
- `0x140085f44`
- `0x140093c40`
- `0x140093cf4`
- `0x140093e84`
- `0x1400b8cd0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14000618b`
- `ntoskrnl!PoFxIdleComponent` at `0x140006669`
- `ntoskrnl!PoFxIdleComponent` at `0x14000618b`
- `ntoskrnl!PoFxIdleComponent` at `0x140006669`
- `ntoskrnl!KeLowerIrql` at `0x14000652a`
- `ntoskrnl!KeLowerIrql` at `0x14000652a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006284`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006284`
- `ntoskrnl!KeInitializeEvent` at `0x140005fd2`
- `ntoskrnl!KeInitializeEvent` at `0x140005fd2`
- `ntoskrnl!KfRaiseIrql` at `0x1400064c4`
- `ntoskrnl!KfRaiseIrql` at `0x1400064c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006147`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006147`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000609b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000667c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000609b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000667c`
- `ntoskrnl!IoFreeMdl` at `0x1400062a5`
- `ntoskrnl!IoFreeMdl` at `0x1400065b9`
- `ntoskrnl!IoFreeMdl` at `0x1400062a5`
- `ntoskrnl!IoFreeMdl` at `0x1400065b9`
- `ntoskrnl!ExAllocatePool2` at `0x140005d8f`
- `ntoskrnl!ExAllocatePool2` at `0x1400062c5`
- `ntoskrnl!ExAllocatePool2` at `0x140005d8f`
- `ntoskrnl!ExAllocatePool2` at `0x1400062c5`
- `ntoskrnl!PoFxActivateComponent` at `0x140006085`
- `ntoskrnl!PoFxActivateComponent` at `0x1400060fe`
- `ntoskrnl!PoFxActivateComponent` at `0x140006085`
- `ntoskrnl!PoFxActivateComponent` at `0x1400060fe`
- `ntoskrnl!MmUnlockPages` at `0x140006292`
- `ntoskrnl!MmUnlockPages` at `0x14000680c`
- `ntoskrnl!MmUnlockPages` at `0x140006292`
- `ntoskrnl!MmUnlockPages` at `0x14000680c`
- `ntoskrnl!MmFreeContiguousMemory` at `0x140006228`
- `ntoskrnl!MmFreeContiguousMemory` at `0x140006228`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400063bc`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400063bc`

## pseudocode

```c
__int64 __fastcall RaidPnPPassToMiniPort(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  int *v5; // r14
  __int64 v6; // r11
  int *v8; // r15
  int v9; // ecx
  __int64 v10; // r12
  __int64 v11; // rax
  unsigned int *v12; // rsi
  __int64 ContiguousIoResources; // r8
  unsigned int v14; // ebp
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 Pool2; // rax
  __int64 v20; // rdi
  unsigned int *v21; // rbp
  _BYTE *v22; // rbx
  char *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  char v27; // cl
  __int64 v28; // rbp
  char v29; // bl
  volatile signed __int32 *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  unsigned int v33; // ebp
  __int64 v34; // r8
  int v35; // eax
  __int64 v36; // r9
  int v37; // ebp
  _QWORD *v38; // rcx
  __int64 v39; // rcx
  struct _MDL *v40; // rcx
  __int64 v42; // rax
  PDEVICE_OBJECT v43; // rcx
  int v44; // eax
  __int64 v45; // rdx
  int v46; // r8d
  __int64 v47; // r9
  char v48; // al
  __int64 v49; // rbx
  __int64 v50; // rax
  int v51; // ebx
  bool v52; // bl
  __int64 v53; // r8
  KIRQL v54; // r14
  __int64 v55; // rcx
  __int64 v56; // rdx
  void (__fastcall *v57)(__int64, _QWORD, __int64); // rax
  __int64 v58; // rdx
  __int64 v59; // r12
  unsigned int *v60; // rax
  int v61; // r8d
  __int64 v62; // rcx
  __int64 *v63; // r12
  int v64; // r8d
  char v65; // r13
  __int128 *v66; // r10
  const int *v67; // rdx
  char v68; // r9
  const int *v69; // r11
  const int *v70; // rbx
  int v71; // r14d
  __int64 *v72; // rcx
  int Timeout; // [rsp+20h] [rbp-138h]
  char *i; // [rsp+B8h] [rbp-A0h]
  _QWORD *BaseAddress; // [rsp+C0h] [rbp-98h]
  unsigned int *v77; // [rsp+C8h] [rbp-90h]
  union _LARGE_INTEGER Interval; // [rsp+D0h] [rbp-88h] BYREF
  __int128 v79; // [rsp+D8h] [rbp-80h] BYREF
  __int128 v80; // [rsp+E8h] [rbp-70h] BYREF
  __int128 v81; // [rsp+F8h] [rbp-60h] BYREF

  v5 = *(int **)(a1 + 64);
  v6 = 0;
  Interval.QuadPart = 0;
  *(_QWORD *)&v80 = a4;
  if ( *v5 == 1431193940 )
    v8 = (int *)*((_QWORD *)v5 + 3);
  else
    v8 = v5;
  if ( *v5 != 1431193940 )
    v5 = 0;
  if ( !*((_QWORD *)v8 + 74) || !*((_QWORD *)v8 + 75) )
    return 0;
  Interval.QuadPart = -1000;
  v9 = *v8;
  v10 = 81;
  v77 = 0;
  v11 = 81;
  BaseAddress = 0;
  v12 = 0;
  if ( *v8 != 1314275652 )
    v11 = 127;
  ContiguousIoResources = 0;
  v14 = 0;
  v15 = (v8[v11] + 7) & 0xFFFFFFF8;
  if ( v9 == 1314275652 )
  {
    v16 = (__int64)v8 + 282;
  }
  else
  {
    v16 = (__int64)v8 + 466;
    if ( v9 != 1094997074 )
      v16 = 98;
  }
  for ( i = (char *)v16; ; v16 = (__int64)i )
  {
    v17 = 88;
    if ( v12 )
      goto LABEL_17;
    v18 = *((_QWORD *)v8 + 1);
    if ( *(_BYTE *)v16 != 1 )
    {
      Pool2 = ExAllocatePool2(64, 88, 1918067026);
      v6 = 0;
      v12 = (unsigned int *)Pool2;
      if ( Pool2 || !v18 )
        goto LABEL_16;
      v61 = 88;
LABEL_154:
      RaidLogAllocationFailure(v18, 64, v61, 1918067026, 0x80000000);
      v6 = 0;
      goto LABEL_16;
    }
    v42 = ExAllocatePool2(64, 168, 1918067026);
    v6 = 0;
    v12 = (unsigned int *)v42;
    if ( !v42 )
    {
      if ( !v18 )
        goto LABEL_16;
      v61 = 168;
      goto LABEL_154;
    }
    *(_WORD *)v42 = 8;
    *(_DWORD *)(v42 + 12) = 1;
    *(_DWORD *)(v42 + 56) = 1;
    *(_BYTE *)(v42 + 2) = 40;
    *(_DWORD *)(v42 + 8) = 1397899864;
    *(_DWORD *)(v42 + 16) = 168;
    *(_DWORD *)(v42 + 20) = 37;
    *(_WORD *)(v42 + 36) = 2;
    *(_DWORD *)(v42 + 52) = 128;
    *(_WORD *)(v42 + 128) = 1;
    *(_DWORD *)(v42 + 132) = 4;
    *(_DWORD *)(v42 + 120) = 144;
LABEL_16:
    ContiguousIoResources = (__int64)BaseAddress;
LABEL_17:
    if ( !ContiguousIoResources )
    {
      ContiguousIoResources = StorAllocateContiguousIoResources(v15 + 1200, v17, v8);
      BaseAddress = (_QWORD *)ContiguousIoResources;
      v6 = 0;
    }
    if ( v12 && ContiguousIoResources )
      break;
    if ( v14 >= 3 )
    {
      v20 = 0;
      v33 = -1073741801;
      goto LABEL_65;
    }
    ++v14;
    KeDelayExecutionThread(0, 0, &Interval);
    ContiguousIoResources = (__int64)BaseAddress;
    v6 = 0;
  }
  v20 = ContiguousIoResources + 48;
  *(_BYTE *)(ContiguousIoResources + 64) &= 0x1Cu;
  *(_BYTE *)(ContiguousIoResources + 65) &= 0x70u;
  *(_WORD *)(ContiguousIoResources + 68) = -1;
  *(_WORD *)(ContiguousIoResources + 828) = -1;
  *(_DWORD *)(ContiguousIoResources + 48) = 523124044;
  *(_QWORD *)(ContiguousIoResources + 56) = 0;
  *(_BYTE *)(ContiguousIoResources + 70) = -1;
  *(_DWORD *)(ContiguousIoResources + 72) = 0;
  *(_QWORD *)(ContiguousIoResources + 152) = 0;
  *(_QWORD *)(ContiguousIoResources + 160) = 0;
  *(_QWORD *)(ContiguousIoResources + 184) = 0;
  *(_QWORD *)(ContiguousIoResources + 200) = 0;
  *(_QWORD *)(ContiguousIoResources + 192) = 0;
  *(_QWORD *)(ContiguousIoResources + 240) = 0;
  *(_QWORD *)(ContiguousIoResources + 208) = 0;
  *(_QWORD *)(ContiguousIoResources + 264) = 0;
  *(_QWORD *)(ContiguousIoResources + 272) = 0;
  *(_QWORD *)(ContiguousIoResources + 168) = 0;
  *(_QWORD *)(ContiguousIoResources + 744) = 0;
  *(_QWORD *)(ContiguousIoResources + 752) = 0;
  *(_QWORD *)(ContiguousIoResources + 760) = 0;
  *(_QWORD *)(ContiguousIoResources + 768) = 0;
  *(_QWORD *)(ContiguousIoResources + 792) = 0;
  *(_QWORD *)(ContiguousIoResources + 808) = 0;
  *(_QWORD *)(ContiguousIoResources + 816) = 0;
  *(_DWORD *)(ContiguousIoResources + 824) = 0;
  *(_QWORD *)(ContiguousIoResources + 832) = 0;
  *(_DWORD *)(ContiguousIoResources + 848) = -1;
  *(_DWORD *)(ContiguousIoResources + 856) = 0;
  *(_DWORD *)(ContiguousIoResources + 864) = 0;
  *(_QWORD *)(ContiguousIoResources + 872) = 0;
  *(_OWORD *)(ContiguousIoResources + 880) = 0;
  *(_QWORD *)(ContiguousIoResources + 896) = 0;
  *(_QWORD *)(ContiguousIoResources + 904) = 0;
  *(_QWORD *)(ContiguousIoResources + 912) = 0;
  *(_QWORD *)(ContiguousIoResources + 920) = 0;
  *(_DWORD *)(ContiguousIoResources + 928) = -1;
  *(_QWORD *)(ContiguousIoResources + 216) = v12;
  *(_QWORD *)(ContiguousIoResources + 224) = *((_QWORD *)v12 + 6);
  if ( *i == 1 )
  {
    v49 = v12[13];
    v21 = v12;
    *((_QWORD *)v12 + 8) = v80;
    v22 = (char *)v12 + v49;
    v12[15] = a5;
    v12[5] = 37;
    v23 = (char *)v12 + v12[30];
    *((_QWORD *)v12 + 12) = v20;
    v12[6] = 256;
    v12[10] = 10;
    v77 = v12;
    *(_DWORD *)v23 = 98;
    *((_DWORD *)v23 + 1) = 16;
    *((_DWORD *)v23 + 3) = a2;
    v23[8] = 0;
    v24 = *((_QWORD *)v12 + 8);
  }
  else
  {
    v21 = 0;
    v22 = 0;
    *((_QWORD *)v12 + 3) = v80;
    v23 = 0;
    v12[4] = a5;
    v12[2] = a2;
    v24 = v80;
    *((_QWORD *)v12 + 6) = v20;
    *((_BYTE *)v12 + 2) = 37;
    *(_WORD *)v12 = 88;
    *((_BYTE *)v12 + 4) = 0;
    v12[3] = 256;
    v12[5] = 10;
  }
  *(_QWORD *)(ContiguousIoResources + 232) = v24;
  v25 = ContiguousIoResources + 1200;
  v26 = *v8;
  if ( *((_BYTE *)v12 + 2) == 40 )
  {
    if ( v26 != 1314275652 )
      v10 = 127;
    if ( ((v8[v10] + 7) & 0xFFFFFFF8) != 0 )
      *((_QWORD *)v12 + 13) = v25;
  }
  else
  {
    if ( v26 != 1314275652 )
      v10 = 127;
    if ( ((v8[v10] + 7) & 0xFFFFFFF8) != 0 )
      *((_QWORD *)v12 + 7) = v25;
  }
  v27 = *i;
  if ( **(_DWORD **)(a1 + 64) == 1431193940 )
  {
    v48 = *((_BYTE *)v5 + 104);
    if ( v27 == 1 )
    {
      v22[8] = v48;
      v22[9] = *((_BYTE *)v5 + 105);
      v22[10] = *((_BYTE *)v5 + 106);
    }
    else
    {
      *((_BYTE *)v12 + 5) = v48;
      *((_BYTE *)v12 + 6) = *((_BYTE *)v5 + 105);
      *((_BYTE *)v12 + 7) = *((_BYTE *)v5 + 106);
    }
  }
  else if ( v27 == 1 )
  {
    *((_DWORD *)v23 + 4) = 1;
    *((_WORD *)v22 + 4) = 0;
    v22[10] = 0;
  }
  else
  {
    v12[16] = 1;
    *(_WORD *)((char *)v12 + 5) = 0;
    *((_BYTE *)v12 + 7) = 0;
  }
  KeInitializeEvent((PRKEVENT)(ContiguousIoResources + 712), NotificationEvent, 0);
  *(_QWORD *)(v20 + 656) = RaidXrbSignalCompletion;
  if ( *i == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          55,
          WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
          v20,
          v21,
          *((_QWORD *)v21 + 13));
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v44 = (unsigned __int8)v22[10];
        v45 = 56;
        v46 = (unsigned __int8)v22[9];
        v47 = (unsigned __int8)v22[8];
LABEL_155:
        WPP_SF_DDD(v43->AttachedDevice, v45, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids, v47, v46, v44);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        57,
        WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
        v20,
        v12,
        *((_QWORD *)v12 + 7));
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v44 = *((unsigned __int8 *)v12 + 7);
      v45 = 58;
      v46 = *((unsigned __int8 *)v12 + 6);
      v47 = *((unsigned __int8 *)v12 + 5);
      goto LABEL_155;
    }
  }
  if ( v5 )
  {
    v28 = *((_QWORD *)v5 + 3);
    if ( *(_QWORD *)(v28 + 5024) )
    {
      RaidAdapterPoFxActivateComponent(*((_QWORD *)v5 + 3), 0, 1);
      v29 = 2;
    }
    else
    {
      v29 = 0;
    }
    if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(v5) )
    {
      if ( (*(_BYTE *)(v28 + 108) & 1) != 0 )
      {
        _InterlockedAdd64((volatile signed __int64 *)v5 + 271, 1u);
        if ( (*(_BYTE *)(v28 + 108) & 2) != 0 )
          _InterlockedAdd64((volatile signed __int64 *)v5 + 272, 1u);
      }
      v30 = (volatile signed __int32 *)*((_QWORD *)v5 + 234);
      if ( (v30[37] & 1) != 0 )
      {
        _InterlockedAdd(v30 + 36, 1u);
        v30 = (volatile signed __int32 *)*((_QWORD *)v5 + 234);
      }
      v31 = 5;
      v32 = *(_QWORD *)v30;
      if ( !v5[259] )
        v31 = 1;
      PoFxActivateComponent(v32, 0, v31);
      v29 |= 1u;
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v5 + 233));
    }
  }
  else
  {
    v29 = 0;
    if ( *((_QWORD *)v8 + 628) )
    {
      if ( (v8[27] & 1) != 0 )
      {
        _InterlockedAdd64((volatile signed __int64 *)v8 + 668, 1u);
        if ( (v8[27] & 2) != 0 )
          _InterlockedAdd64((volatile signed __int64 *)v8 + 669, 1u);
      }
      v34 = 5;
      if ( !v8[23] )
        v34 = 1;
      PoFxActivateComponent(**((_QWORD **)v8 + 628), 0, v34);
    }
  }
  if ( *((_BYTE *)v8 + 4434) )
    v35 = RaidAdapterRaiseIrqlAndExecuteXrb(v8, v20);
  else
    v35 = RaidAdapterPostScatterGatherExecute(v8, v20);
  v37 = v35;
  if ( v35 >= 0 )
    KeWaitForSingleObject((PVOID)(v20 + 664), Executive, 0, 0, 0);
  if ( v37 == 258 )
  {
    _InterlockedIncrement(v8 + 1562);
    v33 = -1073741643;
  }
  else
  {
    v33 = 0;
  }
  if ( (*(_BYTE *)(v20 + 17) & 1) != 0 )
  {
    RaidAdapterPoFxIdleComponentFromMiniport(v8, *(unsigned int *)(v20 + 748), ContiguousIoResources);
    *(_BYTE *)(v20 + 17) &= ~1u;
  }
  v6 = 0;
  if ( v5 )
  {
    v59 = *((_QWORD *)v5 + 3);
    if ( (v29 & 1) != 0 && (unsigned __int8)RaidUnitCheckAndAcquirePoFx(v5) )
    {
      PoFxIdleComponent(**((_QWORD **)v5 + 234), 0, 0);
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v5 + 233));
    }
    if ( (unsigned __int8)v29 >= 2u && *(_QWORD *)(v59 + 5024) )
      RaidAdapterPoFxIdleComponent(v59, 0, 0, v36);
    if ( (*(_BYTE *)(v20 + 17) & 2) != 0 )
    {
      RaidUnitPoFxIdleComponentFromMiniport(v5, *(unsigned int *)(v20 + 748), ContiguousIoResources);
      *(_BYTE *)(v20 + 17) &= ~2u;
    }
LABEL_62:
    v6 = 0;
  }
  else
  {
    v38 = (_QWORD *)*((_QWORD *)v8 + 628);
    if ( v38 )
    {
      PoFxIdleComponent(*v38, 0, 0);
      goto LABEL_62;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids, v8, 0, a2);
    v6 = 0;
  }
LABEL_65:
  if ( StorEtwLoggingEnabled && (v33 == -1073741643 || v33 == -1073741801) )
  {
    v62 = *((_QWORD *)v8 + 2);
    v63 = (__int64 *)*((_QWORD *)v8 + 643);
    v79 = 0;
    v81 = *(_OWORD *)(v8 + 1282);
    v80 = 0;
    RaidDriverGetName(v62, &v79, ContiguousIoResources);
    if ( byte_140177436 < (char)v6 )
    {
      if ( v5 )
      {
        v65 = *((_BYTE *)v5 + 104);
        v66 = (__int128 *)(v5 + 526);
        LOBYTE(v64) = *((_BYTE *)v5 + 105);
        v67 = v5 + 42;
        v68 = *((_BYTE *)v5 + 106);
        v69 = (int *)((char *)v5 + 177);
        v70 = (int *)((char *)v5 + 242);
        v71 = v5[126];
      }
      else
      {
        v67 = &dword_140157D94;
        v65 = -1;
        v70 = &dword_140157D94;
        v66 = &v80;
        v69 = &dword_140157D94;
        LOBYTE(v64) = -1;
        v68 = -1;
        LOBYTE(v71) = 0;
      }
      v72 = &qword_140155FE0;
      if ( v63 )
        v72 = v63;
      McTemplateK0qjzzuuujsssqpquqqq_EtwWriteTransfer(
        (_DWORD)v72,
        (_DWORD)v67,
        v64,
        v8[14],
        (__int64)&v81,
        *((__int64 *)&v79 + 1),
        (__int64)v72,
        v65,
        v64,
        v68,
        (__int64)v66,
        (__int64)v67,
        (__int64)v69,
        (__int64)v70,
        v71,
        (char)v12,
        a2);
      v6 = 0;
    }
  }
  if ( BaseAddress )
  {
    if ( v20 )
    {
      *(_BYTE *)(v20 + 16) &= 0xE3u;
      if ( *(_QWORD *)(v20 + 112) != v6 )
      {
        v50 = *(_QWORD *)(v20 + 168);
        if ( *(_BYTE *)(v50 + 2) == 40 )
          v51 = *(_DWORD *)(v50 + 24) >> 6;
        else
          LOBYTE(v51) = *(_BYTE *)(v50 + 12) >> 6;
        v52 = (v51 & 1) == 0;
        if ( RaidVerifierEnabled != (_DWORD)v6 )
          RaidFreeRemappedScatterGatherListMdl(v20);
        v54 = KfRaiseIrql(2u);
        if ( *(_QWORD *)(v20 + 216) != -880 )
        {
          v55 = *(_QWORD *)(*(_QWORD *)(v20 + 216) + 880LL);
          if ( v55 )
          {
            v56 = *(_QWORD *)(v55 + 8);
            if ( v56 )
            {
              v57 = *(void (__fastcall **)(__int64, _QWORD, __int64))(v56 + 96);
              if ( v57 )
              {
                LOBYTE(v53) = v52;
                v57(v55, *(_QWORD *)(v20 + 112), v53);
              }
            }
          }
        }
        v58 = *(_QWORD *)(v20 + 152);
        *(_QWORD *)(v20 + 112) = 0;
        *(_QWORD *)(v20 + 144) = 0;
        if ( v58 )
        {
          RaidDmaPutScatterGatherList(*(_QWORD *)(v20 + 216) + 880LL, v58, 0);
          *(_QWORD *)(v20 + 152) = 0;
        }
        KeLowerIrql(v54);
      }
      v39 = *(_QWORD *)(v20 + 104);
      if ( v39 && (*(_BYTE *)(v20 + 16) & 1) != 0 )
      {
        if ( (*(_BYTE *)(v39 + 10) & 2) != 0 )
          MmUnlockPages((PMDL)v39);
        IoFreeMdl(*(PMDL *)(v20 + 104));
        *(_BYTE *)(v20 + 16) &= ~1u;
        *(_QWORD *)(v20 + 104) = 0;
      }
      v40 = *(struct _MDL **)(v20 + 136);
      if ( v40 )
      {
        MmUnlockPages(v40);
        IoFreeMdl(*(PMDL *)(v20 + 136));
        *(_QWORD *)(v20 + 136) = 0;
      }
    }
    if ( (unsigned __int8)IsDmarEnabled(v8) )
    {
      LOBYTE(Timeout) = 1;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *, int))(*(_QWORD *)(*((_QWORD *)v8 + 110) + 8LL) + 24LL))(
        *((_QWORD *)v8 + 110),
        *((unsigned int *)BaseAddress + 4),
        BaseAddress[3],
        BaseAddress,
        Timeout);
    }
    else
    {
      MmFreeContiguousMemory(BaseAddress);
    }
    v6 = 0;
  }
  if ( v12 )
  {
    if ( *i == 1 )
    {
      v60 = v77;
      if ( !v77 )
        v60 = v12;
      *((_QWORD *)v60 + 10) = v6;
      *((_QWORD *)v60 + 13) = v6;
    }
    else
    {
      *((_QWORD *)v12 + 6) = v6;
      *((_QWORD *)v12 + 7) = v6;
    }
    ExFreePoolWithTag(v12, 0x72536152u);
  }
  return v33;
}

```

## disassembly

```asm
0x140005c88  push    rbx
0x140005c8a  push    rbp
0x140005c8b  push    rsi
0x140005c8c  push    rdi
0x140005c8d  push    r12
0x140005c8f  push    r13
0x140005c91  push    r14
0x140005c93  push    r15
0x140005c95  sub     rsp, 118h
0x140005c9c  mov     rax, cs:__security_cookie
0x140005ca3  xor     rax, rsp
0x140005ca6  mov     [rsp+158h+var_50], rax
0x140005cae  mov     r14, [rcx+40h]
0x140005cb2  xor     r11d, r11d
0x140005cb5  mov     r13, rcx
0x140005cb8  mov     qword ptr [rsp+158h+Interval], r11
0x140005cc0  mov     ecx, 554E4954h
0x140005cc5  mov     qword ptr [rsp+158h+var_70], r9
0x140005ccd  mov     [rsp+158h+var_A8], edx
0x140005cd4  cmp     [r14], ecx
0x140005cd7  jz      loc_1400060BF
0x140005cdd  mov     r15, r14
0x140005ce0  cmovnz  r14, r11
0x140005ce4  cmp     [r15+250h], r11
0x140005ceb  jz      loc_14000653B
0x140005cf1  cmp     [r15+258h], r11
0x140005cf8  jz      loc_14000653B
0x140005cfe  mov     qword ptr [rsp+158h+Interval], 0FFFFFFFFFFFFFC18h
0x140005d0a  mov     edx, 4E564144h
0x140005d0f  mov     ecx, [r15]
0x140005d12  mov     r12d, 144h
0x140005d18  cmp     ecx, edx
0x140005d1a  mov     [rsp+158h+var_90], r11
0x140005d22  mov     eax, r12d
0x140005d25  mov     [rsp+158h+BaseAddress], r11
0x140005d2d  mov     r9d, 1FCh
0x140005d33  mov     rsi, r11
0x140005d36  cmovnz  eax, r9d
0x140005d3a  mov     r8, r11
0x140005d3d  mov     ebp, r11d
0x140005d40  mov     ebx, [rax+r15]
0x140005d44  add     ebx, 7
0x140005d47  and     ebx, 0FFFFFFF8h
0x140005d4a  cmp     ecx, edx
0x140005d4c  jz      loc_1400063E0
0x140005d52  lea     rax, [r15+1D2h]
0x140005d59  cmp     ecx, 41445452h
0x140005d5f  jnz     loc_1400066F0
0x140005d65  mov     [rsp+158h+var_A0], rax
0x140005d6d  mov     edx, 58h ; 'X'
0x140005d72  lea     ecx, [rdx-57h]
0x140005d75  test    rsi, rsi
0x140005d78  jnz     short loc_140005DB2
0x140005d7a  cmp     [rax], cl
0x140005d7c  mov     r8d, 72536152h
0x140005d82  mov     rdi, [r15+8]
0x140005d86  lea     ecx, [rdx-18h]
0x140005d89  jz      loc_1400062C0
0x140005d8f  call    cs:__imp_ExAllocatePool2
0x140005d96  nop     dword ptr [rax+rax+00h]
0x140005d9b  xor     r11d, r11d
0x140005d9e  mov     rsi, rax
0x140005da1  test    rax, rax
0x140005da4  jz      loc_14000670E
0x140005daa  mov     r8, [rsp+158h+BaseAddress]
0x140005db2  test    r8, r8
0x140005db5  jnz     short loc_140005DD3
0x140005db7  mov     r8, r15
0x140005dba  lea     ecx, [rbx+4B0h]
0x140005dc0  call    StorAllocateContiguousIoResources
0x140005dc5  mov     r8, rax
0x140005dc8  mov     [rsp+158h+BaseAddress], rax
0x140005dd0  xor     r11d, r11d
0x140005dd3  test    rsi, rsi
0x140005dd6  jz      loc_1400060A9
0x140005ddc  test    r8, r8
0x140005ddf  jz      loc_1400060A9
0x140005de5  lea     rdi, [r8+30h]
0x140005de9  mov     r9, [rsp+158h+var_A0]
0x140005df1  and     byte ptr [rdi+10h], 1Ch
0x140005df5  mov     eax, 0FFFFh
0x140005dfa  and     byte ptr [rdi+11h], 70h
0x140005dfe  or      ecx, 0FFFFFFFFh
0x140005e01  mov     [rdi+14h], ax
0x140005e05  xorps   xmm0, xmm0
0x140005e08  mov     [rdi+30Ch], ax
0x140005e0f  mov     r10d, 1
0x140005e15  mov     dword ptr [rdi], 1F2E3D4Ch
0x140005e1b  mov     [rdi+8], r11
0x140005e1f  mov     byte ptr [rdi+16h], 0FFh
0x140005e23  mov     [rdi+18h], r11d
0x140005e27  mov     [rdi+68h], r11
0x140005e2b  mov     [rdi+70h], r11
0x140005e2f  mov     [rdi+88h], r11
0x140005e36  mov     [rdi+98h], r11
0x140005e3d  mov     [rdi+90h], r11
0x140005e44  mov     [rdi+0C0h], r11
0x140005e4b  mov     [rdi+0A0h], r11
0x140005e52  mov     [rdi+0D8h], r11
0x140005e59  mov     [rdi+0E0h], r11
0x140005e60  mov     [rdi+78h], r11
0x140005e64  mov     [rdi+2B8h], r11
0x140005e6b  mov     [rdi+2C0h], r11
0x140005e72  mov     [rdi+2C8h], r11
0x140005e79  mov     [rdi+2D0h], r11
0x140005e80  mov     qword ptr [rdi+2E8h], 0
0x140005e8b  mov     [rdi+2F8h], r11
0x140005e92  mov     [rdi+300h], r11
0x140005e99  mov     [rdi+308h], r11d
0x140005ea0  mov     [rdi+310h], r11
0x140005ea7  mov     [rdi+320h], ecx
0x140005ead  mov     dword ptr [rdi+328h], 0
0x140005eb7  mov     [rdi+330h], r11d
0x140005ebe  mov     [rdi+338h], r11
0x140005ec5  movups  xmmword ptr [rdi+340h], xmm0
0x140005ecc  mov     [rdi+350h], r11
0x140005ed3  mov     [rdi+358h], r11
0x140005eda  mov     [rdi+360h], r11
0x140005ee1  mov     [rdi+368h], r11
0x140005ee8  mov     [rdi+370h], ecx
0x140005eee  mov     [rdi+0A8h], rsi
0x140005ef5  mov     rax, [rsi+30h]
0x140005ef9  mov     [rdi+0B0h], rax
0x140005f00  mov     rax, qword ptr [rsp+158h+var_70]
0x140005f08  cmp     [r9], r10b
0x140005f0b  jz      loc_140006437
0x140005f11  mov     rbp, [rsp+158h+var_90]
0x140005f19  mov     rbx, r11
0x140005f1c  mov     [rsi+18h], rax
0x140005f20  mov     rdx, r11
0x140005f23  mov     eax, [rsp+158h+arg_20]
0x140005f2a  mov     [rsi+10h], eax
0x140005f2d  mov     eax, [rsp+158h+var_A8]
0x140005f34  mov     [rsi+8], eax
0x140005f37  mov     rax, qword ptr [rsp+158h+var_70]
0x140005f3f  mov     [rsi+30h], rdi
0x140005f43  mov     byte ptr [rsi+2], 25h ; '%'
0x140005f47  mov     word ptr [rsi], 58h ; 'X'
0x140005f4c  mov     [rsi+4], r11b
0x140005f50  mov     dword ptr [rsi+0Ch], 100h
0x140005f57  mov     dword ptr [rsi+14h], 0Ah
0x140005f5e  mov     [rdi+0B8h], rax
0x140005f65  lea     rcx, [r8+4B0h]
0x140005f6c  cmp     byte ptr [rsi+2], 28h ; '('
0x140005f70  mov     eax, [r15]
0x140005f73  jnz     loc_140006333
0x140005f79  cmp     eax, 4E564144h
0x140005f7e  mov     eax, 1FCh
0x140005f83  cmovnz  r12, rax
0x140005f87  mov     eax, [r12+r15]
0x140005f8b  add     eax, 7
0x140005f8e  test    eax, 0FFFFFFF8h
0x140005f93  jbe     short loc_140005F99
0x140005f95  mov     [rsi+68h], rcx
0x140005f99  mov     rax, [r13+40h]
0x140005f9d  mov     cl, [r9]
0x140005fa0  cmp     dword ptr [rax], 554E4954h
0x140005fa6  jz      loc_140006414
0x140005fac  cmp     cl, r10b
0x140005faf  jz      loc_1400063EC
0x140005fb5  mov     [rsi+40h], r10d
0x140005fb9  mov     word ptr [rsi+5], 0
0x140005fbf  mov     [rsi+7], r11b
0x140005fc3  lea     r12, [rdi+298h]
0x140005fca  xor     r8d, r8d; State
0x140005fcd  mov     rcx, r12; Event
0x140005fd0  xor     edx, edx; Type
0x140005fd2  call    cs:__imp_KeInitializeEvent
0x140005fd9  nop     dword ptr [rax+rax+00h]
0x140005fde  lea     rax, RaidXrbSignalCompletion
0x140005fe5  mov     [rdi+290h], rax
0x140005fec  mov     rax, [rsp+158h+var_A0]
0x140005ff4  cmp     byte ptr [rax], 1
0x140005ff7  jz      loc_140006542
0x140005ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x140006004  lea     r13, WPP_GLOBAL_Control
0x14000600b  cmp     rcx, r13
0x14000600e  jnz     loc_14000635C
0x140006014  test    r14, r14
0x140006017  jz      loc_1400060C8
0x14000601d  mov     rbp, [r14+18h]
0x140006021  cmp     qword ptr [rbp+13A0h], 0
0x140006029  jnz     loc_1400063FF
0x14000602f  xor     bl, bl
0x140006031  mov     rcx, r14
0x140006034  call    RaidUnitCheckAndAcquirePoFx
0x140006039  test    al, al
0x14000603b  jz      loc_140006114
0x140006041  mov     edx, 1
0x140006046  test    [rbp+6Ch], dl
0x140006049  jnz     loc_1400066D1
0x14000604f  mov     rcx, [r14+750h]
0x140006056  mov     eax, [rcx+94h]
0x14000605c  test    dl, al
0x14000605e  jz      short loc_14000606E
0x140006060  lock add [rcx+90h], edx
0x140006067  mov     rcx, [r14+750h]
0x14000606e  cmp     dword ptr [r14+40Ch], 0
0x140006076  mov     r8d, 5
0x14000607c  mov     rcx, [rcx]
0x14000607f  cmovbe  r8d, edx
0x140006083  xor     edx, edx
0x140006085  call    cs:__imp_PoFxActivateComponent
0x14000608c  nop     dword ptr [rax+rax+00h]
0x140006091  mov     rcx, [r14+748h]; RunRefCacheAware
0x140006098  or      bl, 1
0x14000609b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400060a2  nop     dword ptr [rax+rax+00h]
0x1400060a7  jmp     short loc_140006114
0x1400060a9  cmp     ebp, 3
0x1400060ac  jb      loc_1400063AE
0x1400060b2  mov     rdi, r11
0x1400060b5  mov     ebp, 0C0000017h
0x1400060ba  jmp     loc_1400061BB
0x1400060bf  mov     r15, [r14+18h]
0x1400060c3  jmp     loc_140005CE0
0x1400060c8  xor     bl, bl
0x1400060ca  cmp     qword ptr [r15+13A0h], 0
0x1400060d2  jz      short loc_140006114
0x1400060d4  mov     ecx, 1
0x1400060d9  test    [r15+6Ch], cl
0x1400060dd  jnz     loc_1400066B1
0x1400060e3  cmp     dword ptr [r15+5Ch], 0
0x1400060e8  mov     r8d, 5
0x1400060ee  cmovbe  r8d, ecx
0x1400060f2  mov     rcx, [r15+13A0h]
0x1400060f9  xor     edx, edx
0x1400060fb  mov     rcx, [rcx]
0x1400060fe  call    cs:__imp_PoFxActivateComponent
0x140006105  nop     dword ptr [rax+rax+00h]
0x14000610a  mov     rax, [r15+13A0h]
0x140006111  mov     ecx, [rax+14h]
0x140006114  cmp     byte ptr [r15+1152h], 0
0x14000611c  mov     rdx, rdi
0x14000611f  mov     rcx, r15
0x140006122  jz      loc_1400063A4
0x140006128  call    RaidAdapterRaiseIrqlAndExecuteXrb
0x14000612d  mov     ebp, eax
0x14000612f  test    eax, eax
0x140006131  js      short loc_140006153
0x140006133  xor     r9d, r9d; Alertable
0x140006136  mov     [rsp+158h+Timeout], 0; Timeout
0x14000613f  xor     r8d, r8d; WaitMode
0x140006142  xor     edx, edx; WaitReason
0x140006144  mov     rcx, r12; Object
0x140006147  call    cs:__imp_KeWaitForSingleObject
0x14000614e  nop     dword ptr [rax+rax+00h]
0x140006153  cmp     ebp, 102h
0x140006159  jz      loc_1400065D5
0x14000615f  xor     ebp, ebp
0x140006161  test    byte ptr [rdi+11h], 1
0x140006165  jnz     loc_14000678C
0x14000616b  xor     r11d, r11d
0x14000616e  test    r14, r14
0x140006171  jnz     loc_1400065E7
0x140006177  mov     rcx, [r15+13A0h]
0x14000617e  test    rcx, rcx
0x140006181  jz      short loc_1400061A4
0x140006183  mov     rcx, [rcx]
0x140006186  xor     r8d, r8d
0x140006189  xor     edx, edx
0x14000618b  call    cs:__imp_PoFxIdleComponent
0x140006192  nop     dword ptr [rax+rax+00h]
0x140006197  mov     rax, [r15+13A0h]
0x14000619e  mov     ecx, [rax+14h]
0x1400061a1  xor     r11d, r11d
0x1400061a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061ab  cmp     rcx, r13
0x1400061ae  jz      short loc_1400061BB
0x1400061b0  mov     eax, [rcx+2Ch]
0x1400061b3  test    al, 2
0x1400061b5  jnz     loc_1400067A3
0x1400061bb  cmp     cs:StorEtwLoggingEnabled, r11b
0x1400061c2  jz      short loc_1400061DC
0x1400061c4  cmp     ebp, 0C00000B5h
0x1400061ca  jz      loc_14014C230
0x1400061d0  cmp     ebp, 0C0000017h
0x1400061d6  jz      loc_14014C230
0x1400061dc  mov     r13, [rsp+158h+BaseAddress]
0x1400061e4  test    r13, r13
0x1400061e7  jz      short loc_140006237
0x1400061e9  test    rdi, rdi
0x1400061ec  jz      short loc_140006215
0x1400061ee  and     byte ptr [rdi+10h], 0E3h
0x1400061f2  cmp     [rdi+70h], r11
0x1400061f6  jnz     loc_140006499
0x1400061fc  mov     rcx, [rdi+68h]; MemoryDescriptorList
0x140006200  test    rcx, rcx
0x140006203  jnz     loc_1400065A1
0x140006209  mov     rcx, [rdi+88h]; MemoryDescriptorList
0x140006210  test    rcx, rcx
0x140006213  jnz     short loc_140006292
0x140006215  mov     rcx, r15
0x140006218  call    IsDmarEnabled
0x14000621d  test    al, al
0x14000621f  jnz     loc_14000681D
0x140006225  mov     rcx, r13; BaseAddress
0x140006228  call    cs:__imp_MmFreeContiguousMemory
0x14000622f  nop     dword ptr [rax+rax+00h]
0x140006234  xor     r11d, r11d
  ... truncated ...
```
