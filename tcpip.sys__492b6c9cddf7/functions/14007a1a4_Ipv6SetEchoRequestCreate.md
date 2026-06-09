# Ipv6SetEchoRequestCreate

- ea: `0x14007a1a4`
- end: `0x14007aeb1`
- name: `Ipv6SetEchoRequestCreate`
- size: `3341`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140079110`

## callees

- `0x140017140`
- `0x140026ec0`
- `0x140033ef0`
- `0x140053e98`
- `0x140064c20`
- `0x140064e00`
- `0x140078f8c`
- `0x1400790b4`
- `0x140079358`
- `0x14007a1a4`
- `0x14007aeb8`
- `0x14007b144`
- `0x14007f8e0`
- `0x14009c120`
- `0x14009d754`
- `0x1400a5af0`
- `0x1400a8464`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14007ade4`
- `ntoskrnl!MmUnlockPages` at `0x14007ae38`
- `ntoskrnl!MmUnlockPages` at `0x14007ae6a`
- `ntoskrnl!MmUnlockPages` at `0x14007ade4`
- `ntoskrnl!MmUnlockPages` at `0x14007ae38`
- `ntoskrnl!MmUnlockPages` at `0x14007ae6a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a364`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a48c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a5cb`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a364`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a48c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a5cb`
- `ntoskrnl!IoAllocateMdl` at `0x14007a2eb`
- `ntoskrnl!IoAllocateMdl` at `0x14007a413`
- `ntoskrnl!IoAllocateMdl` at `0x14007a552`
- `ntoskrnl!IoAllocateMdl` at `0x14007a2eb`
- `ntoskrnl!IoAllocateMdl` at `0x14007a413`
- `ntoskrnl!IoAllocateMdl` at `0x14007a552`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a3a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a4c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a3a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a4c0`
- `ntoskrnl!IoFreeMdl` at `0x14007adf3`
- `ntoskrnl!IoFreeMdl` at `0x14007ae47`
- `ntoskrnl!IoFreeMdl` at `0x14007ae79`
- `ntoskrnl!IoFreeMdl` at `0x14007adf3`
- `ntoskrnl!IoFreeMdl` at `0x14007ae47`
- `ntoskrnl!IoFreeMdl` at `0x14007ae79`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ab90`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007abab`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ab90`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007abab`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007abf1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007ac05`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007abf1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007ac05`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007a275`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007a275`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ab05`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ac1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ab05`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ac1b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007a6a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007a6a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007aac5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007aac5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ae8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ae8f`
- `ntoskrnl!ExAllocatePool2` at `0x14007a626`
- `ntoskrnl!ExAllocatePool2` at `0x14007a8d0`
- `ntoskrnl!ExAllocatePool2` at `0x14007a626`
- `ntoskrnl!ExAllocatePool2` at `0x14007a8d0`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007adbf`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007adbf`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14007a68c`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14007a68c`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14007a7ca`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14007a7ca`
- `HAL!KeQueryPerformanceCounter` at `0x14007ab5c`
- `HAL!KeQueryPerformanceCounter` at `0x14007ab5c`

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
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 11) & 4) != 0 || byte_140225C70 )
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
0x14007a1a4  mov     rax, rsp
0x14007a1a7  mov     [rax+10h], rdx
0x14007a1ab  push    rbx
0x14007a1ac  push    rsi
0x14007a1ad  push    rdi
0x14007a1ae  push    r12
0x14007a1b0  push    r13
0x14007a1b2  push    r14
0x14007a1b4  push    r15
0x14007a1b6  sub     rsp, 290h
0x14007a1bd  mov     r15, rdx
0x14007a1c0  mov     rbx, rcx
0x14007a1c3  xor     esi, esi
0x14007a1c5  mov     r13d, esi
0x14007a1c8  mov     [rsp+2C8h+var_267], sil
0x14007a1cd  mov     [rsp+2C8h+var_266], sil
0x14007a1d2  mov     [rsp+2C8h+var_268], sil
0x14007a1d7  mov     [rax-200h], rsi
0x14007a1de  mov     [rax-1F8h], rsi
0x14007a1e5  mov     [rax-208h], rsi
0x14007a1ec  mov     edi, esi
0x14007a1ee  mov     [rsp+2C8h+var_258], rsi
0x14007a1f3  mov     [rax-1E8h], rsi
0x14007a1fa  xorps   xmm0, xmm0
0x14007a1fd  movups  xmmword ptr [rax-1E0h], xmm0
0x14007a204  xor     edx, edx; Val
0x14007a206  mov     r8d, 0D8h; Size
0x14007a20c  lea     rcx, [rax-118h]; void *
0x14007a213  call    memset
0x14007a218  mov     [rsp+2C8h+var_248], rsi
0x14007a220  xor     edx, edx; Val
0x14007a222  mov     r8d, 0A0h; Size
0x14007a228  lea     rcx, [rsp+2C8h+var_1B8]; void *
0x14007a230  call    memset
0x14007a235  mov     r12, [rbx+20h]
0x14007a239  mov     [rsp+2C8h+var_228], r12
0x14007a241  test    r12, r12
0x14007a244  jnz     short loc_14007A254
0x14007a246  mov     r14d, esi
0x14007a249  mov     r15d, 0E00041B0h
0x14007a24f  jmp     loc_14007ACF8
0x14007a254  cmp     [r12+1Ch], esi
0x14007a259  jnz     short loc_14007A269
0x14007a25b  mov     r14d, esi
0x14007a25e  mov     r15d, 0E00041B1h
0x14007a264  jmp     loc_14007ACF8
0x14007a269  mov     rbx, [rbx+10h]
0x14007a26d  mov     [rsp+2C8h+var_210], rbx
0x14007a275  call    cs:__imp_PsGetCurrentProcessId
0x14007a27c  nop     dword ptr [rax+rax+00h]
0x14007a281  cmp     [rbx+8], eax
0x14007a284  jz      short loc_14007A294
0x14007a286  mov     r14d, esi
0x14007a289  mov     r15d, 0E00041B2h
0x14007a28f  jmp     loc_14007ACF8
0x14007a294  cmp     [r12+10h], rsi
0x14007a299  jz      loc_14007ACEC
0x14007a29f  mov     [rsp+2C8h+var_240], rsi
0x14007a2a7  mov     [rsp+2C8h+Src], rsi
0x14007a2af  mov     r14d, esi
0x14007a2b2  mov     word ptr [rsp+2C8h+arg_10], si
0x14007a2ba  mov     eax, [r12+4]
0x14007a2bf  cmp     [r12+18h], eax
0x14007a2c4  ja      loc_14007ACEC
0x14007a2ca  mov     edx, [r12]; Length
0x14007a2ce  mov     edi, 1
0x14007a2d3  test    edx, edx
0x14007a2d5  jz      loc_14007A3F2
0x14007a2db  mov     [rsp+2C8h+Irp], rsi; Irp
0x14007a2e0  mov     r9b, dil; ChargeQuota
0x14007a2e3  xor     r8d, r8d; SecondaryBuffer
0x14007a2e6  mov     rcx, [r12+8]; VirtualAddress
0x14007a2eb  call    cs:__imp_IoAllocateMdl
0x14007a2f2  nop     dword ptr [rax+rax+00h]
0x14007a2f7  mov     rbx, rax
0x14007a2fa  mov     [rsp+2C8h+Mdl], rax
0x14007a302  test    rax, rax
0x14007a305  jnz     short loc_14007A35B
0x14007a307  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a30d  test    al, al
0x14007a30f  jns     short loc_14007A32B
0x14007a311  lea     r9, aIpv6EchoDataMd; "IPv6 echo data MDL (IPNG)"
0x14007a318  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a31f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a326  call    McTemplateK0z_EtwWriteTransfer
0x14007a32b  mov     ebx, 0C0000017h
0x14007a330  mov     [rsp+2C8h+var_264], ebx
0x14007a334  mov     r14d, 23h ; '#'
0x14007a33a  mov     [rsp+2C8h+var_260], r14d
0x14007a33f  mov     r15d, 0E00041B4h
0x14007a345  mov     [rsp+2C8h+var_25C], r15d
0x14007a34a  mov     rdi, rsi
0x14007a34d  mov     r10, rsi
0x14007a350  mov     r8, rsi
0x14007a353  mov     r11, rsi
0x14007a356  jmp     loc_14007AD06
0x14007a35b  xor     r8d, r8d; Operation
0x14007a35e  mov     dl, dil; AccessMode
0x14007a361  mov     rcx, rbx; MemoryDescriptorList
0x14007a364  call    cs:__imp_MmProbeAndLockPages
0x14007a36b  nop     dword ptr [rax+rax+00h]
0x14007a370  mov     [rsp+2C8h+var_267], dil
0x14007a375  test    byte ptr [rbx+0Ah], 5
0x14007a379  jz      short loc_14007A389
0x14007a37b  mov     rcx, [rbx+18h]
0x14007a37f  mov     [rsp+2C8h+var_240], rcx
0x14007a387  jmp     short loc_14007A3B7
0x14007a389  mov     [rsp+2C8h+Priority], 40000010h; Priority
0x14007a391  mov     dword ptr [rsp+2C8h+Irp], esi; BugCheckOnFailure
0x14007a395  xor     r9d, r9d; RequestedAddress
0x14007a398  mov     r8d, edi; CacheType
0x14007a39b  xor     edx, edx; AccessMode
0x14007a39d  mov     rcx, rbx; MemoryDescriptorList
0x14007a3a0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007a3a7  nop     dword ptr [rax+rax+00h]
0x14007a3ac  mov     rcx, rax
0x14007a3af  mov     [rsp+2C8h+var_240], rax
0x14007a3b7  mov     [rsp+2C8h+var_1D0], rcx
0x14007a3bf  test    rcx, rcx
0x14007a3c2  jnz     short loc_14007A3F2
0x14007a3c4  mov     ebx, 0C000009Ah
0x14007a3c9  mov     [rsp+2C8h+var_264], ebx
0x14007a3cd  lea     r14d, [rcx+23h]
0x14007a3d1  mov     [rsp+2C8h+var_260], r14d
0x14007a3d6  mov     r15d, 0E00041B5h
0x14007a3dc  mov     [rsp+2C8h+var_25C], r15d
0x14007a3e1  mov     rdi, rsi
0x14007a3e4  mov     r10, rsi
0x14007a3e7  mov     r8, rsi
0x14007a3ea  mov     r11, rsi
0x14007a3ed  jmp     loc_14007AD06
0x14007a3f2  movzx   eax, word ptr [r12+28h]
0x14007a3f8  test    ax, ax
0x14007a3fb  jz      loc_14007A53D
0x14007a401  mov     edx, eax; Length
0x14007a403  mov     [rsp+2C8h+Irp], rsi; Irp
0x14007a408  mov     r9b, dil; ChargeQuota
0x14007a40b  xor     r8d, r8d; SecondaryBuffer
0x14007a40e  mov     rcx, [r12+20h]; VirtualAddress
0x14007a413  call    cs:__imp_IoAllocateMdl
0x14007a41a  nop     dword ptr [rax+rax+00h]
0x14007a41f  mov     rbx, rax
0x14007a422  mov     [rsp+2C8h+var_1F8], rax
0x14007a42a  test    rax, rax
0x14007a42d  jnz     short loc_14007A483
0x14007a42f  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a435  test    al, al
0x14007a437  jns     short loc_14007A453
0x14007a439  lea     r9, aIpv6EchoOption; "IPv6 echo options MDL (IPNG)"
0x14007a440  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a447  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a44e  call    McTemplateK0z_EtwWriteTransfer
0x14007a453  mov     ebx, 0C0000017h
0x14007a458  mov     [rsp+2C8h+var_264], ebx
0x14007a45c  mov     r14d, 23h ; '#'
0x14007a462  mov     [rsp+2C8h+var_260], r14d
0x14007a467  mov     r15d, 0E00041B6h
0x14007a46d  mov     [rsp+2C8h+var_25C], r15d
0x14007a472  mov     rdi, rsi
0x14007a475  mov     r10, rsi
0x14007a478  mov     r8, rsi
0x14007a47b  mov     r11, rsi
0x14007a47e  jmp     loc_14007AD06
0x14007a483  xor     r8d, r8d; Operation
0x14007a486  mov     dl, dil; AccessMode
0x14007a489  mov     rcx, rbx; MemoryDescriptorList
0x14007a48c  call    cs:__imp_MmProbeAndLockPages
0x14007a493  nop     dword ptr [rax+rax+00h]
0x14007a498  mov     [rsp+2C8h+var_266], dil
0x14007a49d  test    byte ptr [rbx+0Ah], 5
0x14007a4a1  jz      short loc_14007A4A9
0x14007a4a3  mov     rax, [rbx+18h]
0x14007a4a7  jmp     short loc_14007A4CC
0x14007a4a9  mov     [rsp+2C8h+Priority], 40000010h; Priority
0x14007a4b1  mov     dword ptr [rsp+2C8h+Irp], esi; BugCheckOnFailure
0x14007a4b5  xor     r9d, r9d; RequestedAddress
0x14007a4b8  mov     r8d, edi; CacheType
0x14007a4bb  xor     edx, edx; AccessMode
0x14007a4bd  mov     rcx, rbx; MemoryDescriptorList
0x14007a4c0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007a4c7  nop     dword ptr [rax+rax+00h]
0x14007a4cc  mov     [rsp+2C8h+Src], rax
0x14007a4d4  mov     [rsp+2C8h+var_1C8], rax
0x14007a4dc  test    rax, rax
0x14007a4df  jnz     short loc_14007A50F
0x14007a4e1  mov     ebx, 0C000009Ah
0x14007a4e6  mov     [rsp+2C8h+var_264], ebx
0x14007a4ea  lea     r14d, [rax+23h]
0x14007a4ee  mov     [rsp+2C8h+var_260], r14d
0x14007a4f3  mov     r15d, 0E00041B7h
0x14007a4f9  mov     [rsp+2C8h+var_25C], r15d
0x14007a4fe  mov     rdi, rsi
0x14007a501  mov     r10, rsi
0x14007a504  mov     r8, rsi
0x14007a507  mov     r11, rsi
0x14007a50a  jmp     loc_14007AD06
0x14007a50f  movzx   r14d, word ptr [r12+28h]
0x14007a515  movzx   eax, r14w
0x14007a519  mov     word ptr [rsp+2C8h+arg_10], ax
0x14007a521  mov     [rsp+2C8h+var_230], ax
0x14007a529  add     r14d, 7
0x14007a52d  and     r14d, 0FFFFFFF8h
0x14007a531  add     r14d, 10h
0x14007a535  mov     [rsp+2C8h+var_1F0], r14d
0x14007a53d  mov     [rsp+2C8h+Irp], rsi; Irp
0x14007a542  mov     r9b, dil; ChargeQuota
0x14007a545  xor     r8d, r8d; SecondaryBuffer
0x14007a548  mov     edx, [r12+4]; Length
0x14007a54d  mov     rcx, [r12+10h]; VirtualAddress
0x14007a552  call    cs:__imp_IoAllocateMdl
0x14007a559  nop     dword ptr [rax+rax+00h]
0x14007a55e  mov     rbx, rax
0x14007a561  mov     [rsp+2C8h+MemoryDescriptorList], rax
0x14007a569  test    rax, rax
0x14007a56c  jnz     short loc_14007A5C2
0x14007a56e  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a574  test    al, al
0x14007a576  jns     short loc_14007A592
0x14007a578  lea     r9, aIpv6EchoReplyM; "IPv6 echo reply MDL (IPNG)"
0x14007a57f  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a586  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a58d  call    McTemplateK0z_EtwWriteTransfer
0x14007a592  mov     ebx, 0C0000017h
0x14007a597  mov     [rsp+2C8h+var_264], ebx
0x14007a59b  mov     r14d, 23h ; '#'
0x14007a5a1  mov     [rsp+2C8h+var_260], r14d
0x14007a5a6  mov     r15d, 0E00041B8h
0x14007a5ac  mov     [rsp+2C8h+var_25C], r15d
0x14007a5b1  mov     rdi, rsi
0x14007a5b4  mov     r10, rsi
0x14007a5b7  mov     r8, rsi
0x14007a5ba  mov     r11, rsi
0x14007a5bd  jmp     loc_14007AD06
0x14007a5c2  mov     r8d, edi; Operation
0x14007a5c5  mov     dl, dil; AccessMode
0x14007a5c8  mov     rcx, rbx; MemoryDescriptorList
0x14007a5cb  call    cs:__imp_MmProbeAndLockPages
0x14007a5d2  nop     dword ptr [rax+rax+00h]
0x14007a5d7  mov     [rsp+2C8h+var_268], dil
0x14007a5dc  call    NdisGetCurrentThreadCompartmentId
0x14007a5e1  mov     [rsp+2C8h+var_1D8], eax
0x14007a5e8  lea     rdx, [rsp+2C8h+var_1E0]
0x14007a5f0  mov     rcx, r15
0x14007a5f3  call    IppGetCompartment
0x14007a5f8  mov     r11, rax
0x14007a5fb  mov     [rsp+2C8h+var_250], rax
0x14007a600  test    rax, rax
0x14007a603  jnz     short loc_14007A616
0x14007a605  mov     r14d, esi
0x14007a608  mov     r15d, 0E00041BAh
0x14007a60e  mov     rdi, rsi
0x14007a611  jmp     loc_14007ACFB
0x14007a616  mov     edx, 100h
0x14007a61b  mov     ecx, 40h ; '@'
0x14007a620  mov     r8d, 20653649h
0x14007a626  call    cs:__imp_ExAllocatePool2
0x14007a62d  nop     dword ptr [rax+rax+00h]
0x14007a632  mov     r13, rax
0x14007a635  test    rax, rax
0x14007a638  jnz     short loc_14007A67C
0x14007a63a  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a640  test    cl, cl
0x14007a642  jns     short loc_14007A65E
0x14007a644  lea     r9, aIpv6EchoReques_0; "IPv6 echo request (IPNG)"
0x14007a64b  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a652  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a659  call    McTemplateK0z_EtwWriteTransfer
0x14007a65e  mov     ebx, 0C000009Ah
0x14007a663  mov     r14d, 23h ; '#'
0x14007a669  mov     r15d, 0E00041BBh
0x14007a66f  mov     rdi, rsi
0x14007a672  mov     r11, [rsp+2C8h+var_250]
0x14007a677  jmp     loc_14007AD00
0x14007a67c  mov     [rax+8], rdi
0x14007a680  lea     rdx, [rax+20h]
0x14007a684  xor     r9d, r9d
0x14007a687  xor     r8d, r8d
0x14007a68a  xor     ecx, ecx
0x14007a68c  call    cs:__imp_RtlInitializeTimerWheelEntry
0x14007a693  nop     dword ptr [rax+rax+00h]
0x14007a698  lea     rax, [r13+10h]
0x14007a69c  mov     [rax+8], rax
0x14007a6a0  mov     [rax], rax
0x14007a6a3  mov     rcx, r13; SpinLock
0x14007a6a6  call    cs:__imp_KeInitializeSpinLock
0x14007a6ad  nop     dword ptr [rax+rax+00h]
0x14007a6b2  mov     r11, [rsp+2C8h+var_250]
0x14007a6b7  mov     [r13+38h], r11
0x14007a6bb  mov     [r13+48h], rbx
0x14007a6bf  mov     r8b, [r12+35h]
0x14007a6c4  mov     byte ptr [rsp+2C8h+NewIrql], r8b
0x14007a6cc  test    r8b, r8b
0x14007a6cf  jz      short loc_14007A6D5
0x14007a6d1  add     r14d, 28h ; '('
0x14007a6d5  mov     eax, [r12]
0x14007a6d9  lea     ecx, [rax+8]
0x14007a6dc  cmp     ecx, eax
0x14007a6de  jnb     short loc_14007A6F6
0x14007a6e0  mov     r15d, 0E00041BCh
0x14007a6e6  mov     r14d, esi
  ... truncated ...
```
