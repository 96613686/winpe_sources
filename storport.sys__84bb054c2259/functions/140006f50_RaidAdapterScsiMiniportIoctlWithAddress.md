# RaidAdapterScsiMiniportIoctlWithAddress

- ea: `0x140006f50`
- end: `0x140008050`
- name: `RaidAdapterScsiMiniportIoctlWithAddress`
- size: `4352`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x140004db0`
- `0x140034df0`

## callees

- `0x140005984`
- `0x140006f50`
- `0x140008058`
- `0x140008210`
- `0x140008258`
- `0x140008eb0`
- `0x14000befc`
- `0x140013d10`
- `0x1400172d0`
- `0x140025510`
- `0x1400255b4`
- `0x1400280b0`
- `0x14002be60`
- `0x140031f60`
- `0x140040110`
- `0x14004a890`
- `0x14006d1c0`
- `0x14006d298`
- `0x140071618`
- `0x1400848c4`
- `0x140089d94`
- `0x1400b8cd0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x1400075cd`
- `ntoskrnl!PoFxIdleComponent` at `0x1400075cd`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400078b3`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400078b3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140007716`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140007716`
- `ntoskrnl!KeFlushIoBuffers` at `0x140007f12`
- `ntoskrnl!KeFlushIoBuffers` at `0x140007f29`
- `ntoskrnl!KeFlushIoBuffers` at `0x140007f12`
- `ntoskrnl!KeFlushIoBuffers` at `0x140007f29`
- `ntoskrnl!KeSetEvent` at `0x140007d2b`
- `ntoskrnl!KeSetEvent` at `0x140007d2b`
- `ntoskrnl!KeLowerIrql` at `0x140007565`
- `ntoskrnl!KeLowerIrql` at `0x1400079e3`
- `ntoskrnl!KeLowerIrql` at `0x140007565`
- `ntoskrnl!KeLowerIrql` at `0x1400079e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076e7`
- `ntoskrnl!KeInitializeEvent` at `0x140007436`
- `ntoskrnl!KeInitializeEvent` at `0x140007436`
- `ntoskrnl!KfRaiseIrql` at `0x1400074a5`
- `ntoskrnl!KfRaiseIrql` at `0x140007976`
- `ntoskrnl!KfRaiseIrql` at `0x1400074a5`
- `ntoskrnl!KfRaiseIrql` at `0x140007976`
- `ntoskrnl!IofCompleteRequest` at `0x140007746`
- `ntoskrnl!IofCompleteRequest` at `0x140007746`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000758d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000758d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400072dd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400072dd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140007270`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140007270`
- `ntoskrnl!IoAllocateMdl` at `0x140007250`
- `ntoskrnl!IoAllocateMdl` at `0x140007250`
- `ntoskrnl!IoFreeMdl` at `0x14000787a`
- `ntoskrnl!IoFreeMdl` at `0x140007a24`
- `ntoskrnl!IoFreeMdl` at `0x14000787a`
- `ntoskrnl!IoFreeMdl` at `0x140007a24`
- `ntoskrnl!ExAllocatePool2` at `0x14000700e`
- `ntoskrnl!ExAllocatePool2` at `0x1400077b9`
- `ntoskrnl!ExAllocatePool2` at `0x14000700e`
- `ntoskrnl!ExAllocatePool2` at `0x1400077b9`
- `ntoskrnl!PoFxActivateComponent` at `0x140007480`
- `ntoskrnl!PoFxActivateComponent` at `0x140007480`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x140007793`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x140007793`
- `ntoskrnl!MmUnlockPages` at `0x140007867`
- `ntoskrnl!MmUnlockPages` at `0x140007f89`
- `ntoskrnl!MmUnlockPages` at `0x140007867`
- `ntoskrnl!MmUnlockPages` at `0x140007f89`
- `ntoskrnl!MmFreeContiguousMemory` at `0x1400076b6`
- `ntoskrnl!MmFreeContiguousMemory` at `0x1400076b6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400072a8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400072a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007358`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007358`

## pseudocode

```c
__int64 __fastcall RaidAdapterScsiMiniportIoctlWithAddress(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned __int8 a5,
        int a6)
{
  __int64 v8; // r14
  __int64 v9; // rdi
  int SrbIoctlFromIrp; // eax
  int v11; // ebx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r15
  __int64 v18; // r12
  bool v19; // zf
  _DWORD *v20; // rax
  __int64 v21; // rbx
  unsigned int v22; // r14d
  unsigned int v23; // r14d
  __int64 v24; // r10
  __int64 ContiguousNodeMemory; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned int *v30; // rbx
  ULONG v31; // ebx
  unsigned int *v32; // rax
  struct _MDL *Mdl; // rax
  unsigned __int8 v34; // al
  char v35; // r9
  char v36; // r10
  KIRQL CurrentIrql; // al
  __int64 v38; // rdx
  _DWORD *v39; // rbx
  _DWORD *v40; // r8
  __int64 UnitAtDirql; // r8
  _DWORD *v42; // rcx
  unsigned int *v43; // rdx
  _BYTE *v44; // r8
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rax
  int v49; // edx
  __int64 v50; // r8
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // rcx
  int v54; // ebx
  __int64 v55; // rdx
  bool v56; // bl
  __int64 v57; // rcx
  __int64 v58; // rax
  void (__fastcall *v59)(__int64, _QWORD, bool); // rax
  __int64 v60; // rcx
  int v61; // eax
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  char v67; // al
  _QWORD *v68; // rcx
  unsigned int v69; // ecx
  __int64 v70; // rax
  __int64 v71; // rcx
  struct _MDL *v72; // rcx
  int v73; // edx
  char *v74; // rcx
  char v75; // al
  __int64 Pool2; // rax
  __int64 v78; // rbx
  __int16 IoPriorityHint; // ax
  unsigned int *v80; // rdx
  char v81; // r10
  char v82; // r11
  __int64 v83; // rax
  int v84; // r15d
  bool v85; // r15
  KIRQL v86; // al
  __int64 v87; // rcx
  __int64 v88; // rdx
  void (__fastcall *v89)(__int64, _QWORD, bool); // rax
  __int64 v90; // rdx
  __int64 v91; // rax
  unsigned __int8 v92; // bl
  int *v93; // rax
  int v94; // ecx
  unsigned __int8 *v95; // r10
  _BYTE *v96; // rdx
  char v97; // di
  unsigned __int8 v98; // r9
  unsigned __int64 v99; // rcx
  char v100; // si
  char v101; // r8
  char v102; // r11
  char v103; // r10
  _BYTE *v104; // rax
  char *v105; // r10
  unsigned int v106; // eax
  char v107; // al
  int v108; // ecx
  signed __int32 v109; // eax
  signed __int32 v110; // ett
  unsigned int v111; // r15d
  __int64 v112; // r11
  __int64 v113; // rcx
  unsigned __int64 v114; // rsi
  __int64 v115; // r14
  int v116; // ecx
  __int64 v117; // r9
  __int64 v118; // rax
  void (__fastcall *v119)(__int64, _QWORD, bool); // rax
  __int64 v120; // rax
  __int64 v121; // r8
  __int64 Unit; // rax
  __int64 v123; // r8
  __int64 v124; // r15
  __int64 v125; // r8
  unsigned __int64 v126; // r8
  int Irp; // [rsp+20h] [rbp-C9h]
  KIRQL v128; // [rsp+60h] [rbp-89h]
  KIRQL v129; // [rsp+60h] [rbp-89h]
  unsigned int v130; // [rsp+64h] [rbp-85h]
  unsigned int v131; // [rsp+68h] [rbp-81h]
  __int64 v132; // [rsp+68h] [rbp-81h]
  _DWORD *v133; // [rsp+68h] [rbp-81h]
  ULONG Length; // [rsp+70h] [rbp-79h] BYREF
  int v135; // [rsp+74h] [rbp-75h]
  int v136; // [rsp+78h] [rbp-71h]
  __int64 v137; // [rsp+80h] [rbp-69h]
  unsigned int *v138; // [rsp+88h] [rbp-61h]
  unsigned int v139; // [rsp+90h] [rbp-59h] BYREF
  PVOID VirtualAddress; // [rsp+98h] [rbp-51h] BYREF
  __int64 v141; // [rsp+A0h] [rbp-49h]
  __int64 v142; // [rsp+A8h] [rbp-41h] BYREF
  __int64 v143; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v144; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v145; // [rsp+C0h] [rbp-29h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-21h] BYREF

  v136 = a4;
  v135 = a3;
  VirtualAddress = 0;
  Length = 0;
  v139 = 0;
  v141 = 0;
  HIBYTE(v130) = 0;
  v8 = 0;
  v9 = 0;
  SrbIoctlFromIrp = RaidGetSrbIoctlFromIrp(
                      a2,
                      (unsigned int)&VirtualAddress,
                      (unsigned int)&Length,
                      (unsigned int)&v139,
                      2);
  v11 = SrbIoctlFromIrp;
  if ( SrbIoctlFromIrp < 0 )
  {
    v137 = 0;
    v18 = 0;
    *(_DWORD *)(a2 + 48) = SrbIoctlFromIrp;
    v70 = 0;
    goto LABEL_72;
  }
  if ( *(_DWORD *)a1 == 1314275652 )
  {
    v137 = a1 + 184;
  }
  else if ( *(_DWORD *)a1 == 1094997074 )
  {
    v137 = a1 + 368;
  }
  else
  {
    v137 = 0;
  }
  v12 = *(_QWORD *)(a1 + 8);
  if ( *(_BYTE *)(v137 + 98) == 1 )
  {
    Pool2 = ExAllocatePool2(64, 144, 1918067026);
    v18 = Pool2;
    if ( !Pool2 && v12 )
    {
      RaidLogAllocationFailure(v12, 64, 144, 1918067026, 0x80000000);
      goto LABEL_95;
    }
    v17 = Pool2;
    if ( Pool2 )
    {
      *(_WORD *)Pool2 = 8;
      v14 = 2;
      *(_BYTE *)(Pool2 + 2) = 40;
      *(_DWORD *)(Pool2 + 8) = 1397899864;
      *(_DWORD *)(Pool2 + 12) = 1;
      *(_DWORD *)(Pool2 + 16) = 144;
      *(_DWORD *)(Pool2 + 20) = 2;
      *(_WORD *)(Pool2 + 36) = 2;
      *(_QWORD *)(Pool2 + 52) = 128;
      *(_WORD *)(Pool2 + 128) = 1;
      *(_DWORD *)(Pool2 + 132) = 4;
      goto LABEL_8;
    }
  }
  else
  {
    v17 = ExAllocatePool2(64, 88, 1918067026);
    if ( !v17 && v12 )
      RaidLogAllocationFailure(v12, 64, 88, 1918067026, 0x80000000);
  }
  v18 = v17;
  if ( !v17 )
  {
LABEL_95:
    v11 = -1073741801;
LABEL_96:
    v70 = 0;
    goto LABEL_72;
  }
LABEL_8:
  v19 = *(_DWORD *)a1 == 1314275652;
  v20 = (_DWORD *)(a1 + 324);
  v145 = v17;
  if ( !v19 )
    v20 = (_DWORD *)(a1 + 508);
  v21 = *(_QWORD *)(a1 + 4368);
  v22 = (*v20 + 7) & 0xFFFFFFF8;
  LockHandle.LockQueue.Next = *(_KSPIN_LOCK_QUEUE *volatile *)(a1 + 880);
  v23 = v22 + 1200;
  v143 = *(_QWORD *)(a1 + 4376);
  v142 = *(_QWORD *)(a1 + 4384);
  v131 = v23;
  v144 = 0;
  if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v14, v13, v15, v16)
    && *(_QWORD *)(a1 + 5688) )
  {
    v23 += 24;
    v131 = v23;
  }
  v138 = (unsigned int *)v23;
  if ( (unsigned __int8)IsDmarEnabled(a1) )
    ContiguousNodeMemory = (*((__int64 (__fastcall **)(_KSPIN_LOCK_QUEUE *volatile, __int64 *, __int64 *, _QWORD, _DWORD, _QWORD, unsigned int, __int64 *))LockHandle.LockQueue.Next->Lock
                            + 34))(
                             LockHandle.LockQueue.Next,
                             &v143,
                             &v142,
                             v23,
                             0,
                             0,
                             0x80000000,
                             &v144);
  else
    ContiguousNodeMemory = MmAllocateContiguousNodeMemory(v24, v143, v142, v21, 4, 0x80000000);
  v30 = v138;
  v8 = ContiguousNodeMemory;
  if ( ContiguousNodeMemory )
  {
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v27, v26, v28, v29) )
    {
      *(_QWORD *)(v8 + 840) = 0;
      if ( !*(_QWORD *)(a1 + 5680) )
      {
LABEL_16:
        *(_QWORD *)(v8 + 24) = v144;
        *(_DWORD *)(v8 + 16) = v131;
        goto LABEL_17;
      }
      v120 = v8 + 856;
    }
    else
    {
      if ( !*(_QWORD *)(a1 + 5688) )
      {
        *(_QWORD *)(v8 + 840) = 0;
        goto LABEL_16;
      }
      v120 = (__int64)v30 + v8 - 24;
    }
    *(_QWORD *)(v8 + 840) = v120;
    *(_OWORD *)v120 = 0;
    *(_QWORD *)(v120 + 16) = 0;
    goto LABEL_16;
  }
  if ( !*(_QWORD *)(a1 + 120) )
    goto LABEL_95;
  if ( _interlockedbittestandset((volatile signed __int32 *)(a1 + 128), 1u) )
    goto LABEL_95;
  v8 = *(_QWORD *)(a1 + 120);
  if ( !v8 )
    goto LABEL_95;
