# NvmeAdapterFabricsConnectControllerIoctl

- ea: `0x1401a20b4`
- end: `0x1401a2b1f`
- name: `NvmeAdapterFabricsConnectControllerIoctl`
- size: `2667`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x140099da0`
- `0x14009a084`
- `0x1400f3c64`
- `0x1400f3d88`
- `0x1400f3e8c`
- `0x1400f6f60`
- `0x1400f8d6c`
- `0x14014b400`
- `0x14014b800`
- `0x1401a20b4`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401a23cc`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401a267a`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401a23cc`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401a267a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a22cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a254b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a22cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a254b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a2561`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a2561`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a21ea`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a21ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a25a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a2843`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a25a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a2843`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1401a23db`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1401a23db`
- `ntoskrnl!IoFreeWorkItem` at `0x1401a24cb`
- `ntoskrnl!IoFreeWorkItem` at `0x1401a24cb`
- `ntoskrnl!KeInitializeEvent` at `0x1401a244a`
- `ntoskrnl!KeInitializeEvent` at `0x1401a244a`
- `ntoskrnl!IofCompleteRequest` at `0x1401a2ae6`
- `ntoskrnl!IofCompleteRequest` at `0x1401a2ae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a249a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a249a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a25c1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a264c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a286d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a25c1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a264c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a286d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a25b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a284f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a25b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a284f`
- `ntoskrnl!_strnicmp` at `0x1401a231a`
- `ntoskrnl!_strnicmp` at `0x1401a235d`
- `ntoskrnl!_strnicmp` at `0x1401a231a`
- `ntoskrnl!_strnicmp` at `0x1401a235d`
- `ntoskrnl!IoQueueWorkItemToNode` at `0x1401a2479`
- `ntoskrnl!IoQueueWorkItemToNode` at `0x1401a2479`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a22e1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a22e1`
- `ntoskrnl!IoAllocateWorkItem` at `0x1401a2400`
- `ntoskrnl!IoAllocateWorkItem` at `0x1401a2400`
- `HAL!KeQueryPerformanceCounter` at `0x1401a23be`
- `HAL!KeQueryPerformanceCounter` at `0x1401a266c`
- `HAL!KeQueryPerformanceCounter` at `0x1401a23be`
- `HAL!KeQueryPerformanceCounter` at `0x1401a266c`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsConnectControllerIoctl(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  char v5; // r14
  __int64 v6; // r15
  __int64 v7; // rcx
  int NvmeHostNQN; // edi
  __int64 SubsystemPort; // rax
  int v10; // r8d
  __int64 v11; // rbx
  bool v12; // zf
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  int *v15; // rax
  int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 NvmeAuthKeyById; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  LARGE_INTEGER v22; // rax
  LARGE_INTEGER v23; // rbx
  __int64 v24; // r15
  char v25; // cl
  int v26; // edx
  int v27; // eax
  _QWORD *v28; // rdx
  _DWORD *v29; // r15
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r8
  __int64 *v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // r13d
  char v38; // bl
  unsigned __int8 v39; // r10
  char *v40; // r11
  _BYTE *v41; // r9
  __int64 v42; // r12
  unsigned __int64 v43; // r15
  __int64 v44; // r8
  int v45; // ecx
  char v46; // cl
  char v47; // r15
  char v48; // r11
  char v49; // r8
  _BYTE *v50; // rax
  char *v51; // r8
  unsigned int v52; // eax
  char v54; // [rsp+60h] [rbp-A0h]
  char v55; // [rsp+60h] [rbp-A0h]
  char v56; // [rsp+61h] [rbp-9Fh]
  char v57; // [rsp+62h] [rbp-9Eh] BYREF
  char v58; // [rsp+63h] [rbp-9Dh]
  __int64 v59; // [rsp+68h] [rbp-98h]
  int v60; // [rsp+70h] [rbp-90h]
  PIO_WORKITEM IoWorkItem; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+88h] [rbp-78h] BYREF
  __int64 v64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+98h] [rbp-68h]
  _QWORD v66[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h]
  __int64 v68; // [rsp+C8h] [rbp-38h]
  char v69; // [rsp+D0h] [rbp-30h]
  struct _KEVENT Event; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v71; // [rsp+F0h] [rbp-10h] BYREF
  char Str2[256]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(v66, 0, 0x50u);
  *(_QWORD *)(a2 + 56) = 0;
  v56 = 0;
  v4 = 0;
  v57 = 0;
  v5 = 1;
  PerformanceFrequency.QuadPart = 0;
  v60 = 0;
  LODWORD(IoWorkItem) = 0;
  v64 = 0;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v6 = *(_QWORD *)(a2 + 24);
    if ( !v6
      || (v7 = *(_QWORD *)(a2 + 184), *(_QWORD *)&v71 = v7, *(_DWORD *)(v7 + 16) < 0x40u)
      || *(_WORD *)v6 != 1
      || *(_WORD *)(v6 + 2) < 0x40u
      || (unsigned __int16)(*(_WORD *)(v6 + 16) + 16) <= 0xEu )
    {
      NvmeHostNQN = -1073741811;
      goto LABEL_13;
    }
    if ( *(_DWORD *)(v7 + 8) < 0x20u )
    {
      NvmeHostNQN = -1073741789;
      goto LABEL_13;
    }
    SubsystemPort = NvmeAdapterFindSubsystemPort(a1, *(_QWORD *)(v6 + 8) ^ a1, 0, 0);
    v59 = SubsystemPort;
    v11 = SubsystemPort;
    if ( !SubsystemPort )
    {
      NvmeHostNQN = -1073741275;
      goto LABEL_13;
    }
    v17 = *(_QWORD *)(SubsystemPort + 32);
    if ( *(_WORD *)(v6 + 16) == 0xFFFF )
    {
      if ( (v17 & 4) != 0 )
        goto LABEL_24;
    }
    else if ( (v17 & 4) == 0 )
    {
LABEL_24:
      if ( (v17 & 2) == 0 && (*(_WORD *)(v6 + 18) || *(_WORD *)(v6 + 20)) )
      {
        NvmeHostNQN = -1073741811;
LABEL_97:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v11 + 40));
        goto LABEL_13;
      }
      v18 = 0;
      v58 = 0;
      v54 = 1;
      v65 = 0;
      v62 = 0;
      if ( *(_DWORD *)(v6 + 56) )
      {
        NvmeHostNQN = GetNvmeHostNQN(0, Str2);
        if ( NvmeHostNQN < 0 )
          goto LABEL_97;
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)&WPP_MAIN_CB.DeviceQueue.32, 1u);
        NvmeAuthKeyById = FindNvmeAuthKeyById(*(unsigned int *)(v6 + 56));
        v65 = NvmeAuthKeyById;
        v18 = NvmeAuthKeyById;
        if ( !NvmeAuthKeyById )
          goto LABEL_33;
        if ( _strnicmp((const char *)(NvmeAuthKeyById + 20), Str2, 0x100u) )
          goto LABEL_35;
        v20 = *(unsigned int *)(v6 + 60);
        v58 = 1;
        if ( (_DWORD)v20 )
        {
          v21 = FindNvmeAuthKeyById(v20);
          v62 = v21;
          if ( !v21 )
          {
LABEL_33:
            NvmeHostNQN = -1073741275;
LABEL_95:
            ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceQueue.32);
            KeLeaveCriticalRegion();
LABEL_96:
            if ( !v54 )
              goto LABEL_13;
            goto LABEL_97;
          }
          if ( _strnicmp((const char *)(v21 + 20), (const char *)(v11 + 60), 0x100u) )
          {
LABEL_35:
            NvmeHostNQN = -1073740007;
            goto LABEL_95;
          }
        }
      }
      if ( (byte_140177439 & 8) != 0 )
        McTemplateK0qjzsh_EtwWriteTransfer(
          v11 + 60,
          (unsigned int)EventNVMeoFConnectControllerStart,
          v10,
          *(_DWORD *)(a1 + 56),
          a1 + 1048,
          *(_QWORD *)(a1 + 1032),
          v11 + 60,
          *(_WORD *)(v6 + 16));
      if ( UseQPCTime )
        v22 = KeQueryPerformanceCounter(&PerformanceFrequency);
      else
        v22.QuadPart = KeQueryUnbiasedInterruptTime();
      v23 = v22;
      if ( KeGetCurrentNodeNumber() == *(_DWORD *)(*(_QWORD *)(v59 + 24) + 16LL) )
      {
        v26 = v6;
        v24 = v59;
        v27 = NvmeAdapterConnectFabricControllerInternal(
                v59,
                v26,
                v18,
                v62,
                (__int64)&v57,
                (__int64)&v64,
                (__int64)&IoWorkItem);
        v25 = v57;
        NvmeHostNQN = v27;
        v4 = v64;
        v60 = (int)IoWorkItem;
      }
      else
      {
        IoWorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 8));
        if ( !IoWorkItem )
        {
          NvmeHostNQN = -1073741670;
          goto LABEL_66;
        }
        v66[0] = v59;
        v66[3] = v62;
        v66[1] = v6;
        v66[2] = v18;
        v67 = 0;
        v68 = 0;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v24 = v59;
        if ( (unsigned __int8)IoQueueWorkItemToNode(
                                IoWorkItem,
                                NvmeAdapterConnectControllerWorker,
                                1,
                                v66,
                                *(_DWORD *)(*(_QWORD *)(v59 + 24) + 16LL)) )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          NvmeHostNQN = v68;
          v60 = HIDWORD(v68);
          if ( (int)v68 >= 0 )
          {
            v4 = v67;
            v56 = v69;
          }
        }
        else
        {
          NvmeHostNQN = -1073741823;
        }
        IoFreeWorkItem(IoWorkItem);
        v25 = v56;
      }
      if ( NvmeHostNQN >= 0 )
      {
        if ( v65 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v65 + 16), 1u);
          if ( v62 )
            _InterlockedAdd((volatile signed __int32 *)(v62 + 16), 1u);
        }
        if ( v25 )
        {
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)(v24 + 632), 1u);
          v28 = *(_QWORD **)(v24 + 616);
          if ( *v28 != v24 + 608 )
            __fastfail(3u);
          *(_QWORD *)(v4 + 64) = v24 + 608;
          *(_QWORD *)(v4 + 72) = v28;
          *v28 = v4 + 64;
          *(_QWORD *)(v24 + 616) = v4 + 64;
          ++*(_DWORD *)(v24 + 624);
          ExReleaseResourceLite((PERESOURCE)(v24 + 632));
          KeLeaveCriticalRegion();
        }
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v24 + 40));
        v29 = *(_DWORD **)(a2 + 24);
        v54 = 0;
        memset_0(v29, 0, *(unsigned int *)(v71 + 8));
        v29[1] |= 1u;
        *v29 = 2097153;
        if ( (*(_BYTE *)(v4 + 136) & 4) != 0 )
          v29[1] |= 8u;
        *((_QWORD *)v29 + 1) = v4 ^ a1;
        *((_WORD *)v29 + 8) = *(_WORD *)(v4 + 4);
        v29[5] = *(_DWORD *)(v4 + 572);
        if ( *(_DWORD *)(v4 + 572) == 1 )
        {
          *((_WORD *)v29 + 12) = *(_WORD *)(v4 + 20);
          *((_WORD *)v29 + 13) = *(_WORD *)(v4 + 8);
        }
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v4 + 552));
        *(_QWORD *)(a2 + 56) = *((unsigned __int16 *)v29 + 1);
      }
