# Ipv6SetEchoRequestCreate

- ea: `0x140086914`
- end: `0x140087621`
- name: `Ipv6SetEchoRequestCreate`
- size: `3341`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140085880`

## callees

- `0x140014a08`
- `0x140023e30`
- `0x140024010`
- `0x140024940`
- `0x140031300`
- `0x140074f30`
- `0x1400812a8`
- `0x1400826e4`
- `0x140084aac`
- `0x140084bd4`
- `0x140085ac8`
- `0x140086914`
- `0x140087628`
- `0x14008d41c`
- `0x14008f110`
- `0x1400915e4`
- `0x1400bff50`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140087554`
- `ntoskrnl!MmUnlockPages` at `0x1400875a8`
- `ntoskrnl!MmUnlockPages` at `0x1400875da`
- `ntoskrnl!MmUnlockPages` at `0x140087554`
- `ntoskrnl!MmUnlockPages` at `0x1400875a8`
- `ntoskrnl!MmUnlockPages` at `0x1400875da`
- `ntoskrnl!MmProbeAndLockPages` at `0x140086ad4`
- `ntoskrnl!MmProbeAndLockPages` at `0x140086bfc`
- `ntoskrnl!MmProbeAndLockPages` at `0x140086d3b`
- `ntoskrnl!MmProbeAndLockPages` at `0x140086ad4`
- `ntoskrnl!MmProbeAndLockPages` at `0x140086bfc`
- `ntoskrnl!MmProbeAndLockPages` at `0x140086d3b`
- `ntoskrnl!IoAllocateMdl` at `0x140086a5b`
- `ntoskrnl!IoAllocateMdl` at `0x140086b83`
- `ntoskrnl!IoAllocateMdl` at `0x140086cc2`
- `ntoskrnl!IoAllocateMdl` at `0x140086a5b`
- `ntoskrnl!IoAllocateMdl` at `0x140086b83`
- `ntoskrnl!IoAllocateMdl` at `0x140086cc2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140086b10`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140086c30`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140086b10`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140086c30`
- `ntoskrnl!IoFreeMdl` at `0x140087563`
- `ntoskrnl!IoFreeMdl` at `0x1400875b7`
- `ntoskrnl!IoFreeMdl` at `0x1400875e9`
- `ntoskrnl!IoFreeMdl` at `0x140087563`
- `ntoskrnl!IoFreeMdl` at `0x1400875b7`
- `ntoskrnl!IoFreeMdl` at `0x1400875e9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140087300`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008731b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140087300`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008731b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140087361`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140087375`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140087361`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140087375`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400869e5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400869e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087275`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008738b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087275`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008738b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140086e16`
- `ntoskrnl!KeInitializeSpinLock` at `0x140086e16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087235`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087235`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400875ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400875ff`
- `ntoskrnl!ExAllocatePool2` at `0x140086d96`
- `ntoskrnl!ExAllocatePool2` at `0x140087040`
- `ntoskrnl!ExAllocatePool2` at `0x140086d96`
- `ntoskrnl!ExAllocatePool2` at `0x140087040`
- `NETIO!NetioDereferenceNetBufferList` at `0x14008752f`
- `NETIO!NetioDereferenceNetBufferList` at `0x14008752f`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140086dfc`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140086dfc`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140086f3a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140086f3a`
- `HAL!KeQueryPerformanceCounter` at `0x1400872cc`
- `HAL!KeQueryPerformanceCounter` at `0x1400872cc`

## pseudocode