LABEL_17:
  v9 = v8 + 48;
  v31 = Length;
  *(_BYTE *)(v8 + 64) &= 0x1Cu;
  *(_BYTE *)(v8 + 65) &= 0x70u;
  *(_QWORD *)(v8 + 56) = 0;
  *(_WORD *)(v8 + 68) = -1;
  *(_DWORD *)(v8 + 72) = 0;
  *(_QWORD *)(v8 + 152) = 0;
  *(_QWORD *)(v8 + 160) = 0;
  *(_QWORD *)(v8 + 184) = 0;
  *(_QWORD *)(v8 + 200) = 0;
  *(_QWORD *)(v8 + 192) = 0;
  *(_QWORD *)(v8 + 240) = 0;
  *(_QWORD *)(v8 + 208) = 0;
  *(_QWORD *)(v8 + 216) = 0;
  *(_QWORD *)(v8 + 264) = 0;
  *(_QWORD *)(v8 + 272) = 0;
  *(_QWORD *)(v8 + 168) = 0;
  *(_QWORD *)(v8 + 744) = 0;
  *(_QWORD *)(v8 + 752) = 0;
  *(_QWORD *)(v8 + 760) = 0;
  *(_QWORD *)(v8 + 768) = 0;
  *(_QWORD *)(v8 + 808) = 0;
  *(_QWORD *)(v8 + 816) = 0;
  *(_DWORD *)(v8 + 824) = 0;
  *(_WORD *)(v8 + 828) = -1;
  v32 = (unsigned int *)VirtualAddress;
  *(_QWORD *)(v8 + 832) = 0;
  *(_DWORD *)(v8 + 864) = 0;
  *(_QWORD *)(v8 + 872) = 0;
  *(_DWORD *)(v8 + 48) = 523124044;
  *(_BYTE *)(v8 + 70) = -1;
  *(_QWORD *)(v8 + 792) = 0;
  *(_DWORD *)(v8 + 848) = -1;
  *(_DWORD *)(v8 + 856) = 0;
  *(_OWORD *)(v8 + 880) = 0;
  *(_QWORD *)(v8 + 896) = 0;
  *(_QWORD *)(v8 + 904) = 0;
  *(_QWORD *)(v8 + 912) = 0;
  *(_QWORD *)(v8 + 920) = 0;
  *(_DWORD *)(v8 + 928) = -1;
  v138 = v32;
  Mdl = IoAllocateMdl(v32, v31, 0, 0, 0);
  *(_QWORD *)(v8 + 152) = Mdl;
  if ( !Mdl )
    goto LABEL_95;
  *(_BYTE *)(v8 + 64) |= 1u;
  MmBuildMdlForNonPagedPool(Mdl);
  v34 = a5;
  v35 = v135;
  v36 = v136;
  v132 = 0;
  LOBYTE(v130) = v135;
  BYTE1(v130) = v136;
  BYTE2(v130) = a5;
  if ( a6 == 1 )
  {
    CurrentIrql = KeGetCurrentIrql();
    if ( CurrentIrql )
    {
      if ( (unsigned int)CurrentIrql >= *(_DWORD *)(a1 + 856) )
      {
        UnitAtDirql = RaidAdapterFindUnitAtDirql(a1, v130);
        v132 = UnitAtDirql;
      }
      else
      {
        v92 = RaidAdapterAcquireInterruptLock(a1, v38);
        v132 = RaidAdapterFindUnitAtDirql(a1, v130);
        RaidAdapterReleaseInterruptLock(a1, v92);
        UnitAtDirql = v132;
        v31 = Length;
      }
    }
    else
    {
      v133 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 136), &LockHandle);
      v39 = (_DWORD *)(a1 + 144);
      v40 = *(_DWORD **)(a1 + 144);
      VirtualAddress = v40;
      if ( v40 != (_DWORD *)(a1 + 144) )
      {
        do
        {
          v133 = v40 - 16;
          if ( ((unsigned __int8)BYTE2(v40[10])
              | ((((unsigned __int8)v40[10] << 8) | (unsigned __int8)BYTE1(v40[10])) << 8)) == (a5
                                                                                              | (((unsigned __int8)v136
                                                                                                | ((unsigned __int8)v135 << 8)) << 8)) )
            break;
          v40 = *(_DWORD **)v40;
        }
        while ( v40 != v39 );
        VirtualAddress = v40;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      UnitAtDirql = 0;
      v19 = VirtualAddress == v39;
      v31 = Length;
      if ( !v19 )
        UnitAtDirql = (__int64)v133;
      v132 = UnitAtDirql;
    }
    v34 = a5;
    v35 = v135;
    v36 = v136;
    *(_QWORD *)(v8 + 272) = UnitAtDirql;
  }
  v42 = (_DWORD *)(v17 + 24);
  if ( *(_BYTE *)(v137 + 98) == 1 )
  {
    v78 = *(unsigned int *)(v17 + 52);
    *v42 = 192;
    v141 = v17;
    *(_QWORD *)(v17 + 96) = v9;
    *(_QWORD *)(v17 + 80) = a2;
    *(_DWORD *)(v17 + 20) = 2;
    IoPriorityHint = IoGetIoPriorityHint((PIRP)a2);
    v80 = v138;
    v42 = (_DWORD *)(v17 + 64);
    v44 = (_BYTE *)(v17 + 2);
    v81 = v135;
    v82 = v136;
    *(_WORD *)(v17 + 36) = IoPriorityHint;
    *(_DWORD *)(v17 + 40) = v80[3];
    *(_DWORD *)(v17 + 60) = Length;
    *(_QWORD *)(v17 + 64) = v80;
    *(_BYTE *)(v78 + v17 + 8) = v81;
    *(_BYTE *)(v78 + v17 + 9) = v82;
    *(_BYTE *)(v78 + v17 + 10) = a5;
    *(_QWORD *)(v8 + 216) = v17;
    v45 = *(_QWORD *)(v17 + 80);
  }
  else
  {
    v43 = v138;
    v44 = (_BYTE *)(v17 + 2);
    *(_BYTE *)(v17 + 7) = v34;
    *(_QWORD *)(v17 + 48) = v9;
    *(_WORD *)v17 = 88;
    *(_BYTE *)(v17 + 2) = 2;
    *(_BYTE *)(v17 + 5) = v35;
    *(_BYTE *)(v17 + 6) = v36;
    *(_DWORD *)(v17 + 12) = 192;
    *(_QWORD *)v42 = v43;
    *(_DWORD *)(v17 + 16) = v31;
    *(_DWORD *)(v17 + 20) = v43[3];
    v45 = a2;
    *(_QWORD *)(v8 + 216) = v17;
  }
  *(_QWORD *)(v8 + 224) = v45;
  v46 = *(_QWORD *)v42;
  v47 = v8 + 1200;
  *(_QWORD *)(v8 + 232) = v46;
  v48 = 324;
  v49 = *(_DWORD *)a1;
  if ( *v44 == 40 )
  {
    if ( v49 != 1314275652 )
      v48 = 508;
    if ( ((*(_DWORD *)(v48 + a1) + 7) & 0xFFFFFFF8) != 0 )
      *(_QWORD *)(v17 + 104) = v47;
  }
  else
  {
    if ( v49 != 1314275652 )
      v48 = 508;
    if ( ((*(_DWORD *)(v48 + a1) + 7) & 0xFFFFFFF8) != 0 )
      *(_QWORD *)(v17 + 56) = v47;
  }
  KeInitializeEvent((PRKEVENT)(v8 + 712), NotificationEvent, 0);
  *(_QWORD *)(v8 + 704) = RaidXrbSignalCompletion;
  if ( *(_QWORD *)(a1 + 5024) )
  {
    if ( (*(_BYTE *)(a1 + 108) & 1) != 0 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 5344));
      if ( (*(_BYTE *)(a1 + 108) & 2) != 0 )
        _InterlockedIncrement64((volatile signed __int64 *)(a1 + 5352));
    }
    if ( *(_DWORD *)(a1 + 92) )
      v50 = 5;
    else
      v50 = 1;
    PoFxActivateComponent(**(_QWORD **)(a1 + 5024), 0, v50);
  }
  if ( *(_BYTE *)(a1 + 4434) )
  {
    v128 = KfRaiseIrql(2u);
    if ( *(_BYTE *)(a1 + 4434) )
    {
      v52 = *(_QWORD *)(v8 + 216);
      v53 = 24;
      if ( *(_BYTE *)(v52 + 2) != 40 )
        v53 = 12;
      v54 = *(_DWORD *)(v53 + v52);
      if ( (*(_BYTE *)(a1 + 4435) & 4) != 0 )
      {
        v55 = a1 + 880;
        v56 = (v54 & 0x40) != 0;
        if ( *(_QWORD *)(v8 + 152) )
        {
          if ( a1 != -880 )
          {
            v57 = *(_QWORD *)v55;
            if ( *(_QWORD *)v55 )
            {
              v58 = *(_QWORD *)(v57 + 8);
              if ( v58 )
              {
                if ( *(int *)(a1 + 908) >= 3 && (v59 = *(void (__fastcall **)(__int64, _QWORD, bool))(v58 + 240)) != 0 )
                {
                  v59(v57, *(_QWORD *)(v8 + 152), v56);
                }
                else
                {
                  LOBYTE(v51) = 1;
                  KeFlushIoBuffers(*(_QWORD *)(v8 + 152), v56, v51);
                }
                v55 = a1 + 880;
              }
            }
          }
        }
        v60 = *(_QWORD *)(v8 + 184);
        if ( v60 )
        {
          if ( v55 )
          {
            v117 = *(_QWORD *)v55;
            if ( *(_QWORD *)v55 )
            {
              v118 = *(_QWORD *)(v117 + 8);
              if ( v118 )
              {
                if ( *(int *)(v55 + 28) >= 3 && (v119 = *(void (__fastcall **)(__int64, _QWORD, bool))(v118 + 240)) != 0 )
                {
                  v119(v117, *(_QWORD *)(v8 + 184), v56);
                }
                else
                {
                  LOBYTE(v51) = 1;
                  KeFlushIoBuffers(v60, v56, v51);
                }
              }
            }
          }
        }
      }
      else
      {
        if ( *(_QWORD *)(v8 + 184) )
        {
          v61 = RaidAdapterScatterGatherExecuteBidirectionalRequest(a1, v8 + 48);
          goto LABEL_55;
        }
        if ( (v54 & 0xC0) != 0 )
        {
          v61 = RaidAdapterScatterGatherExecute(a1, v8 + 48);
          goto LABEL_55;
        }
      }
    }
    v61 = RaidAdapterPostScatterGatherExecute(a1, v8 + 48);
LABEL_55:
    v11 = v61;
    KeLowerIrql(v128);
    goto LABEL_56;
  }
  v11 = RaidAdapterPostScatterGatherExecute(a1, v8 + 48);
