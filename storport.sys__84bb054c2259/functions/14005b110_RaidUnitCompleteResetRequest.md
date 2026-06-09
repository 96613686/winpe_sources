# RaidUnitCompleteResetRequest

- ea: `0x14005b110`
- end: `0x14005bcfd`
- name: `RaidUnitCompleteResetRequest`
- size: `3053`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `broker_com_uri`

## callees

- `0x1400016cc`
- `0x140005984`
- `0x140005c50`
- `0x140008258`
- `0x14000befc`
- `0x14000bf40`
- `0x14000e350`
- `0x14000ebfc`
- `0x140012290`
- `0x14001ebe8`
- `0x140046c60`
- `0x140054800`
- `0x14005b110`
- `0x140066e18`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x140071800`
- `0x1400848c4`
- `0x140093144`
- `0x140096fe0`
- `0x1400c9274`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14005b664`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14005b71d`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14005b664`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14005b71d`
- `ntoskrnl!PoFxIdleComponent` at `0x14005b2f2`
- `ntoskrnl!PoFxIdleComponent` at `0x14005b2f2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005b575`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ba16`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005b575`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ba16`
- `ntoskrnl!KeSetEvent` at `0x14005b95a`
- `ntoskrnl!KeSetEvent` at `0x14005b95a`
- `ntoskrnl!IofCompleteRequest` at `0x14005bcd0`
- `ntoskrnl!IofCompleteRequest` at `0x14005bcd0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005b306`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005b306`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b4a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b4a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005b3e1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005b3e1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005b494`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005b494`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005b3c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005b3c5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b54f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b54f`
- `HAL!KeQueryPerformanceCounter` at `0x14005b656`
- `HAL!KeQueryPerformanceCounter` at `0x14005b6f4`
- `HAL!KeQueryPerformanceCounter` at `0x14005b656`
- `HAL!KeQueryPerformanceCounter` at `0x14005b6f4`

## pseudocode

