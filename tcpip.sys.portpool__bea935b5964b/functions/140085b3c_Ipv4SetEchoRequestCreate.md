# Ipv4SetEchoRequestCreate

- ea: `0x140085b3c`
- end: `0x14008690d`
- name: `Ipv4SetEchoRequestCreate`
- size: `3537`
- prototype: `__int64 __fastcall(__int64, __int64)`
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
  unsigned int *v4; // r12
  int v5; // r14d
  int v6; // r15d
  unsigned int v7; // r15d
  struct _MDL *v8; // rax
  __int64 v9; // r8
  struct _MDL *v10; // rbx
  int v11; // ebx
  int v12; // r10d
  _QWORD *v13; // r8
  int *Compartment; // r11
  PVOID MappedSystemVa; // rcx
  struct _MDL *v16; // rax
  __int64 v17; // r8
  struct _MDL *v18; // rbx
  PVOID v19; // rbx
  struct _MDL *v20; // rax
  __int64 v21; // r8
  struct _MDL *v22; // rdi
  __int64 Pool2; // rax
  __int64 v24; // r8
  __int64 v25; // r14
  unsigned __int16 v26; // r8
  unsigned int v27; // ecx
  unsigned int v28; // edx
  ULONG v29; // r8d
  ULONG v30; // ecx
  __int64 NetBufferListForEcho; // rax
  __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned __int32 v34; // eax
  __int64 v35; // rax
  __int64 v36; // r8
  char *v37; // rdx
  _DWORD *v38; // r9
  __int64 v39; // r8
  _DWORD *v40; // r15
  unsigned int v41; // ebx
  __int64 v42; // rcx
  __int64 v43; // r15
  KSPIN_LOCK *v44; // rbx
  KIRQL v45; // r14
  __int64 v46; // rdx
  __int64 v47; // rdx
  unsigned __int64 v48; // rdi
  unsigned int v49; // eax
  int v50; // r9d
  __int64 v51; // rdx
  __int64 v52; // rax
  void *v53; // r12
  char v55; // [rsp+60h] [rbp-278h]
  char v56; // [rsp+61h] [rbp-277h]
  char v57; // [rsp+62h] [rbp-276h]
  LARGE_INTEGER *SpinLock; // [rsp+68h] [rbp-270h]
  __int64 v59; // [rsp+80h] [rbp-258h]
  int *v60; // [rsp+88h] [rbp-250h]
  _QWORD *v61; // [rsp+90h] [rbp-248h]
  PVOID v62; // [rsp+98h] [rbp-240h]
  unsigned int v63; // [rsp+98h] [rbp-240h]
  char *P; // [rsp+A0h] [rbp-238h]
  void *Src; // [rsp+A8h] [rbp-230h]
  __int64 v66; // [rsp+B0h] [rbp-228h]
  unsigned int *v67; // [rsp+B8h] [rbp-220h]
  struct _MDL *MemoryDescriptorList; // [rsp+C8h] [rbp-210h]
  struct _MDL *Mdl; // [rsp+D0h] [rbp-208h]
  struct _MDL *v70; // [rsp+D8h] [rbp-200h]
  __int64 v71; // [rsp+E8h] [rbp-1F0h] BYREF
  __int64 v72; // [rsp+F0h] [rbp-1E8h]
  __int128 v73; // [rsp+F8h] [rbp-1E0h] BYREF
  PVOID v74; // [rsp+108h] [rbp-1D0h]
  PVOID v75; // [rsp+110h] [rbp-1C8h]
  _QWORD v76[20]; // [rsp+120h] [rbp-1B8h] BYREF
  _QWORD v77[35]; // [rsp+1C0h] [rbp-118h] BYREF
  unsigned __int16 NewIrql; // [rsp+2E0h] [rbp+8h]
  KIRQL NewIrqla; // [rsp+2E0h] [rbp+8h]
  __int16 v81; // [rsp+2F0h] [rbp+18h]
  int v82; // [rsp+2F8h] [rbp+20h]
  KSPIN_LOCK *v83; // [rsp+2F8h] [rbp+20h]

  v3 = 0;
  v56 = 0;
  v57 = 0;
  v55 = 0;
  Mdl = 0;
  v70 = 0;
  MemoryDescriptorList = 0;
  P = 0;
  v59 = 0;
  v71 = 0;
  v73 = 0;
  memset(v77, 0, 0xD8u);
  v61 = 0;
  memset(v76, 0, sizeof(v76));
  v4 = *(unsigned int **)(a1 + 32);
  if ( !v4 )
  {
    v5 = 0;
    v6 = -536854149;
LABEL_85:
    Compartment = 0;
    goto LABEL_86;
  }
  if ( !v4[7] )
  {
    v5 = 0;
    v6 = -536854148;
    goto LABEL_85;
  }
  v72 = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(v72 + 8) != (unsigned int)PsGetCurrentProcessId() )
  {
    v5 = 0;
    v6 = -536854147;
    goto LABEL_85;
  }
  if ( !*((_QWORD *)v4 + 2) || (v62 = 0, Src = 0, v7 = 0, NewIrql = 0, v4[6] > v4[1]) )
  {
    v5 = 15;
    v6 = -536854146;
    goto LABEL_85;
  }
  if ( *v4 )
  {
    v8 = IoAllocateMdl(*((PVOID *)v4 + 1), *v4, 0, 1u, 0);
    v10 = v8;
    Mdl = v8;
    if ( !v8 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v9,
          L"IPv4 echo data MDL (IPNG)");
      v11 = -1073741801;
      v5 = 35;
      v6 = -536854145;
      v3 = 0;
      v12 = 0;
      v13 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
    MmProbeAndLockPages(v8, 1, IoReadAccess);
    v56 = 1;
    if ( (v10->MdlFlags & 5) != 0 )
      MappedSystemVa = v10->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
    v62 = MappedSystemVa;
    v74 = MappedSystemVa;
    if ( !MappedSystemVa )
    {
      v11 = -1073741670;
      v5 = 35;
      v6 = -536854144;
      v3 = 0;
      v12 = 0;
      v13 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
  }
  if ( *((_WORD *)v4 + 20) )
  {
    v16 = IoAllocateMdl(*((PVOID *)v4 + 4), *((unsigned __int16 *)v4 + 20), 0, 1u, 0);
    v18 = v16;
    v70 = v16;
    if ( !v16 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v17,
          L"IPv4 echo options MDL (IPNG)");
      v11 = -1073741801;
      v5 = 35;
      v6 = -536854143;
      v3 = 0;
      v12 = 0;
      v13 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
    MmProbeAndLockPages(v16, 1, IoReadAccess);
    v57 = 1;
    if ( (v18->MdlFlags & 5) != 0 )
      v19 = v18->MappedSystemVa;
    else
      v19 = MmMapLockedPagesSpecifyCache(v18, 0, MmCached, 0, 0, 0x40000010u);
    Src = v19;
    v75 = v19;
    if ( !v19 )
    {
      v11 = -1073741670;
      v5 = 35;
      v6 = -536854142;
      v3 = 0;
      v12 = 0;
      v13 = 0;
      Compartment = 0;
      goto LABEL_89;
    }
    NewIrql = *((_WORD *)v4 + 20);
    v7 = ((NewIrql + 7) & 0xFFFFFFF8) + 16;
  }
  v20 = IoAllocateMdl(*((PVOID *)v4 + 2), v4[1], 0, 1u, 0);
  v22 = v20;
  MemoryDescriptorList = v20;
  if ( !v20 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v21,
        L"IPv4 echo reply MDL (IPNG)");
    v11 = -1073741801;
    v5 = 35;
    v6 = -536854141;
    v3 = 0;
    v12 = 0;
    v13 = 0;
    Compartment = 0;
    goto LABEL_89;
  }
  MmProbeAndLockPages(v20, 1, IoWriteAccess);
  v55 = 1;
  DWORD2(v73) = NdisGetCurrentThreadCompartmentId();
  Compartment = (int *)IppGetCompartment(a2, &v73);
  v60 = Compartment;
  if ( !Compartment )
  {
    v5 = 0;
    v6 = -536854139;
    v3 = 0;
LABEL_86:
    v11 = -1073741811;
    goto LABEL_87;
  }
  Pool2 = ExAllocatePool2(64, 232, 543503433);
  v25 = Pool2;
  SpinLock = (LARGE_INTEGER *)Pool2;
  if ( !Pool2 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v24,
        L"IPv4 echo request (IPNG)");
    v11 = -1073741670;
    v5 = 35;
    v6 = -536854138;
    v3 = 0;
    Compartment = v60;
    goto LABEL_87;
  }
  *(_QWORD *)(Pool2 + 8) = 1;
  RtlInitializeTimerWheelEntry(0, Pool2 + 32, 0, 0);
  *(_QWORD *)(v25 + 24) = v25 + 16;
  *(_QWORD *)(v25 + 16) = v25 + 16;
  KeInitializeSpinLock((PKSPIN_LOCK)v25);
  Compartment = v60;
  *(_QWORD *)(v25 + 56) = v60;
  *(_QWORD *)(v25 + 72) = v22;
  if ( *((_BYTE *)v4 + 53) )
  {
    if ( Src )
    {
      v11 = -1073741811;
      v6 = -536854137;
LABEL_43:
      v5 = 0;
      v3 = SpinLock;
LABEL_87:
      v12 = 0;
      goto LABEL_88;
    }
    v26 = 8;
    v81 = 8;
    v7 += 24;
    v66 = 1;
  }
  else
  {
    v26 = 0;
    v81 = 0;
    v66 = 0;
  }
  v27 = *v4 + 8;
  if ( v27 < *v4 )
  {
    v11 = -1073741675;
    v6 = -536854136;
    goto LABEL_43;
  }
  v28 = v27 + ((NewIrql + 3) & 0xFFFFFFFC);
  if ( v28 < v27 )
  {
    v11 = -1073741675;
    v6 = -536854135;
    goto LABEL_43;
  }
  v82 = v26;
  v29 = v26 + v28;
  if ( v29 < v28 )
  {
    v11 = -1073741675;
    v6 = -536854134;
    goto LABEL_43;
  }
  v30 = v29 + *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 8LL);
  if ( v30 < v29 )
  {
    v11 = -1073741675;
    v6 = -536854133;
    goto LABEL_43;
  }
  NetBufferListForEcho = IppAllocateNetBufferListForEcho(v30);
  v12 = NetBufferListForEcho;
  v59 = NetBufferListForEcho;
  if ( !NetBufferListForEcho )
  {
    v11 = -1073741670;
    v5 = 35;
    v6 = -536854132;
LABEL_56:
    v3 = SpinLock;
    Compartment = v60;
LABEL_88:
    v13 = 0;
    goto LABEL_89;
  }
  v32 = *v4;
  if ( (_DWORD)v32 )
  {
    NetioRetreatNetBuffer(*(_QWORD *)(NetBufferListForEcho + 8), v32, 0);
    RtlCopyKernelBufferToMdl(
      v62,
      *(_QWORD *)(*(_QWORD *)(v59 + 8) + 8LL),
      *(unsigned int *)(*(_QWORD *)(v59 + 8) + 16LL),
      *v4,
      &v71);
  }
  v33 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 20076));
  if ( v33 < 0x10000 )
  {
    _InterlockedAdd((volatile signed __int32 *)(a2 + 20076), 0x10000u);
    v33 += 0x10000;
  }
  v34 = _byteswap_ulong(v33);
  *(_DWORD *)(v25 + 64) = v34;
  HIDWORD(v77[26]) = v34;
  v67 = v4 + 16;
  v76[0] = *(_QWORD *)(v25 + 56);
  v76[8] = v4 + 16;
  LODWORD(v76[7]) = v4[12];
  if ( v4[15] )
  {
    LODWORD(v76[10]) = v4[11];
    v76[11] = v4 + 15;
  }
  v76[16] = *(_QWORD *)(a2 + 640);
  v76[17] = 0;
  LODWORD(v76[19]) = 1;
  BYTE4(v76[19]) = 8;
  v11 = IppJoinPath(a2, v76);
  if ( v11 < 0 )
  {
    v5 = 13;
    v6 = -536854130;
    v12 = v59;
    goto LABEL_56;
  }
  v61 = (_QWORD *)v76[15];
  if ( *((_BYTE *)v4 + 56) )
    v7 += 24;
  v63 = v7 + 24;
  v35 = ExAllocatePool2(64, v7 + 24, 543503433);
  v37 = (char *)v35;
  P = (char *)v35;
  if ( v35 )
  {
    v38 = (_DWORD *)(v35 + 16);
    v39 = a2;
    v40 = (_DWORD *)(a2 + 24);
    if ( v81 )
    {
      *(_QWORD *)v35 = ((v82 + 7) & 0xFFFFFFF8) + 16LL;
      *(_DWORD *)(v35 + 8) = *v40;
      *(_DWORD *)(v35 + 12) = 1;
      v41 = *(_DWORD *)v35;
      *v38 = 134710017;
      v38[v66] = v4[16];
      v67 = **(unsigned int ***)(*v61 + 16LL);
    }
    else
    {
      v41 = 0;
    }
    if ( NewIrql )
    {
      *(_QWORD *)v35 = ((NewIrql + 7) & 0xFFFFFFF8) + 16LL;
      *(_DWORD *)(v35 + 8) = *v40;
      *(_DWORD *)(v35 + 12) = 1;
      v41 = ((NewIrql + 7) & 0xFFFFFFF8) + 16;
      memmove(v38, Src, NewIrql);
      v37 = P;
      v39 = a2;
    }
    if ( *((_BYTE *)v4 + 56) )
    {
      v42 = v41;
      *(_QWORD *)&v37[v41] = 24;
      *(_DWORD *)&v37[v41 + 8] = *v40;
      *(_DWORD *)&v37[v41 + 12] = 14;
      v41 += 24;
      *(_DWORD *)&v37[v42 + 16] = 1;
    }
    *(_QWORD *)&v37[v41] = 24;
    *(_DWORD *)&v37[v41 + 8] = *v40;
    *(_DWORD *)&v37[v41 + 12] = 21;
    *(_DWORD *)&v37[v41 + 16] = *((unsigned __int8 *)v4 + 52);
    v43 = v72;
    *(_OWORD *)(v25 + 88) = *(_OWORD *)v72;
    *(_OWORD *)(v25 + 104) = *(_OWORD *)(v43 + 16);
    *(_OWORD *)(v25 + 160) = *(_OWORD *)v4;
    *(_OWORD *)(v25 + 176) = *((_OWORD *)v4 + 1);
    *(_OWORD *)(v25 + 192) = *((_OWORD *)v4 + 2);
    *(_OWORD *)(v25 + 208) = *((_OWORD *)v4 + 3);
    *(_QWORD *)(v25 + 224) = *((_QWORD *)v4 + 8);
    *(_DWORD *)(v25 + 120) = 259;
    v44 = (KSPIN_LOCK *)(v39 + 20048);
    v83 = (KSPIN_LOCK *)(v39 + 20048);
    v45 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v39 + 20048));
    NewIrqla = v45;
    if ( IppFindEchoRequest(a2 + 19936, v46, v43) )
    {
      KeReleaseSpinLock(v44, v45);
      v11 = -1073741270;
      v5 = 36;
      v6 = -536854128;
    }
    else
    {
      v5 = 44;
      v6 = -536850433;
      IppInsertEchoRequest(a2 + 19936, v47, SpinLock);
      if ( _InterlockedIncrement64((volatile signed __int64 *)&SpinLock[1]) <= 1 )
        __fastfail(0xEu);
      SpinLock[10] = KeQueryPerformanceCounter(0);
      v48 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&SpinLock->QuadPart);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 20064));
      v49 = IppMillisecondsToTicks(v4[7]);
      IppStartEchoRequestTimer(a2, SpinLock, v48 / 0x1F4, v49);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 20064));
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&SpinLock->QuadPart);
      KeReleaseSpinLock(v83, NewIrqla);
      v77[0] = v59;
      LOBYTE(v77[26]) = 8;
      LOWORD(v77[7]) = 1;
      LODWORD(v77[17]) = v4[12];
      v77[18] = v67;
      v77[4] = v61;
      v77[10] = P;
      LODWORD(v77[9]) = v63;
      IppSendControl(0, a2, v77);
      v11 = 0;
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
    v11 = -1073741670;
    v5 = 35;
    v6 = -536854129;
  }
  v3 = SpinLock;
  v12 = v59;
  v13 = v61;
  Compartment = v60;