LABEL_56:
  if ( v11 >= 0 )
  {
    KeWaitForSingleObject((PVOID)(v8 + 712), Executive, 0, 0, 0);
    v11 = RaidSrbStatusToNtStatus(*(unsigned __int8 *)(v17 + 3), v64, v65, v66);
  }
  v67 = *(_BYTE *)(v8 + 65);
  if ( (v67 & 1) != 0 )
  {
    RaidAdapterPoFxIdleComponentFromMiniport(a1, *(unsigned int *)(v8 + 796), v62);
    *(_BYTE *)(v8 + 65) &= ~1u;
    v67 = *(_BYTE *)(v8 + 65);
  }
  if ( (v67 & 2) != 0 )
  {
    if ( a6 == 1 )
    {
      if ( v132 )
      {
        RaidUnitPoFxIdleComponentFromMiniport(v132, *(unsigned int *)(v8 + 796), v62);
        *(_BYTE *)(v8 + 65) &= ~2u;
      }
    }
    else
    {
      Unit = RaidAdapterFindUnit(a1, v130, v62, v63);
      v124 = Unit;
      if ( Unit )
      {
        LOBYTE(v123) = 1;
        if ( !(unsigned int)RaUnitAcquireRemoveLock(Unit, a2, v123) )
        {
          RaidUnitPoFxIdleComponentFromMiniport(v124, *(unsigned int *)(v8 + 796), v125);
          *(_BYTE *)(v8 + 65) &= ~2u;
          v126 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          v109 = *(_DWORD *)(v126 + *(_QWORD *)(v124 + 40));
          while ( (v109 & 1) == 0 )
          {
            v110 = v109;
            v109 = _InterlockedCompareExchange(
                     (volatile signed __int32 *)(v126 + *(_QWORD *)(v124 + 40)),
                     v109 - 2,
                     v109);
            if ( v110 == v109 )
              goto LABEL_61;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v124 + 1032), 0xFFFFFFFF) == 1 )
            KeSetEvent((PRKEVENT)(v124 + 520), 0, 0);
        }
      }
    }
  }
