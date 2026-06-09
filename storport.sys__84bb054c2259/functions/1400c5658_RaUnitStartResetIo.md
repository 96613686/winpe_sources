# RaUnitStartResetIo

- ea: `0x1400c5658`
- end: `0x1400c6447`
- name: `RaUnitStartResetIo`
- size: `3567`
- prototype: ``
- caller_count: `3`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x14002e3d0`
- `0x140033b18`
- `0x1400342b0`

## callees

- `0x1400016cc`
- `0x1400018b0`
- `0x140005c50`
- `0x140008eb0`
- `0x14000b0c0`
- `0x14000befc`
- `0x14000bf40`
- `0x14000e350`
- `0x140014018`
- `0x1400172d0`
- `0x140017ae8`
- `0x14001ebe8`
- `0x14002be60`
- `0x140030b30`
- `0x140046c60`
- `0x14004a890`
- `0x140054800`
- `0x140066e18`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x140071800`
- `0x1400848c4`
- `0x140093144`
- `0x140096fe0`
- `0x1400c5658`
- `0x1400c9274`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400c5d45`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400c5e05`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400c5d45`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400c5e05`
- `ntoskrnl!PoFxIdleComponent` at `0x1400c6109`
- `ntoskrnl!PoFxIdleComponent` at `0x1400c6109`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c5c53`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c616b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c5c53`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c616b`
- `ntoskrnl!KeFlushIoBuffers` at `0x1400c596c`
- `ntoskrnl!KeFlushIoBuffers` at `0x1400c59c9`
- `ntoskrnl!KeFlushIoBuffers` at `0x1400c596c`
- `ntoskrnl!KeFlushIoBuffers` at `0x1400c59c9`
- `ntoskrnl!KeSetEvent` at `0x1400c573c`
- `ntoskrnl!KeSetEvent` at `0x1400c6062`
- `ntoskrnl!KeSetEvent` at `0x1400c573c`
- `ntoskrnl!KeSetEvent` at `0x1400c6062`
- `ntoskrnl!IofCompleteRequest` at `0x1400c6413`
- `ntoskrnl!IofCompleteRequest` at `0x1400c6413`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c611c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c611c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400c5b80`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400c5b80`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400c5aba`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400c5aba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400c5b6f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400c5b6f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c5a9e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c5a9e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400c5c30`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400c5c30`
- `HAL!KeQueryPerformanceCounter` at `0x1400c5d37`
- `HAL!KeQueryPerformanceCounter` at `0x1400c5ddc`
- `HAL!KeQueryPerformanceCounter` at `0x1400c5d37`
- `HAL!KeQueryPerformanceCounter` at `0x1400c5ddc`

## pseudocode