```c
__int64 __fastcall Ipv6SetEchoRequestCreate(__int64 a1, __int64 a2)
{
  __int64 v4; // r13
  void *v5; // rdi
  unsigned int *v6; // r12
  int v7; // r14d
  int v8; // r15d
  unsigned int v9; // r14d
  struct _MDL *v10; // rax
  __int64 v11; // r8
  struct _MDL *v12; // rbx
  int v13; // ebx
  int v14; // r10d
  _QWORD *v15; // r8
  int *Compartment; // r11
  PVOID MappedSystemVa; // rcx
  struct _MDL *v18; // rax
  __int64 v19; // r8
  struct _MDL *v20; // rbx
  PVOID v21; // rax
  struct _MDL *v22; // rax
  __int64 v23; // r8
  struct _MDL *v24; // rbx
  __int64 Pool2; // rax
  __int64 v26; // r8
  char v27; // r8
  unsigned int v28; // ecx
  unsigned int v29; // edx
  ULONG v30; // r8d
  ULONG v31; // ecx
  __int64 NetBufferListForEcho; // rax
  __int64 v33; // rdx
  unsigned int v34; // eax
  unsigned __int32 v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // r11
  unsigned int v40; // ebx
  __int64 v41; // rax
  unsigned int *v42; // rcx
  unsigned int v43; // edx
  __int64 v44; // rcx
  KIRQL v45; // r14
  __int64 v46; // rdx
  __int64 v47; // rdx
  unsigned __int64 v48; // rdi
  __int64 v49; // rbx
  unsigned int v50; // eax
  int v51; // r9d
  __int64 v52; // rdx
  __int64 v53; // rax
  void *v54; // r12
  char v56; // [rsp+60h] [rbp-268h]
  char v57; // [rsp+61h] [rbp-267h]
  char v58; // [rsp+62h] [rbp-266h]
  __int64 v59; // [rsp+70h] [rbp-258h]
  int *v60; // [rsp+78h] [rbp-250h]
  _QWORD *v61; // [rsp+80h] [rbp-248h]
  PVOID v62; // [rsp+88h] [rbp-240h]
  void *v63; // [rsp+88h] [rbp-240h]
  unsigned int *v64; // [rsp+90h] [rbp-238h]
  int v65; // [rsp+A0h] [rbp-228h]
  unsigned int v66; // [rsp+A8h] [rbp-220h]
  void *Src; // [rsp+B0h] [rbp-218h]
  __int64 v68; // [rsp+B8h] [rbp-210h]
  struct _MDL *MemoryDescriptorList; // [rsp+C0h] [rbp-208h]
  struct _MDL *Mdl; // [rsp+C8h] [rbp-200h]
  struct _MDL *v71; // [rsp+D0h] [rbp-1F8h]
  __int64 v72; // [rsp+E0h] [rbp-1E8h] BYREF
  __int128 v73; // [rsp+E8h] [rbp-1E0h] BYREF
  PVOID v74; // [rsp+F8h] [rbp-1D0h]
  PVOID v75; // [rsp+100h] [rbp-1C8h]
  _QWORD v76[20]; // [rsp+110h] [rbp-1B8h] BYREF
  _QWORD v77[35]; // [rsp+1B0h] [rbp-118h] BYREF
  int NewIrql; // [rsp+2D0h] [rbp+8h] BYREF
  __int64 v79; // [rsp+2D8h] [rbp+10h]
  __int64 v80; // [rsp+2E0h] [rbp+18h]
  PKSPIN_LOCK SpinLock; // [rsp+2E8h] [rbp+20h]

  v79 = a2;
  v4 = 0;
  v57 = 0;
  v58 = 0;
  v56 = 0;
  Mdl = 0;
  v71 = 0;
  MemoryDescriptorList = 0;
  v5 = 0;
  v59 = 0;
  v72 = 0;
  v73 = 0;
  memset(v77, 0, 0xD8u);
  v61 = 0;
  memset(v76, 0, sizeof(v76));
  v6 = *(unsigned int **)(a1 + 32);
  if ( !v6 )
  {
    v7 = 0;
    v8 = -536854096;
LABEL_80:
    Compartment = 0;
    goto LABEL_81;
  }
  if ( !v6[7] )
  {
    v7 = 0;
    v8 = -536854095;
    goto LABEL_80;
  }
  v68 = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(v68 + 8) != (unsigned int)PsGetCurrentProcessId() )
  {
    v7 = 0;
    v8 = -536854094;
    goto LABEL_80;
  }
  if ( !*((_QWORD *)v6 + 2) || (v62 = 0, Src = 0, v9 = 0, LOWORD(v80) = 0, v6[6] > v6[1]) )
  {
    v7 = 15;
    v8 = -536854093;
    goto LABEL_80;
  }
  if ( *v6 )
  {
    v10 = IoAllocateMdl(*((PVOID *)v6 + 1), *v6, 0, 1u, 0);
    v12 = v10;
    Mdl = v10;
    if ( !v10 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v11,
          L"IPv6 echo data MDL (IPNG)");
      v13 = -1073741801;
      v7 = 35;
      v8 = -536854092;
      v5 = 0;
      v14 = 0;
      v15 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
    MmProbeAndLockPages(v10, 1, IoReadAccess);
    v57 = 1;
    if ( (v12->MdlFlags & 5) != 0 )
      MappedSystemVa = v12->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v12, 0, MmCached, 0, 0, 0x40000010u);
    v62 = MappedSystemVa;
    v74 = MappedSystemVa;
    if ( !MappedSystemVa )
    {
      v13 = -1073741670;
      v7 = 35;
      v8 = -536854091;
      v5 = 0;
      v14 = 0;
      v15 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
  }
  if ( *((_WORD *)v6 + 20) )
  {
    v18 = IoAllocateMdl(*((PVOID *)v6 + 4), *((unsigned __int16 *)v6 + 20), 0, 1u, 0);
    v20 = v18;
    v71 = v18;
    if ( !v18 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v19,
          L"IPv6 echo options MDL (IPNG)");
      v13 = -1073741801;
      v7 = 35;
      v8 = -536854090;
      v5 = 0;
      v14 = 0;
      v15 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
    MmProbeAndLockPages(v18, 1, IoReadAccess);
    v58 = 1;
    if ( (v20->MdlFlags & 5) != 0 )
      v21 = v20->MappedSystemVa;
    else
      v21 = MmMapLockedPagesSpecifyCache(v20, 0, MmCached, 0, 0, 0x40000010u);
    Src = v21;
    v75 = v21;
    if ( !v21 )
    {
      v13 = -1073741670;
      v7 = 35;
      v8 = -536854089;
      v5 = 0;
      v14 = 0;
      v15 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
    LOWORD(v80) = *((_WORD *)v6 + 20);
    v9 = (((unsigned __int16)v80 + 7) & 0xFFFFFFF8) + 16;
  }
  v22 = IoAllocateMdl(*((PVOID *)v6 + 2), v6[1], 0, 1u, 0);
  v24 = v22;
  MemoryDescriptorList = v22;
  if ( v22 )
  {
    MmProbeAndLockPages(v22, 1, IoWriteAccess);
    v56 = 1;
    DWORD2(v73) = NdisGetCurrentThreadCompartmentId();
    Compartment = (int *)IppGetCompartment(a2, &v73);
    v60 = Compartment;
    if ( !Compartment )
    {
      v7 = 0;
      v8 = -536854086;
      v5 = 0;
LABEL_81:
      v13 = -1073741811;
      goto LABEL_82;
    }
    Pool2 = ExAllocatePool2(64, 256, 543503945);
    v4 = Pool2;
    if ( !Pool2 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v26,
          L"IPv6 echo request (IPNG)");
      v13 = -1073741670;
      v7 = 35;
      v8 = -536854085;
      v5 = 0;
      Compartment = v60;
      goto LABEL_82;
    }
    *(_QWORD *)(Pool2 + 8) = 1;
    RtlInitializeTimerWheelEntry(0, Pool2 + 32, 0, 0);
    *(_QWORD *)(v4 + 24) = v4 + 16;
    *(_QWORD *)(v4 + 16) = v4 + 16;
    KeInitializeSpinLock((PKSPIN_LOCK)v4);
    Compartment = v60;
    *(_QWORD *)(v4 + 56) = v60;
    *(_QWORD *)(v4 + 72) = v24;
    v27 = *((_BYTE *)v6 + 53);
    LOBYTE(NewIrql) = v27;
    if ( v27 )
      v9 += 40;
    v28 = *v6 + 8;
    if ( v28 < *v6 )
    {
      v8 = -536854084;
LABEL_44:
      v7 = 0;
      v13 = -1073741675;
      v5 = 0;
LABEL_82:
      v14 = 0;
      goto LABEL_83;
    }
    v65 = (unsigned __int16)v80 + 7;
    v29 = (v65 & 0xFFFFFFF8) + v28;
    if ( v29 < v28 )
    {
      v8 = -536854083;
      goto LABEL_44;
    }
    LODWORD(SpinLock) = v27 != 0 ? 0x18 : 0;
    v30 = (_DWORD)SpinLock + v29;
    if ( (unsigned int)SpinLock + v29 < v29 )
    {
      v8 = -536854082;
      goto LABEL_44;
    }
    v31 = v30 + *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 8LL);
    if ( v31 < v30 )
    {
      v8 = -536854081;
      goto LABEL_44;
    }
    NetBufferListForEcho = IppAllocateNetBufferListForEcho(v31);
    v14 = NetBufferListForEcho;
    v59 = NetBufferListForEcho;
    if ( !NetBufferListForEcho )
    {
      v13 = -1073741670;
      v7 = 35;
      v8 = -536854080;
LABEL_53:
      v5 = 0;
      Compartment = v60;
LABEL_83:
      v15 = 0;
      goto LABEL_84;
    }
    v33 = *v6;
    if ( (_DWORD)v33 )
    {
      NetioRetreatNetBuffer(*(_QWORD *)(NetBufferListForEcho + 8), v33, 0);
      RtlCopyKernelBufferToMdl(
        v62,
        *(_QWORD *)(*(_QWORD *)(v59 + 8) + 8LL),
        *(unsigned int *)(*(_QWORD *)(v59 + 8) + 16LL),
        *v6,
        &v72);
    }
    v34 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 20076));
    if ( v34 < 0x10000 )
    {
      _InterlockedAdd((volatile signed __int32 *)(a2 + 20076), 0x10000u);
      v34 += 0x10000;
    }
    v35 = _byteswap_ulong(v34);
    *(_DWORD *)(v4 + 64) = v35;
    HIDWORD(v77[26]) = v35;
    v64 = v6 + 18;
    v76[0] = *(_QWORD *)(v4 + 56);
    v76[8] = v6 + 18;
    LODWORD(v76[7]) = v6[12];
    if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(v6 + 14)) )
    {
      LODWORD(v76[10]) = v6[11];
      v76[11] = v36;
    }
    v76[16] = *(_QWORD *)(a2 + 4744);
    v76[17] = 0;
    LODWORD(v76[19]) = 58;
    BYTE4(v76[19]) = 0x80;
    v13 = IppJoinPath(a2, v76);
    if ( v13 < 0 )
    {
      v7 = 13;
      v8 = -536854078;
      v14 = v59;
      goto LABEL_53;
    }
    v61 = (_QWORD *)v76[15];
    v66 = v9 + 24;
    v37 = ExAllocatePool2(64, v9 + 24, 543503945);
    v39 = v37;
    v63 = (void *)v37;
    if ( v37 )
    {
      v40 = 0;
      if ( (_BYTE)NewIrql )
      {
        *(_QWORD *)v37 = (((_DWORD)SpinLock + 7) & 0xFFFFFFF8) + 16LL;
        *(_DWORD *)(v37 + 8) = *(_DWORD *)(a2 + 24);
        *(_DWORD *)(v37 + 12) = 32;
        v40 = *(_DWORD *)v37;
        *(_WORD *)(v37 + 17) = 2;
        *(_BYTE *)(v37 + 19) = 1;
        *(_OWORD *)(v37 + 24) = *(_OWORD *)(v6 + 18);
        v41 = *(_QWORD *)(*v61 + 16LL);
        v42 = *(unsigned int **)v41;
        v64 = *(unsigned int **)v41;
        NewIrql = *(_DWORD *)(v41 + 8);
        IN6_UNCANONICALIZE_SCOPE_ID(v42, &NewIrql);
      }
      v43 = (unsigned __int16)v80;
      if ( (_WORD)v80 )
      {
        v44 = v40;
        *(_QWORD *)(v40 + v39) = (v65 & 0xFFFFFFF8) + 16LL;
        *(_DWORD *)(v40 + v39 + 8) = *(_DWORD *)(a2 + 24);
        *(_DWORD *)(v40 + v39 + 12) = 1;
        v40 += *(_DWORD *)(v40 + v39);
        memmove((void *)(v39 + 16 + v44), Src, v43);
        v39 = (__int64)v63;
      }
      if ( *((_BYTE *)v6 + 52) )
      {
        *(_QWORD *)(v40 + v39) = 24;
        *(_DWORD *)(v40 + v39 + 8) = *(_DWORD *)(a2 + 24);
        *(_DWORD *)(v40 + v39 + 12) = 21;
        *(_DWORD *)(v40 + v39 + 16) = *((unsigned __int8 *)v6 + 52);
      }
      *(_OWORD *)(v4 + 88) = *(_OWORD *)v68;
      *(_OWORD *)(v4 + 104) = *(_OWORD *)(v68 + 16);
      *(_OWORD *)(v4 + 168) = *(_OWORD *)v6;
      *(_OWORD *)(v4 + 184) = *((_OWORD *)v6 + 1);
      *(_OWORD *)(v4 + 200) = *((_OWORD *)v6 + 2);
      *(_OWORD *)(v4 + 216) = *((_OWORD *)v6 + 3);
      *(_OWORD *)(v4 + 232) = *((_OWORD *)v6 + 4);
      *(_QWORD *)(v4 + 248) = *((_QWORD *)v6 + 10);
      *(_DWORD *)(v4 + 120) = 259;
      SpinLock = (PKSPIN_LOCK)(a2 + 20048);
      v45 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 20048));
      LOBYTE(NewIrql) = v45;
      v80 = a2 + 19936;
      if ( !IppFindEchoRequest(a2 + 19936, v46, v68) )
      {
        v7 = 44;
        v8 = -536850433;
        IppInsertEchoRequest(v80, v47, v4);
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 8)) <= 1 )
          __fastfail(0xEu);
        *(LARGE_INTEGER *)(v4 + 80) = KeQueryPerformanceCounter(0);
        v48 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v4);
        v49 = v79;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v79 + 20064));
        v50 = IppMillisecondsToTicks(v6[7]);
        IppStartEchoRequestTimer(v49, v4, v48 / 0x1F4, v50);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v49 + 20064));
        KeReleaseSpinLockFromDpcLevel(SpinLock);
        KeReleaseSpinLock((PKSPIN_LOCK)v4, NewIrql);
        v77[0] = v59;
        LOBYTE(v77[26]) = 0x80;
        LOWORD(v77[7]) = 58;
        LODWORD(v77[17]) = v6[12];
        v77[18] = v64;
        v77[4] = v61;
        v5 = v63;
        v77[10] = v63;
        LODWORD(v77[9]) = v66;
        IppSendControl(0, v49, v77);
        v13 = 0;
        goto LABEL_67;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 20048), v45);
      v13 = -1073741270;
      v7 = 36;
      v8 = -536854076;
    }
    else
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v38,
          L"IPv6 echo ancillary data (IPNG)");
      v13 = -1073741670;
      v7 = 35;
      v8 = -536854077;
    }
    v5 = v63;
LABEL_67:
    v14 = v59;
    v15 = v61;
    Compartment = v60;
    goto LABEL_84;
  }
  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v23,
      L"IPv6 echo reply MDL (IPNG)");
  v13 = -1073741801;
  v7 = 35;
  v8 = -536854088;
  v5 = 0;
  v14 = 0;
  v15 = 0;
  Compartment = 0;
LABEL_84:
  if ( v13 < 0 )
  {
    if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredContext) & 4) != 0 || byte_140229CC0 )
    {
      v51 = 0;
      if ( v15 )
      {
        v52 = **(_QWORD **)(*v15 + 16LL);
        v53 = *(_QWORD *)(*v15 + 8LL);
        v54 = (void *)v15[2];
      }
      else
      {
        LODWORD(v53) = 0;
        if ( v6 )
        {
          v52 = (__int64)(v6 + 14);
          v54 = v6 + 18;
        }
        else
        {
          v52 = 0;
          v54 = 0;
        }
      }
      if ( Compartment )
        v51 = *Compartment;
      LogIcmpSendDrop(v79, 128, SBYTE1(v77[26]), v7, v13, v51, v52, v54, v53, v14, 0, v8);
    }
    if ( v59 )
    {
      *(_DWORD *)(v59 + 140) = v13;
      *(_DWORD *)(v4 + 68) |= 2u;
      NetioDereferenceNetBufferList(v59, 0);
    }
    else
    {
      if ( MemoryDescriptorList )
      {
        if ( v56 )
          MmUnlockPages(MemoryDescriptorList);
        IoFreeMdl(MemoryDescriptorList);
      }
      if ( v4 )
        IppDereferenceEchoRequest((PVOID)v4);
    }
  }
  if ( v61 )
    IppDereferencePath(v61);
  if ( Mdl )
  {
    if ( v57 )
      MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
  }
  if ( v71 )
  {
    if ( v58 )
      MmUnlockPages(v71);
    IoFreeMdl(v71);
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140086914  mov     rax, rsp
0x140086917  mov     [rax+10h], rdx
0x14008691b  push    rbx
0x14008691c  push    rsi
0x14008691d  push    rdi
0x14008691e  push    r12
0x140086920  push    r13
0x140086922  push    r14
0x140086924  push    r15
0x140086926  sub     rsp, 290h
0x14008692d  mov     r15, rdx
0x140086930  mov     rbx, rcx
0x140086933  xor     esi, esi
0x140086935  mov     r13d, esi
0x140086938  mov     [rsp+2C8h+var_267], sil
0x14008693d  mov     [rsp+2C8h+var_266], sil
0x140086942  mov     [rsp+2C8h+var_268], sil
0x140086947  mov     [rax-200h], rsi
0x14008694e  mov     [rax-1F8h], rsi
0x140086955  mov     [rax-208h], rsi
0x14008695c  mov     edi, esi
0x14008695e  mov     [rsp+2C8h+var_258], rsi
0x140086963  mov     [rax-1E8h], rsi
0x14008696a  xorps   xmm0, xmm0
0x14008696d  movups  xmmword ptr [rax-1E0h], xmm0
0x140086974  xor     edx, edx; Val
0x140086976  mov     r8d, 0D8h; Size
0x14008697c  lea     rcx, [rax-118h]; void *
0x140086983  call    memset
0x140086988  mov     [rsp+2C8h+var_248], rsi
0x140086990  xor     edx, edx; Val
0x140086992  mov     r8d, 0A0h; Size
0x140086998  lea     rcx, [rsp+2C8h+var_1B8]; void *
0x1400869a0  call    memset
0x1400869a5  mov     r12, [rbx+20h]
0x1400869a9  mov     [rsp+2C8h+var_228], r12
0x1400869b1  test    r12, r12
0x1400869b4  jnz     short loc_1400869C4
0x1400869b6  mov     r14d, esi
0x1400869b9  mov     r15d, 0E00041B0h
0x1400869bf  jmp     loc_140087468
0x1400869c4  cmp     [r12+1Ch], esi
0x1400869c9  jnz     short loc_1400869D9
0x1400869cb  mov     r14d, esi
0x1400869ce  mov     r15d, 0E00041B1h
0x1400869d4  jmp     loc_140087468
0x1400869d9  mov     rbx, [rbx+10h]
0x1400869dd  mov     [rsp+2C8h+var_210], rbx
0x1400869e5  call    cs:__imp_PsGetCurrentProcessId
0x1400869ec  nop     dword ptr [rax+rax+00h]
0x1400869f1  cmp     [rbx+8], eax
0x1400869f4  jz      short loc_140086A04
0x1400869f6  mov     r14d, esi
0x1400869f9  mov     r15d, 0E00041B2h
0x1400869ff  jmp     loc_140087468
0x140086a04  cmp     [r12+10h], rsi
0x140086a09  jz      loc_14008745C
0x140086a0f  mov     [rsp+2C8h+var_240], rsi
0x140086a17  mov     [rsp+2C8h+Src], rsi
0x140086a1f  mov     r14d, esi
0x140086a22  mov     word ptr [rsp+2C8h+arg_10], si
0x140086a2a  mov     eax, [r12+4]
0x140086a2f  cmp     [r12+18h], eax
0x140086a34  ja      loc_14008745C
0x140086a3a  mov     edx, [r12]; Length
0x140086a3e  mov     edi, 1
0x140086a43  test    edx, edx
0x140086a45  jz      loc_140086B62
0x140086a4b  mov     [rsp+2C8h+Irp], rsi; Irp
0x140086a50  mov     r9b, dil; ChargeQuota
0x140086a53  xor     r8d, r8d; SecondaryBuffer
0x140086a56  mov     rcx, [r12+8]; VirtualAddress
0x140086a5b  call    cs:__imp_IoAllocateMdl
0x140086a62  nop     dword ptr [rax+rax+00h]
0x140086a67  mov     rbx, rax
0x140086a6a  mov     [rsp+2C8h+Mdl], rax
0x140086a72  test    rax, rax
0x140086a75  jnz     short loc_140086ACB
0x140086a77  mov     al, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140086a7d  test    al, al
0x140086a7f  jns     short loc_140086A9B
0x140086a81  lea     r9, aIpv6EchoDataMd; "IPv6 echo data MDL (IPNG)"
0x140086a88  lea     rdx, TCPIP_MEMORY_FAILURES
0x140086a8f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140086a96  call    McTemplateK0z_EtwWriteTransfer
0x140086a9b  mov     ebx, 0C0000017h
0x140086aa0  mov     [rsp+2C8h+var_264], ebx
0x140086aa4  mov     r14d, 23h ; '#'
0x140086aaa  mov     [rsp+2C8h+var_260], r14d
0x140086aaf  mov     r15d, 0E00041B4h
0x140086ab5  mov     [rsp+2C8h+var_25C], r15d
0x140086aba  mov     rdi, rsi
0x140086abd  mov     r10, rsi
0x140086ac0  mov     r8, rsi
0x140086ac3  mov     r11, rsi
0x140086ac6  jmp     loc_140087476
0x140086acb  xor     r8d, r8d; Operation
0x140086ace  mov     dl, dil; AccessMode
0x140086ad1  mov     rcx, rbx; MemoryDescriptorList
0x140086ad4  call    cs:__imp_MmProbeAndLockPages
0x140086adb  nop     dword ptr [rax+rax+00h]
0x140086ae0  mov     [rsp+2C8h+var_267], dil
0x140086ae5  test    byte ptr [rbx+0Ah], 5
0x140086ae9  jz      short loc_140086AF9
0x140086aeb  mov     rcx, [rbx+18h]
0x140086aef  mov     [rsp+2C8h+var_240], rcx
0x140086af7  jmp     short loc_140086B27
0x140086af9  mov     [rsp+2C8h+Priority], 40000010h; Priority
0x140086b01  mov     dword ptr [rsp+2C8h+Irp], esi; BugCheckOnFailure
0x140086b05  xor     r9d, r9d; RequestedAddress
0x140086b08  mov     r8d, edi; CacheType
0x140086b0b  xor     edx, edx; AccessMode
0x140086b0d  mov     rcx, rbx; MemoryDescriptorList
0x140086b10  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140086b17  nop     dword ptr [rax+rax+00h]
0x140086b1c  mov     rcx, rax
0x140086b1f  mov     [rsp+2C8h+var_240], rax
0x140086b27  mov     [rsp+2C8h+var_1D0], rcx
0x140086b2f  test    rcx, rcx
0x140086b32  jnz     short loc_140086B62
0x140086b34  mov     ebx, 0C000009Ah
0x140086b39  mov     [rsp+2C8h+var_264], ebx
0x140086b3d  lea     r14d, [rcx+23h]
0x140086b41  mov     [rsp+2C8h+var_260], r14d
0x140086b46  mov     r15d, 0E00041B5h
0x140086b4c  mov     [rsp+2C8h+var_25C], r15d
0x140086b51  mov     rdi, rsi
0x140086b54  mov     r10, rsi
0x140086b57  mov     r8, rsi
0x140086b5a  mov     r11, rsi
0x140086b5d  jmp     loc_140087476
0x140086b62  movzx   eax, word ptr [r12+28h]
0x140086b68  test    ax, ax
0x140086b6b  jz      loc_140086CAD
0x140086b71  mov     edx, eax; Length
0x140086b73  mov     [rsp+2C8h+Irp], rsi; Irp
0x140086b78  mov     r9b, dil; ChargeQuota
0x140086b7b  xor     r8d, r8d; SecondaryBuffer
0x140086b7e  mov     rcx, [r12+20h]; VirtualAddress
0x140086b83  call    cs:__imp_IoAllocateMdl
0x140086b8a  nop     dword ptr [rax+rax+00h]
0x140086b8f  mov     rbx, rax
0x140086b92  mov     [rsp+2C8h+var_1F8], rax
0x140086b9a  test    rax, rax
0x140086b9d  jnz     short loc_140086BF3
0x140086b9f  mov     al, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140086ba5  test    al, al
0x140086ba7  jns     short loc_140086BC3
0x140086ba9  lea     r9, aIpv6EchoOption; "IPv6 echo options MDL (IPNG)"
0x140086bb0  lea     rdx, TCPIP_MEMORY_FAILURES
0x140086bb7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140086bbe  call    McTemplateK0z_EtwWriteTransfer
0x140086bc3  mov     ebx, 0C0000017h
0x140086bc8  mov     [rsp+2C8h+var_264], ebx
0x140086bcc  mov     r14d, 23h ; '#'
0x140086bd2  mov     [rsp+2C8h+var_260], r14d
0x140086bd7  mov     r15d, 0E00041B6h
0x140086bdd  mov     [rsp+2C8h+var_25C], r15d
0x140086be2  mov     rdi, rsi
0x140086be5  mov     r10, rsi
0x140086be8  mov     r8, rsi
0x140086beb  mov     r11, rsi
0x140086bee  jmp     loc_140087476
0x140086bf3  xor     r8d, r8d; Operation
0x140086bf6  mov     dl, dil; AccessMode
0x140086bf9  mov     rcx, rbx; MemoryDescriptorList
0x140086bfc  call    cs:__imp_MmProbeAndLockPages
0x140086c03  nop     dword ptr [rax+rax+00h]
0x140086c08  mov     [rsp+2C8h+var_266], dil
0x140086c0d  test    byte ptr [rbx+0Ah], 5
0x140086c11  jz      short loc_140086C19
0x140086c13  mov     rax, [rbx+18h]
0x140086c17  jmp     short loc_140086C3C
0x140086c19  mov     [rsp+2C8h+Priority], 40000010h; Priority
0x140086c21  mov     dword ptr [rsp+2C8h+Irp], esi; BugCheckOnFailure
0x140086c25  xor     r9d, r9d; RequestedAddress
0x140086c28  mov     r8d, edi; CacheType
0x140086c2b  xor     edx, edx; AccessMode
0x140086c2d  mov     rcx, rbx; MemoryDescriptorList
0x140086c30  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140086c37  nop     dword ptr [rax+rax+00h]
0x140086c3c  mov     [rsp+2C8h+Src], rax
0x140086c44  mov     [rsp+2C8h+var_1C8], rax
0x140086c4c  test    rax, rax
0x140086c4f  jnz     short loc_140086C7F
0x140086c51  mov     ebx, 0C000009Ah
0x140086c56  mov     [rsp+2C8h+var_264], ebx
0x140086c5a  lea     r14d, [rax+23h]
0x140086c5e  mov     [rsp+2C8h+var_260], r14d
0x140086c63  mov     r15d, 0E00041B7h
0x140086c69  mov     [rsp+2C8h+var_25C], r15d
0x140086c6e  mov     rdi, rsi
0x140086c71  mov     r10, rsi
0x140086c74  mov     r8, rsi
0x140086c77  mov     r11, rsi
0x140086c7a  jmp     loc_140087476
0x140086c7f  movzx   r14d, word ptr [r12+28h]
0x140086c85  movzx   eax, r14w
0x140086c89  mov     word ptr [rsp+2C8h+arg_10], ax
0x140086c91  mov     [rsp+2C8h+var_230], ax
0x140086c99  add     r14d, 7
0x140086c9d  and     r14d, 0FFFFFFF8h
0x140086ca1  add     r14d, 10h
0x140086ca5  mov     [rsp+2C8h+var_1F0], r14d
0x140086cad  mov     [rsp+2C8h+Irp], rsi; Irp
0x140086cb2  mov     r9b, dil; ChargeQuota
0x140086cb5  xor     r8d, r8d; SecondaryBuffer
0x140086cb8  mov     edx, [r12+4]; Length
0x140086cbd  mov     rcx, [r12+10h]; VirtualAddress
0x140086cc2  call    cs:__imp_IoAllocateMdl
0x140086cc9  nop     dword ptr [rax+rax+00h]
0x140086cce  mov     rbx, rax
0x140086cd1  mov     [rsp+2C8h+MemoryDescriptorList], rax
0x140086cd9  test    rax, rax
0x140086cdc  jnz     short loc_140086D32
0x140086cde  mov     al, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140086ce4  test    al, al
0x140086ce6  jns     short loc_140086D02
0x140086ce8  lea     r9, aIpv6EchoReplyM; "IPv6 echo reply MDL (IPNG)"
0x140086cef  lea     rdx, TCPIP_MEMORY_FAILURES
0x140086cf6  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140086cfd  call    McTemplateK0z_EtwWriteTransfer
0x140086d02  mov     ebx, 0C0000017h
0x140086d07  mov     [rsp+2C8h+var_264], ebx
0x140086d0b  mov     r14d, 23h ; '#'
0x140086d11  mov     [rsp+2C8h+var_260], r14d
0x140086d16  mov     r15d, 0E00041B8h
0x140086d1c  mov     [rsp+2C8h+var_25C], r15d
0x140086d21  mov     rdi, rsi
0x140086d24  mov     r10, rsi
0x140086d27  mov     r8, rsi
0x140086d2a  mov     r11, rsi
0x140086d2d  jmp     loc_140087476
0x140086d32  mov     r8d, edi; Operation
0x140086d35  mov     dl, dil; AccessMode
0x140086d38  mov     rcx, rbx; MemoryDescriptorList
0x140086d3b  call    cs:__imp_MmProbeAndLockPages
0x140086d42  nop     dword ptr [rax+rax+00h]
0x140086d47  mov     [rsp+2C8h+var_268], dil
0x140086d4c  call    NdisGetCurrentThreadCompartmentId
0x140086d51  mov     [rsp+2C8h+var_1D8], eax
0x140086d58  lea     rdx, [rsp+2C8h+var_1E0]
0x140086d60  mov     rcx, r15
0x140086d63  call    IppGetCompartment
0x140086d68  mov     r11, rax
0x140086d6b  mov     [rsp+2C8h+var_250], rax
0x140086d70  test    rax, rax
0x140086d73  jnz     short loc_140086D86
0x140086d75  mov     r14d, esi
0x140086d78  mov     r15d, 0E00041BAh
0x140086d7e  mov     rdi, rsi
0x140086d81  jmp     loc_14008746B
0x140086d86  mov     edx, 100h
0x140086d8b  mov     ecx, 40h ; '@'
0x140086d90  mov     r8d, 20653649h
0x140086d96  call    cs:__imp_ExAllocatePool2
0x140086d9d  nop     dword ptr [rax+rax+00h]
0x140086da2  mov     r13, rax
0x140086da5  test    rax, rax
0x140086da8  jnz     short loc_140086DEC
0x140086daa  mov     cl, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140086db0  test    cl, cl
0x140086db2  jns     short loc_140086DCE
0x140086db4  lea     r9, aIpv6EchoReques_0; "IPv6 echo request (IPNG)"
0x140086dbb  lea     rdx, TCPIP_MEMORY_FAILURES
0x140086dc2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140086dc9  call    McTemplateK0z_EtwWriteTransfer
0x140086dce  mov     ebx, 0C000009Ah
0x140086dd3  mov     r14d, 23h ; '#'
0x140086dd9  mov     r15d, 0E00041BBh
0x140086ddf  mov     rdi, rsi
0x140086de2  mov     r11, [rsp+2C8h+var_250]
0x140086de7  jmp     loc_140087470
0x140086dec  mov     [rax+8], rdi
0x140086df0  lea     rdx, [rax+20h]
0x140086df4  xor     r9d, r9d
0x140086df7  xor     r8d, r8d
0x140086dfa  xor     ecx, ecx
0x140086dfc  call    cs:__imp_RtlInitializeTimerWheelEntry
0x140086e03  nop     dword ptr [rax+rax+00h]
0x140086e08  lea     rax, [r13+10h]
0x140086e0c  mov     [rax+8], rax
0x140086e10  mov     [rax], rax
0x140086e13  mov     rcx, r13; SpinLock
0x140086e16  call    cs:__imp_KeInitializeSpinLock
0x140086e1d  nop     dword ptr [rax+rax+00h]
0x140086e22  mov     r11, [rsp+2C8h+var_250]
0x140086e27  mov     [r13+38h], r11
0x140086e2b  mov     [r13+48h], rbx
0x140086e2f  mov     r8b, [r12+35h]
0x140086e34  mov     byte ptr [rsp+2C8h+NewIrql], r8b
0x140086e3c  test    r8b, r8b
0x140086e3f  jz      short loc_140086E45
0x140086e41  add     r14d, 28h ; '('
0x140086e45  mov     eax, [r12]
0x140086e49  lea     ecx, [rax+8]
0x140086e4c  cmp     ecx, eax
0x140086e4e  jnb     short loc_140086E66
0x140086e50  mov     r15d, 0E00041BCh
0x140086e56  mov     r14d, esi
  ... truncated ...
```
