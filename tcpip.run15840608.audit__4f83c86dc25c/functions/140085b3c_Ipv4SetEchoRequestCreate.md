# Ipv4SetEchoRequestCreate

- ea: `0x140085b3c`
- end: `0x14008690d`
- name: `Ipv4SetEchoRequestCreate`
- size: `3537`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140085970`

## callees

- `0x140014a08`
- `0x140024010`
- `0x140024940`
- `0x140031300`
- `0x140074f30`
- `0x1400812a8`
- `0x1400826e4`
- `0x140084aac`
- `0x140084bd4`
- `0x140085ac8`
- `0x140085b3c`
- `0x140087628`
- `0x14008d41c`
- `0x14008f110`
- `0x1400915e4`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140086838`
- `ntoskrnl!MmUnlockPages` at `0x14008688c`
- `ntoskrnl!MmUnlockPages` at `0x1400868be`
- `ntoskrnl!MmUnlockPages` at `0x140086838`
- `ntoskrnl!MmUnlockPages` at `0x14008688c`
- `ntoskrnl!MmUnlockPages` at `0x1400868be`
- `ntoskrnl!MmProbeAndLockPages` at `0x140085d07`
- `ntoskrnl!MmProbeAndLockPages` at `0x140085e36`
- `ntoskrnl!MmProbeAndLockPages` at `0x140085f8a`
- `ntoskrnl!MmProbeAndLockPages` at `0x140085d07`
- `ntoskrnl!MmProbeAndLockPages` at `0x140085e36`
- `ntoskrnl!MmProbeAndLockPages` at `0x140085f8a`
- `ntoskrnl!IoAllocateMdl` at `0x140085c8a`
- `ntoskrnl!IoAllocateMdl` at `0x140085db9`
- `ntoskrnl!IoAllocateMdl` at `0x140085f0d`
- `ntoskrnl!IoAllocateMdl` at `0x140085c8a`
- `ntoskrnl!IoAllocateMdl` at `0x140085db9`
- `ntoskrnl!IoAllocateMdl` at `0x140085f0d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140085d43`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140085e72`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140085d43`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140085e72`
- `ntoskrnl!IoFreeMdl` at `0x140086847`
- `ntoskrnl!IoFreeMdl` at `0x14008689b`
- `ntoskrnl!IoFreeMdl` at `0x1400868cd`
- `ntoskrnl!IoFreeMdl` at `0x140086847`
- `ntoskrnl!IoFreeMdl` at `0x14008689b`
- `ntoskrnl!IoFreeMdl` at `0x1400868cd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400865d0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400865eb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400865d0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400865eb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140086633`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140086644`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140086633`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140086644`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140085c13`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140085c13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086540`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008665f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086540`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008665f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008607a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008607a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400864fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400864fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400868eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400868eb`
- `ntoskrnl!ExAllocatePool2` at `0x140085ff0`
- `ntoskrnl!ExAllocatePool2` at `0x1400862fe`
- `ntoskrnl!ExAllocatePool2` at `0x140085ff0`
- `ntoskrnl!ExAllocatePool2` at `0x1400862fe`
- `NETIO!NetioDereferenceNetBufferList` at `0x140086813`
- `NETIO!NetioDereferenceNetBufferList` at `0x140086813`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140086060`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140086060`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400861f2`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400861f2`
- `HAL!KeQueryPerformanceCounter` at `0x14008659c`
- `HAL!KeQueryPerformanceCounter` at `0x14008659c`

## pseudocode

