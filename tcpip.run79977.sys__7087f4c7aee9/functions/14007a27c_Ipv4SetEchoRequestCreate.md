# Ipv4SetEchoRequestCreate

- ea: `0x14007a27c`
- end: `0x14007b04d`
- name: `Ipv4SetEchoRequestCreate`
- size: `3537`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007a0b0`

## callees

- `0x140017140`
- `0x140027160`
- `0x140034190`
- `0x140054138`
- `0x1400650a0`
- `0x140079e3c`
- `0x140079f64`
- `0x14007a208`
- `0x14007a27c`
- `0x14007bd68`
- `0x14007bff4`
- `0x14009cfd0`
- `0x14009e604`
- `0x1400a69c0`
- `0x1400a9334`
- `0x1401bf780`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14007af78`
- `ntoskrnl!MmUnlockPages` at `0x14007afcc`
- `ntoskrnl!MmUnlockPages` at `0x14007affe`
- `ntoskrnl!MmUnlockPages` at `0x14007af78`
- `ntoskrnl!MmUnlockPages` at `0x14007afcc`
- `ntoskrnl!MmUnlockPages` at `0x14007affe`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a447`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a576`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a6ca`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a447`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a576`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007a6ca`
- `ntoskrnl!IoAllocateMdl` at `0x14007a3ca`
- `ntoskrnl!IoAllocateMdl` at `0x14007a4f9`
- `ntoskrnl!IoAllocateMdl` at `0x14007a64d`
- `ntoskrnl!IoAllocateMdl` at `0x14007a3ca`
- `ntoskrnl!IoAllocateMdl` at `0x14007a4f9`
- `ntoskrnl!IoAllocateMdl` at `0x14007a64d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a483`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a5b2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a483`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a5b2`
- `ntoskrnl!IoFreeMdl` at `0x14007af87`
- `ntoskrnl!IoFreeMdl` at `0x14007afdb`
- `ntoskrnl!IoFreeMdl` at `0x14007b00d`
- `ntoskrnl!IoFreeMdl` at `0x14007af87`
- `ntoskrnl!IoFreeMdl` at `0x14007afdb`
- `ntoskrnl!IoFreeMdl` at `0x14007b00d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ad10`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ad2b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ad10`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14007ad2b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007ad73`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007ad84`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007ad73`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007ad84`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007a353`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007a353`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ac80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ad9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ac80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007ad9f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007a7ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007a7ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007ac3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007ac3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b02b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b02b`
- `ntoskrnl!ExAllocatePool2` at `0x14007a730`
- `ntoskrnl!ExAllocatePool2` at `0x14007aa3e`
- `ntoskrnl!ExAllocatePool2` at `0x14007a730`
- `ntoskrnl!ExAllocatePool2` at `0x14007aa3e`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007af53`
- `NETIO!NetioDereferenceNetBufferList` at `0x14007af53`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14007a7a0`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14007a7a0`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14007a932`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14007a932`
- `HAL!KeQueryPerformanceCounter` at `0x14007acdc`
- `HAL!KeQueryPerformanceCounter` at `0x14007acdc`

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
          &TCPIP_MEMORY_FAILURES,
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
          &TCPIP_MEMORY_FAILURES,
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
        &TCPIP_MEMORY_FAILURES,
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
        &TCPIP_MEMORY_FAILURES,
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
        &TCPIP_MEMORY_FAILURES,
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
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 11) & 4) != 0 || byte_140225C30 )
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
0x14007a27c  mov     r11, rsp
0x14007a27f  mov     [r11+10h], rdx
0x14007a283  push    rbx
0x14007a284  push    rsi
0x14007a285  push    rdi
0x14007a286  push    r12
0x14007a288  push    r13
0x14007a28a  push    r14
0x14007a28c  push    r15
0x14007a28e  sub     rsp, 2A0h
0x14007a295  mov     rbx, rcx
0x14007a298  xor     esi, esi
0x14007a29a  mov     r13d, esi
0x14007a29d  mov     [rsp+2D8h+var_277], sil
0x14007a2a2  mov     [rsp+2D8h+var_276], sil
0x14007a2a7  mov     [rsp+2D8h+var_278], sil
0x14007a2ac  mov     [r11-208h], rsi
0x14007a2b3  mov     [r11-200h], rsi
0x14007a2ba  mov     [r11-210h], rsi
0x14007a2c1  mov     eax, esi
0x14007a2c3  mov     [rsp+2D8h+P], rax
0x14007a2cb  mov     [rsp+2D8h+var_258], rax
0x14007a2d3  mov     [r11-1F0h], rsi
0x14007a2da  xorps   xmm0, xmm0
0x14007a2dd  movups  [rsp+2D8h+var_1E0], xmm0
0x14007a2e5  xor     edx, edx; Val
0x14007a2e7  mov     r8d, 0D8h; Size
0x14007a2ed  lea     rcx, [r11-118h]; void *
0x14007a2f4  call    memset
0x14007a2f9  mov     [rsp+2D8h+var_248], rsi
0x14007a301  xor     edx, edx; Val
0x14007a303  mov     r8d, 0A0h; Size
0x14007a309  lea     rcx, [rsp+2D8h+var_1B8]; void *
0x14007a311  call    memset
0x14007a316  mov     r12, [rbx+20h]
0x14007a31a  mov     [rsp+2D8h+SpinLock], r12
0x14007a31f  test    r12, r12
0x14007a322  jnz     short loc_14007A332
0x14007a324  mov     r14d, esi
0x14007a327  mov     r15d, 0E000417Bh
0x14007a32d  jmp     loc_14007AE8B
0x14007a332  cmp     [r12+1Ch], esi
0x14007a337  jnz     short loc_14007A347
0x14007a339  mov     r14d, esi
0x14007a33c  mov     r15d, 0E000417Ch
0x14007a342  jmp     loc_14007AE8B
0x14007a347  mov     rbx, [rbx+10h]
0x14007a34b  mov     [rsp+2D8h+var_1E8], rbx
0x14007a353  call    cs:__imp_PsGetCurrentProcessId
0x14007a35a  nop     dword ptr [rax+rax+00h]
0x14007a35f  cmp     [rbx+8], eax
0x14007a362  jz      short loc_14007A372
0x14007a364  mov     r14d, esi
0x14007a367  mov     r15d, 0E000417Dh
0x14007a36d  jmp     loc_14007AE8B
0x14007a372  cmp     [r12+10h], rsi
0x14007a377  jz      loc_14007AE7F
0x14007a37d  mov     [rsp+2D8h+var_240], rsi
0x14007a385  mov     [rsp+2D8h+Src], rsi
0x14007a38d  mov     r15d, esi
0x14007a390  mov     word ptr [rsp+2D8h+NewIrql], si
0x14007a398  mov     eax, [r12+4]
0x14007a39d  cmp     [r12+18h], eax
0x14007a3a2  ja      loc_14007AE7F
0x14007a3a8  mov     edx, [r12]; Length
0x14007a3ac  mov     r13d, 1
0x14007a3b2  test    edx, edx
0x14007a3b4  jz      loc_14007A4D8
0x14007a3ba  mov     [rsp+2D8h+Irp], rsi; Irp
0x14007a3bf  mov     r9b, r13b; ChargeQuota
0x14007a3c2  xor     r8d, r8d; SecondaryBuffer
0x14007a3c5  mov     rcx, [r12+8]; VirtualAddress
0x14007a3ca  call    cs:__imp_IoAllocateMdl
0x14007a3d1  nop     dword ptr [rax+rax+00h]
0x14007a3d6  mov     rbx, rax
0x14007a3d9  mov     [rsp+2D8h+Mdl], rax
0x14007a3e1  test    rax, rax
0x14007a3e4  jnz     short loc_14007A43E
0x14007a3e6  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a3ec  test    cl, cl
0x14007a3ee  jns     short loc_14007A40A
0x14007a3f0  lea     r9, aIpv4EchoDataMd; "IPv4 echo data MDL (IPNG)"
0x14007a3f7  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a3fe  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a405  call    McTemplateK0z_EtwWriteTransfer
0x14007a40a  mov     ebx, 0C0000017h
0x14007a40f  mov     [rsp+2D8h+var_268], ebx
0x14007a413  mov     r14d, 23h ; '#'
0x14007a419  mov     [rsp+2D8h+var_264], r14d
0x14007a41e  mov     r15d, 0E000417Fh
0x14007a424  mov     [rsp+2D8h+var_260], r15d
0x14007a429  lea     edi, [r14-1Bh]
0x14007a42d  mov     r13, rsi
0x14007a430  mov     r10, rsi
0x14007a433  mov     r8, rsi
0x14007a436  mov     r11, rsi
0x14007a439  jmp     loc_14007AE9E
0x14007a43e  xor     r8d, r8d; Operation
0x14007a441  mov     dl, r13b; AccessMode
0x14007a444  mov     rcx, rbx; MemoryDescriptorList
0x14007a447  call    cs:__imp_MmProbeAndLockPages
0x14007a44e  nop     dword ptr [rax+rax+00h]
0x14007a453  mov     [rsp+2D8h+var_277], r13b
0x14007a458  test    byte ptr [rbx+0Ah], 5
0x14007a45c  jz      short loc_14007A46C
0x14007a45e  mov     rcx, [rbx+18h]
0x14007a462  mov     [rsp+2D8h+var_240], rcx
0x14007a46a  jmp     short loc_14007A49A
0x14007a46c  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x14007a474  mov     dword ptr [rsp+2D8h+Irp], esi; BugCheckOnFailure
0x14007a478  xor     r9d, r9d; RequestedAddress
0x14007a47b  mov     r8d, r13d; CacheType
0x14007a47e  xor     edx, edx; AccessMode
0x14007a480  mov     rcx, rbx; MemoryDescriptorList
0x14007a483  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007a48a  nop     dword ptr [rax+rax+00h]
0x14007a48f  mov     rcx, rax
0x14007a492  mov     [rsp+2D8h+var_240], rax
0x14007a49a  mov     [rsp+2D8h+var_1D0], rcx
0x14007a4a2  test    rcx, rcx
0x14007a4a5  jnz     short loc_14007A4D8
0x14007a4a7  mov     ebx, 0C000009Ah
0x14007a4ac  mov     [rsp+2D8h+var_268], ebx
0x14007a4b0  lea     r14d, [rcx+23h]
0x14007a4b4  mov     [rsp+2D8h+var_264], r14d
0x14007a4b9  mov     r15d, 0E0004180h
0x14007a4bf  mov     [rsp+2D8h+var_260], r15d
0x14007a4c4  lea     edi, [rcx+8]
0x14007a4c7  mov     r13, rsi
0x14007a4ca  mov     r10, rsi
0x14007a4cd  mov     r8, rsi
0x14007a4d0  mov     r11, rsi
0x14007a4d3  jmp     loc_14007AE9E
0x14007a4d8  movzx   eax, word ptr [r12+28h]
0x14007a4de  test    ax, ax
0x14007a4e1  jz      loc_14007A638
0x14007a4e7  mov     edx, eax; Length
0x14007a4e9  mov     [rsp+2D8h+Irp], rsi; Irp
0x14007a4ee  mov     r9b, r13b; ChargeQuota
0x14007a4f1  xor     r8d, r8d; SecondaryBuffer
0x14007a4f4  mov     rcx, [r12+20h]; VirtualAddress
0x14007a4f9  call    cs:__imp_IoAllocateMdl
0x14007a500  nop     dword ptr [rax+rax+00h]
0x14007a505  mov     rbx, rax
0x14007a508  mov     [rsp+2D8h+var_200], rax
0x14007a510  test    rax, rax
0x14007a513  jnz     short loc_14007A56D
0x14007a515  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a51b  test    cl, cl
0x14007a51d  jns     short loc_14007A539
0x14007a51f  lea     r9, aIpv4EchoOption; "IPv4 echo options MDL (IPNG)"
0x14007a526  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a52d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a534  call    McTemplateK0z_EtwWriteTransfer
0x14007a539  mov     ebx, 0C0000017h
0x14007a53e  mov     [rsp+2D8h+var_268], ebx
0x14007a542  mov     r14d, 23h ; '#'
0x14007a548  mov     [rsp+2D8h+var_264], r14d
0x14007a54d  mov     r15d, 0E0004181h
0x14007a553  mov     [rsp+2D8h+var_260], r15d
0x14007a558  lea     edi, [r14-1Bh]
0x14007a55c  mov     r13, rsi
0x14007a55f  mov     r10, rsi
0x14007a562  mov     r8, rsi
0x14007a565  mov     r11, rsi
0x14007a568  jmp     loc_14007AE9E
0x14007a56d  xor     r8d, r8d; Operation
0x14007a570  mov     dl, r13b; AccessMode
0x14007a573  mov     rcx, rbx; MemoryDescriptorList
0x14007a576  call    cs:__imp_MmProbeAndLockPages
0x14007a57d  nop     dword ptr [rax+rax+00h]
0x14007a582  mov     [rsp+2D8h+var_276], r13b
0x14007a587  test    byte ptr [rbx+0Ah], 5
0x14007a58b  jz      short loc_14007A59B
0x14007a58d  mov     rbx, [rbx+18h]
0x14007a591  mov     [rsp+2D8h+Src], rbx
0x14007a599  jmp     short loc_14007A5C9
0x14007a59b  mov     [rsp+2D8h+Priority], 40000010h; Priority
0x14007a5a3  mov     dword ptr [rsp+2D8h+Irp], esi; BugCheckOnFailure
0x14007a5a7  xor     r9d, r9d; RequestedAddress
0x14007a5aa  mov     r8d, r13d; CacheType
0x14007a5ad  xor     edx, edx; AccessMode
0x14007a5af  mov     rcx, rbx; MemoryDescriptorList
0x14007a5b2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007a5b9  nop     dword ptr [rax+rax+00h]
0x14007a5be  mov     rbx, rax
0x14007a5c1  mov     [rsp+2D8h+Src], rax
0x14007a5c9  mov     [rsp+2D8h+var_1C8], rbx
0x14007a5d1  test    rbx, rbx
0x14007a5d4  jnz     short loc_14007A60A
0x14007a5d6  mov     ebx, 0C000009Ah
0x14007a5db  mov     [rsp+2D8h+var_268], ebx
0x14007a5df  mov     r14d, 23h ; '#'
0x14007a5e5  mov     [rsp+2D8h+var_264], r14d
0x14007a5ea  mov     r15d, 0E0004182h
0x14007a5f0  mov     [rsp+2D8h+var_260], r15d
0x14007a5f5  lea     edi, [r14-1Bh]
0x14007a5f9  mov     r13, rsi
0x14007a5fc  mov     r10, rsi
0x14007a5ff  mov     r8, rsi
0x14007a602  mov     r11, rsi
0x14007a605  jmp     loc_14007AE9E
0x14007a60a  movzx   r15d, word ptr [r12+28h]
0x14007a610  movzx   ebx, r15w
0x14007a614  mov     word ptr [rsp+2D8h+NewIrql], bx
0x14007a61c  mov     [rsp+2D8h+var_218], bx
0x14007a624  add     r15d, 7
0x14007a628  and     r15d, 0FFFFFFF8h
0x14007a62c  add     r15d, 10h
0x14007a630  mov     [rsp+2D8h+var_1F8], r15d
0x14007a638  mov     [rsp+2D8h+Irp], rsi; Irp
0x14007a63d  mov     r9b, r13b; ChargeQuota
0x14007a640  xor     r8d, r8d; SecondaryBuffer
0x14007a643  mov     edx, [r12+4]; Length
0x14007a648  mov     rcx, [r12+10h]; VirtualAddress
0x14007a64d  call    cs:__imp_IoAllocateMdl
0x14007a654  nop     dword ptr [rax+rax+00h]
0x14007a659  mov     rdi, rax
0x14007a65c  mov     [rsp+2D8h+MemoryDescriptorList], rax
0x14007a664  test    rax, rax
0x14007a667  jnz     short loc_14007A6C1
0x14007a669  mov     cl, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a66f  test    cl, cl
0x14007a671  jns     short loc_14007A68D
0x14007a673  lea     r9, aIpv4EchoReplyM; "IPv4 echo reply MDL (IPNG)"
0x14007a67a  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a681  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a688  call    McTemplateK0z_EtwWriteTransfer
0x14007a68d  mov     ebx, 0C0000017h
0x14007a692  mov     [rsp+2D8h+var_268], ebx
0x14007a696  mov     r14d, 23h ; '#'
0x14007a69c  mov     [rsp+2D8h+var_264], r14d
0x14007a6a1  mov     r15d, 0E0004183h
0x14007a6a7  mov     [rsp+2D8h+var_260], r15d
0x14007a6ac  lea     edi, [r14-1Bh]
0x14007a6b0  mov     r13, rsi
0x14007a6b3  mov     r10, rsi
0x14007a6b6  mov     r8, rsi
0x14007a6b9  mov     r11, rsi
0x14007a6bc  jmp     loc_14007AE9E
0x14007a6c1  mov     r8d, r13d; Operation
0x14007a6c4  mov     dl, r13b; AccessMode
0x14007a6c7  mov     rcx, rdi; MemoryDescriptorList
0x14007a6ca  call    cs:__imp_MmProbeAndLockPages
0x14007a6d1  nop     dword ptr [rax+rax+00h]
0x14007a6d6  mov     [rsp+2D8h+var_278], r13b
0x14007a6db  call    NdisGetCurrentThreadCompartmentId
0x14007a6e0  mov     dword ptr [rsp+2D8h+var_1E0+8], eax
0x14007a6e7  lea     rdx, [rsp+2D8h+var_1E0]
0x14007a6ef  mov     rbx, qword ptr [rsp+2D8h+arg_8]
0x14007a6f7  mov     rcx, rbx
0x14007a6fa  call    IppGetCompartment
0x14007a6ff  mov     r11, rax
0x14007a702  mov     [rsp+2D8h+var_250], rax
0x14007a70a  test    rax, rax
0x14007a70d  jnz     short loc_14007A720
0x14007a70f  mov     r14d, esi
0x14007a712  mov     r15d, 0E0004185h
0x14007a718  mov     r13, rsi
0x14007a71b  jmp     loc_14007AE8E
0x14007a720  mov     edx, 0E8h
0x14007a725  mov     ecx, 40h ; '@'
0x14007a72a  mov     r8d, 20653449h
0x14007a730  call    cs:__imp_ExAllocatePool2
0x14007a737  nop     dword ptr [rax+rax+00h]
0x14007a73c  mov     r14, rax
0x14007a73f  mov     [rsp+2D8h+SpinLock], rax
0x14007a744  test    rax, rax
0x14007a747  jnz     short loc_14007A790
0x14007a749  mov     al, byte ptr cs:WPP_MAIN_CB.Reserved+3
0x14007a74f  test    al, al
0x14007a751  jns     short loc_14007A76D
0x14007a753  lea     r9, aIpv4EchoReques; "IPv4 echo request (IPNG)"
0x14007a75a  lea     rdx, TCPIP_MEMORY_FAILURES
0x14007a761  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14007a768  call    McTemplateK0z_EtwWriteTransfer
0x14007a76d  mov     ebx, 0C000009Ah
0x14007a772  mov     r14d, 23h ; '#'
0x14007a778  mov     r15d, 0E0004186h
0x14007a77e  mov     r13, [rsp+2D8h+SpinLock]
0x14007a783  mov     r11, [rsp+2D8h+var_250]
0x14007a78b  jmp     loc_14007AE93
0x14007a790  mov     [rax+8], r13
0x14007a794  lea     rdx, [rax+20h]
0x14007a798  xor     r9d, r9d
0x14007a79b  xor     r8d, r8d
0x14007a79e  xor     ecx, ecx
0x14007a7a0  call    cs:__imp_RtlInitializeTimerWheelEntry
0x14007a7a7  nop     dword ptr [rax+rax+00h]
0x14007a7ac  lea     rax, [r14+10h]
0x14007a7b0  mov     [rax+8], rax
0x14007a7b4  mov     [rax], rax
0x14007a7b7  mov     rcx, r14; SpinLock
0x14007a7ba  call    cs:__imp_KeInitializeSpinLock
0x14007a7c1  nop     dword ptr [rax+rax+00h]
0x14007a7c6  mov     r11, [rsp+2D8h+var_250]
0x14007a7ce  mov     [r14+38h], r11
0x14007a7d2  mov     [r14+48h], rdi
0x14007a7d6  mov     edi, 8
0x14007a7db  cmp     [r12+35h], sil
  ... truncated ...
```