```c
void __fastcall RaidUnitCompleteResetRequest(_QWORD *a1)
{
  __int64 v1; // r13
  __int64 v2; // rax
  __int64 v3; // rsi
  __int64 v4; // r12
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // r15
  int v8; // eax
  int v9; // edx
  int v10; // eax
  __int64 v11; // r8
  char v12; // r14
  __int64 v13; // rcx
  char v14; // al
  __int64 v15; // rax
  unsigned __int8 v16; // bl
  __int64 v17; // rdi
  char v18; // al
  _QWORD *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // r13
  bool v24; // zf
  __int64 v25; // rbx
  __int64 *v26; // rbx
  union _LARGE_INTEGER v27; // rcx
  __int64 v28; // r15
  KIRQL CurrentIrql; // al
  KSPIN_LOCK *v30; // rcx
  char v31; // al
  __int64 v32; // r8
  int v33; // r10d
  __int64 *v34; // rcx
  __int64 **v35; // rax
  __int64 *v36; // r9
  __int64 *v37; // rcx
  __int64 *v38; // rdx
  __int64 **v39; // rax
  char v40; // al
  __int64 v41; // r8
  int v42; // r10d
  __int64 *v43; // rcx
  __int64 **v44; // rax
  __int64 *v45; // r9
  __int64 *v46; // rcx
  __int64 *v47; // rdx
  __int64 **v48; // rax
  __int64 v49; // r15
  int v50; // edx
  int v51; // ecx
  int v52; // r9d
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rcx
  __int64 v58; // rax
  LARGE_INTEGER v59; // rax
  LARGE_INTEGER v60; // rbx
  __int64 v61; // r8
  __int64 v62; // rcx
  unsigned __int64 v63; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v65; // rdx
  unsigned int LowPart; // ecx
  unsigned __int64 v67; // r8
  char v68; // r10
  unsigned __int64 v69; // r9
  __int64 v70; // r15
  unsigned int v71; // ebx
  __int64 v72; // r8
  __int64 v73; // rcx
  __int64 v74; // rdx
  unsigned __int64 v75; // r10
  int v76; // eax
  __int64 v77; // rax
  unsigned __int64 v78; // r8
  signed __int32 v79; // eax
  int v80; // eax
  signed __int32 v81; // ett
  _QWORD *v82; // rbx
  unsigned __int64 v83; // rcx
  __int64 v84; // rdx
  int *v85; // rax
  int v86; // ecx
  __int64 *v87; // rdx
  __int64 v88; // rdx
  unsigned int v89; // r12d
  unsigned __int8 v90; // r10
  char *v91; // r11
  char v92; // bl
  _BYTE *v93; // r9
  char v94; // r13
  unsigned __int64 v95; // rdi
  __int64 v96; // r8
  int v97; // ecx
  char v98; // cl
  char v99; // di
  char v100; // r11
  _BYTE *v101; // rax
  char v102; // r8
  char *v103; // r8
  unsigned int v104; // eax
  char v105; // [rsp+60h] [rbp-A0h] BYREF
  char v106; // [rsp+61h] [rbp-9Fh] BYREF
  char v107; // [rsp+62h] [rbp-9Eh] BYREF
  char v108; // [rsp+63h] [rbp-9Dh] BYREF
  __int64 v109; // [rsp+68h] [rbp-98h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+70h] [rbp-90h] BYREF
  int v111; // [rsp+78h] [rbp-88h]
  _QWORD *v112; // [rsp+80h] [rbp-80h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  __int128 v114; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v115; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v116[18]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = a1[21];
  v2 = 60;
  v3 = a1[20];
  v4 = a1[28];
  *(_QWORD *)&v114 = v1;
  v5 = *(unsigned __int8 *)(v1 + 2);
  v6 = 16;
  v112 = a1;
  if ( (_BYTE)v5 != 40 )
    v2 = 16;
  v7 = *(unsigned int *)(v2 + v1);
  if ( (_BYTE)v5 == 40 )
    v8 = *(_DWORD *)(v1 + 20);
  else
    v8 = v5;
  v111 = v8;
  if ( v8 != 16 )
  {
    if ( (_BYTE)v5 == 40 )
      LODWORD(v5) = *(_DWORD *)(v1 + 20);
    _InterlockedDecrement((volatile signed __int32 *)(v4 + 1396));
    v9 = v5 - 18;
    if ( v9 && (v5 = (unsigned int)(v9 - 1), (_DWORD)v5) )
    {
      if ( (_DWORD)v5 != 13 )
        goto LABEL_15;
      RaidResumeAndRestartUnitQueue(v4);
    }
    else
    {
      RaidResumeAndRestartAdapterQueues(*(_QWORD *)(v4 + 24));
    }
    v6 = 16;
  }
LABEL_15:
  v10 = *(unsigned __int8 *)(v1 + 2);
  if ( (_BYTE)v10 == 40 )
    v10 = *(_DWORD *)(v1 + 20);
  v11 = 0;
  v12 = 1;
  if ( v10 == 16 && (unsigned int)dword_140176178 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL) )
  {
    v13 = *(_QWORD *)(v4 + 24);
    v116[5] = 16;
    v116[7] = 16;
    v116[4] = v13 + 5128;
    v116[6] = v4 + 2104;
    LODWORD(v109) = *(_DWORD *)(v13 + 56);
    v116[8] = (__int64)&v109;
    v105 = *(_BYTE *)(v4 + 104);
    v116[10] = (__int64)&v105;
    v106 = *(_BYTE *)(v4 + 105);
    v116[12] = (__int64)&v106;
    v107 = *(_BYTE *)(v4 + 106);
    v116[14] = (__int64)&v107;
    v14 = *(_BYTE *)(v1 + 3) & 0x3F;
    v116[9] = 4;
    v108 = v14;
    v116[16] = (__int64)&v108;
    v116[11] = 1;
    v116[13] = 1;
    v116[15] = 1;
    v116[17] = 1;
    tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_14016481B, v11, v6, 9u, (__int64)v116);
    v11 = 0;
  }
  v15 = *(_QWORD *)(v3 + 184);
  v16 = *(_BYTE *)(v15 + 16) & 3;
  *(_QWORD *)(v15 + 16) = v11;
  v17 = *(_QWORD *)(v4 + 24);
  if ( (v16 & 1) != 0 )
  {
    v18 = RaidUnitCheckAndAcquirePoFx(v4);
    v11 = 0;
    if ( v18 )
    {
      PoFxIdleComponent(**(_QWORD **)(v4 + 1872), 0, 0);
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v4 + 1864));
      v11 = 0;
    }
  }
  if ( v16 >= 2u && *(_QWORD *)(v17 + 5024) != v11 )
    RaidAdapterPoFxIdleComponent(v17, 0, 0, v6);
  v19 = v112;
  if ( (*((_BYTE *)v112 + 17) & 2) != 0 )
  {
    RaidUnitPoFxIdleComponentFromMiniport(v4, *((unsigned int *)v112 + 187), v11);
    *((_BYTE *)v19 + 17) &= ~2u;
  }
  LOBYTE(a1) = *(_BYTE *)(v1 + 3);
  *(_DWORD *)(v3 + 48) = RaidSrbStatusToNtStatus(a1, v5, v11, v6);
  v20 = *(_QWORD *)(v3 + 184);
  *(_QWORD *)(v3 + 56) = v7;
  v21 = *(_QWORD *)(v20 + 8);
  v22 = 96;
  if ( *(_BYTE *)(v21 + 2) != 40 )
    v22 = 48;
  v23 = *(_QWORD *)(v22 + v21);
  v24 = (*(_BYTE *)(v23 + 16) & 2) == 0;
  v25 = *(_QWORD *)(v23 + 224);
  v109 = v25;
  if ( v24 )
  {
    v49 = 0;
    goto LABEL_69;
  }
  v26 = (__int64 *)(v23 + 48);
  v27.QuadPart = (unsigned __int64)*(unsigned int *)(v23 + 84) << 6;
  *(_QWORD *)&v115 = *(_QWORD *)(v109 + 560);
  memset(&LockHandle, 0, sizeof(LockHandle));
  PerformanceFrequency = v27;
  v28 = v27.QuadPart + v115 + 64;
  CurrentIrql = KeGetCurrentIrql();
  v30 = (KSPIN_LOCK *)(v28 + 40);
  if ( CurrentIrql == 2 )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel(v30, &LockHandle);
    v31 = *(_BYTE *)(v23 + 16);
    if ( (v31 & 2) == 0 )
    {
LABEL_47:
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      goto LABEL_62;
    }
    v32 = v115;
    v33 = *(_DWORD *)v115;
    *(_BYTE *)(v23 + 16) = v31 & 0xFD;
    v34 = (__int64 *)*v26;
    if ( *(__int64 **)(*v26 + 8) == v26 )
    {
      v35 = *(__int64 ***)(v23 + 56);
      if ( *v35 == v26 )
      {
        v36 = *(__int64 **)v28;
        *v35 = v34;
        v34[1] = (__int64)v35;
        if ( (*(_DWORD *)(v23 + 96) & 1) == 0 )
        {
LABEL_42:
          if ( (v33 & 4) == 0 && v36 == v26 )
          {
            if ( *(_QWORD *)v28 == v28 )
              *(_DWORD *)(v28 + 48) = -1;
            else
              *(_DWORD *)(PerformanceFrequency.QuadPart + v32 + 112) = *(_DWORD *)(*(_QWORD *)v28 + 32LL);
          }
          goto LABEL_47;
        }
        v37 = (__int64 *)(v23 + 64);
        if ( *(_QWORD *)(v28 + 32) == v23 + 64 )
          *(_QWORD *)(v28 + 32) = *v37;
        v38 = (__int64 *)*v37;
        if ( *(__int64 **)(*v37 + 8) == v37 )
        {
          v39 = *(__int64 ***)(v23 + 72);
          if ( *v39 == v37 )
          {
            *v39 = v38;
            v38[1] = (__int64)v39;
            *(_DWORD *)(v23 + 96) &= ~1u;
            goto LABEL_42;
          }
        }
      }
    }
LABEL_67:
    __fastfail(3u);
  }
  KeAcquireInStackQueuedSpinLock(v30, &LockHandle);
  v40 = *(_BYTE *)(v23 + 16);
  if ( (v40 & 2) != 0 )
  {
    v41 = v115;
    v42 = *(_DWORD *)v115;
    *(_BYTE *)(v23 + 16) = v40 & 0xFD;
    v43 = (__int64 *)*v26;
    if ( *(__int64 **)(*v26 + 8) != v26 )
      goto LABEL_67;
    v44 = *(__int64 ***)(v23 + 56);
    if ( *v44 != v26 )
      goto LABEL_67;
    v45 = *(__int64 **)v28;
    *v44 = v43;
    v43[1] = (__int64)v44;
    if ( (*(_DWORD *)(v23 + 96) & 1) != 0 )
    {
      v46 = (__int64 *)(v23 + 64);
      if ( *(_QWORD *)(v28 + 32) == v23 + 64 )
        *(_QWORD *)(v28 + 32) = *v46;
      v47 = (__int64 *)*v46;
      if ( *(__int64 **)(*v46 + 8) != v46 )
        goto LABEL_67;
      v48 = *(__int64 ***)(v23 + 72);
      if ( *v48 != v46 )
        goto LABEL_67;
      *v48 = v47;
      v47[1] = (__int64)v48;
      *(_DWORD *)(v23 + 96) &= ~1u;
    }
    if ( (v42 & 4) == 0 && v45 == v26 )
    {
      if ( *(_QWORD *)v28 == v28 )
        *(_DWORD *)(PerformanceFrequency.QuadPart + v41 + 112) = -1;
      else
        *(_DWORD *)(PerformanceFrequency.QuadPart + v41 + 112) = *(_DWORD *)(*(_QWORD *)v28 + 32LL);
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_62:
  v49 = 0;
  if ( StorEtwLoggingEnabled )
  {
    v115 = 0;
    IoGetActivityIdIrp(v3, &v115);
    if ( byte_140177432 < 0 )
      McTemplateK0dud_EtwWriteTransfer(v51, v50, (unsigned int)&v115, v52, 4);
  }
  v25 = v109;
LABEL_69:
  StorUnmapSenseInfo(v23, *(_QWORD *)(*(_QWORD *)(v25 + 24) + 8LL));
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v54, v53, v55, v56) )
  {
    v58 = *(_QWORD *)(v25 + 3608);
    if ( !v58 || !*(_QWORD *)(v58 + 112) )
    {
      v57 = *(_QWORD *)(v25 + 24);
      if ( !*(_QWORD *)(v57 + 5680) )
        goto LABEL_78;
      goto LABEL_77;
    }
LABEL_75:
    RaidReleaseNvmeIceKeyResources(v25, v23);
    goto LABEL_78;
  }
  v57 = *(_QWORD *)(v25 + 24);
  if ( !*(_QWORD *)(v57 + 5688) )
    goto LABEL_78;
  if ( (*(_BYTE *)(v57 + 112) & 0x10) != 0 )
    goto LABEL_75;
LABEL_77:
  RaidAdapterReleaseCryptoKeyResources(v57, v23);
LABEL_78:
  if ( *(_BYTE *)(v21 + 2) == 40 )
  {
    if ( (*(_BYTE *)(v23 + 16) & 0x40) != 0 )
    {
      PerformanceFrequency.QuadPart = 1;
      if ( v21 )
      {
        v49 = *(_QWORD *)(v23 + 752);
        if ( v49 )
        {
          if ( UseQPCTime )
            v59 = KeQueryPerformanceCounter(&PerformanceFrequency);
          else
            v59.QuadPart = KeQueryUnbiasedInterruptTime();
          v60 = v59;
          *(_BYTE *)(v49 + 3) = *(_BYTE *)(v21 + 3);
          *(_DWORD *)(v49 + 12) = *(_DWORD *)(v21 + 24);
          if ( (*(_DWORD *)(v21 + 24) & 0x40) != 0 )
            *(_DWORD *)(v49 + 16) = *(_DWORD *)(v21 + 60);
          if ( *(_BYTE *)(v21 + 3) == 48 )
            *(_DWORD *)(v49 + 64) = *(_DWORD *)(v21 + 44);
          if ( !*(_DWORD *)(v21 + 20) )
          {
            v61 = 0;
            if ( *(_DWORD *)(v21 + 56) )
            {
              while ( 1 )
              {
                v62 = *(unsigned int *)(v21 + 4 * v61 + 120);
                if ( (unsigned int)v62 >= 0x80 )
                {
                  v63 = *(unsigned int *)(v21 + 16);
                  if ( (unsigned int)v62 <= (unsigned int)v63 && *(_DWORD *)(v62 + v21) == 64 && v62 + 40 <= v63 )
                    break;
                }
                v61 = (unsigned int)(v61 + 1);
                if ( (unsigned int)v61 >= *(_DWORD *)(v21 + 56) )
                  goto LABEL_96;
              }
              *(_BYTE *)(v49 + 4) = *(_BYTE *)((unsigned int)v62 + v21 + 8);
              *(_QWORD *)(v49 + 32) = *(_QWORD *)((unsigned int)v62 + v21 + 16);
              *(_BYTE *)(v49 + 11) = *(_BYTE *)((unsigned int)v62 + v21 + 9);
            }
            else
            {
LABEL_96:
              *(_BYTE *)(v49 + 3) = 48;
              *(_DWORD *)(v49 + 64) = -1073741811;
            }
          }
          v49 = 0;
          if ( UseQPCTime )
            PerformanceCounter = KeQueryPerformanceCounter(0);
          else
            PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
          if ( PerformanceCounter.QuadPart <= 0 || PerformanceCounter.QuadPart >= v60.QuadPart )
            v67 = PerformanceCounter.QuadPart - v60.QuadPart;
          else
            v67 = PerformanceCounter.QuadPart - v60.QuadPart - 1;
          if ( UseQPCTime )
          {
            LowPart = PerformanceFrequency.LowPart;
            v68 = 0;
            if ( PerformanceFrequency.QuadPart && v67 )
            {
              v69 = 1000 * (v67 % PerformanceFrequency.QuadPart);
              v67 = v69 / PerformanceFrequency.QuadPart + 1000 * (v67 / PerformanceFrequency.QuadPart);
              v65.QuadPart = 10000 * (v69 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart;
              v68 = 10000 * (v69 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart + 16 * v67;
            }
          }
          else
          {
            v68 = v67;
          }
          if ( (Microsoft_Windows_StorPortEnableBits & 0x40) != 0 )
            McTemplateK0zx_EtwWriteTransfer(
              LowPart,
              v65.LowPart,
              v67,
              (unsigned int)L"Translate STORAGE_REQUEST_BLOCK result",
              v68);
          v25 = v109;
        }
      }
      *(_QWORD *)(*(_QWORD *)(v23 + 752) + 48LL) = *(_QWORD *)(v23 + 176);
      *(_QWORD *)(*(_QWORD *)(v23 + 752) + 24LL) = *(_QWORD *)(v23 + 184);
      *(_QWORD *)(*(_QWORD *)(v23 + 752) + 56LL) = v49;
      *(_QWORD *)(*(_QWORD *)(v23 + 752) + 40LL) = v49;
      *(_QWORD *)(*(_QWORD *)(v3 + 184) + 8LL) = *(_QWORD *)(v23 + 752);
      *(_BYTE *)(v23 + 16) &= ~0x40u;
      *(_QWORD *)(v23 + 752) = v49;
    }
    else
    {
      *(_QWORD *)(v21 + 96) = 0;
      *(_QWORD *)(v21 + 64) = *(_QWORD *)(v23 + 184);
      *(_QWORD *)(v21 + 104) = 0;
      v70 = *(_QWORD *)(v23 + 192);
      if ( v70 && (*(_BYTE *)(v21 + 24) & 0xC0) == 0xC0 )
      {
        v71 = *(_DWORD *)(v21 + 56);
        if ( v71 )
        {
          v72 = 0;
          while ( 1 )
          {
            v73 = *(unsigned int *)(v21 + 4 * v72 + 120);
            v74 = 0;
            if ( (unsigned int)v73 >= 0x80 )
            {
              v75 = *(unsigned int *)(v21 + 16);
              if ( (unsigned int)v73 <= (unsigned int)v75 && *(_DWORD *)(v73 + v21) == 1 && v73 + 24 <= v75 )
                break;
            }
            v72 = (unsigned int)(v72 + 1);
            if ( (unsigned int)v72 >= v71 )
              goto LABEL_125;
          }
          v74 = v73 + v21;
LABEL_125:
          v25 = v109;
          if ( v74 )
            *(_QWORD *)(v74 + 16) = v70;
        }
        else
        {
          v25 = v109;
        }
      }
      v76 = *(_DWORD *)(v21 + 24);
      if ( (v76 & 0x2000000) != 0 )
        *(_DWORD *)(v21 + 24) = v76 & 0xFDFFFFFF;
      v49 = 0;
    }
  }
  else
  {
    *(_QWORD *)(v21 + 48) = *(_QWORD *)(v23 + 176);
    *(_QWORD *)(v21 + 24) = *(_QWORD *)(v23 + 184);
    v80 = *(_DWORD *)(v21 + 12);
    *(_QWORD *)(v21 + 56) = 0;
    *(_QWORD *)(v21 + 40) = 0;
    if ( (v80 & 0x2000000) != 0 )
      *(_DWORD *)(v21 + 12) = v80 & 0xFDFFFFFF;
  }
  RaidXrbDeallocateResources(v23, 1);
  v77 = 24;
  if ( *(_BYTE *)(v21 + 2) != 40 )
    v77 = 12;
  if ( (*(_DWORD *)(v77 + v21) & 0x4000) == 0 )
  {
    v78 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v79 = *(_DWORD *)(v78 + *(_QWORD *)(v25 + 40));
    while ( (v79 & 1) == 0 )
    {
      v81 = v79;
      v79 = _InterlockedCompareExchange((volatile signed __int32 *)(v78 + *(_QWORD *)(v25 + 40)), v79 - 2, v79);
      if ( v81 == v79 )
        goto LABEL_141;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v25 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v25 + 520), 0, 0);
  }
LABEL_141:
  if ( v111 == 16 )
  {
    v82 = v112;
    RaidXrbDeallocateResources(v112, 1);
    StorFreeContiguousIoResources(*(_QWORD *)(v4 + 24), v82 - 6);
  }
  else
  {
    *(_DWORD *)(v4 + 1856) = v49;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
      v4,
      v3,
      *(_DWORD *)(v3 + 48));
  }
  if ( (qword_140176450 & 0x10) != 0 )
    RaidLogRequestComplete(*(_QWORD *)(v4 + 24), v3, v114);
  v24 = StorEtwLoggingEnabled == (char)v49;
  *(_BYTE *)(v3 + 141) = -84;
  if ( !v24 )
  {
    v114 = 0;
    IoGetActivityIdIrp(v3, &v114);
    v84 = *(_QWORD *)(v3 + 184);
    if ( *(_BYTE *)v84 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_214;
      v87 = EventNonReadWriteRequestComplete;
      goto LABEL_213;
    }
    if ( *(_BYTE *)v84 != 15 )
    {
      if ( *(_BYTE *)v84 != 27 )
        goto LABEL_214;
      if ( *(_BYTE *)(v84 + 1) == 7 && *(_DWORD *)(v84 + 8) == (_DWORD)v49 )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v85 = *(int **)(v3 + 56);
          if ( v85 )
            v86 = *v85;
          else
            v86 = v49;
          McTemplateK0pqd_EtwWriteTransfer(v86, v84, (unsigned int)&v114, v3, v86, *(_DWORD *)(v3 + 48));
        }
        goto LABEL_214;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_214;
      v87 = EventPnpRequestComplete;
LABEL_213:
      McTemplateK0pd_EtwWriteTransfer(v83, v87, &v114, v3, *(_DWORD *)(v3 + 48));
      goto LABEL_214;
    }
    if ( byte_140177431 >= (char)v49 )
      goto LABEL_214;
    v88 = *(_QWORD *)(v84 + 8);
    if ( *(_BYTE *)(v88 + 2) != 40 )
    {
      v98 = *(_BYTE *)(v88 + 72);
      v93 = *(_BYTE **)(v88 + 32);
      v90 = *(_BYTE *)(v88 + 11);
      v92 = *(_BYTE *)(v88 + 4);
      if ( *(_BYTE *)(v88 + 2) )
        goto LABEL_214;
LABEL_192:
      LOBYTE(v83) = v98 - 8;
      if ( (v83 & 0x5D) != 0 )
        goto LABEL_214;
      v99 = *(_BYTE *)(v88 + 3);
      if ( v99 == 1 || !v93 || !v90 )
        goto LABEL_209;
      LOBYTE(v88) = v49;
      v83 = (unsigned __int64)&v93[v90];
      v100 = v49;
      v101 = v93 + 8;
      v102 = v49;
      if ( (unsigned __int8)((*v93 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v101 <= v83 )
        {
          v100 = v93[2];
          LOBYTE(v88) = v93[1] & 0xF;
          v102 = v93[3];
          goto LABEL_208;
        }
      }
      else if ( (unsigned __int64)v101 <= v83 )
      {
        v103 = v93 + 13;
        LOBYTE(v88) = v93[2] & 0xF;
        v104 = v90;
        if ( (unsigned int)(unsigned __int8)v93[7] + 8 <= v90 )
          v104 = (unsigned __int8)v93[7] + 8;
        v83 = (unsigned __int64)&v93[v104];
        if ( (unsigned __int64)v103 <= v83 )
          v100 = v93[12];
        if ( (unsigned __int64)(v93 + 14) > v83 )
          v102 = v49;
        else
          v102 = *v103;
LABEL_208:
        if ( v12 )
        {
LABEL_210:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v83,
            v88,
            (unsigned int)&v114,
            v3,
            *(_DWORD *)(v3 + 48),
            v99,
            v92,
            v88,
            v100,
            v102,
            v3);
          goto LABEL_214;
        }
LABEL_209:
        LOBYTE(v88) = v49;
        v100 = v49;
        v102 = v49;
        goto LABEL_210;
      }
      v12 = v49;
      goto LABEL_208;
    }
    if ( *(_DWORD *)(v88 + 20) == (_DWORD)v49 )
    {
      v89 = *(_DWORD *)(v88 + 56);
      if ( v89 )
      {
        v90 = v49;
        v91 = (char *)v49;
        v92 = v49;
        v93 = (_BYTE *)v49;
        v94 = 0;
        do
        {
          v83 = *(unsigned int *)(v88 + 4LL * (unsigned int)v49 + 120);
          if ( (unsigned int)v83 >= 0x80 )
          {
            v95 = *(unsigned int *)(v88 + 16);
            if ( (unsigned int)v83 < (unsigned int)v95 )
            {
              v96 = (unsigned int)v83;
              v97 = *(_DWORD *)(v88 + v83) - 64;
              if ( v97 )
              {
                LODWORD(v83) = v97 - 1;
                if ( (_DWORD)v83 )
                {
                  if ( (_DWORD)v83 == 1 )
                  {
                    LODWORD(v83) = v96 + 40;
                    if ( v96 + 40 <= v95 )
                    {
                      LOBYTE(v49) = 0;
                      if ( *(_DWORD *)(v88 + v96 + 12) )
                        v91 = (char *)(v96 + v88 + 32);
                      v93 = *(_BYTE **)(v88 + v96 + 24);
LABEL_177:
                      v92 = *(_BYTE *)(v88 + v96 + 8);
                      v90 = *(_BYTE *)(v88 + v96 + 9);
                      goto LABEL_186;
                    }
                  }
                }
                else
                {
                  LODWORD(v83) = v96 + 56;
                  if ( v96 + 56 <= v95 )
                  {
                    v94 = 1;
                    if ( *(_BYTE *)(v88 + v96 + 10) )
                      v91 = (char *)(v96 + v88 + 24);
                    v92 = *(_BYTE *)(v88 + v96 + 8);
                    v93 = *(_BYTE **)(v88 + v96 + 16);
                    v90 = *(_BYTE *)(v88 + v96 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v83) = v96 + 40;
                if ( v96 + 40 <= v95 )
                {
                  LOBYTE(v49) = 0;
                  if ( *(_BYTE *)(v88 + v96 + 10) )
                    v91 = (char *)(v96 + v88 + 24);
                  v93 = *(_BYTE **)(v88 + v96 + 16);
                  goto LABEL_177;
                }
              }
              if ( v94 )
                break;
            }
          }
          LODWORD(v49) = v49 + 1;
        }
        while ( (unsigned int)v49 < v89 );
        LOBYTE(v49) = 0;
LABEL_186:
        if ( v91 )
        {
          v98 = *v91;
          goto LABEL_192;
        }
      }
    }
  }
LABEL_214:
  IofCompleteRequest((PIRP)v3, 0);
}

```