```c
__int64 __fastcall Ipv4SetEchoRequestCreate(__int64 a1, __int64 a2)
{
  LARGE_INTEGER *v3; // r13
  __int64 v4; // rdx
  unsigned int *v5; // r12
  int v6; // r14d
  int v7; // r15d
  unsigned int v8; // r15d
  struct _MDL *v9; // rax
  __int64 v10; // r8
  struct _MDL *v11; // rbx
  int v12; // ebx
  int v13; // r10d
  _QWORD *v14; // r8
  int *Compartment; // r11
  PVOID MappedSystemVa; // rcx
  struct _MDL *v17; // rax
  __int64 v18; // r8
  struct _MDL *v19; // rbx
  PVOID v20; // rbx
  struct _MDL *v21; // rax
  __int64 v22; // r8
  struct _MDL *v23; // rdi
  __int64 Pool2; // rax
  __int64 v25; // r8
  __int64 v26; // r14
  unsigned __int16 v27; // r8
  unsigned int v28; // ecx
  unsigned int v29; // r8d
  ULONG v30; // ecx
  __int64 NetBufferListForEcho; // rax
  __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned __int32 v34; // eax
  __int64 v35; // rax
  __int64 v36; // r8
  _DWORD *v37; // r9
  __int64 v38; // r8
  _DWORD *v39; // r15
  unsigned int v40; // ebx
  __int64 v41; // rcx
  __int64 v42; // r15
  KSPIN_LOCK *v43; // rbx
  KIRQL v44; // r14
  __int64 v45; // rdx
  __int64 v46; // rdx
  unsigned __int64 v47; // rdi
  unsigned int v48; // eax
  int v49; // r9d
  __int64 v50; // rdx
  __int64 v51; // rax
  void *v52; // r12
  char v54; // [rsp+60h] [rbp-278h]
  char v55; // [rsp+61h] [rbp-277h]
  char v56; // [rsp+62h] [rbp-276h]
  LARGE_INTEGER *SpinLock; // [rsp+68h] [rbp-270h]
  __int64 v58; // [rsp+80h] [rbp-258h]
  int *v59; // [rsp+88h] [rbp-250h]
  _QWORD *v60; // [rsp+90h] [rbp-248h]
  PVOID v61; // [rsp+98h] [rbp-240h]
  unsigned int v62; // [rsp+98h] [rbp-240h]
  PVOID P; // [rsp+A0h] [rbp-238h]
  void *Src; // [rsp+A8h] [rbp-230h]
  __int64 v65; // [rsp+B0h] [rbp-228h]
  unsigned int *v66; // [rsp+B8h] [rbp-220h]
  struct _MDL *MemoryDescriptorList; // [rsp+C8h] [rbp-210h]
  struct _MDL *Mdl; // [rsp+D0h] [rbp-208h]
  struct _MDL *v69; // [rsp+D8h] [rbp-200h]
  __int64 v70; // [rsp+E8h] [rbp-1F0h] BYREF
  __int64 v71; // [rsp+F0h] [rbp-1E8h]
  __int128 v72; // [rsp+F8h] [rbp-1E0h] BYREF
  PVOID v73; // [rsp+108h] [rbp-1D0h]
  PVOID v74; // [rsp+110h] [rbp-1C8h]
  _QWORD v75[20]; // [rsp+120h] [rbp-1B8h] BYREF
  _QWORD v76[35]; // [rsp+1C0h] [rbp-118h] BYREF
  unsigned __int16 NewIrql; // [rsp+2E0h] [rbp+8h]
  KIRQL NewIrqla; // [rsp+2E0h] [rbp+8h]
  __int16 v80; // [rsp+2F0h] [rbp+18h]
  int v81; // [rsp+2F8h] [rbp+20h]
  KSPIN_LOCK *v82; // [rsp+2F8h] [rbp+20h]

  v3 = 0;
  v55 = 0;
  v56 = 0;
  v54 = 0;
  Mdl = 0;
  v69 = 0;
  MemoryDescriptorList = 0;
  P = 0;
  v58 = 0;
  v70 = 0;
  v72 = 0;
  memset(v76, 0, 0xD8u);
  v60 = 0;
  memset(v75, 0, sizeof(v75));
  v5 = *(unsigned int **)(a1 + 32);
  if ( !v5 )
  {
    v6 = 0;
    v7 = -536854149;
LABEL_85:
    Compartment = 0;
    goto LABEL_86;
  }
  if ( !v5[7] )
  {
    v6 = 0;
    v7 = -536854148;
    goto LABEL_85;
  }
  v71 = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(v71 + 8) != (unsigned int)PsGetCurrentProcessId() )
  {
    v6 = 0;
    v7 = -536854147;
    goto LABEL_85;
  }
  if ( !*((_QWORD *)v5 + 2) || (v61 = 0, Src = 0, v8 = 0, NewIrql = 0, v5[6] > v5[1]) )
  {
    v6 = 15;
    v7 = -536854146;
    goto LABEL_85;
  }
  if ( *v5 )
  {
    v9 = IoAllocateMdl(*((PVOID *)v5 + 1), *v5, 0, 1u, 0);
    v11 = v9;
    Mdl = v9;
    if ( !v9 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v10,
          L"IPv4 echo data MDL (IPNG)");
      v12 = -1073741801;
      v6 = 35;
      v7 = -536854145;
      v3 = 0;
      v13 = 0;
      v14 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
    MmProbeAndLockPages(v9, 1, IoReadAccess);
    v55 = 1;
    if ( (v11->MdlFlags & 5) != 0 )
      MappedSystemVa = v11->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
    v61 = MappedSystemVa;
    v73 = MappedSystemVa;
    if ( !MappedSystemVa )
    {
      v12 = -1073741670;
      v6 = 35;
      v7 = -536854144;
      v3 = 0;
      v13 = 0;
      v14 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
  }
  if ( *((_WORD *)v5 + 20) )
  {
    v17 = IoAllocateMdl(*((PVOID *)v5 + 4), *((unsigned __int16 *)v5 + 20), 0, 1u, 0);
    v19 = v17;
    v69 = v17;
    if ( !v17 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v18,
          L"IPv4 echo options MDL (IPNG)");
      v12 = -1073741801;
      v6 = 35;
      v7 = -536854143;
      v3 = 0;
      v13 = 0;
      v14 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
    MmProbeAndLockPages(v17, 1, IoReadAccess);
    v56 = 1;
    if ( (v19->MdlFlags & 5) != 0 )
      v20 = v19->MappedSystemVa;
    else
      v20 = MmMapLockedPagesSpecifyCache(v19, 0, MmCached, 0, 0, 0x40000010u);
    Src = v20;
    v74 = v20;
    if ( !v20 )
    {
      v12 = -1073741670;
      v6 = 35;
      v7 = -536854142;
      v3 = 0;
      v13 = 0;
      v14 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
    NewIrql = *((_WORD *)v5 + 20);
    v8 = ((NewIrql + 7) & 0xFFFFFFF8) + 16;
  }
  v21 = IoAllocateMdl(*((PVOID *)v5 + 2), v5[1], 0, 1u, 0);
  v23 = v21;
  MemoryDescriptorList = v21;
  if ( !v21 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v22,
        L"IPv4 echo reply MDL (IPNG)");
    v12 = -1073741801;
    v6 = 35;
    v7 = -536854141;
    v3 = 0;
    v13 = 0;
    v14 = 0;
    Compartment = 0;
    goto LABEL_89;
  }
  MmProbeAndLockPages(v21, 1, IoWriteAccess);
  v54 = 1;
  DWORD2(v72) = NdisGetCurrentThreadCompartmentId();
  Compartment = (int *)IppGetCompartment(a2, &v72);
  v59 = Compartment;
  if ( !Compartment )
  {
    v6 = 0;
    v7 = -536854139;
    v3 = 0;
LABEL_86:
    v12 = -1073741811;
    goto LABEL_87;
  }
  Pool2 = ExAllocatePool2(64, 232, 543503433);
  v26 = Pool2;
  SpinLock = (LARGE_INTEGER *)Pool2;
  if ( !Pool2 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v25,
        L"IPv4 echo request (IPNG)");
    v12 = -1073741670;
    v6 = 35;
    v7 = -536854138;
    v3 = 0;
    Compartment = v59;
    goto LABEL_87;
  }
  *(_QWORD *)(Pool2 + 8) = 1;
  RtlInitializeTimerWheelEntry(0, Pool2 + 32, 0, 0);
  *(_QWORD *)(v26 + 24) = v26 + 16;
  *(_QWORD *)(v26 + 16) = v26 + 16;
  KeInitializeSpinLock((PKSPIN_LOCK)v26);
  Compartment = v59;
  *(_QWORD *)(v26 + 56) = v59;
  *(_QWORD *)(v26 + 72) = v23;
  if ( *((_BYTE *)v5 + 53) )
  {
    if ( Src )
    {
      v12 = -1073741811;
      v7 = -536854137;
LABEL_43:
      v6 = 0;
      v3 = SpinLock;
LABEL_87:
      v13 = 0;
      goto LABEL_88;
    }
    v27 = 8;
    v80 = 8;
    v8 += 24;
    v65 = 1;
  }
  else
  {
    v27 = 0;
    v80 = 0;
    v65 = 0;
  }
  v28 = *v5 + 8;
  if ( v28 < *v5 )
  {
    v12 = -1073741675;
    v7 = -536854136;
    goto LABEL_43;
  }
  v4 = v28 + ((NewIrql + 3) & 0xFFFFFFFC);
  if ( (unsigned int)v4 < v28 )
  {
    v12 = -1073741675;
    v7 = -536854135;
    goto LABEL_43;
  }
  v81 = v27;
  v29 = v27 + (_DWORD)v4;
  if ( v29 < (unsigned int)v4 )
  {
    v12 = -1073741675;
    v7 = -536854134;
    goto LABEL_43;
  }
  v30 = v29 + *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 8LL);
  if ( v30 < v29 )
  {
    v12 = -1073741675;
    v7 = -536854133;
    goto LABEL_43;
  }
  NetBufferListForEcho = IppAllocateNetBufferListForEcho(v30);
  v13 = NetBufferListForEcho;
  v58 = NetBufferListForEcho;
  if ( !NetBufferListForEcho )
  {
    v12 = -1073741670;
    v6 = 35;
    v7 = -536854132;
LABEL_56:
    v3 = SpinLock;
    Compartment = v59;
LABEL_88:
    v14 = 0;
    goto LABEL_89;
  }
  v32 = *v5;
  if ( (_DWORD)v32 )
  {
    NetioRetreatNetBuffer(*(_QWORD *)(NetBufferListForEcho + 8), v32, 0);
    RtlCopyKernelBufferToMdl(
      v61,
      *(_QWORD *)(*(_QWORD *)(v58 + 8) + 8LL),
      *(unsigned int *)(*(_QWORD *)(v58 + 8) + 16LL),
      *v5,
      &v70);
  }
  v33 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 20076));
  if ( v33 < 0x10000 )
  {
    _InterlockedAdd((volatile signed __int32 *)(a2 + 20076), 0x10000u);
    v33 += 0x10000;
  }
  v34 = _byteswap_ulong(v33);
  *(_DWORD *)(v26 + 64) = v34;
  HIDWORD(v76[26]) = v34;
  v66 = v5 + 16;
  v75[0] = *(_QWORD *)(v26 + 56);
  v75[8] = v5 + 16;
  LODWORD(v75[7]) = v5[12];
  if ( v5[15] )
  {
    LODWORD(v75[10]) = v5[11];
    v75[11] = v5 + 15;
  }
  v75[16] = *(_QWORD *)(a2 + 640);
  v75[17] = 0;
  LODWORD(v75[19]) = 1;
  BYTE4(v75[19]) = 8;
  v12 = IppJoinPath(a2, v75);
  if ( v12 < 0 )
  {
    v6 = 13;
    v7 = -536854130;
    v13 = v58;
    goto LABEL_56;
  }
  v60 = (_QWORD *)v75[15];
  if ( *((_BYTE *)v5 + 56) )
    v8 += 24;
  v62 = v8 + 24;
  v35 = ExAllocatePool2(64, v8 + 24, 543503433);
  v4 = v35;
  P = (PVOID)v35;
  if ( v35 )
  {
    v37 = (_DWORD *)(v35 + 16);
    v38 = a2;
    v39 = (_DWORD *)(a2 + 24);
    if ( v80 )
    {
      *(_QWORD *)v35 = ((v81 + 7) & 0xFFFFFFF8) + 16LL;
      *(_DWORD *)(v35 + 8) = *v39;
      *(_DWORD *)(v35 + 12) = 1;
      v40 = *(_DWORD *)v35;
      *v37 = 134710017;
      v37[v65] = v5[16];
      v66 = **(unsigned int ***)(*v60 + 16LL);
    }
    else
    {
      v40 = 0;
    }
    if ( NewIrql )
    {
      *(_QWORD *)v35 = ((NewIrql + 7) & 0xFFFFFFF8) + 16LL;
      *(_DWORD *)(v35 + 8) = *v39;
      *(_DWORD *)(v35 + 12) = 1;
      v40 = ((NewIrql + 7) & 0xFFFFFFF8) + 16;
      memmove(v37, Src, NewIrql);
      v4 = (__int64)P;
      v38 = a2;
    }
    if ( *((_BYTE *)v5 + 56) )
    {
      v41 = v40;
      *(_QWORD *)(v40 + v4) = 24;
      *(_DWORD *)(v40 + v4 + 8) = *v39;
      *(_DWORD *)(v40 + v4 + 12) = 14;
      v40 += 24;
      *(_DWORD *)(v41 + v4 + 16) = 1;
    }
    *(_QWORD *)(v40 + v4) = 24;
    *(_DWORD *)(v40 + v4 + 8) = *v39;
    *(_DWORD *)(v40 + v4 + 12) = 21;
    *(_DWORD *)(v40 + v4 + 16) = *((unsigned __int8 *)v5 + 52);
    v42 = v71;
    *(_OWORD *)(v26 + 88) = *(_OWORD *)v71;
    *(_OWORD *)(v26 + 104) = *(_OWORD *)(v42 + 16);
    *(_OWORD *)(v26 + 160) = *(_OWORD *)v5;
    *(_OWORD *)(v26 + 176) = *((_OWORD *)v5 + 1);
    *(_OWORD *)(v26 + 192) = *((_OWORD *)v5 + 2);
    *(_OWORD *)(v26 + 208) = *((_OWORD *)v5 + 3);
    *(_QWORD *)(v26 + 224) = *((_QWORD *)v5 + 8);
    *(_DWORD *)(v26 + 120) = 259;
    v43 = (KSPIN_LOCK *)(v38 + 20048);
    v82 = (KSPIN_LOCK *)(v38 + 20048);
    v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v38 + 20048));
    NewIrqla = v44;
    if ( IppFindEchoRequest(a2 + 19936, v45, v42) )
    {
      KeReleaseSpinLock(v43, v44);
      v12 = -1073741270;
      v6 = 36;
      v7 = -536854128;
    }
    else
    {
      v6 = 44;
      v7 = -536850433;
      IppInsertEchoRequest(a2 + 19936, v46, SpinLock);
      if ( _InterlockedIncrement64((volatile signed __int64 *)&SpinLock[1]) <= 1 )
        __fastfail(0xEu);
      SpinLock[10] = KeQueryPerformanceCounter(0);
      v47 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&SpinLock->QuadPart);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 20064));
      v48 = IppMillisecondsToTicks(v5[7]);
      IppStartEchoRequestTimer(a2, SpinLock, v47 / 0x1F4, v48);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 20064));
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&SpinLock->QuadPart);
      KeReleaseSpinLock(v82, NewIrqla);
      v76[0] = v58;
      LOBYTE(v76[26]) = 8;
      LOWORD(v76[7]) = 1;
      LODWORD(v76[17]) = v5[12];
      v76[18] = v66;
      v76[4] = v60;
      v76[10] = P;
      LODWORD(v76[9]) = v62;
      IppSendControl(0, a2, v76);
      v12 = 0;
    }
  }
  else
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v36,
        L"IPv4 echo ancillary data (IPNG)");
    v12 = -1073741670;
    v6 = 35;
    v7 = -536854129;
  }
  v3 = SpinLock;
  v13 = v58;
  v14 = v60;
  Compartment = v59;
LABEL_89:
  if ( v12 < 0 )
  {
    if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredContext) & 4) != 0 || byte_140229CC0 )
    {
      v49 = 0;
      if ( v14 )
      {
        v50 = **(_QWORD **)(*v14 + 16LL);
        v51 = *(_QWORD *)(*v14 + 8LL);
        v52 = (void *)v14[2];
      }
      else
      {
        LODWORD(v51) = 0;
        if ( v5 )
        {
          v50 = (__int64)(v5 + 15);
          v52 = v5 + 16;
        }
        else
        {
          v50 = 0;
          v52 = 0;
        }
      }
      if ( Compartment )
        v49 = *Compartment;
      LogIcmpSendDrop(a2, 8, SBYTE1(v76[26]), v6, v12, v49, v50, v52, v51, v13, 0, v7);
    }
    if ( v58 )
    {
      *(_DWORD *)(v58 + 140) = v12;
      v3[8].HighPart |= 2u;
      NetioDereferenceNetBufferList(v58, 0);
    }
    else
    {
      if ( MemoryDescriptorList )
      {
        if ( v54 )
          MmUnlockPages(MemoryDescriptorList);
        IoFreeMdl(MemoryDescriptorList);
      }
      if ( v3 )
        IppDereferenceEchoRequest(v3);
    }
  }
  if ( v60 )
    IppDereferencePath(v60, v4, v14);
  if ( Mdl )
  {
    if ( v55 )
      MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
  }
  if ( v69 )
  {
    if ( v56 )
      MmUnlockPages(v69);
    IoFreeMdl(v69);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140085b3c  mov     r11, rsp
0x140085b3f  mov     [r11+10h], rdx
0x140085b43  push    rbx
0x140085b44  push    rsi
0x140085b45  push    rdi
0x140085b46  push    r12
0x140085b48  push    r13
0x140085b4a  push    r14
0x140085b4c  push    r15
0x140085b4e  sub     rsp, 2A0h
0x140085b55  mov     rbx, rcx
0x140085b58  xor     esi, esi
0x140085b5a  mov     r13d, esi
0x140085b5d  mov     [rsp+2D8h+var_277], sil
0x140085b62  mov     [rsp+2D8h+var_276], sil
0x140085b67  mov     [rsp+2D8h+var_278], sil
0x140085b6c  mov     [r11-208h], rsi
0x140085b73  mov     [r11-200h], rsi
0x140085b7a  mov     [r11-210h], rsi
0x140085b81  mov     eax, esi
0x140085b83  mov     [rsp+2D8h+P], rax
0x140085b8b  mov     [rsp+2D8h+var_258], rax
0x140085b93  mov     [r11-1F0h], rsi
0x140085b9a  xorps   xmm0, xmm0
0x140085b9d  movups  [rsp+2D8h+var_1E0], xmm0
0x140085ba5  xor     edx, edx; Val
0x140085ba7  mov     r8d, 0D8h; Size
0x140085bad  lea     rcx, [r11-118h]; void *
0x140085bb4  call    memset
0x140085bb9  mov     [rsp+2D8h+var_248], rsi
0x140085bc1  xor     edx, edx; Val
0x140085bc3  mov     r8d, 0A0h; Size
0x140085bc9  lea     rcx, [rsp+2D8h+var_1B8]; void *
0x140085bd1  call    memset
0x140085bd6  mov     r12, [rbx+20h]
0x140085bda  mov     [rsp+2D8h+SpinLock], r12
0x140085bdf  test    r12, r12
0x140085be2  jnz     short loc_140085BF2
0x140085be4  mov     r14d, esi
0x140085be7  mov     r15d, 0E000417Bh
0x140085bed  jmp     loc_14008674B
0x140085bf2  cmp     [r12+1Ch], esi
0x140085bf7  jnz     short loc_140085C07
0x140085bf9  mov     r14d, esi
0x140085bfc  mov     r15d, 0E000417Ch
0x140085c02  jmp     loc_14008674B
0x140085c07  mov     rbx, [rbx+10h]
0x140085c0b  mov     [rsp+2D8h+var_1E8], rbx
0x140085c13  call    cs:__imp_PsGetCurrentProcessId
0x140085c1a  nop     dword ptr [rax+rax+00h]
0x140085c1f  cmp     [rbx+8], eax
0x140085c22  jz      short loc_140085C32
0x140085c24  mov     r14d, esi
0x140085c27  mov     r15d, 0E000417Dh
0x140085c2d  jmp     loc_14008674B
0x140085c32  cmp     [r12+10h], rsi
0x140085c37  jz      loc_14008673F
0x140085c3d  mov     [rsp+2D8h+var_240], rsi
0x140085c45  mov     [rsp+2D8h+Src], rsi
0x140085c4d  mov     r15d, esi
0x140085c50  mov     word ptr [rsp+2D8h+NewIrql], si
0x140085c58  mov     eax, [r12+4]
0x140085c5d  cmp     [r12+18h], eax
0x140085c62  ja      loc_14008673F
0x140085c68  mov     edx, [r12]; Length
0x140085c6c  mov     r13d, 1
0x140085c72  test    edx, edx
0x140085c74  jz      loc_140085D98
0x140085c7a  mov     [rsp+2D8h+Irp], rsi; Irp
0x140085c7f  mov     r9b, r13b; ChargeQuota
0x140085c82  xor     r8d, r8d; SecondaryBuffer
0x140085c85  mov     rcx, [r12+8]; VirtualAddress
0x140085c8a  call    cs:__imp_IoAllocateMdl
0x140085c91  nop     dword ptr [rax+rax+00h]
0x140085c96  mov     rbx, rax
0x140085c99  mov     [rsp+2D8h+Mdl], rax
0x140085ca1  test    rax, rax
0x140085ca4  jnz     short loc_140085CFE
0x140085ca6  mov     cl, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140085cac  test    cl, cl
0x140085cae  jns     short loc_140085CCA
0x140085cb0  lea     r9, aIpv4EchoDataMd; "IPv4 echo data MDL (IPNG)"
0x140085cb7  lea     rdx, TCPIP_MEMORY_FAILURES
0x140085cbe  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140085cc5  call    McTemplateK0z_EtwWriteTransfer
0x140085cca  mov     ebx, 0C0000017h
0x140085ccf  mov     [rsp+2D8h+var_268], ebx
0x140085cd3  mov     r14d, 23h ; '#'
0x140085cd9  mov     [rsp+2D8h+var_264], r14d
0x140085cde  mov     r15d, 0E000417Fh
0x140085ce4  mov     [rsp+2D8h+var_260], r15d
0x140085ce9  lea     edi, [r14-1Bh]
0x140085ced  mov     r13, rsi
0x140085cf0  mov     r10, rsi
0x140085cf3  mov     r8, rsi
0x140085cf6  mov     r11, rsi
0x140085cf9  jmp     loc_14008675E
0x140085cfe  xor     r8d, r8d; Operation
0x140085d01  mov     dl, r13b; AccessMode
0x140085d04  mov     rcx, rbx; MemoryDescriptorList
0x140085d07  call    cs:__imp_MmProbeAndLockPages
0x140085d0e  nop     dword ptr [rax+rax+00h]
0x140085d13  mov     [rsp+2D8h+var_277], r13b
0x140085d18  test    byte ptr [rbx+0Ah], 5
0x140085d1c  jz      short loc_140085D2C
0x140085d1e  mov     rcx, [rbx+18h]
0x140085d22  mov     [rsp+2D8h+var_240], rcx
0x140085d2a  jmp     short loc_140085D5A
0x140085d2c  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x140085d34  mov     dword ptr [rsp+2D8h+Irp], esi; BugCheckOnFailure
0x140085d38  xor     r9d, r9d; RequestedAddress
0x140085d3b  mov     r8d, r13d; CacheType
0x140085d3e  xor     edx, edx; AccessMode
0x140085d40  mov     rcx, rbx; MemoryDescriptorList
0x140085d43  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140085d4a  nop     dword ptr [rax+rax+00h]
0x140085d4f  mov     rcx, rax
0x140085d52  mov     [rsp+2D8h+var_240], rax
0x140085d5a  mov     [rsp+2D8h+var_1D0], rcx
0x140085d62  test    rcx, rcx
0x140085d65  jnz     short loc_140085D98
0x140085d67  mov     ebx, 0C000009Ah
0x140085d6c  mov     [rsp+2D8h+var_268], ebx
0x140085d70  lea     r14d, [rcx+23h]
0x140085d74  mov     [rsp+2D8h+var_264], r14d
0x140085d79  mov     r15d, 0E0004180h
0x140085d7f  mov     [rsp+2D8h+var_260], r15d
0x140085d84  lea     edi, [rcx+8]
0x140085d87  mov     r13, rsi
0x140085d8a  mov     r10, rsi
0x140085d8d  mov     r8, rsi
0x140085d90  mov     r11, rsi
0x140085d93  jmp     loc_14008675E
0x140085d98  movzx   eax, word ptr [r12+28h]
0x140085d9e  test    ax, ax
0x140085da1  jz      loc_140085EF8
0x140085da7  mov     edx, eax; Length
0x140085da9  mov     [rsp+2D8h+Irp], rsi; Irp
0x140085dae  mov     r9b, r13b; ChargeQuota
0x140085db1  xor     r8d, r8d; SecondaryBuffer
0x140085db4  mov     rcx, [r12+20h]; VirtualAddress
0x140085db9  call    cs:__imp_IoAllocateMdl
0x140085dc0  nop     dword ptr [rax+rax+00h]
0x140085dc5  mov     rbx, rax
0x140085dc8  mov     [rsp+2D8h+var_200], rax
0x140085dd0  test    rax, rax
0x140085dd3  jnz     short loc_140085E2D
0x140085dd5  mov     cl, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140085ddb  test    cl, cl
0x140085ddd  jns     short loc_140085DF9
0x140085ddf  lea     r9, aIpv4EchoOption; "IPv4 echo options MDL (IPNG)"
0x140085de6  lea     rdx, TCPIP_MEMORY_FAILURES
0x140085ded  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140085df4  call    McTemplateK0z_EtwWriteTransfer
0x140085df9  mov     ebx, 0C0000017h
0x140085dfe  mov     [rsp+2D8h+var_268], ebx
0x140085e02  mov     r14d, 23h ; '#'
0x140085e08  mov     [rsp+2D8h+var_264], r14d
0x140085e0d  mov     r15d, 0E0004181h
0x140085e13  mov     [rsp+2D8h+var_260], r15d
0x140085e18  lea     edi, [r14-1Bh]
0x140085e1c  mov     r13, rsi
0x140085e1f  mov     r10, rsi
0x140085e22  mov     r8, rsi
0x140085e25  mov     r11, rsi
0x140085e28  jmp     loc_14008675E
0x140085e2d  xor     r8d, r8d; Operation
0x140085e30  mov     dl, r13b; AccessMode
0x140085e33  mov     rcx, rbx; MemoryDescriptorList
0x140085e36  call    cs:__imp_MmProbeAndLockPages
0x140085e3d  nop     dword ptr [rax+rax+00h]
0x140085e42  mov     [rsp+2D8h+var_276], r13b
0x140085e47  test    byte ptr [rbx+0Ah], 5
0x140085e4b  jz      short loc_140085E5B
0x140085e4d  mov     rbx, [rbx+18h]
0x140085e51  mov     [rsp+2D8h+Src], rbx
0x140085e59  jmp     short loc_140085E89
0x140085e5b  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x140085e63  mov     dword ptr [rsp+2D8h+Irp], esi; BugCheckOnFailure
0x140085e67  xor     r9d, r9d; RequestedAddress
0x140085e6a  mov     r8d, r13d; CacheType
0x140085e6d  xor     edx, edx; AccessMode
0x140085e6f  mov     rcx, rbx; MemoryDescriptorList
0x140085e72  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140085e79  nop     dword ptr [rax+rax+00h]
0x140085e7e  mov     rbx, rax
0x140085e81  mov     [rsp+2D8h+Src], rax
0x140085e89  mov     [rsp+2D8h+var_1C8], rbx
0x140085e91  test    rbx, rbx
0x140085e94  jnz     short loc_140085ECA
0x140085e96  mov     ebx, 0C000009Ah
0x140085e9b  mov     [rsp+2D8h+var_268], ebx
0x140085e9f  mov     r14d, 23h ; '#'
0x140085ea5  mov     [rsp+2D8h+var_264], r14d
0x140085eaa  mov     r15d, 0E0004182h
0x140085eb0  mov     [rsp+2D8h+var_260], r15d
0x140085eb5  lea     edi, [r14-1Bh]
0x140085eb9  mov     r13, rsi
0x140085ebc  mov     r10, rsi
0x140085ebf  mov     r8, rsi
0x140085ec2  mov     r11, rsi
0x140085ec5  jmp     loc_14008675E
0x140085eca  movzx   r15d, word ptr [r12+28h]
0x140085ed0  movzx   ebx, r15w
0x140085ed4  mov     word ptr [rsp+2D8h+NewIrql], bx
0x140085edc  mov     [rsp+2D8h+var_218], bx
0x140085ee4  add     r15d, 7
0x140085ee8  and     r15d, 0FFFFFFF8h
0x140085eec  add     r15d, 10h
0x140085ef0  mov     [rsp+2D8h+var_1F8], r15d
0x140085ef8  mov     [rsp+2D8h+Irp], rsi; Irp
0x140085efd  mov     r9b, r13b; ChargeQuota
0x140085f00  xor     r8d, r8d; SecondaryBuffer
0x140085f03  mov     edx, [r12+4]; Length
0x140085f08  mov     rcx, [r12+10h]; VirtualAddress
0x140085f0d  call    cs:__imp_IoAllocateMdl
0x140085f14  nop     dword ptr [rax+rax+00h]
0x140085f19  mov     rdi, rax
0x140085f1c  mov     [rsp+2D8h+MemoryDescriptorList], rax
0x140085f24  test    rax, rax
0x140085f27  jnz     short loc_140085F81
0x140085f29  mov     cl, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x140085f2f  test    cl, cl
0x140085f31  jns     short loc_140085F4D
0x140085f33  lea     r9, aIpv4EchoReplyM; "IPv4 echo reply MDL (IPNG)"
0x140085f3a  lea     rdx, TCPIP_MEMORY_FAILURES
0x140085f41  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140085f48  call    McTemplateK0z_EtwWriteTransfer
0x140085f4d  mov     ebx, 0C0000017h
0x140085f52  mov     [rsp+2D8h+var_268], ebx
0x140085f56  mov     r14d, 23h ; '#'
0x140085f5c  mov     [rsp+2D8h+var_264], r14d
0x140085f61  mov     r15d, 0E0004183h
0x140085f67  mov     [rsp+2D8h+var_260], r15d
0x140085f6c  lea     edi, [r14-1Bh]
0x140085f70  mov     r13, rsi
0x140085f73  mov     r10, rsi
0x140085f76  mov     r8, rsi
0x140085f79  mov     r11, rsi
0x140085f7c  jmp     loc_14008675E
0x140085f81  mov     r8d, r13d; Operation
0x140085f84  mov     dl, r13b; AccessMode
0x140085f87  mov     rcx, rdi; MemoryDescriptorList
0x140085f8a  call    cs:__imp_MmProbeAndLockPages
0x140085f91  nop     dword ptr [rax+rax+00h]
0x140085f96  mov     [rsp+2D8h+var_278], r13b
0x140085f9b  call    NdisGetCurrentThreadCompartmentId
0x140085fa0  mov     dword ptr [rsp+2D8h+var_1E0+8], eax
0x140085fa7  lea     rdx, [rsp+2D8h+var_1E0]
0x140085faf  mov     rbx, qword ptr [rsp+2D8h+arg_8]
0x140085fb7  mov     rcx, rbx
0x140085fba  call    IppGetCompartment
0x140085fbf  mov     r11, rax
0x140085fc2  mov     [rsp+2D8h+var_250], rax
0x140085fca  test    rax, rax
0x140085fcd  jnz     short loc_140085FE0
0x140085fcf  mov     r14d, esi
0x140085fd2  mov     r15d, 0E0004185h
0x140085fd8  mov     r13, rsi
0x140085fdb  jmp     loc_14008674E
0x140085fe0  mov     edx, 0E8h
0x140085fe5  mov     ecx, 40h ; '@'
0x140085fea  mov     r8d, 20653449h
0x140085ff0  call    cs:__imp_ExAllocatePool2
0x140085ff7  nop     dword ptr [rax+rax+00h]
0x140085ffc  mov     r14, rax
0x140085fff  mov     [rsp+2D8h+SpinLock], rax
0x140086004  test    rax, rax
0x140086007  jnz     short loc_140086050
0x140086009  mov     al, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3
0x14008600f  test    al, al
0x140086011  jns     short loc_14008602D
0x140086013  lea     r9, aIpv4EchoReques; "IPv4 echo request (IPNG)"
0x14008601a  lea     rdx, TCPIP_MEMORY_FAILURES
0x140086021  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140086028  call    McTemplateK0z_EtwWriteTransfer
0x14008602d  mov     ebx, 0C000009Ah
0x140086032  mov     r14d, 23h ; '#'
0x140086038  mov     r15d, 0E0004186h
0x14008603e  mov     r13, [rsp+2D8h+SpinLock]
0x140086043  mov     r11, [rsp+2D8h+var_250]
0x14008604b  jmp     loc_140086753
0x140086050  mov     [rax+8], r13
0x140086054  lea     rdx, [rax+20h]
0x140086058  xor     r9d, r9d
0x14008605b  xor     r8d, r8d
0x14008605e  xor     ecx, ecx
0x140086060  call    cs:__imp_RtlInitializeTimerWheelEntry
0x140086067  nop     dword ptr [rax+rax+00h]
0x14008606c  lea     rax, [r14+10h]
0x140086070  mov     [rax+8], rax
0x140086074  mov     [rax], rax
0x140086077  mov     rcx, r14; SpinLock
0x14008607a  call    cs:__imp_KeInitializeSpinLock
0x140086081  nop     dword ptr [rax+rax+00h]
0x140086086  mov     r11, [rsp+2D8h+var_250]
0x14008608e  mov     [r14+38h], r11
0x140086092  mov     [r14+48h], rdi
0x140086096  mov     edi, 8
0x14008609b  cmp     [r12+35h], sil
  ... truncated ...
```
