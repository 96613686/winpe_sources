# Ipv4SetEchoRequestCreate

- ea: `0x1400793cc`
- end: `0x14007a19d`
- name: `Ipv4SetEchoRequestCreate`
- size: `3537`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140079200`

## callees

- `0x140017140`
- `0x140026ec0`
- `0x140033ef0`
- `0x140053e98`
- `0x140064e00`
- `0x140078f8c`
- `0x1400790b4`
- `0x140079358`
- `0x1400793cc`
- `0x14007aeb8`
- `0x14007b144`
- `0x14009c120`
- `0x14009d754`
- `0x1400a5af0`
- `0x1400a8464`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14007a0c8`
- `ntoskrnl!MmUnlockPages` at `0x14007a11c`
- `ntoskrnl!MmUnlockPages` at `0x14007a14e`
- `ntoskrnl!MmUnlockPages` at `0x14007a0c8`
- `ntoskrnl!MmUnlockPages` at `0x14007a11c`
- `ntoskrnl!MmUnlockPages` at `0x14007a14e`
- `ntoskrnl!MmProbeAndLockPages` at `0x140079597`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400796c6`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007981a`
- `ntoskrnl!MmProbeAndLockPages` at `0x140079597`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400796c6`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007981a`
- `ntoskrnl!IoAllocateMdl` at `0x14007951a`
- `ntoskrnl!IoAllocateMdl` at `0x140079649`
- `ntoskrnl!IoAllocateMdl` at `0x14007979d`
- `ntoskrnl!IoAllocateMdl` at `0x14007951a`
- `ntoskrnl!IoAllocateMdl` at `0x140079649`
- `ntoskrnl!IoAllocateMdl` at `0x14007979d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400795d3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140079702`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400795d3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140079702`
- `ntoskrnl!IoFreeMdl` at `0x14007a0d7`
- `ntoskrnl!IoFreeMdl` at `0x14007a12b`
- `ntoskrnl!IoFreeMdl` at `0x14007a15d`
- `ntoskrnl!IoFreeMdl` at `0x14007a0d7`
- `ntoskrnl!IoFreeMdl` at `0x14007a12b`
- `ntoskrnl!IoFreeMdl` at `0x14007a15d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079e60`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079e7b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079e60`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079e7b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140079ec3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140079ed4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140079ec3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140079ed4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400794a3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400794a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079eef`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079eef`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007990a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007990a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079d8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079d8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a17b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a17b`
- `ntoskrnl!ExAllocatePool2` at `0x140079880`
- `ntoskrnl!ExAllocatePool2` at `0x140079b8e`
- `ntoskrnl!ExAllocatePool2` at `0x140079880`
- `ntoskrnl!ExAllocatePool2` at `0x140079b8e`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007a0a3`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007a0a3`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x1400798f0`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x1400798f0`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140079a82`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140079a82`
- `HAL!KeQueryPerformanceCounter` at `0x140079e2c`
- `HAL!KeQueryPerformanceCounter` at `0x140079e2c`

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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 11) & 4) != 0 || byte_140225C70 )
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
0x1400793cc  mov     r11, rsp
0x1400793cf  mov     [r11+10h], rdx
0x1400793d3  push    rbx
0x1400793d4  push    rsi
0x1400793d5  push    rdi
0x1400793d6  push    r12
0x1400793d8  push    r13
0x1400793da  push    r14
0x1400793dc  push    r15
0x1400793de  sub     rsp, 2A0h
0x1400793e5  mov     rbx, rcx
0x1400793e8  xor     esi, esi
0x1400793ea  mov     r13d, esi
0x1400793ed  mov     [rsp+2D8h+var_277], sil
0x1400793f2  mov     [rsp+2D8h+var_276], sil
0x1400793f7  mov     [rsp+2D8h+var_278], sil
0x1400793fc  mov     [r11-208h], rsi
0x140079403  mov     [r11-200h], rsi
0x14007940a  mov     [r11-210h], rsi
0x140079411  mov     eax, esi
0x140079413  mov     [rsp+2D8h+P], rax
0x14007941b  mov     [rsp+2D8h+var_258], rax
0x140079423  mov     [r11-1F0h], rsi
0x14007942a  xorps   xmm0, xmm0
0x14007942d  movups  [rsp+2D8h+var_1E0], xmm0
0x140079435  xor     edx, edx; Val
0x140079437  mov     r8d, 0D8h; Size
0x14007943d  lea     rcx, [r11-118h]; void *
0x140079444  call    memset
0x140079449  mov     [rsp+2D8h+var_248], rsi
0x140079451  xor     edx, edx; Val
0x140079453  mov     r8d, 0A0h; Size
0x140079459  lea     rcx, [rsp+2D8h+var_1B8]; void *
0x140079461  call    memset
0x140079466  mov     r12, [rbx+20h]
0x14007946a  mov     [rsp+2D8h+SpinLock], r12
0x14007946f  test    r12, r12
0x140079472  jnz     short loc_140079482
0x140079474  mov     r14d, esi
0x140079477  mov     r15d, 0E000417Bh
0x14007947d  jmp     loc_140079FDB
0x140079482  cmp     [r12+1Ch], esi
0x140079487  jnz     short loc_140079497
0x140079489  mov     r14d, esi
0x14007948c  mov     r15d, 0E000417Ch
0x140079492  jmp     loc_140079FDB
0x140079497  mov     rbx, [rbx+10h]
0x14007949b  mov     [rsp+2D8h+var_1E8], rbx
0x1400794a3  call    cs:__imp_PsGetCurrentProcessId
0x1400794aa  nop     dword ptr [rax+rax+00h]
0x1400794af  cmp     [rbx+8], eax
0x1400794b2  jz      short loc_1400794C2
0x1400794b4  mov     r14d, esi
0x1400794b7  mov     r15d, 0E000417Dh
0x1400794bd  jmp     loc_140079FDB
0x1400794c2  cmp     [r12+10h], rsi
0x1400794c7  jz      loc_140079FCF
0x1400794cd  mov     [rsp+2D8h+var_240], rsi
0x1400794d5  mov     [rsp+2D8h+Src], rsi
0x1400794dd  mov     r15d, esi
0x1400794e0  mov     word ptr [rsp+2D8h+NewIrql], si
0x1400794e8  mov     eax, [r12+4]
0x1400794ed  cmp     [r12+18h], eax
0x1400794f2  ja      loc_140079FCF
0x1400794f8  mov     edx, [r12]; Length
0x1400794fc  mov     r13d, 1
0x140079502  test    edx, edx
0x140079504  jz      loc_140079628
0x14007950a  mov     [rsp+2D8h+Irp], rsi; Irp
0x14007950f  mov     r9b, r13b; ChargeQuota
0x140079512  xor     r8d, r8d; SecondaryBuffer
0x140079515  mov     rcx, [r12+8]; VirtualAddress
0x14007951a  call    cs:__imp_IoAllocateMdl
0x140079521  nop     dword ptr [rax+rax+00h]
0x140079526  mov     rbx, rax
0x140079529  mov     [rsp+2D8h+Mdl], rax
0x140079531  test    rax, rax
0x140079534  jnz     short loc_14007958E
0x140079536  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007953c  test    cl, cl
0x14007953e  jns     short loc_14007955A
0x140079540  lea     r9, aIpv4EchoDataMd; "IPv4 echo data MDL (IPNG)"
0x140079547  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007954e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140079555  call    McTemplateK0z_EtwWriteTransfer
0x14007955a  mov     ebx, 0C0000017h
0x14007955f  mov     [rsp+2D8h+var_268], ebx
0x140079563  mov     r14d, 23h ; '#'
0x140079569  mov     [rsp+2D8h+var_264], r14d
0x14007956e  mov     r15d, 0E000417Fh
0x140079574  mov     [rsp+2D8h+var_260], r15d
0x140079579  lea     edi, [r14-1Bh]
0x14007957d  mov     r13, rsi
0x140079580  mov     r10, rsi
0x140079583  mov     r8, rsi
0x140079586  mov     r11, rsi
0x140079589  jmp     loc_140079FEE
0x14007958e  xor     r8d, r8d; Operation
0x140079591  mov     dl, r13b; AccessMode
0x140079594  mov     rcx, rbx; MemoryDescriptorList
0x140079597  call    cs:__imp_MmProbeAndLockPages
0x14007959e  nop     dword ptr [rax+rax+00h]
0x1400795a3  mov     [rsp+2D8h+var_277], r13b
0x1400795a8  test    byte ptr [rbx+0Ah], 5
0x1400795ac  jz      short loc_1400795BC
0x1400795ae  mov     rcx, [rbx+18h]
0x1400795b2  mov     [rsp+2D8h+var_240], rcx
0x1400795ba  jmp     short loc_1400795EA
0x1400795bc  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x1400795c4  mov     dword ptr [rsp+2D8h+Irp], esi; BugCheckOnFailure
0x1400795c8  xor     r9d, r9d; RequestedAddress
0x1400795cb  mov     r8d, r13d; CacheType
0x1400795ce  xor     edx, edx; AccessMode
0x1400795d0  mov     rcx, rbx; MemoryDescriptorList
0x1400795d3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400795da  nop     dword ptr [rax+rax+00h]
0x1400795df  mov     rcx, rax
0x1400795e2  mov     [rsp+2D8h+var_240], rax
0x1400795ea  mov     [rsp+2D8h+var_1D0], rcx
0x1400795f2  test    rcx, rcx
0x1400795f5  jnz     short loc_140079628
0x1400795f7  mov     ebx, 0C000009Ah
0x1400795fc  mov     [rsp+2D8h+var_268], ebx
0x140079600  lea     r14d, [rcx+23h]
0x140079604  mov     [rsp+2D8h+var_264], r14d
0x140079609  mov     r15d, 0E0004180h
0x14007960f  mov     [rsp+2D8h+var_260], r15d
0x140079614  lea     edi, [rcx+8]
0x140079617  mov     r13, rsi
0x14007961a  mov     r10, rsi
0x14007961d  mov     r8, rsi
0x140079620  mov     r11, rsi
0x140079623  jmp     loc_140079FEE
0x140079628  movzx   eax, word ptr [r12+28h]
0x14007962e  test    ax, ax
0x140079631  jz      loc_140079788
0x140079637  mov     edx, eax; Length
0x140079639  mov     [rsp+2D8h+Irp], rsi; Irp
0x14007963e  mov     r9b, r13b; ChargeQuota
0x140079641  xor     r8d, r8d; SecondaryBuffer
0x140079644  mov     rcx, [r12+20h]; VirtualAddress
0x140079649  call    cs:__imp_IoAllocateMdl
0x140079650  nop     dword ptr [rax+rax+00h]
0x140079655  mov     rbx, rax
0x140079658  mov     [rsp+2D8h+var_200], rax
0x140079660  test    rax, rax
0x140079663  jnz     short loc_1400796BD
0x140079665  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007966b  test    cl, cl
0x14007966d  jns     short loc_140079689
0x14007966f  lea     r9, aIpv4EchoOption; "IPv4 echo options MDL (IPNG)"
0x140079676  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007967d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140079684  call    McTemplateK0z_EtwWriteTransfer
0x140079689  mov     ebx, 0C0000017h
0x14007968e  mov     [rsp+2D8h+var_268], ebx
0x140079692  mov     r14d, 23h ; '#'
0x140079698  mov     [rsp+2D8h+var_264], r14d
0x14007969d  mov     r15d, 0E0004181h
0x1400796a3  mov     [rsp+2D8h+var_260], r15d
0x1400796a8  lea     edi, [r14-1Bh]
0x1400796ac  mov     r13, rsi
0x1400796af  mov     r10, rsi
0x1400796b2  mov     r8, rsi
0x1400796b5  mov     r11, rsi
0x1400796b8  jmp     loc_140079FEE
0x1400796bd  xor     r8d, r8d; Operation
0x1400796c0  mov     dl, r13b; AccessMode
0x1400796c3  mov     rcx, rbx; MemoryDescriptorList
0x1400796c6  call    cs:__imp_MmProbeAndLockPages
0x1400796cd  nop     dword ptr [rax+rax+00h]
0x1400796d2  mov     [rsp+2D8h+var_276], r13b
0x1400796d7  test    byte ptr [rbx+0Ah], 5
0x1400796db  jz      short loc_1400796EB
0x1400796dd  mov     rbx, [rbx+18h]
0x1400796e1  mov     [rsp+2D8h+Src], rbx
0x1400796e9  jmp     short loc_140079719
0x1400796eb  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x1400796f3  mov     dword ptr [rsp+2D8h+Irp], esi; BugCheckOnFailure
0x1400796f7  xor     r9d, r9d; RequestedAddress
0x1400796fa  mov     r8d, r13d; CacheType
0x1400796fd  xor     edx, edx; AccessMode
0x1400796ff  mov     rcx, rbx; MemoryDescriptorList
0x140079702  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140079709  nop     dword ptr [rax+rax+00h]
0x14007970e  mov     rbx, rax
0x140079711  mov     [rsp+2D8h+Src], rax
0x140079719  mov     [rsp+2D8h+var_1C8], rbx
0x140079721  test    rbx, rbx
0x140079724  jnz     short loc_14007975A
0x140079726  mov     ebx, 0C000009Ah
0x14007972b  mov     [rsp+2D8h+var_268], ebx
0x14007972f  mov     r14d, 23h ; '#'
0x140079735  mov     [rsp+2D8h+var_264], r14d
0x14007973a  mov     r15d, 0E0004182h
0x140079740  mov     [rsp+2D8h+var_260], r15d
0x140079745  lea     edi, [r14-1Bh]
0x140079749  mov     r13, rsi
0x14007974c  mov     r10, rsi
0x14007974f  mov     r8, rsi
0x140079752  mov     r11, rsi
0x140079755  jmp     loc_140079FEE
0x14007975a  movzx   r15d, word ptr [r12+28h]
0x140079760  movzx   ebx, r15w
0x140079764  mov     word ptr [rsp+2D8h+NewIrql], bx
0x14007976c  mov     [rsp+2D8h+var_218], bx
0x140079774  add     r15d, 7
0x140079778  and     r15d, 0FFFFFFF8h
0x14007977c  add     r15d, 10h
0x140079780  mov     [rsp+2D8h+var_1F8], r15d
0x140079788  mov     [rsp+2D8h+Irp], rsi; Irp
0x14007978d  mov     r9b, r13b; ChargeQuota
0x140079790  xor     r8d, r8d; SecondaryBuffer
0x140079793  mov     edx, [r12+4]; Length
0x140079798  mov     rcx, [r12+10h]; VirtualAddress
0x14007979d  call    cs:__imp_IoAllocateMdl
0x1400797a4  nop     dword ptr [rax+rax+00h]
0x1400797a9  mov     rdi, rax
0x1400797ac  mov     [rsp+2D8h+MemoryDescriptorList], rax
0x1400797b4  test    rax, rax
0x1400797b7  jnz     short loc_140079811
0x1400797b9  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x1400797bf  test    cl, cl
0x1400797c1  jns     short loc_1400797DD
0x1400797c3  lea     r9, aIpv4EchoReplyM; "IPv4 echo reply MDL (IPNG)"
0x1400797ca  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400797d1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400797d8  call    McTemplateK0z_EtwWriteTransfer
0x1400797dd  mov     ebx, 0C0000017h
0x1400797e2  mov     [rsp+2D8h+var_268], ebx
0x1400797e6  mov     r14d, 23h ; '#'
0x1400797ec  mov     [rsp+2D8h+var_264], r14d
0x1400797f1  mov     r15d, 0E0004183h
0x1400797f7  mov     [rsp+2D8h+var_260], r15d
0x1400797fc  lea     edi, [r14-1Bh]
0x140079800  mov     r13, rsi
0x140079803  mov     r10, rsi
0x140079806  mov     r8, rsi
0x140079809  mov     r11, rsi
0x14007980c  jmp     loc_140079FEE
0x140079811  mov     r8d, r13d; Operation
0x140079814  mov     dl, r13b; AccessMode
0x140079817  mov     rcx, rdi; MemoryDescriptorList
0x14007981a  call    cs:__imp_MmProbeAndLockPages
0x140079821  nop     dword ptr [rax+rax+00h]
0x140079826  mov     [rsp+2D8h+var_278], r13b
0x14007982b  call    NdisGetCurrentThreadCompartmentId
0x140079830  mov     dword ptr [rsp+2D8h+var_1E0+8], eax
0x140079837  lea     rdx, [rsp+2D8h+var_1E0]
0x14007983f  mov     rbx, qword ptr [rsp+2D8h+arg_8]
0x140079847  mov     rcx, rbx
0x14007984a  call    IppGetCompartment
0x14007984f  mov     r11, rax
0x140079852  mov     [rsp+2D8h+var_250], rax
0x14007985a  test    rax, rax
0x14007985d  jnz     short loc_140079870
0x14007985f  mov     r14d, esi
0x140079862  mov     r15d, 0E0004185h
0x140079868  mov     r13, rsi
0x14007986b  jmp     loc_140079FDE
0x140079870  mov     edx, 0E8h
0x140079875  mov     ecx, 40h ; '@'
0x14007987a  mov     r8d, 20653449h
0x140079880  call    cs:__imp_ExAllocatePool2
0x140079887  nop     dword ptr [rax+rax+00h]
0x14007988c  mov     r14, rax
0x14007988f  mov     [rsp+2D8h+SpinLock], rax
0x140079894  test    rax, rax
0x140079897  jnz     short loc_1400798E0
0x140079899  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007989f  test    al, al
0x1400798a1  jns     short loc_1400798BD
0x1400798a3  lea     r9, aIpv4EchoReques; "IPv4 echo request (IPNG)"
0x1400798aa  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400798b1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400798b8  call    McTemplateK0z_EtwWriteTransfer
0x1400798bd  mov     ebx, 0C000009Ah
0x1400798c2  mov     r14d, 23h ; '#'
0x1400798c8  mov     r15d, 0E0004186h
0x1400798ce  mov     r13, [rsp+2D8h+SpinLock]
0x1400798d3  mov     r11, [rsp+2D8h+var_250]
0x1400798db  jmp     loc_140079FE3
0x1400798e0  mov     [rax+8], r13
0x1400798e4  lea     rdx, [rax+20h]
0x1400798e8  xor     r9d, r9d
0x1400798eb  xor     r8d, r8d
0x1400798ee  xor     ecx, ecx
0x1400798f0  call    cs:__imp_RtlInitializeTimerWheelEntry
0x1400798f7  nop     dword ptr [rax+rax+00h]
0x1400798fc  lea     rax, [r14+10h]
0x140079900  mov     [rax+8], rax
0x140079904  mov     [rax], rax
0x140079907  mov     rcx, r14; SpinLock
0x14007990a  call    cs:__imp_KeInitializeSpinLock
0x140079911  nop     dword ptr [rax+rax+00h]
0x140079916  mov     r11, [rsp+2D8h+var_250]
0x14007991e  mov     [r14+38h], r11
0x140079922  mov     [r14+48h], rdi
0x140079926  mov     edi, 8
0x14007992b  cmp     [r12+35h], sil
  ... truncated ...
```