LABEL_66:
      if ( UseQPCTime )
        PerformanceCounter = KeQueryPerformanceCounter(0);
      else
        PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
      if ( NvmeHostNQN < 0 )
      {
        if ( (byte_14017743A & 8) != 0 )
        {
          if ( PerformanceCounter.QuadPart <= 0 || PerformanceCounter.QuadPart >= v23.QuadPart )
            v33 = PerformanceCounter.QuadPart - v23.QuadPart;
          else
            v33 = PerformanceCounter.QuadPart - v23.QuadPart - 1;
          if ( UseQPCTime )
          {
            v34 = 0;
            if ( PerformanceFrequency.QuadPart && v33 )
              v34 = 10000
                  * (1000 * (v33 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart)
                  / PerformanceFrequency.QuadPart
                  + 10000
                  * (1000 * (v33 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart
                   + 1000 * (v33 / PerformanceFrequency.QuadPart));
          }
          else
          {
            v34 = v33;
          }
          v11 = v59;
          McTemplateK0qjzsdqq_EtwWriteTransfer(
            a1 + 1048,
            v60,
            v34,
            *(_DWORD *)(a1 + 56),
            a1 + 1048,
            *(_QWORD *)(a1 + 1032),
            v59 + 60,
            NvmeHostNQN,
            v60,
            v34 / 0xA);
LABEL_94:
          if ( !v58 )
            goto LABEL_96;
          goto LABEL_95;
        }
      }
      else if ( (byte_14017743A & 4) != 0 )
      {
        if ( PerformanceCounter.QuadPart <= 0 || PerformanceCounter.QuadPart >= v23.QuadPart )
          v31 = PerformanceCounter.QuadPart - v23.QuadPart;
        else
          v31 = PerformanceCounter.QuadPart - v23.QuadPart - 1;
        if ( UseQPCTime )
        {
          v32 = 0;
          if ( PerformanceFrequency.QuadPart && v31 )
            v32 = 10000
                * (1000 * (v31 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart)
                / PerformanceFrequency.QuadPart
                + 10000
                * (1000 * (v31 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart
                 + 1000 * (v31 / PerformanceFrequency.QuadPart));
        }
        else
        {
          v32 = v31;
        }
        v11 = v59;
        McTemplateK0qjzshq_EtwWriteTransfer(
          v59 + 60,
          v32 / 0xA,
          a1 + 1048,
          *(_DWORD *)(a1 + 56),
          a1 + 1048,
          *(_QWORD *)(a1 + 1032),
          v59 + 60,
          *(_WORD *)(v4 + 4),
          v32 / 0xA);
        goto LABEL_94;
      }
      v11 = v59;
      goto LABEL_94;
    }
    NvmeHostNQN = -1073741637;
    goto LABEL_97;
  }
  NvmeHostNQN = -1073741637;
LABEL_13:
  v12 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = NvmeHostNQN;
  if ( v12 )
    goto LABEL_154;
  v71 = 0;
  IoGetActivityIdIrp(a2, &v71);
  v14 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v14 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_154;
    v35 = EventNonReadWriteRequestComplete;
    goto LABEL_153;
  }
  if ( *(_BYTE *)v14 != 15 )
  {
    if ( *(_BYTE *)v14 != 27 )
      goto LABEL_154;
    if ( *(_BYTE *)(v14 + 1) == 7 && !*(_DWORD *)(v14 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v15 = *(int **)(a2 + 56);
        if ( v15 )
          v16 = *v15;
        else
          v16 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v16, v14, (unsigned int)&v71, a2, v16, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_154;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_154;
    v35 = EventPnpRequestComplete;
LABEL_153:
    McTemplateK0pd_EtwWriteTransfer(v13, v35, &v71, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_154;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_154;
  v36 = *(_QWORD *)(v14 + 8);
  if ( *(_BYTE *)(v36 + 2) != 40 )
  {
    v46 = *(_BYTE *)(v36 + 72);
    v41 = *(_BYTE **)(v36 + 32);
    v39 = *(_BYTE *)(v36 + 11);
    v38 = *(_BYTE *)(v36 + 4);
    if ( *(_BYTE *)(v36 + 2) )
      goto LABEL_154;
LABEL_132:
    LOBYTE(v13) = v46 - 8;
    if ( (v13 & 0x5D) != 0 )
      goto LABEL_154;
    v47 = *(_BYTE *)(v36 + 3);
    if ( v47 == 1 || !v41 || !v39 )
      goto LABEL_149;
    LOBYTE(v36) = 0;
    v48 = 0;
    v49 = 0;
    v13 = (unsigned __int64)&v41[v39];
    v50 = v41 + 8;
    if ( (unsigned __int8)((*v41 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v50 <= v13 )
      {
        v48 = v41[2];
        LOBYTE(v36) = v41[1] & 0xF;
        v49 = v41[3];
        goto LABEL_148;
      }
    }
    else if ( (unsigned __int64)v50 <= v13 )
    {
      v51 = v41 + 13;
      LOBYTE(v36) = v41[2] & 0xF;
      v52 = v39;
      if ( (unsigned int)(unsigned __int8)v41[7] + 8 <= v39 )
        v52 = (unsigned __int8)v41[7] + 8;
      v13 = (unsigned __int64)&v41[v52];
      if ( (unsigned __int64)v51 <= v13 )
        v48 = v41[12];
      if ( (unsigned __int64)(v41 + 14) > v13 )
        v49 = 0;
      else
        v49 = *v51;
LABEL_148:
      if ( v5 )
      {
LABEL_150:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v13,
          v36,
          (unsigned int)&v71,
          a2,
          *(_DWORD *)(a2 + 48),
          v47,
          v38,
          v36,
          v48,
          v49,
          a2);
        goto LABEL_154;
      }
LABEL_149:
      LOBYTE(v36) = 0;
      v48 = 0;
      v49 = 0;
      goto LABEL_150;
    }
    v5 = 0;
    goto LABEL_148;
  }
  if ( *(_DWORD *)(v36 + 20) )
    goto LABEL_154;
  v37 = *(_DWORD *)(v36 + 56);
  if ( !v37 )
    goto LABEL_154;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v55 = 0;
  v41 = 0;
  v42 = 0;
  while ( 1 )
  {
    v13 = *(unsigned int *)(v36 + 4 * v42 + 120);
    if ( (unsigned int)v13 >= 0x80 )
    {
      v43 = *(unsigned int *)(v36 + 16);
      if ( (unsigned int)v13 < (unsigned int)v43 )
        break;
    }
LABEL_123:
    v42 = (unsigned int)(v42 + 1);
    if ( (unsigned int)v42 >= v37 )
      goto LABEL_129;
  }
  v44 = (unsigned int)v13;
  v45 = *(_DWORD *)(v13 + v36) - 64;
  if ( v45 )
  {
    LODWORD(v13) = v45 - 1;
    if ( (_DWORD)v13 )
    {
      if ( (_DWORD)v13 == 1 )
      {
        LODWORD(v13) = v44 + 40;
        if ( v44 + 40 <= v43 )
        {
          if ( *(_DWORD *)(v44 + v36 + 12) )
            v40 = (char *)(v44 + v36 + 32);
          v41 = *(_BYTE **)(v44 + v36 + 24);
          goto LABEL_128;
        }
      }
    }
    else
    {
      LODWORD(v13) = v44 + 56;
      if ( v44 + 56 <= v43 )
      {
        v55 = 1;
        if ( *(_BYTE *)(v44 + v36 + 10) )
          v40 = (char *)(v44 + v36 + 24);
        v38 = *(_BYTE *)(v44 + v36 + 8);
        v41 = *(_BYTE **)(v44 + v36 + 16);
        v39 = *(_BYTE *)(v44 + v36 + 9);
      }
    }
    goto LABEL_122;
  }
  LODWORD(v13) = v44 + 40;
  if ( v44 + 40 > v43 )
  {
LABEL_122:
    if ( v55 )
      goto LABEL_129;
    goto LABEL_123;
  }
  if ( *(_BYTE *)(v44 + v36 + 10) )
    v40 = (char *)(v44 + v36 + 24);
  v41 = *(_BYTE **)(v44 + v36 + 16);
LABEL_128:
  v39 = *(_BYTE *)(v44 + v36 + 9);
  v38 = *(_BYTE *)(v44 + v36 + 8);
LABEL_129:
  if ( v40 )
  {
    v46 = *v40;
    goto LABEL_132;
  }
LABEL_154:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)NvmeHostNQN;
}

```

## disassembly

```asm
0x1401a20b4  mov     [rsp-8+arg_10], rbx
0x1401a20b9  push    rbp
0x1401a20ba  push    rsi
0x1401a20bb  push    rdi
0x1401a20bc  push    r12
0x1401a20be  push    r13
0x1401a20c0  push    r14
0x1401a20c2  push    r15
0x1401a20c4  lea     rbp, [rsp-110h]
0x1401a20cc  sub     rsp, 210h
0x1401a20d3  mov     rax, cs:__security_cookie
0x1401a20da  xor     rax, rsp
0x1401a20dd  mov     [rbp+140h+var_40], rax
0x1401a20e4  mov     rsi, rdx
0x1401a20e7  mov     r13, rcx
0x1401a20ea  xor     edx, edx; Val
0x1401a20ec  lea     rcx, [rbp+140h+var_1A0]; void *
0x1401a20f0  lea     r8d, [rdx+50h]; Size
0x1401a20f4  call    memset_0
0x1401a20f9  xor     r10d, r10d
0x1401a20fc  mov     al, r10b
0x1401a20ff  mov     [rsi+38h], r10
0x1401a2103  mov     [rsp+240h+var_1DF], al
0x1401a2107  mov     r12d, r10d
0x1401a210a  mov     [rsp+240h+var_1DE], al
0x1401a210e  mov     eax, r10d
0x1401a2111  lea     r14d, [r10+1]
0x1401a2115  mov     qword ptr [rbp+140h+PerformanceFrequency], r10
0x1401a2119  lea     ebx, [r10+20h]
0x1401a211d  mov     [rsp+240h+var_1D0], eax
0x1401a2121  lea     edx, [rbx+20h]
0x1401a2124  mov     dword ptr [rsp+240h+IoWorkItem], eax
0x1401a2128  lea     r8d, [r10+0Eh]
0x1401a212c  mov     [rbp+140h+var_1B0], r10
0x1401a2130  test    [r13+98h], r14b
0x1401a2137  jz      loc_1401A2881
0x1401a213d  cmp     [r13+268h], r10
0x1401a2144  jz      loc_1401A2881
0x1401a214a  mov     r15, [rsi+18h]
0x1401a214e  test    r15, r15
0x1401a2151  jz      short loc_1401A217F
0x1401a2153  mov     rcx, [rsi+0B8h]
0x1401a215a  mov     qword ptr [rbp+140h+var_150], rcx
0x1401a215e  cmp     [rcx+10h], edx
0x1401a2161  jb      short loc_1401A217F
0x1401a2163  cmp     [r15], r14w
0x1401a2167  jnz     short loc_1401A217F
0x1401a2169  cmp     [r15+2], dx
0x1401a216e  jb      short loc_1401A217F
0x1401a2170  movzx   eax, word ptr [r15+10h]
0x1401a2175  add     ax, 10h
0x1401a2179  cmp     ax, r8w
0x1401a217d  ja      short loc_1401A2186
0x1401a217f  mov     edi, 0C000000Dh
0x1401a2184  jmp     short loc_1401A21C5
0x1401a2186  cmp     [rcx+8], ebx
0x1401a2189  jnb     short loc_1401A2192
0x1401a218b  mov     edi, 0C0000023h
0x1401a2190  jmp     short loc_1401A21C5
0x1401a2192  mov     rdx, r13
0x1401a2195  xor     r9d, r9d
0x1401a2198  xor     rdx, [r15+8]
0x1401a219c  xor     r8d, r8d
0x1401a219f  mov     rcx, r13
0x1401a21a2  call    NvmeAdapterFindSubsystemPort
0x1401a21a7  xor     r10d, r10d
0x1401a21aa  mov     [rsp+240h+var_1D8], rax
0x1401a21af  mov     rbx, rax
0x1401a21b2  test    rax, rax
0x1401a21b5  jnz     loc_1401A2250
0x1401a21bb  mov     edi, 0C0000225h
0x1401a21c0  mov     ebx, 20h ; ' '
0x1401a21c5  cmp     cs:StorEtwLoggingEnabled, r10b
0x1401a21cc  mov     byte ptr [rsi+8Dh], 0ACh
0x1401a21d3  mov     [rsi+30h], edi
0x1401a21d6  jz      loc_1401A2AE1
0x1401a21dc  xorps   xmm0, xmm0
0x1401a21df  lea     rdx, [rbp+140h+var_150]
0x1401a21e3  mov     rcx, rsi
0x1401a21e6  movups  [rbp+140h+var_150], xmm0
0x1401a21ea  call    cs:__imp_IoGetActivityIdIrp
0x1401a21f1  nop     dword ptr [rax+rax+00h]
0x1401a21f6  mov     rdx, [rsi+0B8h]
0x1401a21fd  movzx   eax, byte ptr [rdx]
0x1401a2200  sub     eax, 0Eh
0x1401a2203  jz      loc_1401A2ABE
0x1401a2209  sub     eax, r14d
0x1401a220c  jz      loc_1401A28C1
0x1401a2212  cmp     eax, 0Ch
0x1401a2215  jnz     loc_1401A2AE1
0x1401a221b  cmp     byte ptr [rdx+1], 7
0x1401a221f  jnz     loc_1401A28A9
0x1401a2225  cmp     dword ptr [rdx+8], 0
0x1401a2229  jnz     loc_1401A28A9
0x1401a222f  test    cs:byte_140177432, 40h
0x1401a2236  jz      loc_1401A2AE1
0x1401a223c  mov     rax, [rsi+38h]
0x1401a2240  test    rax, rax
0x1401a2243  jz      loc_1401A288B
0x1401a2249  mov     ecx, [rax]
0x1401a224b  jmp     loc_1401A288D
0x1401a2250  mov     rcx, [rax+20h]
0x1401a2254  mov     edx, 0FFFFh
0x1401a2259  mov     rax, rcx
0x1401a225c  and     eax, 4
0x1401a225f  cmp     [r15+10h], dx
0x1401a2264  jnz     short loc_1401A2288
0x1401a2266  test    rax, rax
0x1401a2269  jz      short loc_1401A228D
0x1401a226b  test    cl, 2
0x1401a226e  jnz     short loc_1401A2297
0x1401a2270  cmp     [r15+12h], r10w
0x1401a2275  jnz     short loc_1401A227E
0x1401a2277  cmp     [r15+14h], r10w
0x1401a227c  jz      short loc_1401A2297
0x1401a227e  mov     edi, 0C000000Dh
0x1401a2283  jmp     loc_1401A2869
0x1401a2288  test    rax, rax
0x1401a228b  jz      short loc_1401A226B
0x1401a228d  mov     edi, 0C00000BBh
0x1401a2292  jmp     loc_1401A2869
0x1401a2297  mov     rdi, r10
0x1401a229a  mov     [rsp+240h+var_1DD], r10b
0x1401a229f  mov     [rsp+240h+var_1E0], r14b
0x1401a22a4  mov     [rbp+140h+var_1A8], r10
0x1401a22a8  mov     [rbp+140h+var_1C0], r10
0x1401a22ac  cmp     [r15+38h], r10d
0x1401a22b0  jz      loc_1401A236D
0x1401a22b6  lea     rdx, [rbp+140h+Str2]
0x1401a22ba  xor     ecx, ecx
0x1401a22bc  call    GetNvmeHostNQN
0x1401a22c1  mov     edi, eax
0x1401a22c3  test    eax, eax
0x1401a22c5  js      loc_1401A2869
0x1401a22cb  call    cs:__imp_KeEnterCriticalRegion
0x1401a22d2  nop     dword ptr [rax+rax+00h]
0x1401a22d7  mov     dl, r14b; Wait
0x1401a22da  lea     rcx, WPP_MAIN_CB.DeviceQueue.___u4; Resource
0x1401a22e1  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a22e8  nop     dword ptr [rax+rax+00h]
0x1401a22ed  mov     ecx, [r15+38h]
0x1401a22f1  call    FindNvmeAuthKeyById
0x1401a22f6  mov     [rbp+140h+var_1A8], rax
0x1401a22fa  mov     rdi, rax
0x1401a22fd  test    rax, rax
0x1401a2300  jnz     short loc_1401A230C
0x1401a2302  mov     edi, 0C0000225h
0x1401a2307  jmp     loc_1401A283C
0x1401a230c  lea     rcx, [rax+14h]; Str1
0x1401a2310  mov     r8d, 100h; MaxCount
0x1401a2316  lea     rdx, [rbp+140h+Str2]; Str2
0x1401a231a  call    cs:__imp__strnicmp
0x1401a2321  nop     dword ptr [rax+rax+00h]
0x1401a2326  test    eax, eax
0x1401a2328  jz      short loc_1401A2334
0x1401a232a  mov     edi, 0C0000719h
0x1401a232f  jmp     loc_1401A283C
0x1401a2334  mov     ecx, [r15+3Ch]
0x1401a2338  mov     [rsp+240h+var_1DD], r14b
0x1401a233d  test    ecx, ecx
0x1401a233f  jz      short loc_1401A236D
0x1401a2341  call    FindNvmeAuthKeyById
0x1401a2346  mov     [rbp+140h+var_1C0], rax
0x1401a234a  test    rax, rax
0x1401a234d  jz      short loc_1401A2302
0x1401a234f  lea     rdx, [rbx+3Ch]; Str2
0x1401a2353  mov     r8d, 100h; MaxCount
0x1401a2359  lea     rcx, [rax+14h]; Str1
0x1401a235d  call    cs:__imp__strnicmp
0x1401a2364  nop     dword ptr [rax+rax+00h]
0x1401a2369  test    eax, eax
0x1401a236b  jnz     short loc_1401A232A
0x1401a236d  test    cs:byte_140177439, 8
0x1401a2374  jz      short loc_1401A23B1
0x1401a2376  movzx   eax, word ptr [r15+10h]
0x1401a237b  lea     rcx, [rbx+3Ch]
0x1401a237f  mov     r9d, [r13+38h]
0x1401a2383  lea     rdx, [r13+418h]
0x1401a238a  mov     word ptr [rsp+240h+var_208], ax
0x1401a238f  mov     rax, [r13+408h]
0x1401a2396  mov     [rsp+240h+var_210], rcx
0x1401a239b  mov     [rsp+240h+var_218], rax
0x1401a23a0  mov     [rsp+240h+Timeout], rdx
0x1401a23a5  lea     rdx, EventNVMeoFConnectControllerStart
0x1401a23ac  call    McTemplateK0qjzsh_EtwWriteTransfer
0x1401a23b1  cmp     cs:UseQPCTime, r12b
0x1401a23b8  jz      short loc_1401A23CC
0x1401a23ba  lea     rcx, [rbp+140h+PerformanceFrequency]; PerformanceFrequency
0x1401a23be  call    cs:__imp_KeQueryPerformanceCounter
0x1401a23c5  nop     dword ptr [rax+rax+00h]
0x1401a23ca  jmp     short loc_1401A23D8
0x1401a23cc  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1401a23d3  nop     dword ptr [rax+rax+00h]
0x1401a23d8  mov     rbx, rax
0x1401a23db  call    cs:__imp_KeGetCurrentNodeNumber
0x1401a23e2  nop     dword ptr [rax+rax+00h]
0x1401a23e7  movzx   ecx, ax
0x1401a23ea  mov     rax, [rsp+240h+var_1D8]
0x1401a23ef  mov     rax, [rax+18h]
0x1401a23f3  cmp     ecx, [rax+10h]
0x1401a23f6  jz      loc_1401A24DD
0x1401a23fc  mov     rcx, [r13+8]; DeviceObject
0x1401a2400  call    cs:__imp_IoAllocateWorkItem
0x1401a2407  nop     dword ptr [rax+rax+00h]
0x1401a240c  mov     [rsp+240h+IoWorkItem], rax
0x1401a2411  test    rax, rax
0x1401a2414  jnz     short loc_1401A2420
0x1401a2416  mov     edi, 0C000009Ah
0x1401a241b  jmp     loc_1401A2661
0x1401a2420  mov     rax, [rsp+240h+var_1D8]
0x1401a2425  lea     rcx, [rbp+140h+Event]; Event
0x1401a2429  mov     r9, [rbp+140h+var_1C0]
0x1401a242d  xor     r8d, r8d; State
0x1401a2430  xor     edx, edx; Type
0x1401a2432  mov     [rbp+140h+var_1A0], rax
0x1401a2436  mov     [rbp+140h+var_188], r9
0x1401a243a  mov     [rbp+140h+var_198], r15
0x1401a243e  mov     [rbp+140h+var_190], rdi
0x1401a2442  mov     [rbp+140h+var_180], r12
0x1401a2446  mov     [rbp+140h+var_178], r12
0x1401a244a  call    cs:__imp_KeInitializeEvent
0x1401a2451  nop     dword ptr [rax+rax+00h]
0x1401a2456  mov     r15, [rsp+240h+var_1D8]
0x1401a245b  lea     r9, [rbp+140h+var_1A0]
0x1401a245f  mov     r8d, r14d
0x1401a2462  lea     rdx, NvmeAdapterConnectControllerWorker
0x1401a2469  mov     rax, [r15+18h]
0x1401a246d  mov     ecx, [rax+10h]
0x1401a2470  mov     dword ptr [rsp+240h+Timeout], ecx
0x1401a2474  mov     rcx, [rsp+240h+IoWorkItem]
0x1401a2479  call    cs:__imp_IoQueueWorkItemToNode
0x1401a2480  nop     dword ptr [rax+rax+00h]
0x1401a2485  test    al, al
0x1401a2487  jz      short loc_1401A24C1
0x1401a2489  xor     r9d, r9d; Alertable
0x1401a248c  mov     [rsp+240h+Timeout], r12; Timeout
0x1401a2491  xor     r8d, r8d; WaitMode
0x1401a2494  lea     rcx, [rbp+140h+Event]; Object
0x1401a2498  xor     edx, edx; WaitReason
0x1401a249a  call    cs:__imp_KeWaitForSingleObject
0x1401a24a1  nop     dword ptr [rax+rax+00h]
0x1401a24a6  mov     edi, dword ptr [rbp+140h+var_178]
0x1401a24a9  mov     eax, dword ptr [rbp+140h+var_178+4]
0x1401a24ac  mov     [rsp+240h+var_1D0], eax
0x1401a24b0  test    edi, edi
0x1401a24b2  js      short loc_1401A24C6
0x1401a24b4  mov     al, [rbp+140h+var_170]
0x1401a24b7  mov     r12, [rbp+140h+var_180]
0x1401a24bb  mov     [rsp+240h+var_1DF], al
0x1401a24bf  jmp     short loc_1401A24C6
0x1401a24c1  mov     edi, 0C0000001h
0x1401a24c6  mov     rcx, [rsp+240h+IoWorkItem]; IoWorkItem
0x1401a24cb  call    cs:__imp_IoFreeWorkItem
0x1401a24d2  nop     dword ptr [rax+rax+00h]
0x1401a24d7  mov     cl, [rsp+240h+var_1DF]
0x1401a24db  jmp     short loc_1401A2523
0x1401a24dd  mov     r9, [rbp+140h+var_1C0]
0x1401a24e1  lea     rax, [rsp+240h+IoWorkItem]
0x1401a24e6  mov     [rsp+240h+var_210], rax
0x1401a24eb  mov     rdx, r15
0x1401a24ee  mov     r15, [rsp+240h+var_1D8]
0x1401a24f3  lea     rax, [rbp+140h+var_1B0]
0x1401a24f7  mov     [rsp+240h+var_218], rax
0x1401a24fc  mov     r8, rdi
0x1401a24ff  lea     rax, [rsp+240h+var_1DE]
0x1401a2504  mov     rcx, r15
0x1401a2507  mov     [rsp+240h+Timeout], rax
0x1401a250c  call    NvmeAdapterConnectFabricControllerInternal
0x1401a2511  mov     cl, [rsp+240h+var_1DE]
0x1401a2515  mov     edi, eax
0x1401a2517  mov     eax, dword ptr [rsp+240h+IoWorkItem]
0x1401a251b  mov     r12, [rbp+140h+var_1B0]
0x1401a251f  mov     [rsp+240h+var_1D0], eax
0x1401a2523  test    edi, edi
0x1401a2525  js      loc_1401A2661
0x1401a252b  mov     rax, [rbp+140h+var_1A8]
0x1401a252f  test    rax, rax
0x1401a2532  jz      short loc_1401A2547
0x1401a2534  lock add [rax+10h], r14d
0x1401a2539  mov     rax, [rbp+140h+var_1C0]
0x1401a253d  test    rax, rax
0x1401a2540  jz      short loc_1401A2547
0x1401a2542  lock add [rax+10h], r14d
0x1401a2547  test    cl, cl
0x1401a2549  jz      short loc_1401A25BD
0x1401a254b  call    cs:__imp_KeEnterCriticalRegion
0x1401a2552  nop     dword ptr [rax+rax+00h]
0x1401a2557  lea     rcx, [r15+278h]; Resource
0x1401a255e  mov     dl, r14b; Wait
0x1401a2561  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a2568  nop     dword ptr [rax+rax+00h]
0x1401a256d  lea     rcx, [r15+260h]
0x1401a2574  mov     rdx, [rcx+8]
0x1401a2578  cmp     [rdx], rcx
0x1401a257b  jz      short loc_1401A2584
0x1401a257d  mov     ecx, 3
0x1401a2582  int     29h; Win8: RtlFailFast(ecx)
0x1401a2584  lea     rax, [r12+40h]
0x1401a2589  mov     [rax], rcx
0x1401a258c  mov     [rax+8], rdx
  ... truncated ...
```