LABEL_61:
  v68 = *(_QWORD **)(a1 + 5024);
  if ( v68 )
    PoFxIdleComponent(*v68, 0, 0);
  if ( v11 < 0 )
    goto LABEL_96;
  if ( *(_QWORD *)(v138 + 1) == 0x5551455441455243LL && (v138[17] & 0x30) == 0x10 )
  {
    v11 = RaidAdapterMapUsermodeNvmeDoorbellAddress(a1, (IRP *)a2, (__int64)(v138 + 7), (__int64)v138 + v138[9] + 28);
    v18 = v145;
    if ( v11 < 0 )
      goto LABEL_96;
  }
  if ( *(_BYTE *)(v18 + 2) == 40 )
    v69 = *(_DWORD *)(v141 + 60);
  else
    v69 = *(_DWORD *)(v18 + 16);
  if ( v139 < v69 )
    v69 = v139;
  v70 = v69;
LABEL_72:
  *(_QWORD *)(a2 + 56) = v70;
  if ( v8 )
  {
    if ( v9 )
    {
      *(_BYTE *)(v9 + 16) &= 0xE3u;
      if ( *(_QWORD *)(v9 + 112) )
      {
        v83 = *(_QWORD *)(v9 + 168);
        if ( *(_BYTE *)(v83 + 2) == 40 )
          v84 = *(_DWORD *)(v83 + 24) >> 6;
        else
          LOBYTE(v84) = *(_BYTE *)(v83 + 12) >> 6;
        v85 = (v84 & 1) == 0;
        if ( RaidVerifierEnabled )
          RaidFreeRemappedScatterGatherListMdl(v9);
        v86 = KfRaiseIrql(2u);
        v129 = v86;
        if ( *(_QWORD *)(v9 + 216) != -880 )
        {
          v87 = *(_QWORD *)(*(_QWORD *)(v9 + 216) + 880LL);
          if ( v87 )
          {
            v88 = *(_QWORD *)(v87 + 8);
            if ( v88 )
            {
              v89 = *(void (__fastcall **)(__int64, _QWORD, bool))(v88 + 96);
              if ( v89 )
                v89(v87, *(_QWORD *)(v9 + 112), v85);
              v86 = v129;
            }
          }
        }
        v90 = *(_QWORD *)(v9 + 152);
        *(_QWORD *)(v9 + 112) = 0;
        *(_QWORD *)(v9 + 144) = 0;
        if ( v90 )
        {
          RaidDmaPutScatterGatherList(*(_QWORD *)(v9 + 216) + 880LL, v90, 0);
          v86 = v129;
          *(_QWORD *)(v9 + 152) = 0;
        }
        KeLowerIrql(v86);
      }
      v71 = *(_QWORD *)(v9 + 104);
      if ( v71 && (*(_BYTE *)(v9 + 16) & 1) != 0 )
      {
        if ( (*(_BYTE *)(v71 + 10) & 2) != 0 )
          MmUnlockPages((PMDL)v71);
        IoFreeMdl(*(PMDL *)(v9 + 104));
        *(_BYTE *)(v9 + 16) &= ~1u;
        *(_QWORD *)(v9 + 104) = 0;
      }
      v72 = *(struct _MDL **)(v9 + 136);
      if ( v72 )
      {
        MmUnlockPages(v72);
        IoFreeMdl(*(PMDL *)(v9 + 136));
        *(_QWORD *)(v9 + 136) = 0;
      }
    }
    if ( v8 == *(_QWORD *)(a1 + 120) )
    {
      _interlockedbittestandreset((volatile signed __int32 *)(a1 + 128), 0);
    }
    else
    {
      if ( *(_DWORD *)a1 == 1094997074 )
      {
        if ( *(_BYTE *)(a1 + 888) && *(_DWORD *)(a1 + 908) == 3 )
        {
LABEL_216:
          LOBYTE(Irp) = 1;
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(*(_QWORD *)(*(_QWORD *)(a1 + 880) + 8LL) + 24LL))(
            *(_QWORD *)(a1 + 880),
            *(unsigned int *)(v8 + 16),
            *(_QWORD *)(v8 + 24),
            v8,
            Irp);
          goto LABEL_82;
        }
      }
      else if ( *(_DWORD *)a1 == 1314275652 && *(_BYTE *)(a1 + 1168) && *(_DWORD *)(a1 + 1188) == 3 )
      {
        goto LABEL_216;
      }
      MmFreeContiguousMemory((PVOID)v8);
    }
  }
