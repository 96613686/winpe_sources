# Ipv6SetEchoRequestCreate

- ea: `0x14007b054`
- end: `0x14007bd61`
- name: `Ipv6SetEchoRequestCreate`
- size: `3341`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140079fc0`

## callees

- `0x140017140`
- `0x140027160`
- `0x140034190`
- `0x140054138`
- `0x140064ec0`
- `0x1400650a0`
- `0x140079e3c`
- `0x140079f64`
- `0x14007a208`
- `0x14007b054`
- `0x14007bd68`
- `0x14007bff4`
- `0x140080790`
- `0x14009cfd0`
- `0x14009e604`
- `0x1400a69c0`
- `0x1400a9334`
- `0x1401bf780`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14007bc94`
- `ntoskrnl!MmUnlockPages` at `0x14007bce8`
- `ntoskrnl!MmUnlockPages` at `0x14007bd1a`
- `ntoskrnl!MmUnlockPages` at `0x14007bc94`
- `ntoskrnl!MmUnlockPages` at `0x14007bce8`
- `ntoskrnl!MmUnlockPages` at `0x14007bd1a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007b214`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007b33c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007b47b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007b214`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007b33c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007b47b`
- `ntoskrnl!IoAllocateMdl` at `0x14007b19b`
- `ntoskrnl!IoAllocateMdl` at `0x14007b2c3`
- `ntoskrnl!IoAllocateMdl` at `0x14007b402`
- `ntoskrnl!IoAllocateMdl` at `0x14007b19b`
- `ntoskrnl!IoAllocateMdl` at `0x14007b2c3`
- `ntoskrnl!IoAllocateMdl` at `0x14007b402`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007b250`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007b370`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007b250`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007b370`
- `ntoskrnl!IoFreeMdl` at `0x14007bca3`
- `ntoskrnl!IoFreeMdl` at `0x14007bcf7`
- `ntoskrnl!IoFreeMdl` at `0x14007bd29`
- `ntoskrnl!IoFreeMdl` at `0x14007bca3`
- `ntoskrnl!IoFreeMdl` at `0x14007bcf7`
- `ntoskrnl!IoFreeMdl` at `0x14007bd29`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ba40`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ba5b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ba40`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ba5b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007baa1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007bab5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007baa1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007bab5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b125`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b125`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007b9b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007bacb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007b9b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007bacb`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007b556`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007b556`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007b975`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007b975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd3f`
- `ntoskrnl!ExAllocatePool2` at `0x14007b4d6`
- `ntoskrnl!ExAllocatePool2` at `0x14007b780`
- `ntoskrnl!ExAllocatePool2` at `0x14007b4d6`
- `ntoskrnl!ExAllocatePool2` at `0x14007b780`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007bc6f`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007bc6f`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14007b53c`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14007b53c`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14007b67a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14007b67a`
- `HAL!KeQueryPerformanceCounter` at `0x14007ba0c`
- `HAL!KeQueryPerformanceCounter` at `0x14007ba0c`

## pseudocode