```c
void __fastcall RaUnitStartResetIo(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  __int64 v5; // r13
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // r15d
  char v9; // r14
  __int64 v10; // r12
  __int64 v11; // r8
  unsigned __int64 v12; // r8
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // r13
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // ecx
  int v27; // r9d
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  bool v31; // bl
  __int64 *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  void (__fastcall *v35)(__int64, _QWORD, __int64); // rax
  __int64 *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  void (__fastcall *v39)(__int64, _QWORD, __int64); // rax
  __int64 v40; // rax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rdi
  __int64 v45; // rax
  __int64 v46; // r12
  bool v47; // zf
  __int64 v48; // rbx
  __int64 *v49; // rbx
  union _LARGE_INTEGER v50; // rcx
  __int64 v51; // r13
  KIRQL CurrentIrql; // al
  KSPIN_LOCK *v53; // rcx
  char v54; // al
  __int64 v55; // r8
  int v56; // r10d
  __int64 *v57; // rcx
  __int64 **v58; // rax
  __int64 *v59; // r9
  __int64 *v60; // rcx
  __int64 *v61; // rdx
  __int64 **v62; // rax
  char v63; // al
  __int64 v64; // r8
  int v65; // r10d
  __int64 *v66; // rcx
  __int64 **v67; // rax
  __int64 *v68; // r9
  __int64 *v69; // rcx
  __int64 *v70; // rdx
  __int64 **v71; // rax
  int v72; // edx
  int v73; // ecx
  int v74; // r9d
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // r13
  LARGE_INTEGER v82; // rax
  LARGE_INTEGER v83; // rbx
  unsigned int v84; // r8d
  __int64 v85; // rcx
  unsigned __int64 v86; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v88; // rdx
  unsigned int LowPart; // ecx
  unsigned __int64 v90; // r8
  char v91; // r10
  unsigned __int64 v92; // r9
  __int64 v93; // r13
  unsigned int v94; // ebx
  __int64 v95; // r8
  __int64 v96; // rcx
  __int64 v97; // rdx
  unsigned __int64 v98; // r10
  int v99; // eax
  int v100; // eax
  __int64 v101; // rax
  unsigned __int64 v102; // r8
  signed __int32 v103; // eax
  signed __int32 v104; // ett
  __int64 v105; // r9
  __int64 v106; // rax
  unsigned __int8 v107; // bl
  __int64 v108; // r12
  unsigned __int64 v109; // rcx
  __int64 v110; // rdx
  int *v111; // rax
  int v112; // ecx
  __int64 *v113; // rdx
  __int64 v114; // rdx
  unsigned int v115; // r12d
  unsigned __int8 v116; // r10
  char *v117; // r11
  char v118; // bl
  _BYTE *v119; // r9
  __int64 v120; // r15
  char v121; // r13
  unsigned __int64 v122; // rdi
  __int64 v123; // r8
  int v124; // ecx
  char v125; // cl
  char v126; // di
  char v127; // r11
  char v128; // r8
  _BYTE *v129; // rax
  char *v130; // r8
  unsigned int v131; // eax
  char v132; // [rsp+60h] [rbp-A0h] BYREF
  char v133; // [rsp+61h] [rbp-9Fh] BYREF
  char v134; // [rsp+62h] [rbp-9Eh] BYREF
  __int64 v135; // [rsp+68h] [rbp-98h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+70h] [rbp-90h] BYREF
  __int64 v137; // [rsp+78h] [rbp-88h]
  __int64 v138; // [rsp+80h] [rbp-80h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  __int128 v140; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v141[16]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a2 + 184);
  v138 = v2;
  v5 = *(_QWORD *)(v3 + 8);
  v137 = v5;
  v8 = RaUnitCheckRemoveState(v2);
  v9 = 1;
  if ( v8 >= 0 )
  {
    v10 = *(_QWORD *)(v2 + 24);
    LOBYTE(v7) = 1;
    v8 = RaUnitAcquireRemoveLock(v2, v6, v7);
    if ( v8 >= 0 )
    {
      v8 = RaidUnitClaimIrp(v2, a2, 0);
      if ( v8 < 0 )
      {
        v12 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
        v13 = *(_DWORD *)(v12 + *(_QWORD *)(v2 + 40));
        while ( (v13 & 1) == 0 )
        {
          v14 = v13;
          v13 = _InterlockedCompareExchange((volatile signed __int32 *)(v12 + *(_QWORD *)(v2 + 40)), v13 - 2, v13);
          if ( v14 == v13 )
            goto LABEL_176;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 1032), 0xFFFFFFFF) == 1 )
          KeSetEvent((PRKEVENT)(v2 + 520), 0, 0);
        goto LABEL_176;
      }
      v15 = *(_QWORD *)(a2 + 184);
      PerformanceFrequency.LowPart = 0;
      v16 = *(_QWORD *)(v15 + 8);
      v17 = 96;
      if ( *(_BYTE *)(v16 + 2) != 40 )
        v17 = 48;
      v18 = v137;
      v19 = *(_QWORD **)(v17 + v16);
      v20 = *(unsigned __int8 *)(v137 + 2);
      if ( (_BYTE)v20 == 40 )
        v20 = *(_DWORD *)(v137 + 20);
      if ( v20 == 16 )
      {
LABEL_24:
        v25 = *(unsigned __int8 *)(v18 + 2);
        if ( (_BYTE)v25 == 40 )
          v25 = *(_DWORD *)(v18 + 20);
        if ( v25 == 16 && (unsigned int)dword_140176178 > 5 && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL) )
        {
          v141[5] = 16;
          v141[4] = v10 + 5128;
          v141[7] = 16;
          v141[6] = v2 + 2104;
          LODWORD(v135) = *(_DWORD *)(v10 + 56);
          v141[8] = (__int64)&v135;
          v132 = *(_BYTE *)(v2 + 104);
          v141[10] = (__int64)&v132;
          v133 = *(_BYTE *)(v2 + 105);
          v141[12] = (__int64)&v133;
          v134 = *(_BYTE *)(v2 + 106);
          v141[14] = (__int64)&v134;
          v141[9] = 4;
          v141[11] = 1;
          v141[13] = 1;
          v141[15] = 1;
          tlgWriteTransfer_EtwWriteTransfer(v26, (int)&byte_1401647B5, v11, v27, 8u, (__int64)v141);
        }
        v19[82] = RaidUnitCompleteResetRequest;
        if ( *(_BYTE *)(v10 + 4434) )
        {
          v28 = v19[21];
          v29 = 24;
          if ( *(_BYTE *)(v28 + 2) != 40 )
            v29 = 12;
          if ( (*(_BYTE *)(v10 + 4435) & 4) != 0 )
          {
            v31 = (*(_DWORD *)(v29 + v28) & 0x40) != 0;
            if ( v19[13] )
            {
              v32 = (__int64 *)(v10 + 880);
              if ( v10 != -880 )
              {
                v33 = *v32;
                if ( *v32 )
                {
                  v34 = *(_QWORD *)(v33 + 8);
                  if ( v34 )
                  {
                    if ( *(int *)(v10 + 908) >= 3
                      && (v35 = *(void (__fastcall **)(__int64, _QWORD, __int64))(v34 + 240)) != 0 )
                    {
                      LOBYTE(v11) = v31;
                      v35(v33, v19[13], v11);
                    }
                    else
                    {
                      LOBYTE(v11) = 1;
                      LOBYTE(v34) = v31;
                      KeFlushIoBuffers(v19[13], v34, v11);
                    }
                  }
                }
              }
            }
            if ( v19[17] )
            {
              v36 = (__int64 *)(v10 + 880);
              if ( v10 != -880 )
              {
                v37 = *v36;
                if ( *v36 )
                {
                  v38 = *(_QWORD *)(v37 + 8);
                  if ( v38 )
                  {
                    if ( *(int *)(v10 + 908) >= 3
                      && (v39 = *(void (__fastcall **)(__int64, _QWORD, __int64))(v38 + 240)) != 0 )
                    {
                      LOBYTE(v11) = v31;
                      v39(v37, v19[17], v11);
                    }
                    else
                    {
                      LOBYTE(v11) = 1;
                      LOBYTE(v38) = v31;
                      KeFlushIoBuffers(v19[17], v38, v11);
                    }
                  }
                }
              }
            }
          }
          else
          {
            if ( v19[17] )
            {
              v30 = RaidAdapterScatterGatherExecuteBidirectionalRequest(v10, v19);
              goto LABEL_55;
            }
            if ( (*(_DWORD *)(v29 + v28) & 0xC0) != 0 )
            {
              v30 = RaidAdapterScatterGatherExecute(v10, v19);
              goto LABEL_55;
            }
          }
        }
        v30 = RaidAdapterPostScatterGatherExecute(v10, v19);
LABEL_55:
        v8 = v30;
        if ( v30 >= 0 )
          return;
        if ( PerformanceFrequency.LowPart )
        {
          v40 = v19[21];
          if ( *(_BYTE *)(v40 + 2) == 40 )
            v41 = *(_DWORD *)(v40 + 20);
          else
            v41 = *(unsigned __int8 *)(v40 + 2);
          _InterlockedDecrement((volatile signed __int32 *)(v2 + 1396));
          v42 = v41 - 18;
          if ( v42 && (v43 = v42 - 1) != 0 )
          {
            if ( v43 == 13 )
              RaidResumeAndRestartUnitQueue(v2);
          }
          else
          {
            RaidResumeAndRestartAdapterQueues(*(_QWORD *)(v2 + 24));
          }
        }
        v44 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
        v45 = 96;
        if ( *(_BYTE *)(v44 + 2) != 40 )
          v45 = 48;
        v46 = *(_QWORD *)(v45 + v44);
        v47 = (*(_BYTE *)(v46 + 16) & 2) == 0;
        v48 = *(_QWORD *)(v46 + 224);
        v135 = v48;
        if ( v47 )
        {
LABEL_102:
          StorUnmapSenseInfo(v46, *(_QWORD *)(*(_QWORD *)(v48 + 24) + 8LL));
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                               v76,
                               v75,
                               v77,
                               v78) )
          {
            v80 = *(_QWORD *)(v48 + 3608);
            if ( v80 && *(_QWORD *)(v80 + 112) )
            {
LABEL_110:
              RaidReleaseNvmeIceKeyResources(v48, v46);
              goto LABEL_113;
            }
            v79 = *(_QWORD *)(v48 + 24);
            if ( *(_QWORD *)(v79 + 5680) )
LABEL_112:
              RaidAdapterReleaseCryptoKeyResources(v79, v46);
          }
          else
          {
            v79 = *(_QWORD *)(v48 + 24);
            if ( *(_QWORD *)(v79 + 5688) )
            {
              if ( (*(_BYTE *)(v79 + 112) & 0x10) == 0 )
                goto LABEL_112;
              goto LABEL_110;
            }
          }
LABEL_113:
          if ( *(_BYTE *)(v44 + 2) == 40 )
          {
            if ( (*(_BYTE *)(v46 + 16) & 0x40) != 0 )
            {
              PerformanceFrequency.QuadPart = 1;
              if ( v44 )
              {
                v81 = *(_QWORD *)(v46 + 752);
                if ( v81 )
                {
                  if ( UseQPCTime )
                    v82 = KeQueryPerformanceCounter(&PerformanceFrequency);
                  else
                    v82.QuadPart = KeQueryUnbiasedInterruptTime();
                  v83 = v82;
                  *(_BYTE *)(v81 + 3) = *(_BYTE *)(v44 + 3);
                  *(_DWORD *)(v81 + 12) = *(_DWORD *)(v44 + 24);
                  if ( (*(_DWORD *)(v44 + 24) & 0x40) != 0 )
                    *(_DWORD *)(v81 + 16) = *(_DWORD *)(v44 + 60);
                  if ( *(_BYTE *)(v44 + 3) == 48 )
                    *(_DWORD *)(v81 + 64) = *(_DWORD *)(v44 + 44);
                  if ( !*(_DWORD *)(v44 + 20) )
                  {
                    v84 = 0;
                    if ( *(_DWORD *)(v44 + 56) )
                    {
                      while ( 1 )
                      {
                        v85 = *(unsigned int *)(v44 + 4LL * v84 + 120);
                        if ( (unsigned int)v85 >= 0x80 )
                        {
                          v86 = *(unsigned int *)(v44 + 16);
                          if ( (unsigned int)v85 <= (unsigned int)v86 && *(_DWORD *)(v85 + v44) == 64 && v85 + 40 <= v86 )
                            break;
                        }
                        if ( ++v84 >= *(_DWORD *)(v44 + 56) )
                          goto LABEL_131;
                      }
                      *(_BYTE *)(v81 + 4) = *(_BYTE *)((unsigned int)v85 + v44 + 8);
                      *(_QWORD *)(v81 + 32) = *(_QWORD *)((unsigned int)v85 + v44 + 16);
                      *(_BYTE *)(v81 + 11) = *(_BYTE *)((unsigned int)v85 + v44 + 9);
                    }
                    else
                    {
LABEL_131:
                      *(_BYTE *)(v81 + 3) = 48;
                      *(_DWORD *)(v81 + 64) = -1073741811;
                    }
                  }
                  if ( UseQPCTime )
                    PerformanceCounter = KeQueryPerformanceCounter(0);
                  else
                    PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
                  if ( PerformanceCounter.QuadPart <= 0 || PerformanceCounter.QuadPart >= v83.QuadPart )
                    v90 = PerformanceCounter.QuadPart - v83.QuadPart;
                  else
                    v90 = PerformanceCounter.QuadPart - v83.QuadPart - 1;
                  if ( UseQPCTime )
                  {
                    LowPart = PerformanceFrequency.LowPart;
                    v91 = 0;
                    if ( PerformanceFrequency.QuadPart && v90 )
                    {
                      v92 = 1000 * (v90 % PerformanceFrequency.QuadPart);
                      v90 = v92 / PerformanceFrequency.QuadPart + 1000 * (v90 / PerformanceFrequency.QuadPart);
                      v88.QuadPart = 10000 * (v92 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart;
                      v91 = 10000 * (v92 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart + 16 * v90;
                    }
                  }
                  else
                  {
                    v91 = v90;
                  }
                  if ( (Microsoft_Windows_StorPortEnableBits & 0x40) != 0 )
                    McTemplateK0zx_EtwWriteTransfer(
                      LowPart,
                      v88.LowPart,
                      v90,
                      (unsigned int)L"Translate STORAGE_REQUEST_BLOCK result",
                      v91);
                  v48 = v135;
                }
              }
              *(_QWORD *)(*(_QWORD *)(v46 + 752) + 48LL) = *(_QWORD *)(v46 + 176);
              *(_QWORD *)(*(_QWORD *)(v46 + 752) + 24LL) = *(_QWORD *)(v46 + 184);
              *(_QWORD *)(*(_QWORD *)(v46 + 752) + 56LL) = 0;
              *(_QWORD *)(*(_QWORD *)(v46 + 752) + 40LL) = 0;
              *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL) = *(_QWORD *)(v46 + 752);
              *(_BYTE *)(v46 + 16) &= ~0x40u;
              *(_QWORD *)(v46 + 752) = 0;
            }
            else
            {
              *(_QWORD *)(v44 + 96) = 0;
              *(_QWORD *)(v44 + 64) = *(_QWORD *)(v46 + 184);
              *(_QWORD *)(v44 + 104) = 0;
              v93 = *(_QWORD *)(v46 + 192);
              if ( v93 && (*(_BYTE *)(v44 + 24) & 0xC0) == 0xC0 )
              {
                v94 = *(_DWORD *)(v44 + 56);
                if ( v94 )
                {
                  v95 = 0;
                  while ( 1 )
                  {
                    v96 = *(unsigned int *)(v44 + 4 * v95 + 120);
                    v97 = 0;
                    if ( (unsigned int)v96 >= 0x80 )
                    {
                      v98 = *(unsigned int *)(v44 + 16);
                      if ( (unsigned int)v96 <= (unsigned int)v98 && *(_DWORD *)(v96 + v44) == 1 && v96 + 24 <= v98 )
                        break;
                    }
                    v95 = (unsigned int)(v95 + 1);
                    if ( (unsigned int)v95 >= v94 )
                      goto LABEL_160;
                  }
                  v97 = v96 + v44;
LABEL_160:
                  v48 = v135;
                  if ( v97 )
                    *(_QWORD *)(v97 + 16) = v93;
                }
                else
                {
                  v48 = v135;
                }
              }
              v99 = *(_DWORD *)(v44 + 24);
              if ( (v99 & 0x2000000) != 0 )
                *(_DWORD *)(v44 + 24) = v99 & 0xFDFFFFFF;
            }
          }
          else
          {
            *(_QWORD *)(v44 + 48) = *(_QWORD *)(v46 + 176);
            *(_QWORD *)(v44 + 24) = *(_QWORD *)(v46 + 184);
            v100 = *(_DWORD *)(v44 + 12);
            *(_QWORD *)(v44 + 56) = 0;
            *(_QWORD *)(v44 + 40) = 0;
            if ( (v100 & 0x2000000) != 0 )
              *(_DWORD *)(v44 + 12) = v100 & 0xFDFFFFFF;
          }
          RaidXrbDeallocateResources(v46, 1);
          v101 = 24;
          if ( *(_BYTE *)(v44 + 2) != 40 )
            v101 = 12;
          if ( (*(_DWORD *)(v101 + v44) & 0x4000) == 0 )
          {
            v102 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
            v103 = *(_DWORD *)(v102 + *(_QWORD *)(v48 + 40));
            while ( (v103 & 1) == 0 )
            {
              v104 = v103;
              v103 = _InterlockedCompareExchange(
                       (volatile signed __int32 *)(v102 + *(_QWORD *)(v48 + 40)),
                       v103 - 2,
                       v103);
              if ( v104 == v103 )
                goto LABEL_175;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v48 + 1032), 0xFFFFFFFF) == 1 )
              KeSetEvent((PRKEVENT)(v48 + 520), 0, 0);
          }
LABEL_175:
          v5 = v137;
          v2 = v138;
          goto LABEL_176;
        }
        v49 = (__int64 *)(v46 + 48);
        v50.QuadPart = (unsigned __int64)*(unsigned int *)(v46 + 84) << 6;
        *(_QWORD *)&v140 = *(_QWORD *)(v135 + 560);
        memset(&LockHandle, 0, sizeof(LockHandle));
        PerformanceFrequency = v50;
        v51 = v50.QuadPart + v140 + 64;
        CurrentIrql = KeGetCurrentIrql();
        v53 = (KSPIN_LOCK *)(v51 + 40);
        if ( CurrentIrql == 2 )
        {
          KeAcquireInStackQueuedSpinLockAtDpcLevel(v53, &LockHandle);
          v54 = *(_BYTE *)(v46 + 16);
          if ( (v54 & 2) == 0 )
          {
LABEL_83:
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
            goto LABEL_98;
          }
          v55 = v140;
          v56 = *(_DWORD *)v140;
          *(_BYTE *)(v46 + 16) = v54 & 0xFD;
          v57 = (__int64 *)*v49;
          if ( *(__int64 **)(*v49 + 8) == v49 )
          {
            v58 = *(__int64 ***)(v46 + 56);
            if ( *v58 == v49 )
            {
              v59 = *(__int64 **)v51;
              *v58 = v57;
              v57[1] = (__int64)v58;
              if ( (*(_DWORD *)(v46 + 96) & 1) == 0 )
              {
LABEL_78:
                if ( (v56 & 4) == 0 && v59 == v49 )
                {
                  if ( *(_QWORD *)v51 == v51 )
                    *(_DWORD *)(v51 + 48) = -1;
                  else
                    *(_DWORD *)(PerformanceFrequency.QuadPart + v55 + 112) = *(_DWORD *)(*(_QWORD *)v51 + 32LL);
                }
                goto LABEL_83;
              }
              v60 = (__int64 *)(v46 + 64);
              if ( *(_QWORD *)(v51 + 32) == v46 + 64 )
                *(_QWORD *)(v51 + 32) = *v60;
              v61 = (__int64 *)*v60;
              if ( *(__int64 **)(*v60 + 8) == v60 )
              {
                v62 = *(__int64 ***)(v46 + 72);
                if ( *v62 == v60 )
                {
                  *v62 = v61;
                  v61[1] = (__int64)v62;
                  *(_DWORD *)(v46 + 96) &= ~1u;
                  goto LABEL_78;
                }
              }
            }
          }
LABEL_107:
          __fastfail(3u);
        }
        KeAcquireInStackQueuedSpinLock(v53, &LockHandle);
        v63 = *(_BYTE *)(v46 + 16);
        if ( (v63 & 2) != 0 )
        {
          v64 = v140;
          v65 = *(_DWORD *)v140;
          *(_BYTE *)(v46 + 16) = v63 & 0xFD;
          v66 = (__int64 *)*v49;
          if ( *(__int64 **)(*v49 + 8) != v49 )
            goto LABEL_107;
          v67 = *(__int64 ***)(v46 + 56);
          if ( *v67 != v49 )
            goto LABEL_107;
          v68 = *(__int64 **)v51;
          *v67 = v66;
          v66[1] = (__int64)v67;
          if ( (*(_DWORD *)(v46 + 96) & 1) != 0 )
          {
            v69 = (__int64 *)(v46 + 64);
            if ( *(_QWORD *)(v51 + 32) == v46 + 64 )
              *(_QWORD *)(v51 + 32) = *v69;
            v70 = (__int64 *)*v69;
            if ( *(__int64 **)(*v69 + 8) != v69 )
              goto LABEL_107;
            v71 = *(__int64 ***)(v46 + 72);
            if ( *v71 != v69 )
              goto LABEL_107;
            *v71 = v70;
            v70[1] = (__int64)v71;
            *(_DWORD *)(v46 + 96) &= ~1u;
          }
          if ( (v65 & 4) == 0 && v68 == v49 )
          {
            if ( *(_QWORD *)v51 == v51 )
              *(_DWORD *)(PerformanceFrequency.QuadPart + v64 + 112) = -1;
            else
              *(_DWORD *)(PerformanceFrequency.QuadPart + v64 + 112) = *(_DWORD *)(*(_QWORD *)v51 + 32LL);
          }
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_98:
        if ( StorEtwLoggingEnabled )
        {
          v140 = 0;
          IoGetActivityIdIrp(a2, &v140);
          if ( byte_140177432 < 0 )
            McTemplateK0dud_EtwWriteTransfer(v73, v72, (unsigned int)&v140, v74, 4);
        }
        v48 = v135;
        goto LABEL_102;
      }
      v21 = v19[21];
      v16 = *(unsigned __int8 *)(v21 + 2);
      if ( (_BYTE)v16 == 40 )
        v22 = *(_DWORD *)(v21 + 20);
      else
        v22 = *(unsigned __int8 *)(v21 + 2);
      _InterlockedAdd((volatile signed __int32 *)(v2 + 1396), 1u);
      v23 = v22 - 18;
      if ( v23 && (v24 = v23 - 1) != 0 )
      {
        if ( v24 != 13 )
        {
LABEL_23:
          PerformanceFrequency.LowPart = 1;
          goto LABEL_24;
        }
        RaidPauseUnitQueue(v2);
      }
      else
      {
        RaidPauseAdapterQueue(*(_QWORD *)(v2 + 24));
      }
      v18 = v137;
      goto LABEL_23;
    }
  }
LABEL_176:
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(v5 + 3) = RaidNtStatusToSrbStatus((unsigned int)v8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
      *(_QWORD *)(v2 + 8),
      a2,
      *(_DWORD *)(a2 + 48));
  }
  v106 = *(_QWORD *)(a2 + 184);
  v107 = *(_BYTE *)(v106 + 16) & 3;
  *(_QWORD *)(v106 + 16) = 0;
  v108 = *(_QWORD *)(v2 + 24);
  if ( (v107 & 1) != 0 && (unsigned __int8)RaidUnitCheckAndAcquirePoFx(v2) )
  {
    PoFxIdleComponent(**(_QWORD **)(v2 + 1872), 0, 0);
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 1864));
  }
  if ( v107 >= 2u && *(_QWORD *)(v108 + 5024) )
    RaidAdapterPoFxIdleComponent(v108, 0, 0, v105);
  v47 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v8;
  if ( v47 )
    goto LABEL_250;
  v140 = 0;
  IoGetActivityIdIrp(a2, &v140);
  v110 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v110 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_250;
    v113 = EventNonReadWriteRequestComplete;
    goto LABEL_249;
  }
  if ( *(_BYTE *)v110 != 15 )
  {
    if ( *(_BYTE *)v110 != 27 )
      goto LABEL_250;
    if ( *(_BYTE *)(v110 + 1) == 7 && !*(_DWORD *)(v110 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v111 = *(int **)(a2 + 56);
        if ( v111 )
          v112 = *v111;
        else
          v112 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v112, v110, (unsigned int)&v140, a2, v112, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_250;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_250;
    v113 = EventPnpRequestComplete;
LABEL_249:
    McTemplateK0pd_EtwWriteTransfer(v109, v113, &v140, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_250;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_250;
  v114 = *(_QWORD *)(v110 + 8);
  if ( *(_BYTE *)(v114 + 2) == 40 )
  {
    if ( *(_DWORD *)(v114 + 20) )
      goto LABEL_250;
    v115 = *(_DWORD *)(v114 + 56);
    if ( !v115 )
      goto LABEL_250;
    v116 = 0;
    v117 = 0;
    v118 = 0;
    v119 = 0;
    v120 = 0;
    v121 = 0;
    while ( 1 )
    {
      v109 = *(unsigned int *)(v114 + 4 * v120 + 120);
      if ( (unsigned int)v109 >= 0x80 )
      {
        v122 = *(unsigned int *)(v114 + 16);
        if ( (unsigned int)v109 < (unsigned int)v122 )
        {
          v123 = (unsigned int)v109;
          v124 = *(_DWORD *)(v109 + v114) - 64;
          if ( v124 )
          {
            LODWORD(v109) = v124 - 1;
            if ( (_DWORD)v109 )
            {
              if ( (_DWORD)v109 == 1 )
              {
                LODWORD(v109) = v123 + 40;
                if ( v123 + 40 <= v122 )
                {
                  if ( *(_DWORD *)(v123 + v114 + 12) )
                    v117 = (char *)(v123 + v114 + 32);
                  v119 = *(_BYTE **)(v123 + v114 + 24);
                  goto LABEL_224;
                }
              }
            }
            else
            {
              LODWORD(v109) = v123 + 56;
              if ( v123 + 56 <= v122 )
              {
                v121 = 1;
                if ( *(_BYTE *)(v123 + v114 + 10) )
                  v117 = (char *)(v123 + v114 + 24);
                v118 = *(_BYTE *)(v123 + v114 + 8);
                v119 = *(_BYTE **)(v123 + v114 + 16);
                v116 = *(_BYTE *)(v123 + v114 + 9);
              }
            }
          }
          else
          {
            LODWORD(v109) = v123 + 40;
            if ( v123 + 40 <= v122 )
            {
              if ( *(_BYTE *)(v123 + v114 + 10) )
                v117 = (char *)(v123 + v114 + 24);
              v119 = *(_BYTE **)(v123 + v114 + 16);
LABEL_224:
              v116 = *(_BYTE *)(v123 + v114 + 9);
              v118 = *(_BYTE *)(v123 + v114 + 8);
LABEL_225:
              if ( v117 )
              {
                v125 = *v117;
                goto LABEL_228;
              }
              goto LABEL_250;
            }
          }
          if ( v121 )
            goto LABEL_225;
        }
      }
      v120 = (unsigned int)(v120 + 1);
      if ( (unsigned int)v120 >= v115 )
        goto LABEL_225;
    }
  }
  v125 = *(_BYTE *)(v114 + 72);
  v119 = *(_BYTE **)(v114 + 32);
  v116 = *(_BYTE *)(v114 + 11);
  v118 = *(_BYTE *)(v114 + 4);
  if ( *(_BYTE *)(v114 + 2) )
    goto LABEL_250;
LABEL_228:
  LOBYTE(v109) = v125 - 8;
  if ( (v109 & 0x5D) == 0 )
  {
    v126 = *(_BYTE *)(v114 + 3);
    if ( v126 == 1 || !v119 || !v116 )
      goto LABEL_245;
    LOBYTE(v114) = 0;
    v127 = 0;
    v128 = 0;
    v109 = (unsigned __int64)&v119[v116];
    v129 = v119 + 8;
    if ( (unsigned __int8)((*v119 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v129 <= v109 )
      {
        v127 = v119[2];
        LOBYTE(v114) = v119[1] & 0xF;
        v128 = v119[3];
        goto LABEL_244;
      }
    }
    else if ( (unsigned __int64)v129 <= v109 )
    {
      v130 = v119 + 13;
      LOBYTE(v114) = v119[2] & 0xF;
      v131 = v116;
      if ( (unsigned int)(unsigned __int8)v119[7] + 8 <= v116 )
        v131 = (unsigned __int8)v119[7] + 8;
      v109 = (unsigned __int64)&v119[v131];
      if ( (unsigned __int64)v130 <= v109 )
        v127 = v119[12];
      if ( (unsigned __int64)(v119 + 14) > v109 )
        v128 = 0;
      else
        v128 = *v130;
LABEL_244:
      if ( v9 )
      {
LABEL_246:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v109,
          v114,
          (unsigned int)&v140,
          a2,
          *(_DWORD *)(a2 + 48),
          v126,
          v118,
          v114,
          v127,
          v128,
          a2);
        goto LABEL_250;
      }
LABEL_245:
      LOBYTE(v114) = 0;
      v127 = 0;
      v128 = 0;
      goto LABEL_246;
    }
    v9 = 0;
    goto LABEL_244;
  }
LABEL_250:
  IofCompleteRequest((PIRP)a2, 0);
}

```