LABEL_82:
  if ( v18 )
  {
    if ( *(_BYTE *)(v137 + 98) == 1 )
    {
      v91 = v141;
      if ( !v141 )
        v91 = v18;
      *(_QWORD *)(v91 + 80) = 0;
      *(_QWORD *)(v91 + 104) = 0;
    }
    else
    {
      *(_QWORD *)(v18 + 48) = 0;
      *(_QWORD *)(v18 + 56) = 0;
    }
    ExFreePoolWithTag((PVOID)v18, 0x72536152u);
  }
  v19 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v11;
  if ( v19 )
    goto LABEL_89;
  LockHandle.LockQueue = 0;
  IoGetActivityIdIrp(a2, &LockHandle);
  v74 = *(char **)(a2 + 184);
  v75 = *v74;
  if ( *v74 != 15 )
  {
    if ( v75 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v74, EventNonReadWriteRequestComplete, &LockHandle, a2, *(_DWORD *)(a2 + 48));
    }
    else if ( v75 == 27 )
    {
      if ( v74[1] != 7 || *((_DWORD *)v74 + 2) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v74, EventPnpRequestComplete, &LockHandle, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v93 = *(int **)(a2 + 56);
        if ( v93 )
          v94 = *v93;
        else
          v94 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v94, v73, (unsigned int)&LockHandle, a2, v94, *(_DWORD *)(a2 + 48));
      }
    }
    goto LABEL_89;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_89;
  v121 = *((_QWORD *)v74 + 1);
  if ( *(_BYTE *)(v121 + 2) != 40 )
  {
    LODWORD(v99) = *(unsigned __int8 *)(v121 + 72);
    v96 = *(_BYTE **)(v121 + 32);
    v98 = *(_BYTE *)(v121 + 11);
    v97 = *(_BYTE *)(v121 + 4);
    if ( !*(_BYTE *)(v121 + 2) )
      goto LABEL_154;
    goto LABEL_89;
  }
  if ( *(_DWORD *)(v121 + 20) )
    goto LABEL_89;
  v111 = *(_DWORD *)(v121 + 56);
  if ( !v111 )
    goto LABEL_89;
  v98 = 0;
  v95 = 0;
  v97 = 0;
  v96 = 0;
  v112 = 0;
  while ( 1 )
  {
    v113 = *(unsigned int *)(v121 + 4 * v112 + 120);
    if ( (unsigned int)v113 < 0x80 )
      goto LABEL_219;
    v114 = *(unsigned int *)(v121 + 16);
    if ( (unsigned int)v113 >= (unsigned int)v114 )
      goto LABEL_219;
    v115 = (unsigned int)v113;
    v116 = *(_DWORD *)(v121 + v113);
    if ( v116 == 64 )
    {
      if ( v115 + 40 <= v114 )
      {
        if ( !*(_BYTE *)(v121 + v115 + 10) )
          goto LABEL_152;
LABEL_151:
        v95 = (unsigned __int8 *)(v115 + v121 + 24);
LABEL_152:
        v96 = *(_BYTE **)(v121 + v115 + 16);
        v97 = *(_BYTE *)(v121 + v115 + 8);
        v98 = *(_BYTE *)(v121 + v115 + 9);
        goto LABEL_220;
      }
      goto LABEL_219;
    }
    v108 = v116 - 65;
    if ( v108 )
      break;
    if ( v115 + 56 <= v114 )
    {
      if ( !*(_BYTE *)(v121 + v115 + 10) )
        goto LABEL_152;
      goto LABEL_151;
    }
LABEL_219:
    v112 = (unsigned int)(v112 + 1);
    if ( (unsigned int)v112 >= v111 )
      goto LABEL_220;
  }
  if ( v108 != 1 || v115 + 40 > v114 )
    goto LABEL_219;
  if ( *(_DWORD *)(v121 + v115 + 12) )
    v95 = (unsigned __int8 *)(v115 + v121 + 32);
  v96 = *(_BYTE **)(v121 + v115 + 24);
  v97 = *(_BYTE *)(v121 + v115 + 8);
  v98 = *(_BYTE *)(v121 + v115 + 9);