## disassembly

```asm
0x14005b110  push    rbp
0x14005b112  push    rbx
0x14005b113  push    rsi
0x14005b114  push    rdi
0x14005b115  push    r12
0x14005b117  push    r13
0x14005b119  push    r14
0x14005b11b  push    r15
0x14005b11d  lea     rbp, [rsp-68h]
0x14005b122  sub     rsp, 168h
0x14005b129  mov     rax, cs:__security_cookie
0x14005b130  xor     rax, rsp
0x14005b133  mov     [rbp+0A0h+var_50], rax
0x14005b137  mov     r13, [rcx+0A8h]
0x14005b13e  mov     eax, 3Ch ; '<'
0x14005b143  mov     rsi, [rcx+0A0h]
0x14005b14a  mov     bl, 28h ; '('
0x14005b14c  mov     r12, [rcx+0E0h]
0x14005b153  mov     qword ptr [rbp+0A0h+var_100], r13
0x14005b157  movzx   edx, byte ptr [r13+2]
0x14005b15c  lea     r9d, [rax-2Ch]
0x14005b160  cmp     dl, bl
0x14005b162  mov     [rbp+0A0h+var_120], rcx
0x14005b166  cmovnz  eax, r9d
0x14005b16a  mov     r15d, [rax+r13]
0x14005b16e  jnz     short loc_14005B176
0x14005b170  mov     eax, [r13+14h]
0x14005b174  jmp     short loc_14005B178
0x14005b176  mov     eax, edx
0x14005b178  mov     [rsp+1A0h+var_128], eax
0x14005b17c  cmp     eax, r9d
0x14005b17f  jz      short loc_14005B1BB
0x14005b181  cmp     dl, bl
0x14005b183  jnz     short loc_14005B189
0x14005b185  mov     edx, [r13+14h]
0x14005b189  lock dec dword ptr [r12+574h]
0x14005b192  sub     edx, 12h
0x14005b195  jz      short loc_14005B1AB
0x14005b197  sub     edx, 1
0x14005b19a  jz      short loc_14005B1AB
0x14005b19c  cmp     edx, 0Dh
0x14005b19f  jnz     short loc_14005B1BB
0x14005b1a1  mov     rcx, r12
0x14005b1a4  call    RaidResumeAndRestartUnitQueue
0x14005b1a9  jmp     short loc_14005B1B5
0x14005b1ab  mov     rcx, [r12+18h]
0x14005b1b0  call    RaidResumeAndRestartAdapterQueues
0x14005b1b5  mov     r9d, 10h
0x14005b1bb  movzx   eax, byte ptr [r13+2]
0x14005b1c0  cmp     al, bl
0x14005b1c2  jnz     short loc_14005B1C8
0x14005b1c4  mov     eax, [r13+14h]
0x14005b1c8  xor     r8d, r8d
0x14005b1cb  lea     r14d, [r8+1]
0x14005b1cf  cmp     eax, r9d
0x14005b1d2  jnz     loc_14005B2BB
0x14005b1d8  mov     eax, cs:dword_140176178
0x14005b1de  cmp     eax, 5
0x14005b1e1  jbe     loc_14005B2BB
0x14005b1e7  mov     rdx, 400000000000h
0x14005b1f1  call    _tlgKeywordOn
0x14005b1f6  test    al, al
0x14005b1f8  jz      loc_14005B2BB
0x14005b1fe  mov     rcx, [r12+18h]; int
0x14005b203  lea     rdx, byte_14016481B; int
0x14005b20a  mov     [rbp+0A0h+var_B8], 10h
0x14005b212  mov     [rbp+0A0h+var_A8], 10h
0x14005b21a  lea     rax, [rcx+1408h]
0x14005b221  mov     [rbp+0A0h+var_C0], rax
0x14005b225  lea     rax, [r12+838h]
0x14005b22d  mov     [rbp+0A0h+var_B0], rax
0x14005b231  mov     eax, [rcx+38h]
0x14005b234  mov     dword ptr [rsp+1A0h+var_138], eax
0x14005b238  lea     rax, [rsp+1A0h+var_138]
0x14005b23d  mov     [rbp+0A0h+var_A0], rax
0x14005b241  mov     al, [r12+68h]
0x14005b246  mov     [rsp+1A0h+var_140], al
0x14005b24a  lea     rax, [rsp+1A0h+var_140]
0x14005b24f  mov     [rbp+0A0h+var_90], rax
0x14005b253  mov     al, [r12+69h]
0x14005b258  mov     [rsp+1A0h+var_13F], al
0x14005b25c  lea     rax, [rsp+1A0h+var_13F]
0x14005b261  mov     [rbp+0A0h+var_80], rax
0x14005b265  mov     al, [r12+6Ah]
0x14005b26a  mov     [rsp+1A0h+var_13E], al
0x14005b26e  lea     rax, [rsp+1A0h+var_13E]
0x14005b273  mov     [rbp+0A0h+var_70], rax
0x14005b277  mov     al, [r13+3]
0x14005b27b  and     al, 3Fh
0x14005b27d  mov     [rbp+0A0h+var_98], 4
0x14005b285  mov     [rsp+1A0h+var_13D], al
0x14005b289  lea     rax, [rsp+1A0h+var_13D]
0x14005b28e  mov     [rbp+0A0h+var_60], rax
0x14005b292  lea     rax, [rbp+0A0h+var_E0]
0x14005b296  mov     [rsp+1A0h+var_178], rax; __int64
0x14005b29b  mov     [rsp+1A0h+var_180], 9; ULONG
0x14005b2a3  mov     [rbp+0A0h+var_88], r14
0x14005b2a7  mov     [rbp+0A0h+var_78], r14
0x14005b2ab  mov     [rbp+0A0h+var_68], r14
0x14005b2af  mov     [rbp+0A0h+var_58], r14
0x14005b2b3  call    _tlgWriteTransfer_EtwWriteTransfer
0x14005b2b8  xor     r8d, r8d
0x14005b2bb  mov     rax, [rsi+0B8h]
0x14005b2c2  mov     bl, [rax+10h]
0x14005b2c5  and     bl, 3
0x14005b2c8  mov     [rax+10h], r8
0x14005b2cc  mov     rdi, [r12+18h]
0x14005b2d1  test    r14b, bl
0x14005b2d4  jz      short loc_14005B315
0x14005b2d6  mov     rcx, r12
0x14005b2d9  call    RaidUnitCheckAndAcquirePoFx
0x14005b2de  xor     r8d, r8d
0x14005b2e1  test    al, al
0x14005b2e3  jz      short loc_14005B315
0x14005b2e5  mov     rcx, [r12+750h]
0x14005b2ed  xor     edx, edx
0x14005b2ef  mov     rcx, [rcx]
0x14005b2f2  call    cs:__imp_PoFxIdleComponent
0x14005b2f9  nop     dword ptr [rax+rax+00h]
0x14005b2fe  mov     rcx, [r12+748h]; RunRefCacheAware
0x14005b306  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14005b30d  nop     dword ptr [rax+rax+00h]
0x14005b312  xor     r8d, r8d
0x14005b315  cmp     bl, 2
0x14005b318  jb      short loc_14005B330
0x14005b31a  cmp     [rdi+13A0h], r8
0x14005b321  jz      short loc_14005B330
0x14005b323  xor     r8d, r8d
0x14005b326  xor     edx, edx
0x14005b328  mov     rcx, rdi
0x14005b32b  call    RaidAdapterPoFxIdleComponent
0x14005b330  mov     rbx, [rbp+0A0h+var_120]
0x14005b334  test    byte ptr [rbx+11h], 2
0x14005b338  jz      short loc_14005B34C
0x14005b33a  mov     edx, [rbx+2ECh]
0x14005b340  mov     rcx, r12
0x14005b343  call    RaidUnitPoFxIdleComponentFromMiniport
0x14005b348  and     byte ptr [rbx+11h], 0FDh
0x14005b34c  mov     cl, [r13+3]
0x14005b350  call    RaidSrbStatusToNtStatus
0x14005b355  mov     [rsi+30h], eax
0x14005b358  mov     rax, [rsi+0B8h]
0x14005b35f  mov     [rsi+38h], r15
0x14005b363  mov     rdi, [rax+8]
0x14005b367  mov     eax, 60h ; '`'
0x14005b36c  cmp     byte ptr [rdi+2], 28h ; '('
0x14005b370  lea     ecx, [rax-30h]
0x14005b373  cmovnz  eax, ecx
0x14005b376  mov     r13, [rax+rdi]
0x14005b37a  test    byte ptr [r13+10h], 2
0x14005b37f  mov     rbx, [r13+0E0h]
0x14005b386  mov     [rsp+1A0h+var_138], rbx
0x14005b38b  jz      loc_14005B5B0
0x14005b391  mov     rax, [rsp+1A0h+var_138]
0x14005b396  lea     rbx, [r13+30h]
0x14005b39a  xor     ecx, ecx
0x14005b39c  xorps   xmm0, xmm0
0x14005b39f  mov     qword ptr [rbp+0A0h+LockHandle.OldIrql], rcx
0x14005b3a3  mov     ecx, [rbx+24h]
0x14005b3a6  mov     rax, [rax+230h]
0x14005b3ad  shl     rcx, 6
0x14005b3b1  mov     qword ptr [rbp+0A0h+var_F0], rax
0x14005b3b5  movups  xmmword ptr [rbp+0A0h+LockHandle.LockQueue.Next], xmm0
0x14005b3b9  lea     r15, [rax+40h]
0x14005b3bd  mov     qword ptr [rsp+1A0h+PerformanceFrequency], rcx
0x14005b3c2  add     r15, rcx
0x14005b3c5  call    cs:__imp_KeGetCurrentIrql
0x14005b3cc  nop     dword ptr [rax+rax+00h]
0x14005b3d1  lea     rdx, [rbp+0A0h+LockHandle]; LockHandle
0x14005b3d5  lea     rcx, [r15+28h]; SpinLock
0x14005b3d9  cmp     al, 2
0x14005b3db  jnz     loc_14005B4A5
0x14005b3e1  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005b3e8  nop     dword ptr [rax+rax+00h]
0x14005b3ed  mov     al, [rbx-20h]
0x14005b3f0  test    al, 2
0x14005b3f2  jz      loc_14005B490
0x14005b3f8  mov     r8, qword ptr [rbp+0A0h+var_F0]
0x14005b3fc  and     al, 0FDh
0x14005b3fe  mov     r10d, [r8]
0x14005b401  mov     [rbx-20h], al
0x14005b404  mov     rcx, [rbx]
0x14005b407  cmp     [rcx+8], rbx
0x14005b40b  jnz     loc_14005B5A9
0x14005b411  mov     rax, [rbx+8]
0x14005b415  cmp     [rax], rbx
0x14005b418  jnz     loc_14005B5A9
0x14005b41e  mov     r9, [r15]
0x14005b421  mov     [rax], rcx
0x14005b424  mov     [rcx+8], rax
0x14005b428  mov     eax, [rbx+30h]
0x14005b42b  test    r14b, al
0x14005b42e  jz      short loc_14005B466
0x14005b430  lea     rcx, [rbx+10h]
0x14005b434  cmp     [r15+20h], rcx
0x14005b438  jnz     short loc_14005B441
0x14005b43a  mov     rax, [rcx]
0x14005b43d  mov     [r15+20h], rax
0x14005b441  mov     rdx, [rcx]
0x14005b444  cmp     [rdx+8], rcx
0x14005b448  jnz     loc_14005B5A9
0x14005b44e  mov     rax, [rcx+8]
0x14005b452  cmp     [rax], rcx
0x14005b455  jnz     loc_14005B5A9
0x14005b45b  mov     [rax], rdx
0x14005b45e  mov     [rdx+8], rax
0x14005b462  and     dword ptr [rbx+30h], 0FFFFFFFEh
0x14005b466  test    r10b, 4
0x14005b46a  jnz     short loc_14005B490
0x14005b46c  cmp     r9, rbx
0x14005b46f  jnz     short loc_14005B490
0x14005b471  mov     rax, [r15]
0x14005b474  cmp     rax, r15
0x14005b477  jnz     short loc_14005B483
0x14005b479  mov     dword ptr [r15+30h], 0FFFFFFFFh
0x14005b481  jmp     short loc_14005B490
0x14005b483  mov     rcx, qword ptr [rsp+1A0h+PerformanceFrequency]
0x14005b488  mov     eax, [rax+20h]
0x14005b48b  mov     [rcx+r8+70h], eax
0x14005b490  lea     rcx, [rbp+0A0h+LockHandle]; LockHandle
0x14005b494  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005b49b  nop     dword ptr [rax+rax+00h]
0x14005b4a0  jmp     loc_14005B55B
0x14005b4a5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005b4ac  nop     dword ptr [rax+rax+00h]
0x14005b4b1  mov     al, [rbx-20h]
0x14005b4b4  test    al, 2
0x14005b4b6  jz      loc_14005B54B
0x14005b4bc  mov     r8, qword ptr [rbp+0A0h+var_F0]
0x14005b4c0  and     al, 0FDh
0x14005b4c2  mov     r10d, [r8]
0x14005b4c5  mov     [rbx-20h], al
0x14005b4c8  mov     rcx, [rbx]
0x14005b4cb  cmp     [rcx+8], rbx
0x14005b4cf  jnz     loc_14005B5A9
0x14005b4d5  mov     rax, [rbx+8]
0x14005b4d9  cmp     [rax], rbx
0x14005b4dc  jnz     loc_14005B5A9
0x14005b4e2  mov     r9, [r15]
0x14005b4e5  mov     [rax], rcx
0x14005b4e8  mov     [rcx+8], rax
0x14005b4ec  mov     eax, [rbx+30h]
0x14005b4ef  test    r14b, al
0x14005b4f2  jz      short loc_14005B52A
0x14005b4f4  lea     rcx, [rbx+10h]
0x14005b4f8  cmp     [r15+20h], rcx
0x14005b4fc  jnz     short loc_14005B505
0x14005b4fe  mov     rax, [rcx]
0x14005b501  mov     [r15+20h], rax
0x14005b505  mov     rdx, [rcx]
0x14005b508  cmp     [rdx+8], rcx
0x14005b50c  jnz     loc_14005B5A9
0x14005b512  mov     rax, [rcx+8]
0x14005b516  cmp     [rax], rcx
0x14005b519  jnz     loc_14005B5A9
0x14005b51f  mov     [rax], rdx
0x14005b522  mov     [rdx+8], rax
0x14005b526  and     dword ptr [rbx+30h], 0FFFFFFFEh
0x14005b52a  test    r10b, 4
0x14005b52e  jnz     short loc_14005B54B
0x14005b530  cmp     r9, rbx
0x14005b533  jnz     short loc_14005B54B
0x14005b535  mov     rax, [r15]
0x14005b538  mov     rcx, qword ptr [rsp+1A0h+PerformanceFrequency]
0x14005b53d  cmp     rax, r15
0x14005b540  jnz     short loc_14005B59F
0x14005b542  mov     dword ptr [rcx+r8+70h], 0FFFFFFFFh
0x14005b54b  lea     rcx, [rbp+0A0h+LockHandle]; LockHandle
0x14005b54f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b556  nop     dword ptr [rax+rax+00h]
0x14005b55b  xor     r15d, r15d
0x14005b55e  cmp     cs:StorEtwLoggingEnabled, r15b
0x14005b565  jz      short loc_14005B598
0x14005b567  xorps   xmm0, xmm0
0x14005b56a  lea     rdx, [rbp+0A0h+var_F0]
0x14005b56e  mov     rcx, rsi
0x14005b571  movups  [rbp+0A0h+var_F0], xmm0
0x14005b575  call    cs:__imp_IoGetActivityIdIrp
0x14005b57c  nop     dword ptr [rax+rax+00h]
0x14005b581  cmp     cs:byte_140177432, r15b
0x14005b588  jge     short loc_14005B598
0x14005b58a  lea     r8, [rbp+0A0h+var_F0]
0x14005b58e  mov     byte ptr [rsp+1A0h+var_180], 4
0x14005b593  call    McTemplateK0dud_EtwWriteTransfer
0x14005b598  mov     rbx, [rsp+1A0h+var_138]
0x14005b59d  jmp     short loc_14005B5B3
0x14005b59f  mov     eax, [rax+20h]
0x14005b5a2  mov     [rcx+r8+70h], eax
0x14005b5a7  jmp     short loc_14005B54B
0x14005b5a9  mov     ecx, 3
0x14005b5ae  int     29h; Win8: RtlFailFast(ecx)
0x14005b5b0  xor     r15d, r15d
0x14005b5b3  mov     rdx, [rbx+18h]
0x14005b5b7  mov     rcx, r13
0x14005b5ba  mov     rdx, [rdx+8]
0x14005b5be  call    StorUnmapSenseInfo
0x14005b5c3  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x14005b5c8  test    eax, eax
0x14005b5ca  jnz     short loc_14005B5E1
0x14005b5cc  mov     rcx, [rbx+18h]
  ... truncated ...
```