LABEL_89:
  if ( v11 < 0 )
  {
    if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredContext) & 4) != 0 || byte_140229CC0 )
    {
      v50 = 0;
      if ( v13 )
      {
        v51 = **(_QWORD **)(*v13 + 16LL);
        v52 = *(_QWORD *)(*v13 + 8LL);
        v53 = (void *)v13[2];
      }
      else
      {
        LODWORD(v52) = 0;
        if ( v4 )
        {
          v51 = (__int64)(v4 + 15);
          v53 = v4 + 16;
        }
        else
        {
          v51 = 0;
          v53 = 0;
        }
      }
      if ( Compartment )
        v50 = *Compartment;
      LogIcmpSendDrop(a2, 8, SBYTE1(v77[26]), v5, v11, v50, v51, v53, v52, v12, 0, v6);
    }
    if ( v59 )
    {
      *(_DWORD *)(v59 + 140) = v11;
      v3[8].HighPart |= 2u;
      NetioDereferenceNetBufferList(v59, 0);
    }
    else
    {
      if ( MemoryDescriptorList )
      {
        if ( v55 )
          MmUnlockPages(MemoryDescriptorList);
        IoFreeMdl(MemoryDescriptorList);
      }
      if ( v3 )
        IppDereferenceEchoRequest(v3);
    }
  }
  if ( v61 )
    IppDereferencePath(v61);
  if ( Mdl )
  {
    if ( v56 )
      MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
  }
  if ( v70 )
  {
    if ( v57 )
      MmUnlockPages(v70);
    IoFreeMdl(v70);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v11;
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