LABEL_220:
  if ( !v95 )
    goto LABEL_89;
  LODWORD(v99) = *v95;
LABEL_154:
  LOBYTE(v99) = v99 - 8;
  if ( (v99 & 0x5D) != 0 )
    goto LABEL_89;
  v100 = *(_BYTE *)(v121 + 3);
  if ( v100 == 1 || !v96 || !v98 )
    goto LABEL_190;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v99 = (unsigned __int64)&v96[v98];
  v104 = v96 + 8;
  if ( (unsigned __int8)((*v96 & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v104 <= v99 )
    {
      v102 = v96[2];
      v101 = v96[1] & 0xF;
      v103 = v96[3];
      goto LABEL_166;
    }
    goto LABEL_225;
  }
  if ( (unsigned __int64)v104 > v99 )
  {
LABEL_225:
    v107 = 0;
    goto LABEL_226;
  }
  v105 = v96 + 13;
  v101 = v96[2] & 0xF;
  v106 = v98;
  if ( (unsigned int)(unsigned __int8)v96[7] + 8 <= v98 )
    v106 = (unsigned __int8)v96[7] + 8;
  v99 = (unsigned __int64)&v96[v106];
  if ( (unsigned __int64)v105 <= v99 )
    v102 = v96[12];
  if ( (unsigned __int64)(v96 + 14) > v99 )
    v103 = 0;
  else
    v103 = *v105;
LABEL_166:
  v107 = 1;
LABEL_226:
  if ( !v107 )
  {
LABEL_190:
    v103 = 0;
    v102 = 0;
    v101 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v99,
    (_DWORD)v96,
    (unsigned int)&LockHandle,
    a2,
    *(_DWORD *)(a2 + 48),
    v100,
    v97,
    v101,
    v102,
    v103,
    a2);
LABEL_89:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140006f50  push    rbp
0x140006f52  push    rbx
0x140006f53  push    rsi
0x140006f54  push    rdi
0x140006f55  push    r12
0x140006f57  push    r13
0x140006f59  push    r14
0x140006f5b  push    r15
0x140006f5d  lea     rbp, [rsp-0Fh]
0x140006f62  sub     rsp, 0F8h
0x140006f69  mov     rax, cs:__security_cookie
0x140006f70  xor     rax, rsp
0x140006f73  mov     [rbp+47h+var_50], rax
0x140006f77  xor     r15d, r15d
0x140006f7a  mov     [rbp+47h+var_B8], r9d
0x140006f7e  mov     r13, rdx
0x140006f81  mov     [rbp+47h+var_BC], r8d
0x140006f85  mov     rsi, rcx
0x140006f88  mov     [rbp+47h+VirtualAddress], r15
0x140006f8c  mov     rcx, r13
0x140006f8f  mov     [rbp+47h+Length], r15d
0x140006f93  lea     r9, [rbp+47h+var_A0]
0x140006f97  mov     [rbp+47h+var_A0], r15d
0x140006f9b  lea     r8, [rbp+47h+Length]
0x140006f9f  mov     [rbp+47h+var_90], r15
0x140006fa3  lea     rdx, [rbp+47h+VirtualAddress]
0x140006fa7  mov     [rsp+130h+var_CC], r15d
0x140006fac  mov     r14d, r15d
0x140006faf  mov     dword ptr [rsp+130h+Irp], 2
0x140006fb7  mov     edi, r15d
0x140006fba  call    RaidGetSrbIoctlFromIrp
0x140006fbf  mov     ebx, eax
0x140006fc1  test    eax, eax
0x140006fc3  js      loc_140007AE3
0x140006fc9  mov     eax, [rsi]
0x140006fcb  cmp     eax, 4E564144h
0x140006fd0  jz      loc_1400077A4
0x140006fd6  cmp     eax, 41445452h
0x140006fdb  jnz     loc_140007BA0
0x140006fe1  lea     rbx, [rsi+170h]
0x140006fe8  mov     [rbp+47h+var_B0], rbx
0x140006fec  mov     rax, [rbp+47h+var_B0]
0x140006ff0  mov     ecx, 40h ; '@'
0x140006ff5  mov     rbx, [rsi+8]
0x140006ff9  mov     r8d, 72536152h
0x140006fff  cmp     byte ptr [rax+62h], 1
0x140007003  jz      loc_1400077B4
0x140007009  mov     edx, 58h ; 'X'
0x14000700e  call    cs:__imp_ExAllocatePool2
0x140007015  nop     dword ptr [rax+rax+00h]
0x14000701a  mov     r15, rax
0x14000701d  test    rax, rax
0x140007020  jz      loc_140007E6B
0x140007026  mov     r12, r15
0x140007029  test    r15, r15
0x14000702c  jz      loc_140007833
0x140007032  cmp     dword ptr [rsi], 4E564144h
0x140007038  lea     rax, [rsi+144h]
0x14000703f  mov     [rbp+47h+var_70], r15
0x140007043  jz      short loc_14000704C
0x140007045  lea     rax, [rsi+1FCh]
0x14000704c  mov     r14d, [rax]
0x14000704f  mov     rax, [rsi+370h]
0x140007056  add     r14d, 7
0x14000705a  mov     rbx, [rsi+1110h]
0x140007061  and     r14d, 0FFFFFFF8h
0x140007065  mov     [rbp+47h+LockHandle.LockQueue.Next], rax
0x140007069  add     r14d, 4B0h
0x140007070  mov     rax, [rsi+1118h]
0x140007077  mov     [rbp+47h+var_80], rax
0x14000707b  mov     rax, [rsi+1120h]
0x140007082  mov     [rbp+47h+var_88], rax
0x140007086  mov     dword ptr [rsp+130h+var_C8], r14d
0x14000708b  mov     [rbp+47h+var_78], rdi
0x14000708f  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140007094  test    eax, eax
0x140007096  jz      loc_140007E9A
0x14000709c  mov     r10d, r14d
0x14000709f  mov     rcx, rsi
0x1400070a2  mov     [rbp+47h+var_A8], r10
0x1400070a6  call    IsDmarEnabled
0x1400070ab  test    al, al
0x1400070ad  jz      loc_140007775
0x1400070b3  mov     rcx, [rbp+47h+LockHandle.LockQueue.Next]
0x1400070b7  lea     rdx, [rbp+47h+var_78]
0x1400070bb  mov     [rsp+130h+var_F8], rdx
0x1400070c0  lea     r8, [rbp+47h+var_88]
0x1400070c4  xor     edx, edx
0x1400070c6  mov     [rsp+130h+var_100], 80000000h
0x1400070ce  mov     [rsp+130h+var_108], rdx
0x1400070d3  mov     r9d, r14d
0x1400070d6  mov     rax, [rcx+8]
0x1400070da  mov     dword ptr [rsp+130h+Irp], edx
0x1400070de  lea     rdx, [rbp+47h+var_80]
0x1400070e2  mov     rax, [rax+110h]
0x1400070e9  call    _guard_dispatch_icall
0x1400070ee  mov     rbx, [rbp+47h+var_A8]
0x1400070f2  mov     r14, rax
0x1400070f5  test    rax, rax
0x1400070f8  jz      loc_140007EDC
0x1400070fe  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140007103  test    eax, eax
0x140007105  jz      loc_140007EB5
0x14000710b  xor     ecx, ecx
0x14000710d  mov     [r14+348h], rcx
0x140007114  cmp     [rsi+1630h], rcx
0x14000711b  jnz     loc_140007ED0
0x140007121  mov     rax, [rbp+47h+var_78]
0x140007125  mov     [r14+18h], rax
0x140007129  mov     eax, dword ptr [rsp+130h+var_C8]
0x14000712d  mov     [r14+10h], eax
0x140007131  lea     rdi, [r14+30h]
0x140007135  mov     ebx, [rbp+47h+Length]
0x140007138  and     byte ptr [rdi+10h], 1Ch
0x14000713c  mov     eax, 0FFFFh
0x140007141  and     byte ptr [rdi+11h], 70h
0x140007145  xorps   xmm0, xmm0
0x140007148  mov     [rdi+8], rcx
0x14000714c  xor     r9d, r9d; ChargeQuota
0x14000714f  mov     [rdi+14h], ax
0x140007153  xor     r8d, r8d; SecondaryBuffer
0x140007156  mov     [rdi+18h], ecx
0x140007159  mov     edx, ebx; Length
0x14000715b  mov     [rdi+68h], rcx
0x14000715f  mov     [rdi+70h], rcx
0x140007163  mov     [rdi+88h], rcx
0x14000716a  mov     [rdi+98h], rcx
0x140007171  mov     [rdi+90h], rcx
0x140007178  mov     [rdi+0C0h], rcx
0x14000717f  mov     [rdi+0A0h], rcx
0x140007186  mov     [rdi+0A8h], rcx
0x14000718d  mov     [rdi+0D8h], rcx
0x140007194  mov     [rdi+0E0h], rcx
0x14000719b  mov     [rdi+78h], rcx
0x14000719f  mov     [rdi+2B8h], rcx
0x1400071a6  mov     [rdi+2C0h], rcx
0x1400071ad  mov     [rdi+2C8h], rcx
0x1400071b4  mov     [rdi+2D0h], rcx
0x1400071bb  mov     [rdi+2F8h], rcx
0x1400071c2  mov     [rdi+300h], rcx
0x1400071c9  mov     [rdi+308h], ecx
0x1400071cf  mov     [rdi+30Ch], ax
0x1400071d6  mov     rax, [rbp+47h+VirtualAddress]
0x1400071da  mov     [rdi+310h], rcx
0x1400071e1  mov     [rdi+330h], ecx
0x1400071e7  mov     [rdi+338h], rcx
0x1400071ee  mov     dword ptr [rdi], 1F2E3D4Ch
0x1400071f4  mov     byte ptr [rdi+16h], 0FFh
0x1400071f8  mov     qword ptr [rdi+2E8h], 0
0x140007203  mov     dword ptr [rdi+320h], 0FFFFFFFFh
0x14000720d  mov     dword ptr [rdi+328h], 0
0x140007217  movups  xmmword ptr [rdi+340h], xmm0
0x14000721e  mov     [rdi+350h], rcx
0x140007225  mov     [rdi+358h], rcx
0x14000722c  mov     [rdi+360h], rcx
0x140007233  mov     [rdi+368h], rcx
0x14000723a  mov     [rsp+130h+Irp], rcx; Irp
0x14000723f  mov     rcx, rax; VirtualAddress
0x140007242  mov     dword ptr [rdi+370h], 0FFFFFFFFh
0x14000724c  mov     [rbp+47h+var_A8], rax
0x140007250  call    cs:__imp_IoAllocateMdl
0x140007257  nop     dword ptr [rax+rax+00h]
0x14000725c  mov     [rdi+68h], rax
0x140007260  test    rax, rax
0x140007263  jz      loc_140007833
0x140007269  or      byte ptr [rdi+10h], 1
0x14000726d  mov     rcx, rax; MemoryDescriptorList
0x140007270  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140007277  nop     dword ptr [rax+rax+00h]
0x14000727c  movzx   eax, [rbp+47h+arg_20]
0x140007280  xor     r8d, r8d
0x140007283  cmp     [rbp+47h+arg_28], 1
0x140007287  mov     r9d, [rbp+47h+var_BC]
0x14000728b  mov     r10d, [rbp+47h+var_B8]
0x14000728f  mov     [rsp+130h+var_C8], r8
0x140007294  mov     byte ptr [rsp+130h+var_CC], r9b
0x140007299  mov     byte ptr [rsp+130h+var_CC+1], r10b
0x14000729e  mov     byte ptr [rsp+130h+var_CC+2], al
0x1400072a2  jnz     loc_14000738C
0x1400072a8  call    cs:__imp_KeGetCurrentIrql
0x1400072af  nop     dword ptr [rax+rax+00h]
0x1400072b4  test    al, al
0x1400072b6  jnz     loc_140007B26
0x1400072bc  xorps   xmm0, xmm0
0x1400072bf  mov     [rsp+130h+var_C8], 0
0x1400072c8  xor     eax, eax
0x1400072ca  lea     rcx, [rsi+88h]; SpinLock
0x1400072d1  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400072d5  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x1400072d9  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x1400072dd  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400072e4  nop     dword ptr [rax+rax+00h]
0x1400072e9  lea     rbx, [rsi+90h]
0x1400072f0  mov     r8, [rbx]
0x1400072f3  mov     [rbp+47h+VirtualAddress], r8
0x1400072f7  cmp     r8, rbx
0x1400072fa  jz      short loc_140007354
0x1400072fc  movzx   r9d, [rbp+47h+arg_20]
0x140007301  mov     r10d, [rbp+47h+var_BC]
0x140007305  mov     r11d, [rbp+47h+var_B8]
0x140007309  mov     ecx, [r8+28h]
0x14000730d  lea     rax, [r8-40h]
0x140007311  mov     [rsp+130h+var_C8], rax
0x140007316  mov     eax, ecx
0x140007318  shr     eax, 8
0x14000731b  movzx   edx, al
0x14000731e  movzx   eax, cl
0x140007321  shr     ecx, 10h
0x140007324  shl     eax, 8
0x140007327  or      edx, eax
0x140007329  movzx   eax, cl
0x14000732c  shl     edx, 8
0x14000732f  or      edx, eax
0x140007331  movzx   ecx, r10b
0x140007335  shl     ecx, 8
0x140007338  movzx   eax, r11b
0x14000733c  or      ecx, eax
0x14000733e  shl     ecx, 8
0x140007341  or      ecx, r9d
0x140007344  cmp     edx, ecx
0x140007346  jz      short loc_140007350
0x140007348  mov     r8, [r8]
0x14000734b  cmp     r8, rbx
0x14000734e  jnz     short loc_140007309
0x140007350  mov     [rbp+47h+VirtualAddress], r8
0x140007354  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140007358  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000735f  nop     dword ptr [rax+rax+00h]
0x140007364  xor     r8d, r8d
0x140007367  cmp     [rbp+47h+VirtualAddress], rbx
0x14000736b  mov     ebx, [rbp+47h+Length]
0x14000736e  cmovnz  r8, [rsp+130h+var_C8]
0x140007374  mov     [rsp+130h+var_C8], r8
0x140007379  movzx   eax, [rbp+47h+arg_20]
0x14000737d  mov     r9d, [rbp+47h+var_BC]
0x140007381  mov     r10d, [rbp+47h+var_B8]
0x140007385  mov     [rdi+0E0h], r8
0x14000738c  mov     rdx, [rbp+47h+var_B0]
0x140007390  lea     rcx, [r15+18h]
0x140007394  cmp     byte ptr [rdx+62h], 1
0x140007398  jz      loc_140007892
0x14000739e  mov     rdx, [rbp+47h+var_A8]
0x1400073a2  lea     r8, [r15+2]
0x1400073a6  mov     [r15+7], al
0x1400073aa  mov     [r15+30h], rdi
0x1400073ae  mov     word ptr [r15], 58h ; 'X'
0x1400073b4  mov     byte ptr [r8], 2
0x1400073b8  mov     [r15+5], r9b
0x1400073bc  mov     [r15+6], r10b
0x1400073c0  mov     dword ptr [r15+0Ch], 0C0h
0x1400073c8  mov     [rcx], rdx
0x1400073cb  mov     [r15+10h], ebx
0x1400073cf  mov     eax, [rdx+0Ch]
0x1400073d2  mov     [r15+14h], eax
0x1400073d6  mov     rax, r13
0x1400073d9  mov     [rdi+0A8h], r15
0x1400073e0  mov     [rdi+0B0h], rax
0x1400073e7  mov     rax, [rcx]
0x1400073ea  lea     rcx, [r14+4B0h]
0x1400073f1  mov     [rdi+0B8h], rax
0x1400073f8  mov     eax, 144h
0x1400073fd  cmp     byte ptr [r8], 28h ; '('
0x140007401  mov     r8d, 1FCh
0x140007407  mov     edx, [rsi]
0x140007409  jnz     loc_140007843
0x14000740f  cmp     edx, 4E564144h
0x140007415  cmovnz  eax, r8d
0x140007419  mov     eax, [rax+rsi]
0x14000741c  add     eax, 7
0x14000741f  test    eax, 0FFFFFFF8h
0x140007424  jbe     short loc_14000742A
0x140007426  mov     [r15+68h], rcx
0x14000742a  lea     rcx, [rdi+298h]; Event
0x140007431  xor     r8d, r8d; State
0x140007434  xor     edx, edx; Type
0x140007436  call    cs:__imp_KeInitializeEvent
0x14000743d  nop     dword ptr [rax+rax+00h]
0x140007442  lea     rax, RaidXrbSignalCompletion
0x140007449  mov     [rdi+290h], rax
0x140007450  cmp     qword ptr [rsi+13A0h], 0
0x140007458  jz      short loc_140007496
0x14000745a  test    byte ptr [rsi+6Ch], 1
0x14000745e  jnz     loc_140007A7A
0x140007464  cmp     dword ptr [rsi+5Ch], 0
0x140007468  ja      loc_140007A99
0x14000746e  mov     r8d, 1
0x140007474  mov     rcx, [rsi+13A0h]
0x14000747b  xor     edx, edx
0x14000747d  mov     rcx, [rcx]
0x140007480  call    cs:__imp_PoFxActivateComponent
0x140007487  nop     dword ptr [rax+rax+00h]
0x14000748c  mov     rax, [rsi+13A0h]
0x140007493  mov     ecx, [rax+14h]
0x140007496  cmp     byte ptr [rsi+1152h], 0
0x14000749d  jz      loc_140007934
0x1400074a3  mov     cl, 2; NewIrql
0x1400074a5  call    cs:__imp_KfRaiseIrql
0x1400074ac  nop     dword ptr [rax+rax+00h]
0x1400074b1  cmp     byte ptr [rsi+1152h], 0
0x1400074b8  mov     [rsp+130h+var_D0], al
  ... truncated ...
```