```c
__int64 __fastcall Ipv6SetEchoRequestCreate(__int64 a1, __int64 a2)
{
  __int64 v4; // r13
  void *v5; // rdi
  __int64 v6; // rdx
  unsigned int *v7; // r12
  int v8; // r14d
  int v9; // r15d
  unsigned int v10; // r14d
  struct _MDL *v11; // rax
  __int64 v12; // r8
  struct _MDL *v13; // rbx
  int v14; // ebx
  int v15; // r10d
  _QWORD *v16; // r8
  int *Compartment; // r11
  PVOID MappedSystemVa; // rcx
  struct _MDL *v19; // rax
  __int64 v20; // r8
  struct _MDL *v21; // rbx
  PVOID v22; // rax
  struct _MDL *v23; // rax
  __int64 v24; // r8
  struct _MDL *v25; // rbx
  __int64 Pool2; // rax
  __int64 v27; // r8
  char v28; // r8
  unsigned int v29; // ecx
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
  v7 = *(unsigned int **)(a1 + 32);
  if ( !v7 )
  {
    v8 = 0;
    v9 = -536854096;
LABEL_80:
    Compartment = 0;
    goto LABEL_81;
  }
  if ( !v7[7] )
  {
    v8 = 0;
    v9 = -536854095;
    goto LABEL_80;
  }
  v68 = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(v68 + 8) != (unsigned int)PsGetCurrentProcessId() )
  {
    v8 = 0;
    v9 = -536854094;
    goto LABEL_80;
  }
  if ( !*((_QWORD *)v7 + 2) || (v62 = 0, Src = 0, v10 = 0, LOWORD(v80) = 0, v7[6] > v7[1]) )
  {
    v8 = 15;
    v9 = -536854093;
    goto LABEL_80;
  }
  if ( *v7 )
  {
    v11 = IoAllocateMdl(*((PVOID *)v7 + 1), *v7, 0, 1u, 0);
    v13 = v11;
    Mdl = v11;
    if ( !v11 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v12,
          L"IPv6 echo data MDL (IPNG)");
      v14 = -1073741801;
      v8 = 35;
      v9 = -536854092;
      v5 = 0;
      v15 = 0;
      v16 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
    MmProbeAndLockPages(v11, 1, IoReadAccess);
    v57 = 1;
    if ( (v13->MdlFlags & 5) != 0 )
      MappedSystemVa = v13->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v13, 0, MmCached, 0, 0, 0x40000010u);
    v62 = MappedSystemVa;
    v74 = MappedSystemVa;
    if ( !MappedSystemVa )
    {
      v14 = -1073741670;
      v8 = 35;
      v9 = -536854091;
      v5 = 0;
      v15 = 0;
      v16 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
  }
  if ( *((_WORD *)v7 + 20) )
  {
    v19 = IoAllocateMdl(*((PVOID *)v7 + 4), *((unsigned __int16 *)v7 + 20), 0, 1u, 0);
    v21 = v19;
    v71 = v19;
    if ( !v19 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v20,
          L"IPv6 echo options MDL (IPNG)");
      v14 = -1073741801;
      v8 = 35;
      v9 = -536854090;
      v5 = 0;
      v15 = 0;
      v16 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
    MmProbeAndLockPages(v19, 1, IoReadAccess);
    v58 = 1;
    if ( (v21->MdlFlags & 5) != 0 )
      v22 = v21->MappedSystemVa;
    else
      v22 = MmMapLockedPagesSpecifyCache(v21, 0, MmCached, 0, 0, 0x40000010u);
    Src = v22;
    v75 = v22;
    if ( !v22 )
    {
      v14 = -1073741670;
      v8 = 35;
      v9 = -536854089;
      v5 = 0;
      v15 = 0;
      v16 = 0;
      Compartment = 0;
      goto LABEL_84;
    }
    LOWORD(v80) = *((_WORD *)v7 + 20);
    v10 = (((unsigned __int16)v80 + 7) & 0xFFFFFFF8) + 16;
  }
  v23 = IoAllocateMdl(*((PVOID *)v7 + 2), v7[1], 0, 1u, 0);
  v25 = v23;
  MemoryDescriptorList = v23;
  if ( v23 )
  {
    MmProbeAndLockPages(v23, 1, IoWriteAccess);
    v56 = 1;
    DWORD2(v73) = NdisGetCurrentThreadCompartmentId();
    Compartment = (int *)IppGetCompartment(a2, &v73);
    v60 = Compartment;
    if ( !Compartment )
    {
      v8 = 0;
      v9 = -536854086;
      v5 = 0;
LABEL_81:
      v14 = -1073741811;
      goto LABEL_82;
    }
    Pool2 = ExAllocatePool2(64, 256, 543503945);
    v4 = Pool2;
    if ( !Pool2 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v27,
          L"IPv6 echo request (IPNG)");
      v14 = -1073741670;
      v8 = 35;
      v9 = -536854085;
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
    *(_QWORD *)(v4 + 72) = v25;
    v28 = *((_BYTE *)v7 + 53);
    LOBYTE(NewIrql) = v28;
    if ( v28 )
      v10 += 40;
    v29 = *v7 + 8;
    if ( v29 < *v7 )
    {
      v9 = -536854084;
LABEL_44:
      v8 = 0;
      v14 = -1073741675;
      v5 = 0;
LABEL_82:
      v15 = 0;
      goto LABEL_83;
    }
    v65 = (unsigned __int16)v80 + 7;
    v6 = (v65 & 0xFFFFFFF8) + v29;
    if ( (unsigned int)v6 < v29 )
    {
      v9 = -536854083;
      goto LABEL_44;
    }
    LODWORD(SpinLock) = v28 != 0 ? 0x18 : 0;
    v30 = (_DWORD)SpinLock + v6;
    if ( (int)SpinLock + (int)v6 < (unsigned int)v6 )
    {
      v9 = -536854082;
      goto LABEL_44;
    }
    v31 = v30 + *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 8LL);
    if ( v31 < v30 )
    {
      v9 = -536854081;
      goto LABEL_44;
    }
    NetBufferListForEcho = IppAllocateNetBufferListForEcho(v31);
    v15 = NetBufferListForEcho;
    v59 = NetBufferListForEcho;
    if ( !NetBufferListForEcho )
    {
      v14 = -1073741670;
      v8 = 35;
      v9 = -536854080;
LABEL_53:
      v5 = 0;
      Compartment = v60;
LABEL_83:
      v16 = 0;
      goto LABEL_84;
    }
    v33 = *v7;
    if ( (_DWORD)v33 )
    {
      NetioRetreatNetBuffer(*(_QWORD *)(NetBufferListForEcho + 8), v33, 0);
      RtlCopyKernelBufferToMdl(
        v62,
        *(_QWORD *)(*(_QWORD *)(v59 + 8) + 8LL),
        *(unsigned int *)(*(_QWORD *)(v59 + 8) + 16LL),
        *v7,
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
    v64 = v7 + 18;
    v76[0] = *(_QWORD *)(v4 + 56);
    v76[8] = v7 + 18;
    LODWORD(v76[7]) = v7[12];
    if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(v7 + 14)) )
    {
      LODWORD(v76[10]) = v7[11];
      v76[11] = v36;
    }
    v76[16] = *(_QWORD *)(a2 + 4744);
    v76[17] = 0;
    LODWORD(v76[19]) = 58;
    BYTE4(v76[19]) = 0x80;
    v14 = IppJoinPath(a2, v76);
    if ( v14 < 0 )
    {
      v8 = 13;
      v9 = -536854078;
      v15 = v59;
      goto LABEL_53;
    }
    v61 = (_QWORD *)v76[15];
    v66 = v10 + 24;
    v37 = ExAllocatePool2(64, v10 + 24, 543503945);
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
        *(_OWORD *)(v37 + 24) = *(_OWORD *)(v7 + 18);
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
      if ( *((_BYTE *)v7 + 52) )
      {
        *(_QWORD *)(v40 + v39) = 24;
        *(_DWORD *)(v40 + v39 + 8) = *(_DWORD *)(a2 + 24);
        *(_DWORD *)(v40 + v39 + 12) = 21;
        *(_DWORD *)(v40 + v39 + 16) = *((unsigned __int8 *)v7 + 52);
      }
      *(_OWORD *)(v4 + 88) = *(_OWORD *)v68;
      *(_OWORD *)(v4 + 104) = *(_OWORD *)(v68 + 16);
      *(_OWORD *)(v4 + 168) = *(_OWORD *)v7;
      *(_OWORD *)(v4 + 184) = *((_OWORD *)v7 + 1);
      *(_OWORD *)(v4 + 200) = *((_OWORD *)v7 + 2);
      *(_OWORD *)(v4 + 216) = *((_OWORD *)v7 + 3);
      *(_OWORD *)(v4 + 232) = *((_OWORD *)v7 + 4);
      *(_QWORD *)(v4 + 248) = *((_QWORD *)v7 + 10);
      *(_DWORD *)(v4 + 120) = 259;
      SpinLock = (PKSPIN_LOCK)(a2 + 20048);
      v45 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 20048));
      LOBYTE(NewIrql) = v45;
      v80 = a2 + 19936;
      if ( !IppFindEchoRequest(a2 + 19936, v46, v68) )
      {
        v8 = 44;
        v9 = -536850433;
        IppInsertEchoRequest(v80, v47, v4);
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 8)) <= 1 )
          __fastfail(0xEu);
        *(LARGE_INTEGER *)(v4 + 80) = KeQueryPerformanceCounter(0);
        v48 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v4);
        v49 = v79;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v79 + 20064));
        v50 = IppMillisecondsToTicks(v7[7]);
        IppStartEchoRequestTimer(v49, v4, v48 / 0x1F4, v50);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v49 + 20064));
        KeReleaseSpinLockFromDpcLevel(SpinLock);
        KeReleaseSpinLock((PKSPIN_LOCK)v4, NewIrql);
        v77[0] = v59;
        LOBYTE(v77[26]) = 0x80;
        LOWORD(v77[7]) = 58;
        LODWORD(v77[17]) = v7[12];
        v77[18] = v64;
        v77[4] = v61;
        v5 = v63;
        v77[10] = v63;
        LODWORD(v77[9]) = v66;
        IppSendControl(0, v49, v77);
        v14 = 0;
        goto LABEL_67;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 20048), v45);
      v14 = -1073741270;
      v8 = 36;
      v9 = -536854076;
    }
    else
    {
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v38,
          L"IPv6 echo ancillary data (IPNG)");
      v14 = -1073741670;
      v8 = 35;
      v9 = -536854077;
    }
    v5 = v63;
LABEL_67:
    v15 = v59;
    v16 = v61;
    Compartment = v60;
    goto LABEL_84;
  }
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v24,
      L"IPv6 echo reply MDL (IPNG)");
  v14 = -1073741801;
  v8 = 35;
  v9 = -536854088;
  v5 = 0;
  v15 = 0;
  v16 = 0;
  Compartment = 0;
LABEL_84:
  if ( v14 < 0 )
  {
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 11) & 4) != 0 || byte_140225C30 )
    {
      v51 = 0;
      if ( v16 )
      {
        v52 = **(_QWORD **)(*v16 + 16LL);
        v53 = *(_QWORD *)(*v16 + 8LL);
        v54 = (void *)v16[2];
      }
      else
      {
        LODWORD(v53) = 0;
        if ( v7 )
        {
          v52 = (__int64)(v7 + 14);
          v54 = v7 + 18;
        }
        else
        {
          v52 = 0;
          v54 = 0;
        }
      }
      if ( Compartment )
        v51 = *Compartment;
      LogIcmpSendDrop(v79, 128, SBYTE1(v77[26]), v8, v14, v51, v52, v54, v53, v15, 0, v9);
    }
    if ( v59 )
    {
      *(_DWORD *)(v59 + 140) = v14;
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
    IppDereferencePath(v61, v6, v16);
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
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14007b054  mov     rax, rsp
0x14007b057  mov     [rax+10h], rdx
0x14007b05b  push    rbx
0x14007b05c  push    rsi
0x14007b05d  push    rdi
0x14007b05e  push    r12
0x14007b060  push    r13
0x14007b062  push    r14
0x14007b064  push    r15
0x14007b066  sub     rsp, 290h
0x14007b06d  mov     r15, rdx
0x14007b070  mov     rbx, rcx
0x14007b073  xor     esi, esi
0x14007b075  mov     r13d, esi
0x14007b078  mov     [rsp+2C8h+var_267], sil
0x14007b07d  mov     [rsp+2C8h+var_266], sil
0x14007b082  mov     [rsp+2C8h+var_268], sil
0x14007b087  mov     [rax-200h], rsi
0x14007b08e  mov     [rax-1F8h], rsi
0x14007b095  mov     [rax-208h], rsi
0x14007b09c  mov     edi, esi
0x14007b09e  mov     [rsp+2C8h+var_258], rsi
0x14007b0a3  mov     [rax-1E8h], rsi
0x14007b0aa  xorps   xmm0, xmm0
0x14007b0ad  movups  xmmword ptr [rax-1E0h], xmm0
0x14007b0b4  xor     edx, edx; Val
0x14007b0b6  mov     r8d, 0D8h; Size
0x14007b0bc  lea     rcx, [rax-118h]; void *
0x14007b0c3  call    memset
0x14007b0c8  mov     [rsp+2C8h+var_248], rsi
0x14007b0d0  xor     edx, edx; Val
0x14007b0d2  mov     r8d, 0A0h; Size
0x14007b0d8  lea     rcx, [rsp+2C8h+var_1B8]; void *
0x14007b0e0  call    memset
0x14007b0e5  mov     r12, [rbx+20h]
0x14007b0e9  mov     [rsp+2C8h+var_228], r12
0x14007b0f1  test    r12, r12
0x14007b0f4  jnz     short loc_14007B104
0x14007b0f6  mov     r14d, esi
0x14007b0f9  mov     r15d, 0E00041B0h
0x14007b0ff  jmp     loc_14007BBA8
0x14007b104  cmp     [r12+1Ch], esi
0x14007b109  jnz     short loc_14007B119
0x14007b10b  mov     r14d, esi
0x14007b10e  mov     r15d, 0E00041B1h
0x14007b114  jmp     loc_14007BBA8
0x14007b119  mov     rbx, [rbx+10h]
0x14007b11d  mov     [rsp+2C8h+var_210], rbx
0x14007b125  call    cs:__imp_PsGetCurrentProcessId
0x14007b12c  nop     dword ptr [rax+rax+00h]
0x14007b131  cmp     [rbx+8], eax
0x14007b134  jz      short loc_14007B144
0x14007b136  mov     r14d, esi
0x14007b139  mov     r15d, 0E00041B2h
0x14007b13f  jmp     loc_14007BBA8
0x14007b144  cmp     [r12+10h], rsi
0x14007b149  jz      loc_14007BB9C
0x14007b14f  mov     [rsp+2C8h+var_240], rsi
0x14007b157  mov     [rsp+2C8h+Src], rsi
0x14007b15f  mov     r14d, esi
0x14007b162  mov     word ptr [rsp+2C8h+arg_10], si
0x14007b16a  mov     eax, [r12+4]
0x14007b16f  cmp     [r12+18h], eax
0x14007b174  ja      loc_14007BB9C
0x14007b17a  mov     edx, [r12]; Length
0x14007b17e  mov     edi, 1
0x14007b183  test    edx, edx
0x14007b185  jz      loc_14007B2A2
0x14007b18b  mov     [rsp+2C8h+Irp], rsi; Irp
0x14007b190  mov     r9b, dil; ChargeQuota
0x14007b193  xor     r8d, r8d; SecondaryBuffer
0x14007b196  mov     rcx, [r12+8]; VirtualAddress
0x14007b19b  call    cs:__imp_IoAllocateMdl
0x14007b1a2  nop     dword ptr [rax+rax+00h]
0x14007b1a7  mov     rbx, rax
0x14007b1aa  mov     [rsp+2C8h+Mdl], rax
0x14007b1b2  test    rax, rax
0x14007b1b5  jnz     short loc_14007B20B
0x14007b1b7  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007b1bd  test    al, al
0x14007b1bf  jns     short loc_14007B1DB
0x14007b1c1  lea     r9, aIpv6EchoDataMd; "IPv6 echo data MDL (IPNG)"
0x14007b1c8  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007b1cf  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007b1d6  call    McTemplateK0z_EtwWriteTransfer
0x14007b1db  mov     ebx, 0C0000017h
0x14007b1e0  mov     [rsp+2C8h+var_264], ebx
0x14007b1e4  mov     r14d, 23h ; '#'
0x14007b1ea  mov     [rsp+2C8h+var_260], r14d
0x14007b1ef  mov     r15d, 0E00041B4h
0x14007b1f5  mov     [rsp+2C8h+var_25C], r15d
0x14007b1fa  mov     rdi, rsi
0x14007b1fd  mov     r10, rsi
0x14007b200  mov     r8, rsi
0x14007b203  mov     r11, rsi
0x14007b206  jmp     loc_14007BBB6
0x14007b20b  xor     r8d, r8d; Operation
0x14007b20e  mov     dl, dil; AccessMode
0x14007b211  mov     rcx, rbx; MemoryDescriptorList
0x14007b214  call    cs:__imp_MmProbeAndLockPages
0x14007b21b  nop     dword ptr [rax+rax+00h]
0x14007b220  mov     [rsp+2C8h+var_267], dil
0x14007b225  test    byte ptr [rbx+0Ah], 5
0x14007b229  jz      short loc_14007B239
0x14007b22b  mov     rcx, [rbx+18h]
0x14007b22f  mov     [rsp+2C8h+var_240], rcx
0x14007b237  jmp     short loc_14007B267
0x14007b239  mov     [rsp+2C8h+Priority], 40000010h; Priority
0x14007b241  mov     dword ptr [rsp+2C8h+Irp], esi; BugCheckOnFailure
0x14007b245  xor     r9d, r9d; RequestedAddress
0x14007b248  mov     r8d, edi; CacheType
0x14007b24b  xor     edx, edx; AccessMode
0x14007b24d  mov     rcx, rbx; MemoryDescriptorList
0x14007b250  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007b257  nop     dword ptr [rax+rax+00h]
0x14007b25c  mov     rcx, rax
0x14007b25f  mov     [rsp+2C8h+var_240], rax
0x14007b267  mov     [rsp+2C8h+var_1D0], rcx
0x14007b26f  test    rcx, rcx
0x14007b272  jnz     short loc_14007B2A2
0x14007b274  mov     ebx, 0C000009Ah
0x14007b279  mov     [rsp+2C8h+var_264], ebx
0x14007b27d  lea     r14d, [rcx+23h]
0x14007b281  mov     [rsp+2C8h+var_260], r14d
0x14007b286  mov     r15d, 0E00041B5h
0x14007b28c  mov     [rsp+2C8h+var_25C], r15d
0x14007b291  mov     rdi, rsi
0x14007b294  mov     r10, rsi
0x14007b297  mov     r8, rsi
0x14007b29a  mov     r11, rsi
0x14007b29d  jmp     loc_14007BBB6
0x14007b2a2  movzx   eax, word ptr [r12+28h]
0x14007b2a8  test    ax, ax
0x14007b2ab  jz      loc_14007B3ED
0x14007b2b1  mov     edx, eax; Length
0x14007b2b3  mov     [rsp+2C8h+Irp], rsi; Irp
0x14007b2b8  mov     r9b, dil; ChargeQuota
0x14007b2bb  xor     r8d, r8d; SecondaryBuffer
0x14007b2be  mov     rcx, [r12+20h]; VirtualAddress
0x14007b2c3  call    cs:__imp_IoAllocateMdl
0x14007b2ca  nop     dword ptr [rax+rax+00h]
0x14007b2cf  mov     rbx, rax
0x14007b2d2  mov     [rsp+2C8h+var_1F8], rax
0x14007b2da  test    rax, rax
0x14007b2dd  jnz     short loc_14007B333
0x14007b2df  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007b2e5  test    al, al
0x14007b2e7  jns     short loc_14007B303
0x14007b2e9  lea     r9, aIpv6EchoOption; "IPv6 echo options MDL (IPNG)"
0x14007b2f0  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007b2f7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007b2fe  call    McTemplateK0z_EtwWriteTransfer
0x14007b303  mov     ebx, 0C0000017h
0x14007b308  mov     [rsp+2C8h+var_264], ebx
0x14007b30c  mov     r14d, 23h ; '#'
0x14007b312  mov     [rsp+2C8h+var_260], r14d
0x14007b317  mov     r15d, 0E00041B6h
0x14007b31d  mov     [rsp+2C8h+var_25C], r15d
0x14007b322  mov     rdi, rsi
0x14007b325  mov     r10, rsi
0x14007b328  mov     r8, rsi
0x14007b32b  mov     r11, rsi
0x14007b32e  jmp     loc_14007BBB6
0x14007b333  xor     r8d, r8d; Operation
0x14007b336  mov     dl, dil; AccessMode
0x14007b339  mov     rcx, rbx; MemoryDescriptorList
0x14007b33c  call    cs:__imp_MmProbeAndLockPages
0x14007b343  nop     dword ptr [rax+rax+00h]
0x14007b348  mov     [rsp+2C8h+var_266], dil
0x14007b34d  test    byte ptr [rbx+0Ah], 5
0x14007b351  jz      short loc_14007B359
0x14007b353  mov     rax, [rbx+18h]
0x14007b357  jmp     short loc_14007B37C
0x14007b359  mov     [rsp+2C8h+Priority], 40000010h; Priority
0x14007b361  mov     dword ptr [rsp+2C8h+Irp], esi; BugCheckOnFailure
0x14007b365  xor     r9d, r9d; RequestedAddress
0x14007b368  mov     r8d, edi; CacheType
0x14007b36b  xor     edx, edx; AccessMode
0x14007b36d  mov     rcx, rbx; MemoryDescriptorList
0x14007b370  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007b377  nop     dword ptr [rax+rax+00h]
0x14007b37c  mov     [rsp+2C8h+Src], rax
0x14007b384  mov     [rsp+2C8h+var_1C8], rax
0x14007b38c  test    rax, rax
0x14007b38f  jnz     short loc_14007B3BF
0x14007b391  mov     ebx, 0C000009Ah
0x14007b396  mov     [rsp+2C8h+var_264], ebx
0x14007b39a  lea     r14d, [rax+23h]
0x14007b39e  mov     [rsp+2C8h+var_260], r14d
0x14007b3a3  mov     r15d, 0E00041B7h
0x14007b3a9  mov     [rsp+2C8h+var_25C], r15d
0x14007b3ae  mov     rdi, rsi
0x14007b3b1  mov     r10, rsi
0x14007b3b4  mov     r8, rsi
0x14007b3b7  mov     r11, rsi
0x14007b3ba  jmp     loc_14007BBB6
0x14007b3bf  movzx   r14d, word ptr [r12+28h]
0x14007b3c5  movzx   eax, r14w
0x14007b3c9  mov     word ptr [rsp+2C8h+arg_10], ax
0x14007b3d1  mov     [rsp+2C8h+var_230], ax
0x14007b3d9  add     r14d, 7
0x14007b3dd  and     r14d, 0FFFFFFF8h
0x14007b3e1  add     r14d, 10h
0x14007b3e5  mov     [rsp+2C8h+var_1F0], r14d
0x14007b3ed  mov     [rsp+2C8h+Irp], rsi; Irp
0x14007b3f2  mov     r9b, dil; ChargeQuota
0x14007b3f5  xor     r8d, r8d; SecondaryBuffer
0x14007b3f8  mov     edx, [r12+4]; Length
0x14007b3fd  mov     rcx, [r12+10h]; VirtualAddress
0x14007b402  call    cs:__imp_IoAllocateMdl
0x14007b409  nop     dword ptr [rax+rax+00h]
0x14007b40e  mov     rbx, rax
0x14007b411  mov     [rsp+2C8h+MemoryDescriptorList], rax
0x14007b419  test    rax, rax
0x14007b41c  jnz     short loc_14007B472
0x14007b41e  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007b424  test    al, al
0x14007b426  jns     short loc_14007B442
0x14007b428  lea     r9, aIpv6EchoReplyM; "IPv6 echo reply MDL (IPNG)"
0x14007b42f  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007b436  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007b43d  call    McTemplateK0z_EtwWriteTransfer
0x14007b442  mov     ebx, 0C0000017h
0x14007b447  mov     [rsp+2C8h+var_264], ebx
0x14007b44b  mov     r14d, 23h ; '#'
0x14007b451  mov     [rsp+2C8h+var_260], r14d
0x14007b456  mov     r15d, 0E00041B8h
0x14007b45c  mov     [rsp+2C8h+var_25C], r15d
0x14007b461  mov     rdi, rsi
0x14007b464  mov     r10, rsi
0x14007b467  mov     r8, rsi
0x14007b46a  mov     r11, rsi
0x14007b46d  jmp     loc_14007BBB6
0x14007b472  mov     r8d, edi; Operation
0x14007b475  mov     dl, dil; AccessMode
0x14007b478  mov     rcx, rbx; MemoryDescriptorList
0x14007b47b  call    cs:__imp_MmProbeAndLockPages
0x14007b482  nop     dword ptr [rax+rax+00h]
0x14007b487  mov     [rsp+2C8h+var_268], dil
0x14007b48c  call    NdisGetCurrentThreadCompartmentId
0x14007b491  mov     [rsp+2C8h+var_1D8], eax
0x14007b498  lea     rdx, [rsp+2C8h+var_1E0]
0x14007b4a0  mov     rcx, r15
0x14007b4a3  call    IppGetCompartment
0x14007b4a8  mov     r11, rax
0x14007b4ab  mov     [rsp+2C8h+var_250], rax
0x14007b4b0  test    rax, rax
0x14007b4b3  jnz     short loc_14007B4C6
0x14007b4b5  mov     r14d, esi
0x14007b4b8  mov     r15d, 0E00041BAh
0x14007b4be  mov     rdi, rsi
0x14007b4c1  jmp     loc_14007BBAB
0x14007b4c6  mov     edx, 100h
0x14007b4cb  mov     ecx, 40h ; '@'
0x14007b4d0  mov     r8d, 20653649h
0x14007b4d6  call    cs:__imp_ExAllocatePool2
0x14007b4dd  nop     dword ptr [rax+rax+00h]
0x14007b4e2  mov     r13, rax
0x14007b4e5  test    rax, rax
0x14007b4e8  jnz     short loc_14007B52C
0x14007b4ea  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007b4f0  test    cl, cl
0x14007b4f2  jns     short loc_14007B50E
0x14007b4f4  lea     r9, aIpv6EchoReques_0; "IPv6 echo request (IPNG)"
0x14007b4fb  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007b502  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007b509  call    McTemplateK0z_EtwWriteTransfer
0x14007b50e  mov     ebx, 0C000009Ah
0x14007b513  mov     r14d, 23h ; '#'
0x14007b519  mov     r15d, 0E00041BBh
0x14007b51f  mov     rdi, rsi
0x14007b522  mov     r11, [rsp+2C8h+var_250]
0x14007b527  jmp     loc_14007BBB0
0x14007b52c  mov     [rax+8], rdi
0x14007b530  lea     rdx, [rax+20h]
0x14007b534  xor     r9d, r9d
0x14007b537  xor     r8d, r8d
0x14007b53a  xor     ecx, ecx
0x14007b53c  call    cs:__imp_RtlInitializeTimerWheelEntry
0x14007b543  nop     dword ptr [rax+rax+00h]
0x14007b548  lea     rax, [r13+10h]
0x14007b54c  mov     [rax+8], rax
0x14007b550  mov     [rax], rax
0x14007b553  mov     rcx, r13; SpinLock
0x14007b556  call    cs:__imp_KeInitializeSpinLock
0x14007b55d  nop     dword ptr [rax+rax+00h]
0x14007b562  mov     r11, [rsp+2C8h+var_250]
0x14007b567  mov     [r13+38h], r11
0x14007b56b  mov     [r13+48h], rbx
0x14007b56f  mov     r8b, [r12+35h]
0x14007b574  mov     byte ptr [rsp+2C8h+NewIrql], r8b
0x14007b57c  test    r8b, r8b
0x14007b57f  jz      short loc_14007B585
0x14007b581  add     r14d, 28h ; '('
0x14007b585  mov     eax, [r12]
0x14007b589  lea     ecx, [rax+8]
0x14007b58c  cmp     ecx, eax
0x14007b58e  jnb     short loc_14007B5A6
0x14007b590  mov     r15d, 0E00041BCh
0x14007b596  mov     r14d, esi
  ... truncated ...
```