## disassembly

```asm
0x1400c5658  mov     [rsp-8+arg_18], rbx
0x1400c565d  push    rbp
0x1400c565e  push    rsi
0x1400c565f  push    rdi
0x1400c5660  push    r12
0x1400c5662  push    r13
0x1400c5664  push    r14
0x1400c5666  push    r15
0x1400c5668  lea     rbp, [rsp-40h]
0x1400c566d  sub     rsp, 140h
0x1400c5674  mov     rax, cs:__security_cookie
0x1400c567b  xor     rax, rsp
0x1400c567e  mov     [rbp+70h+var_40], rax
0x1400c5682  mov     rdi, [rcx+40h]
0x1400c5686  mov     rbx, r8
0x1400c5689  mov     rax, [rdx+0B8h]
0x1400c5690  mov     rcx, rdi
0x1400c5693  mov     rsi, rdx
0x1400c5696  mov     [rbp+70h+var_F0], rdi
0x1400c569a  mov     r13, [rax+8]
0x1400c569e  mov     [rsp+170h+var_F8], r13
0x1400c56a3  call    RaUnitCheckRemoveState
0x1400c56a8  mov     r15d, eax
0x1400c56ab  mov     r14d, 1
0x1400c56b1  test    eax, eax
0x1400c56b3  js      loc_1400C6077
0x1400c56b9  mov     r12, [rdi+18h]
0x1400c56bd  mov     r8b, r14b
0x1400c56c0  mov     rcx, rdi
0x1400c56c3  call    RaUnitAcquireRemoveLock
0x1400c56c8  mov     r15d, eax
0x1400c56cb  test    eax, eax
0x1400c56cd  js      loc_1400C6077
0x1400c56d3  mov     r9, rbx
0x1400c56d6  xor     r8d, r8d
0x1400c56d9  mov     rdx, rsi
0x1400c56dc  mov     rcx, rdi
0x1400c56df  call    RaidUnitClaimIrp
0x1400c56e4  mov     r15d, eax
0x1400c56e7  test    eax, eax
0x1400c56e9  jns     short loc_1400C574D
0x1400c56eb  mov     eax, gs:1A4h
0x1400c56f3  mov     r8d, eax
0x1400c56f6  mov     rax, [rdi+28h]
0x1400c56fa  shl     r8, 6
0x1400c56fe  mov     eax, [r8+rax]
0x1400c5702  jmp     short loc_1400C5717
0x1400c5704  mov     rcx, [rdi+28h]
0x1400c5708  lea     edx, [rax-2]
0x1400c570b  lock cmpxchg [r8+rcx], edx
0x1400c5711  jz      loc_1400C6077
0x1400c5717  test    r14b, al
0x1400c571a  jz      short loc_1400C5704
0x1400c571c  or      eax, 0FFFFFFFFh
0x1400c571f  lock xadd [rdi+408h], eax
0x1400c5727  cmp     eax, r14d
0x1400c572a  jnz     loc_1400C6077
0x1400c5730  lea     rcx, [rdi+208h]; Event
0x1400c5737  xor     r8d, r8d; Wait
0x1400c573a  xor     edx, edx; Increment
0x1400c573c  call    cs:__imp_KeSetEvent
0x1400c5743  nop     dword ptr [rax+rax+00h]
0x1400c5748  jmp     loc_1400C6077
0x1400c574d  mov     rax, [rsi+0B8h]
0x1400c5754  xor     r15d, r15d
0x1400c5757  mov     dword ptr [rsp+170h+PerformanceFrequency], r15d
0x1400c575c  mov     rcx, [rax+8]
0x1400c5760  lea     eax, [r15+60h]
0x1400c5764  lea     edx, [rax-30h]
0x1400c5767  cmp     byte ptr [rcx+2], 28h ; '('
0x1400c576b  cmovnz  eax, edx
0x1400c576e  mov     rdx, [rsp+170h+var_F8]
0x1400c5773  mov     r13, [rax+rcx]
0x1400c5777  movzx   eax, byte ptr [rdx+2]
0x1400c577b  cmp     al, 28h ; '('
0x1400c577d  jnz     short loc_1400C5782
0x1400c577f  mov     eax, [rdx+14h]
0x1400c5782  cmp     eax, 10h
0x1400c5785  jz      short loc_1400C57D2
0x1400c5787  mov     rax, [r13+0A8h]
0x1400c578e  movzx   ecx, byte ptr [rax+2]
0x1400c5792  cmp     cl, 28h ; '('
0x1400c5795  jnz     short loc_1400C579C
0x1400c5797  mov     eax, [rax+14h]
0x1400c579a  jmp     short loc_1400C579E
0x1400c579c  mov     eax, ecx
0x1400c579e  lock add [rdi+574h], r14d
0x1400c57a6  sub     eax, 12h
0x1400c57a9  jz      short loc_1400C57BF
0x1400c57ab  sub     eax, r14d
0x1400c57ae  jz      short loc_1400C57BF
0x1400c57b0  cmp     eax, 0Dh
0x1400c57b3  jnz     short loc_1400C57CD
0x1400c57b5  mov     rcx, rdi
0x1400c57b8  call    RaidPauseUnitQueue
0x1400c57bd  jmp     short loc_1400C57C8
0x1400c57bf  mov     rcx, [rdi+18h]
0x1400c57c3  call    RaidPauseAdapterQueue
0x1400c57c8  mov     rdx, [rsp+170h+var_F8]
0x1400c57cd  mov     dword ptr [rsp+170h+PerformanceFrequency], r14d
0x1400c57d2  movzx   eax, byte ptr [rdx+2]
0x1400c57d6  cmp     al, 28h ; '('
0x1400c57d8  jnz     short loc_1400C57DD
0x1400c57da  mov     eax, [rdx+14h]
0x1400c57dd  cmp     eax, 10h
0x1400c57e0  jnz     loc_1400C58A6
0x1400c57e6  mov     eax, cs:dword_140176178
0x1400c57ec  cmp     eax, 5
0x1400c57ef  jbe     loc_1400C58A6
0x1400c57f5  mov     rdx, 400000000000h
0x1400c57ff  call    _tlgKeywordOn
0x1400c5804  test    al, al
0x1400c5806  jz      loc_1400C58A6
0x1400c580c  lea     rax, [r12+1408h]
0x1400c5814  mov     [rbp+70h+var_98], 10h
0x1400c581c  mov     [rbp+70h+var_A0], rax
0x1400c5820  lea     rdx, byte_1401647B5; int
0x1400c5827  lea     rax, [rdi+838h]
0x1400c582e  mov     [rbp+70h+var_88], 10h
0x1400c5836  mov     [rbp+70h+var_90], rax
0x1400c583a  mov     eax, [r12+38h]
0x1400c583f  mov     dword ptr [rsp+170h+var_108], eax
0x1400c5843  lea     rax, [rsp+170h+var_108]
0x1400c5848  mov     [rbp+70h+var_80], rax
0x1400c584c  mov     al, [rdi+68h]
0x1400c584f  mov     [rsp+170h+var_110], al
0x1400c5853  lea     rax, [rsp+170h+var_110]
0x1400c5858  mov     [rbp+70h+var_70], rax
0x1400c585c  mov     al, [rdi+69h]
0x1400c585f  mov     [rsp+170h+var_10F], al
0x1400c5863  lea     rax, [rsp+170h+var_10F]
0x1400c5868  mov     [rbp+70h+var_60], rax
0x1400c586c  mov     al, [rdi+6Ah]
0x1400c586f  mov     [rsp+170h+var_10E], al
0x1400c5873  lea     rax, [rsp+170h+var_10E]
0x1400c5878  mov     [rbp+70h+var_50], rax
0x1400c587c  lea     rax, [rbp+70h+var_C0]
0x1400c5880  mov     [rsp+170h+var_148], rax; __int64
0x1400c5885  mov     [rsp+170h+var_150], 8; ULONG
0x1400c588d  mov     [rbp+70h+var_78], 4
0x1400c5895  mov     [rbp+70h+var_68], r14
0x1400c5899  mov     [rbp+70h+var_58], r14
0x1400c589d  mov     [rbp+70h+var_48], r14
0x1400c58a1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c58a6  lea     rax, RaidUnitCompleteResetRequest
0x1400c58ad  mov     [r13+290h], rax
0x1400c58b4  cmp     [r12+1152h], r15b
0x1400c58bc  jz      loc_1400C59D5
0x1400c58c2  mov     rdx, [r13+0A8h]
0x1400c58c9  mov     eax, 18h
0x1400c58ce  cmp     byte ptr [rdx+2], 28h ; '('
0x1400c58d2  lea     ecx, [rax-0Ch]
0x1400c58d5  cmovnz  eax, ecx
0x1400c58d8  test    byte ptr [r12+1153h], 4
0x1400c58e1  mov     ebx, [rax+rdx]
0x1400c58e4  jnz     short loc_1400C5918
0x1400c58e6  cmp     [r13+88h], r15
0x1400c58ed  jz      short loc_1400C58FF
0x1400c58ef  mov     rdx, r13
0x1400c58f2  mov     rcx, r12
0x1400c58f5  call    RaidAdapterScatterGatherExecuteBidirectionalRequest
0x1400c58fa  jmp     loc_1400C59E0
0x1400c58ff  test    bl, 0C0h
0x1400c5902  jz      loc_1400C59D5
0x1400c5908  mov     rdx, r13
0x1400c590b  mov     rcx, r12
0x1400c590e  call    RaidAdapterScatterGatherExecute
0x1400c5913  jmp     loc_1400C59E0
0x1400c5918  mov     r9, [r13+68h]
0x1400c591c  shr     ebx, 6
0x1400c591f  and     bl, r14b
0x1400c5922  test    r9, r9
0x1400c5925  jz      short loc_1400C5978
0x1400c5927  lea     rax, [r12+370h]
0x1400c592f  test    rax, rax
0x1400c5932  jz      short loc_1400C5978
0x1400c5934  mov     rcx, [rax]
0x1400c5937  test    rcx, rcx
0x1400c593a  jz      short loc_1400C5978
0x1400c593c  mov     rdx, [rcx+8]
0x1400c5940  test    rdx, rdx
0x1400c5943  jz      short loc_1400C5978
0x1400c5945  cmp     dword ptr [rax+1Ch], 3
0x1400c5949  jl      short loc_1400C5964
0x1400c594b  mov     rax, [rdx+0F0h]
0x1400c5952  test    rax, rax
0x1400c5955  jz      short loc_1400C5964
0x1400c5957  mov     r8b, bl
0x1400c595a  mov     rdx, r9
0x1400c595d  call    _guard_dispatch_icall
0x1400c5962  jmp     short loc_1400C5978
0x1400c5964  mov     r8b, r14b
0x1400c5967  mov     dl, bl
0x1400c5969  mov     rcx, r9
0x1400c596c  call    cs:__imp_KeFlushIoBuffers
0x1400c5973  nop     dword ptr [rax+rax+00h]
0x1400c5978  mov     r9, [r13+88h]
0x1400c597f  test    r9, r9
0x1400c5982  jz      short loc_1400C59D5
0x1400c5984  lea     rax, [r12+370h]
0x1400c598c  test    rax, rax
0x1400c598f  jz      short loc_1400C59D5
0x1400c5991  mov     rcx, [rax]
0x1400c5994  test    rcx, rcx
0x1400c5997  jz      short loc_1400C59D5
0x1400c5999  mov     rdx, [rcx+8]
0x1400c599d  test    rdx, rdx
0x1400c59a0  jz      short loc_1400C59D5
0x1400c59a2  cmp     dword ptr [rax+1Ch], 3
0x1400c59a6  jl      short loc_1400C59C1
0x1400c59a8  mov     rax, [rdx+0F0h]
0x1400c59af  test    rax, rax
0x1400c59b2  jz      short loc_1400C59C1
0x1400c59b4  mov     r8b, bl
0x1400c59b7  mov     rdx, r9
0x1400c59ba  call    _guard_dispatch_icall
0x1400c59bf  jmp     short loc_1400C59D5
0x1400c59c1  mov     r8b, r14b
0x1400c59c4  mov     dl, bl
0x1400c59c6  mov     rcx, r9
0x1400c59c9  call    cs:__imp_KeFlushIoBuffers
0x1400c59d0  nop     dword ptr [rax+rax+00h]
0x1400c59d5  mov     rdx, r13
0x1400c59d8  mov     rcx, r12
0x1400c59db  call    RaidAdapterPostScatterGatherExecute
0x1400c59e0  mov     r15d, eax
0x1400c59e3  test    eax, eax
0x1400c59e5  jns     loc_1400C641F
0x1400c59eb  cmp     dword ptr [rsp+170h+PerformanceFrequency], 0
0x1400c59f0  jz      short loc_1400C5A32
0x1400c59f2  mov     rax, [r13+0A8h]
0x1400c59f9  movzx   ecx, byte ptr [rax+2]
0x1400c59fd  cmp     cl, 28h ; '('
0x1400c5a00  jnz     short loc_1400C5A07
0x1400c5a02  mov     eax, [rax+14h]
0x1400c5a05  jmp     short loc_1400C5A09
0x1400c5a07  mov     eax, ecx
0x1400c5a09  lock dec dword ptr [rdi+574h]
0x1400c5a10  sub     eax, 12h
0x1400c5a13  jz      short loc_1400C5A29
0x1400c5a15  sub     eax, r14d
0x1400c5a18  jz      short loc_1400C5A29
0x1400c5a1a  cmp     eax, 0Dh
0x1400c5a1d  jnz     short loc_1400C5A32
0x1400c5a1f  mov     rcx, rdi
0x1400c5a22  call    RaidResumeAndRestartUnitQueue
0x1400c5a27  jmp     short loc_1400C5A32
0x1400c5a29  mov     rcx, [rdi+18h]
0x1400c5a2d  call    RaidResumeAndRestartAdapterQueues
0x1400c5a32  mov     rax, [rsi+0B8h]
0x1400c5a39  mov     rdi, [rax+8]
0x1400c5a3d  mov     eax, 60h ; '`'
0x1400c5a42  cmp     byte ptr [rdi+2], 28h ; '('
0x1400c5a46  lea     ecx, [rax-30h]
0x1400c5a49  cmovnz  eax, ecx
0x1400c5a4c  mov     r12, [rax+rdi]
0x1400c5a50  test    byte ptr [r12+10h], 2
0x1400c5a56  mov     rbx, [r12+0E0h]
0x1400c5a5e  mov     [rsp+170h+var_108], rbx
0x1400c5a63  jz      loc_1400C5C7B
0x1400c5a69  mov     rax, [rsp+170h+var_108]
0x1400c5a6e  lea     rbx, [r12+30h]
0x1400c5a73  xor     ecx, ecx
0x1400c5a75  xorps   xmm0, xmm0
0x1400c5a78  mov     qword ptr [rbp+70h+LockHandle.OldIrql], rcx
0x1400c5a7c  mov     ecx, [rbx+24h]
0x1400c5a7f  mov     rax, [rax+230h]
0x1400c5a86  shl     rcx, 6
0x1400c5a8a  mov     qword ptr [rbp+70h+var_D0], rax
0x1400c5a8e  movups  xmmword ptr [rbp+70h+LockHandle.LockQueue.Next], xmm0
0x1400c5a92  lea     r13, [rax+40h]
0x1400c5a96  mov     qword ptr [rsp+170h+PerformanceFrequency], rcx
0x1400c5a9b  add     r13, rcx
0x1400c5a9e  call    cs:__imp_KeGetCurrentIrql
0x1400c5aa5  nop     dword ptr [rax+rax+00h]
0x1400c5aaa  lea     rdx, [rbp+70h+LockHandle]; LockHandle
0x1400c5aae  lea     rcx, [r13+28h]; SpinLock
0x1400c5ab2  cmp     al, 2
0x1400c5ab4  jnz     loc_1400C5B80
0x1400c5aba  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400c5ac1  nop     dword ptr [rax+rax+00h]
0x1400c5ac6  mov     al, [rbx-20h]
0x1400c5ac9  test    al, 2
0x1400c5acb  jz      loc_1400C5B6B
0x1400c5ad1  mov     r8, qword ptr [rbp+70h+var_D0]
0x1400c5ad5  and     al, 0FDh
0x1400c5ad7  mov     r10d, [r8]
0x1400c5ada  mov     [rbx-20h], al
0x1400c5add  mov     rcx, [rbx]
0x1400c5ae0  cmp     [rcx+8], rbx
0x1400c5ae4  jnz     loc_1400C5CB7
0x1400c5aea  mov     rax, [rbx+8]
0x1400c5aee  cmp     [rax], rbx
0x1400c5af1  jnz     loc_1400C5CB7
0x1400c5af7  mov     r9, [r13+0]
0x1400c5afb  mov     [rax], rcx
0x1400c5afe  mov     [rcx+8], rax
0x1400c5b02  mov     eax, [rbx+30h]
0x1400c5b05  test    r14b, al
0x1400c5b08  jz      short loc_1400C5B40
  ... truncated ...
```
