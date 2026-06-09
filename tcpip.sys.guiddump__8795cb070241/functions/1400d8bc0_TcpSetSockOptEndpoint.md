# TcpSetSockOptEndpoint

- ea: `0x1400d8bc0`
- end: `0x1400d9a8b`
- name: `TcpSetSockOptEndpoint`
- size: `3787`
- prototype: `__int64 __fastcall(unsigned __int64 SpinLock, __int64, __int64, int, unsigned int, _BYTE *, unsigned __int64, _QWORD *, unsigned __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d86b0`

## callees

- `0x140012f00`
- `0x14002f9e0`
- `0x140047800`
- `0x140048790`
- `0x140059590`
- `0x14007cf70`
- `0x1400b1540`
- `0x1400d6500`
- `0x1400d7980`
- `0x1400d7f90`
- `0x1400d8bc0`
- `0x1400d9aa0`
- `0x1400e8424`
- `0x1400e8ab4`
- `0x14011b110`
- `0x14011cbf4`
- `0x14011faf0`
- `0x14012a5bc`
- `0x14012df90`
- `0x14012f36c`
- `0x140131174`
- `0x140154e94`
- `0x1401615fc`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400d90c6`
- `ntoskrnl!KfRaiseIrql` at `0x1400d90c6`
- `ntoskrnl!KeLowerIrql` at `0x1400d9128`
- `ntoskrnl!KeLowerIrql` at `0x1400d9128`
- `ntoskrnl!IoFileObjectType` at `0x1401d19f6`
- `ntoskrnl!KeBugCheck` at `0x1400d90a0`
- `ntoskrnl!KeBugCheck` at `0x1400d90a0`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x1400d93d4`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x1400d95ba`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x1400d93d4`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x1400d95ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400d93e3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400d95c9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400d93e3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400d95c9`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400d9401`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400d95e7`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400d9401`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400d95e7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400d8fc7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400d8fc7`
- `ntoskrnl!RtlCompareMemory` at `0x1400d9a3d`
- `ntoskrnl!RtlCompareMemory` at `0x1400d9a3d`
- `ntoskrnl!PsGetProcessId` at `0x1400d91f2`
- `ntoskrnl!PsGetProcessId` at `0x1400d91f2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d1a1d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d1a1d`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d1a9b`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d1a9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8cd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8f84`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9046`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9151`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d96d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9709`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d976f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d97f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9879`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9962`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d99c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d1a85`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8cd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d8f84`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9046`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9151`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d96d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9709`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d976f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d97f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9879`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d9962`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d99c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d1a85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d8c4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d916e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d9699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d1a53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d8c4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d916e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d9699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d1a53`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d960c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d960c`
- `ntoskrnl!ExAllocatePool2` at `0x1400d8f31`
- `ntoskrnl!ExAllocatePool2` at `0x1400d906a`
- `ntoskrnl!ExAllocatePool2` at `0x1400d8f31`
- `ntoskrnl!ExAllocatePool2` at `0x1400d906a`
- `NETIO!NetioInsertWorkQueue` at `0x1400d96f1`
- `NETIO!NetioInsertWorkQueue` at `0x1400d96f1`
- `NETIO!NetioNcmNotificationChannelContextRequest` at `0x1400d920d`
- `NETIO!NetioNcmNotificationChannelContextRequest` at `0x1400d920d`
- `NETIO!NetioNrtAssociateContext` at `0x1401d1a71`
- `NETIO!NetioNrtAssociateContext` at `0x1401d1a71`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401d1a3c`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401d1a3c`

## pseudocode

```c
__int64 __fastcall TcpSetSockOptEndpoint(
        unsigned __int64 SpinLock,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        _BYTE *a6,
        unsigned __int64 a7,
        _QWORD *a8,
        unsigned __int64 a9,
        _QWORD *a10)
{
  KIRQL v12; // r13
  int v13; // edi
  KIRQL v14; // dl
  int v16; // ecx
  int v17; // ecx
  __int16 v18; // ax
  KSPIN_LOCK v19; // r15
  PKSPIN_LOCK v20; // r12
  int v21; // ecx
  PKSPIN_LOCK v22; // rax
  __int64 (__fastcall *v23)(__int128 *); // rax
  int v24; // eax
  __int64 Pool2; // rax
  _QWORD *v26; // rdi
  __int64 v27; // r12
  int *v28; // rax
  int *v29; // rcx
  __int64 v30; // rax
  _QWORD *v31; // r13
  __int64 v32; // r8
  KIRQL v33; // di
  __int64 v34; // r8
  int v35; // edi
  struct _KPROCESS *v36; // rcx
  int v37; // ecx
  volatile signed __int32 *v38; // r9
  signed __int32 v39; // r10d
  volatile unsigned __int32 v40; // r11d
  unsigned __int32 v41; // r10d
  volatile unsigned __int32 v42; // edi
  volatile signed __int32 *v43; // rdi
  KSPIN_LOCK v44; // rdx
  KSPIN_LOCK v45; // rcx
  __int64 v46; // rax
  __int64 (__fastcall *v47)(__int64); // rax
  int v48; // eax
  _QWORD *v49; // rdx
  unsigned int v50; // r15d
  __int64 v51; // rsi
  __int64 v52; // r14
  volatile signed __int32 *v53; // r8
  signed __int32 v54; // r9d
  volatile unsigned __int32 v55; // r10d
  unsigned __int32 v56; // r9d
  volatile unsigned __int32 v57; // r11d
  volatile signed __int32 *v58; // rbx
  signed __int32 v59; // r10d
  signed __int32 v60; // r9d
  KIRQL v61; // al
  __int64 v62; // r12
  KSPIN_LOCK v63; // rcx
  int v64; // eax
  __int64 v65; // r14
  KSPIN_LOCK v66; // r8
  char v67; // cl
  int v68; // eax
  KSPIN_LOCK v69; // rcx
  __int64 v70; // r15
  int v71; // edx
  void *v72; // rcx
  _QWORD *v73; // r14
  KIRQL v74; // bl
  KIRQL v75; // [rsp+40h] [rbp-C0h]
  PVOID Object; // [rsp+50h] [rbp-B0h] BYREF
  int v77; // [rsp+58h] [rbp-A8h]
  _DWORD *v78; // [rsp+60h] [rbp-A0h]
  void *Source2; // [rsp+68h] [rbp-98h]
  _QWORD *v80; // [rsp+70h] [rbp-90h]
  __int64 v81; // [rsp+78h] [rbp-88h]
  __int64 v82; // [rsp+80h] [rbp-80h]
  _QWORD v83[3]; // [rsp+90h] [rbp-70h] BYREF
  int v84; // [rsp+A8h] [rbp-58h]
  int v85; // [rsp+ACh] [rbp-54h]
  __int64 v86; // [rsp+B0h] [rbp-50h]
  __int64 v87; // [rsp+B8h] [rbp-48h]
  PVOID v88; // [rsp+C0h] [rbp-40h]
  int v89; // [rsp+C8h] [rbp-38h]
  unsigned int v90; // [rsp+CCh] [rbp-34h]
  void *v91; // [rsp+D0h] [rbp-30h]
  int v92; // [rsp+D8h] [rbp-28h]
  int v93; // [rsp+DCh] [rbp-24h]
  _QWORD *v94; // [rsp+E0h] [rbp-20h]
  unsigned int v95; // [rsp+E8h] [rbp-18h]
  int v96; // [rsp+ECh] [rbp-14h]
  _QWORD *v97; // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v98)(PVOID); // [rsp+F8h] [rbp-8h]
  __int64 v99; // [rsp+100h] [rbp+0h]
  KSPIN_LOCK v100; // [rsp+108h] [rbp+8h]
  __int128 v101; // [rsp+110h] [rbp+10h]
  __int64 v102; // [rsp+120h] [rbp+20h]
  __int128 v103; // [rsp+130h] [rbp+30h] BYREF

  Source2 = a6;
  v80 = a10;
  v82 = a3;
  v81 = a2;
  if ( dword_1402241D4 )
  {
    v103 = 0;
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
    {
      *(_QWORD *)&v103 = SpinLock;
      v37 = a7;
      if ( !a6 )
        v37 = 0;
      McTemplateK0pqqqbr3_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_SETSOCKOPT,
        (unsigned int)&v103,
        SpinLock,
        a4,
        a5,
        v37,
        (__int64)a6);
    }
  }
  v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
  v12 = v75;
  if ( a4 == 6 )
  {
    v13 = TcpSetTcpLevelOption((int)SpinLock + 168, a5, (_DWORD)a6, a7, 0);
    if ( v13 < 0 || a5 != 18 )
      goto LABEL_12;
    if ( a7 )
    {
      *(_DWORD *)(SpinLock + 16) = *(_DWORD *)(SpinLock + 16) & 0xFFFFFFBF | (*a6 != 0 ? 0x40 : 0);
      goto LABEL_11;
    }
    goto LABEL_103;
  }
  if ( a4 == 0xFFFF )
  {
    if ( a5 == 12293 )
    {
      if ( a7 >= 4 )
      {
        if ( (*(_DWORD *)(SpinLock + 16) & 1) == 0 )
        {
          *(_BYTE *)(SpinLock + 203) = *(_BYTE *)(SpinLock + 203) & 0xBF | (*(_DWORD *)a6 != 0 ? 0x40 : 0);
          goto LABEL_11;
        }
        goto LABEL_144;
      }
    }
    else
    {
      if ( a5 != 12295 )
      {
        v13 = TcpSetSoLevelOption((int)SpinLock + 168, a5, (_DWORD)a6, a7, 0);
        goto LABEL_12;
      }
      if ( a7 )
      {
        if ( (*(_DWORD *)(SpinLock + 16) & 1) == 0 )
        {
          if ( (*(_BYTE *)(SpinLock + 204) & 1) == 0
            && (*(_BYTE *)(SpinLock + 202) & 0x40) == 0
            && (*(_BYTE *)(SpinLock + 205) & 2) == 0
            && !PortTrackerEnabled
            && *(_WORD *)(*(_QWORD *)InetGetCompartmentContext(TcpCompartmentSet, **(unsigned int **)(SpinLock + 88))
                        + 148LL) )
          {
            *(_BYTE *)(SpinLock + 205) = *(_BYTE *)(SpinLock + 205) & 0xFE | (*a6 != 0);
          }
          goto LABEL_11;
        }
        goto LABEL_144;
      }
    }
LABEL_103:
    v13 = -1073741306;
    goto LABEL_12;
  }
  if ( a4 != 65532 )
  {
    if ( a4 == 41 && a5 == 27 )
    {
      if ( a7 >= 4 )
      {
        if ( (*(_DWORD *)(SpinLock + 16) & 1) == 0 )
        {
          *(_BYTE *)(SpinLock + 202) = *(_BYTE *)(SpinLock + 202) & 0xFD | (*(_DWORD *)a6 != 0 ? 2 : 0);
LABEL_11:
          v13 = 0;
LABEL_12:
          v14 = v12;
LABEL_13:
          KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v14);
          return (unsigned int)v13;
        }
LABEL_144:
        v13 = -1073741256;
        goto LABEL_12;
      }
      goto LABEL_103;
    }
    goto LABEL_34;
  }
  if ( a5 == -1744830460 || a5 + 1744830448 <= 1 )
  {
LABEL_82:
    v13 = TcpSetSioLevelOption((int)SpinLock + 168, a5, (_DWORD)a6, a7, (__int64)a8, a9, 0);
    if ( v13 >= 0 && a5 == -1744830446 && (*(_BYTE *)(SpinLock + 204) & 4) != 0 )
    {
      v36 = *(struct _KPROCESS **)(SpinLock + 40);
      DWORD2(v103) = 0;
      *(_QWORD *)&v103 = 0;
      LODWORD(v103) = (unsigned int)PsGetProcessId(v36);
      v13 = NetioNcmNotificationChannelContextRequest(&v103, 0, 2);
      if ( v13 < 0 )
        *(_BYTE *)(SpinLock + 204) &= ~4u;
    }
    goto LABEL_12;
  }
  switch ( a5 )
  {
    case 0x98000012:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
      v35 = (int)TcpEndpointSoAccessCheck(*(PEPROCESS *)(SpinLock + 40)) >> 31;
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
      v13 = v35 & 0xC0000022;
      if ( v13 < 0 )
        goto LABEL_12;
      goto LABEL_82;
    case 0x9800012C:
      goto LABEL_82;
    case 0x98000014:
      v13 = -1073741637;
      goto LABEL_12;
  }
  if ( a5 + 1744830442 <= 2 || a5 == -1744830234 )
    goto LABEL_82;
  switch ( a5 )
  {
    case 0x98000013:
      LOBYTE(v70) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
      if ( Source2 && a7 >= 0x18 )
      {
        if ( RtlCompareMemory(&ASSOCIATE_NAMERES_CONTEXT, Source2, 0x10u) == 16 )
        {
          v72 = (void *)*((_QWORD *)Source2 + 2);
          Object = 0;
          v13 = ObReferenceObjectByHandle(v72, 0, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
          if ( v13 >= 0 )
          {
            v73 = Object;
            if ( (unsigned __int8)NetioNrtIsTrackerDevice(*((_QWORD *)Object + 1)) )
            {
              v70 = v73[3];
              v74 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
              v13 = NetioNrtAssociateContext(SpinLock, 0, v70, SpinLock + 288);
              KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
            }
            else
            {
              v13 = -1073741816;
            }
            ObfDereferenceObject(v73);
          }
        }
        else
        {
          v13 = -1073741637;
        }
      }
      else
      {
        v13 = -1073741306;
      }
      if ( dword_1402241D4 && (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
      {
        v103 = SpinLock;
        McTemplateK0pqpq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          v71,
          (unsigned int)&v103,
          SpinLock,
          0,
          v70,
          v13);
      }
      return (unsigned int)v13;
    case 0x8800000B:
    case 0x8800001A:
      if ( !*(_QWORD *)(SpinLock + 80) )
      {
        v13 = -1073741808;
        goto LABEL_12;
      }
      v62 = _InterlockedIncrement64((volatile signed __int64 *)(SpinLock + 8));
      if ( v62 > 1 )
      {
        if ( EndpointReferenceHistory )
          RhAppendHistory(EndpointReferenceHistory, (unsigned int)v62);
        KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
        v63 = *(_QWORD *)(SpinLock + 80);
        v64 = a5 == -2013265909 ? QimInspectSetQoS(v63, a6, a7) : QimInspectAssociateQoS(v63, a6, a7);
        v13 = v64;
        v65 = _InterlockedDecrement64((volatile signed __int64 *)(SpinLock + 8));
        if ( v65 >= 0 )
        {
          if ( EndpointReferenceHistory )
            RhAppendHistory(EndpointReferenceHistory, (unsigned int)v65);
          if ( !v65 )
            TcpCleanupEndpoint(SpinLock);
          return (unsigned int)v13;
        }
      }
LABEL_73:
      KeBugCheck(0x1Cu);
    case 0x98000022:
      v13 = InetInspectFirewallSystemPort(*(_QWORD *)(SpinLock + 80), a6, a7);
      goto LABEL_12;
  }
  if ( a5 + 1744830264 <= 0x1F && (v16 = -2143289315, _bittest(&v16, a5 + 1744830264)) || a5 == -671088439 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
    return (unsigned int)InetInspectSocketOption(SpinLock, *(_QWORD *)(SpinLock + 80), a5, a6, a7, a8, a9, a10);
  }
  if ( a5 == 1476395213 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
    v69 = *(_QWORD *)(SpinLock + 80);
    if ( v69 && a9 >= 8 && a8 )
    {
      v13 = 0;
      *a8 = WfpAleQueryOrInsertEndpointHandle(v69);
      if ( a10 )
        *a10 = 8;
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)v13;
  }
  if ( a5 + 1744830364 <= 2 )
  {
    Pool2 = ExAllocatePool2(64, 80, 1464165204);
    v26 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
      v13 = -1073741801;
      goto LABEL_12;
    }
    *(_QWORD *)(Pool2 + 8) = SpinLock;
    v27 = _InterlockedIncrement64((volatile signed __int64 *)(SpinLock + 8));
    if ( v27 > 1 )
    {
      if ( EndpointReferenceHistory )
        RhAppendHistory(EndpointReferenceHistory, (unsigned int)v27);
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
      v26[2] = v81;
      v26[3] = v82;
      v26[6] = a7;
      v26[8] = a9;
      *((_DWORD *)v26 + 8) = a5;
      v26[5] = a6;
      v26[7] = a8;
      if ( KeGetCurrentIrql() )
      {
        NetioInsertWorkQueue(TcpPortReservationWorkQueue, v26);
      }
      else
      {
        *v26 = 0;
        TcpPortReservationWorkQueueRoutine(v26);
      }
      return 259;
    }
    goto LABEL_73;
  }
  switch ( a5 )
  {
    case 0x580000D2u:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
      if ( a9 )
      {
        v13 = 0;
        *(_BYTE *)a8 = (*((__int64 (**)(void))TcpRssControl + 4))();
        if ( a10 )
          *v80 = 1;
      }
      else
      {
        return (unsigned int)-1073741306;
      }
      return (unsigned int)v13;
    case 0x980000E8:
      v68 = TcpHandleSockOptSioWakeEndpoint((PKSPIN_LOCK)SpinLock);
      v14 = v75;
      v13 = v68;
      goto LABEL_13;
    case 0x980000E9:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
      v66 = *(_QWORD *)(SpinLock + 32);
      v67 = *(_WORD *)(v66 + 24) == 23 && (*(_BYTE *)(SpinLock + 202) & 2) == 0;
      return (unsigned int)InetHandleSockOptSioWakeIf(
                             (_DWORD)a6,
                             a7,
                             v66,
                             *(_QWORD *)(SpinLock + 104),
                             *(_QWORD *)(SpinLock + 88),
                             v67,
                             (__int64)TcpWakePortPool);
  }
LABEL_34:
  v17 = *(_DWORD *)(SpinLock + 16);
  Object = 0;
  if ( (v17 & 1) != 0 )
  {
    v18 = *(_WORD *)(SpinLock + 112);
  }
  else if ( *(_WORD *)(*(_QWORD *)(SpinLock + 32) + 24LL) != 23 || (*(_BYTE *)(SpinLock + 202) & 2) != 0 )
  {
    v18 = *(_WORD *)(*(_QWORD *)(SpinLock + 32) + 24LL);
  }
  else
  {
    v18 = 0;
  }
  v19 = *(_QWORD *)(SpinLock + 32);
  v20 = (PKSPIN_LOCK)(SpinLock + 208);
  v21 = v17 & 8;
  if ( v18 && !v21 )
  {
LABEL_44:
    v22 = (PKSPIN_LOCK)(SpinLock + 216);
    goto LABEL_45;
  }
  if ( a4 )
  {
    if ( v21 )
    {
      v19 = 0;
      v78 = 0;
LABEL_42:
      v13 = -1073741808;
      goto LABEL_66;
    }
    goto LABEL_44;
  }
  v19 = *(_QWORD *)(SpinLock + 232);
  if ( !v19 )
  {
    v33 = KfRaiseIrql(2u);
    RtlAcquireReadLockAtDpcLevel(&::SpinLock);
    v19 = qword_14022E250;
    if ( qword_14022E250 )
    {
      v34 = *(_QWORD *)(qword_14022E250 + 16);
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v34
                                        + (unsigned int)(*(_DWORD *)(v34 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v34 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v34 + 24), 2u);
    }
    _InterlockedDecrement(&dword_14022E1D8);
    KeLowerIrql(v33);
    *(_QWORD *)(SpinLock + 232) = v19;
  }
  v22 = (PKSPIN_LOCK)(SpinLock + 240);
  v20 = (PKSPIN_LOCK)(SpinLock + 224);
LABEL_45:
  v78 = v22;
  if ( !v19 )
    goto LABEL_42;
  if ( *v20 )
  {
    Object = (PVOID)*v20;
    v13 = 0;
  }
  else
  {
    v103 = *(unsigned __int64 *)(v19 + 40);
    v23 = *(__int64 (__fastcall **)(__int128 *))(*(_QWORD *)(v19 + 48) + 240LL);
    if ( (char *)v23 == (char *)IpNlpInitializeSessionInfo )
      v24 = IpNlpInitializeSessionInfo(&v103);
    else
      v24 = v23(&v103);
    v13 = v24;
    if ( v24 >= 0 )
    {
      Object = (PVOID)*((_QWORD *)&v103 + 1);
      *v20 = *((_QWORD *)&v103 + 1);
    }
    else
    {
      *v20 = 0;
    }
    if ( v24 < 0 )
      goto LABEL_66;
  }
  if ( (!a4 || a4 == 41) && a5 == 23 )
    v13 = InetInspectSocketPropertyValue(*(_QWORD *)(SpinLock + 80), Source2, a7);
LABEL_66:
  v28 = *(int **)(SpinLock + 88);
  if ( v28 )
  {
    v77 = *v28;
    v29 = 0;
    if ( v19 == *(_QWORD *)(SpinLock + 32) )
      v29 = v28;
    *(_QWORD *)&v103 = v29;
  }
  else
  {
    *(_QWORD *)&v103 = 0;
    v77 = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v75);
  if ( v13 < 0 )
    return (unsigned int)v13;
  v30 = ExAllocatePool2(64, 80, 1464165204);
  v31 = (_QWORD *)v30;
  if ( !v30 )
    return (unsigned int)-1073741801;
  *(_QWORD *)(v30 + 8) = SpinLock;
  v32 = _InterlockedIncrement64((volatile signed __int64 *)(SpinLock + 8));
  if ( v32 <= 1 )
    goto LABEL_73;
  v38 = (volatile signed __int32 *)EndpointReferenceHistory;
  if ( EndpointReferenceHistory )
  {
    v39 = _InterlockedExchangeAdd((volatile signed __int32 *)EndpointReferenceHistory + 1, 1u);
    v40 = *v38;
    v41 = v39 + 1;
    if ( *v38 )
    {
      v42 = 0;
      while ( v38[18 * (v41 % v40) + 3] )
      {
        v59 = _InterlockedExchangeAdd(v38 + 1, 1u);
        v40 = *v38;
        v41 = v59 + 1;
        if ( ++v42 >= *v38 )
          goto LABEL_113;
      }
      if ( v42 < v40 )
      {
        v43 = &v38[18 * (v41 % v40)];
        *((_DWORD *)v43 + 2) = v32;
        *((_DWORD *)v43 + 4) = PsGetCurrentThreadProcessId();
        *((_DWORD *)v43 + 5) = (unsigned int)PsGetCurrentThreadId();
        RtlCaptureStackBackTrace(1u, 6u, (PVOID *)v43 + 3, 0);
        *((_QWORD *)v43 + 9) = SpinLock;
      }
    }
  }
LABEL_113:
  v31[2] = v81;
  v31[3] = v82;
  v44 = *(_QWORD *)(SpinLock + 96);
  v45 = *(_QWORD *)(SpinLock + 80);
  v85 = 0;
  v87 = 0;
  v93 = 0;
  v96 = 0;
  v99 = 0;
  v102 = 0;
  v83[0] = *(_QWORD *)(v19 + 40);
  v83[2] = v103;
  v84 = v77;
  v101 = 0;
  if ( v44 )
    v86 = *(_QWORD *)(v44 + 8);
  else
    v86 = 0;
  v88 = Object;
  v98 = TcpSetSockOptEndpointSetSessionInfoComplete;
  v91 = Source2;
  v92 = a7;
  v100 = v45;
  v95 = a9;
  v46 = *(_QWORD *)(v19 + 48);
  v97 = v31;
  v89 = a4;
  v90 = a5;
  v94 = a8;
  v83[1] = 0;
  v47 = *(__int64 (__fastcall **)(__int64))(v46 + 256);
  if ( v47 == IpNlpSetSessionInfo )
    v48 = IpNlpSetSessionInfo((__int64)v83);
  else
    v48 = v47((__int64)v83);
  v49 = v80;
  v50 = v48;
  if ( v48 >= 0 )
  {
    if ( v80 )
      *v80 = v95;
    if ( v78 )
      *v78 = v99;
  }
  v13 = 259;
  if ( v48 == 259 )
    return 259;
  if ( v48 >= 0 && (!a4 || a4 == 41) && a5 == 71 )
  {
    v61 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
    *(_BYTE *)(SpinLock + 203) |= 4u;
    *(_BYTE *)(SpinLock + 203) = (*(_BYTE *)Source2 < 2u ? 2 : 0) | *(_BYTE *)(SpinLock + 203) & 0xFD;
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v61);
    v49 = v80;
  }
  if ( !v49 )
  {
    TcpSetSockOptEndpointSetSessionInfoComplete(v31);
    return (unsigned int)v13;
  }
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))v31[2])(v31[3], v50, *v49);
  v51 = v31[1];
  v52 = _InterlockedDecrement64((volatile signed __int64 *)(v51 + 8));
  if ( v52 < 0 )
    goto LABEL_73;
  v53 = (volatile signed __int32 *)EndpointReferenceHistory;
  if ( EndpointReferenceHistory )
  {
    v54 = _InterlockedExchangeAdd((volatile signed __int32 *)EndpointReferenceHistory + 1, 1u);
    v55 = *v53;
    v56 = v54 + 1;
    if ( *v53 )
    {
      v57 = 0;
      while ( v53[18 * (v56 % v55) + 3] )
      {
        v60 = _InterlockedExchangeAdd(v53 + 1, 1u);
        v55 = *v53;
        v56 = v60 + 1;
        if ( ++v57 >= *v53 )
          goto LABEL_134;
      }
      if ( v57 < v55 )
      {
        v58 = &v53[18 * (v56 % v55)];
        *((_DWORD *)v58 + 2) = v52;
        *((_DWORD *)v58 + 4) = PsGetCurrentThreadProcessId();
        *((_DWORD *)v58 + 5) = (unsigned int)PsGetCurrentThreadId();
        RtlCaptureStackBackTrace(1u, 6u, (PVOID *)v58 + 3, 0);
        *((_QWORD *)v58 + 9) = v51;
      }
    }
  }
LABEL_134:
  if ( !v52 )
    TcpCleanupEndpoint(v51);
  ExFreePoolWithTag(v31, 0x57456354u);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400d8bc0  mov     [rsp-8+arg_8], rbx
0x1400d8bc5  push    rbp
0x1400d8bc6  push    rsi
0x1400d8bc7  push    rdi
0x1400d8bc8  push    r12
0x1400d8bca  push    r13
0x1400d8bcc  push    r14
0x1400d8bce  push    r15
0x1400d8bd0  lea     rbp, [rsp-50h]
0x1400d8bd5  sub     rsp, 150h
0x1400d8bdc  mov     rax, cs:__security_cookie
0x1400d8be3  xor     rax, rsp
0x1400d8be6  mov     [rbp+80h+var_40], rax
0x1400d8bea  cmp     cs:dword_1402241D4, 0
0x1400d8bf1  mov     r14d, r9d
0x1400d8bf4  mov     rax, [rbp+80h+arg_38]
0x1400d8bfb  mov     rsi, rcx
0x1400d8bfe  mov     r15, [rbp+80h+arg_28]
0x1400d8c05  mov     r12, [rbp+80h+arg_48]
0x1400d8c0c  mov     ebx, [rbp+80h+arg_20]
0x1400d8c12  mov     rdi, [rbp+80h+arg_30]
0x1400d8c19  mov     [rsp+180h+var_138], rax
0x1400d8c1e  mov     [rsp+180h+Source2], r15
0x1400d8c23  mov     [rsp+180h+var_110], r12
0x1400d8c28  mov     [rbp+80h+var_100], r8
0x1400d8c2c  mov     [rsp+180h+var_108], rdx
0x1400d8c31  jz      short loc_1400D8C47
0x1400d8c33  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x1400d8c3a  xorps   xmm0, xmm0
0x1400d8c3d  movups  [rbp+80h+var_50], xmm0
0x1400d8c41  jnz     loc_1400D92EB
0x1400d8c47  mov     rcx, rsi; SpinLock
0x1400d8c4a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d8c51  nop     dword ptr [rax+rax+00h]
0x1400d8c56  mov     [rsp+180h+var_140], al
0x1400d8c5a  movzx   r13d, al
0x1400d8c5e  cmp     r14d, 6
0x1400d8c62  jz      loc_1400D8EC5
0x1400d8c68  cmp     r14d, 0FFFFh
0x1400d8c6f  jz      loc_1400D922F
0x1400d8c75  cmp     r14d, 0FFFCh
0x1400d8c7c  jz      loc_1400D8D08
0x1400d8c82  cmp     r14d, 29h ; ')'
0x1400d8c86  jnz     loc_1400D8DF6
0x1400d8c8c  cmp     ebx, 1Bh
0x1400d8c8f  jnz     loc_1400D8DF6
0x1400d8c95  cmp     [rbp+80h+arg_30], 4
0x1400d8c9d  jb      loc_1400D932A
0x1400d8ca3  mov     eax, [rsi+10h]
0x1400d8ca6  test    al, 1
0x1400d8ca8  jnz     loc_1400D9683
0x1400d8cae  mov     eax, [r15]
0x1400d8cb1  neg     eax
0x1400d8cb3  movzx   eax, byte ptr [rsi+0CAh]
0x1400d8cba  sbb     cl, cl
0x1400d8cbc  and     al, 0FDh
0x1400d8cbe  and     cl, 2
0x1400d8cc1  or      cl, al
0x1400d8cc3  mov     [rsi+0CAh], cl
0x1400d8cc9  xor     edi, edi
0x1400d8ccb  movzx   edx, r13b; NewIrql
0x1400d8ccf  mov     rcx, rsi; SpinLock
0x1400d8cd2  call    cs:__imp_KeReleaseSpinLock
0x1400d8cd9  nop     dword ptr [rax+rax+00h]
0x1400d8cde  mov     eax, edi
0x1400d8ce0  mov     rcx, [rbp+80h+var_40]
0x1400d8ce4  xor     rcx, rsp; StackCookie
0x1400d8ce7  call    __security_check_cookie
0x1400d8cec  mov     rbx, [rsp+180h+arg_8]
0x1400d8cf4  add     rsp, 150h
0x1400d8cfb  pop     r15
0x1400d8cfd  pop     r14
0x1400d8cff  pop     r13
0x1400d8d01  pop     r12
0x1400d8d03  pop     rdi
0x1400d8d04  pop     rsi
0x1400d8d05  pop     rbp
0x1400d8d06  retn
0x1400d8d08  cmp     ebx, 98000004h
0x1400d8d0e  jz      loc_1400D918A
0x1400d8d14  lea     eax, [rbx+67FFFFF0h]
0x1400d8d1a  cmp     eax, 1
0x1400d8d1d  jbe     loc_1400D918A
0x1400d8d23  cmp     ebx, 98000012h
0x1400d8d29  jz      loc_1400D914A
0x1400d8d2f  cmp     ebx, 9800012Ch
0x1400d8d35  jz      loc_1400D918A
0x1400d8d3b  cmp     ebx, 98000014h
0x1400d8d41  jz      loc_1400D9A81
0x1400d8d47  lea     eax, [rbx+67FFFFEAh]
0x1400d8d4d  cmp     eax, 2
0x1400d8d50  jbe     loc_1400D918A
0x1400d8d56  cmp     ebx, 980000E6h
0x1400d8d5c  jz      loc_1400D918A
0x1400d8d62  cmp     ebx, 98000013h
0x1400d8d68  jz      loc_1400D99B7
0x1400d8d6e  cmp     ebx, 8800000Bh
0x1400d8d74  jz      loc_1400D972D
0x1400d8d7a  cmp     ebx, 8800001Ah
0x1400d8d80  jz      loc_1400D972D
0x1400d8d86  cmp     ebx, 98000022h
0x1400d8d8c  jz      loc_1400D9A5A
0x1400d8d92  lea     eax, [rbx+67FFFF38h]
0x1400d8d98  cmp     eax, 1Fh
0x1400d8d9b  ja      short loc_1400D8DAB
0x1400d8d9d  mov     ecx, 8040001Dh
0x1400d8da2  bt      ecx, eax
0x1400d8da5  jb      loc_1400D97EA
0x1400d8dab  cmp     ebx, 0D80000C9h
0x1400d8db1  jz      loc_1400D97EA
0x1400d8db7  cmp     ebx, 580000CDh
0x1400d8dbd  jz      loc_1400D995B
0x1400d8dc3  lea     eax, [rbx+67FFFF9Ch]
0x1400d8dc9  cmp     eax, 2
0x1400d8dcc  jbe     loc_1400D8F21
0x1400d8dd2  cmp     ebx, 580000D2h
0x1400d8dd8  jz      loc_1400D9702
0x1400d8dde  cmp     ebx, 980000E8h
0x1400d8de4  jz      loc_1400D98E1
0x1400d8dea  cmp     ebx, 980000E9h
0x1400d8df0  jz      loc_1400D9872
0x1400d8df6  mov     ecx, [rsi+10h]
0x1400d8df9  xor     r8d, r8d
0x1400d8dfc  mov     [rsp+180h+var_130], r8
0x1400d8e01  test    cl, 1
0x1400d8e04  jnz     loc_1400D92DA
0x1400d8e0a  mov     rax, [rsi+20h]
0x1400d8e0e  movzx   edx, word ptr [rax+18h]
0x1400d8e12  cmp     dx, 17h
0x1400d8e16  jnz     loc_1400D92E3
0x1400d8e1c  test    byte ptr [rsi+0CAh], 2
0x1400d8e23  jnz     loc_1400D92E3
0x1400d8e29  mov     eax, r8d
0x1400d8e2c  mov     r15, [rsi+20h]
0x1400d8e30  lea     r12, [rsi+0D0h]
0x1400d8e37  and     ecx, 8
0x1400d8e3a  test    ax, ax
0x1400d8e3d  jnz     short loc_1400D8E5E
0x1400d8e3f  test    r14d, r14d
0x1400d8e42  jz      loc_1400D90BA
0x1400d8e48  test    ecx, ecx
0x1400d8e4a  jz      short loc_1400D8E62
0x1400d8e4c  mov     r15, r8
0x1400d8e4f  mov     [rsp+180h+var_120], r8
0x1400d8e54  mov     edi, 0C0000010h
0x1400d8e59  jmp     loc_1400D9018
0x1400d8e5e  test    ecx, ecx
0x1400d8e60  jnz     short loc_1400D8E3F
0x1400d8e62  lea     rax, [r12+8]
0x1400d8e67  mov     [rsp+180h+var_120], rax
0x1400d8e6c  test    r15, r15
0x1400d8e6f  jz      short loc_1400D8E54
0x1400d8e71  mov     rax, [r12]
0x1400d8e75  test    rax, rax
0x1400d8e78  jnz     loc_1400D90AD
0x1400d8e7e  mov     rax, [r15+28h]
0x1400d8e82  lea     rcx, IpNlpInitializeSessionInfo
0x1400d8e89  mov     qword ptr [rbp+80h+var_50], rax
0x1400d8e8d  mov     rax, [r15+30h]
0x1400d8e91  mov     qword ptr [rbp+80h+var_50+8], r8
0x1400d8e95  mov     rax, [rax+0F0h]
0x1400d8e9c  cmp     rax, rcx
0x1400d8e9f  lea     rcx, [rbp+80h+var_50]
0x1400d8ea3  jnz     loc_1400D97E0
0x1400d8ea9  call    IpNlpInitializeSessionInfo
0x1400d8eae  mov     edi, eax
0x1400d8eb0  test    eax, eax
0x1400d8eb2  jns     loc_1400D8FF4
0x1400d8eb8  mov     qword ptr [r12], 0
0x1400d8ec0  jmp     loc_1400D9001
0x1400d8ec5  mov     r14, [rbp+80h+arg_30]
0x1400d8ecc  lea     rcx, [rsi+0A8h]
0x1400d8ed3  mov     r9, r14
0x1400d8ed6  mov     [rsp+180h+Object], 0
0x1400d8edf  mov     r8, r15
0x1400d8ee2  mov     edx, ebx
0x1400d8ee4  call    TcpSetTcpLevelOption
0x1400d8ee9  mov     edi, eax
0x1400d8eeb  test    eax, eax
0x1400d8eed  js      loc_1400D8CCB
0x1400d8ef3  cmp     ebx, 12h
0x1400d8ef6  jnz     loc_1400D8CCB
0x1400d8efc  cmp     r14, 1
0x1400d8f00  jb      loc_1400D932A
0x1400d8f06  movzx   eax, byte ptr [r15]
0x1400d8f0a  neg     al
0x1400d8f0c  mov     eax, [rsi+10h]
0x1400d8f0f  sbb     edx, edx
0x1400d8f11  and     eax, 0FFFFFFBFh
0x1400d8f14  and     edx, 40h
0x1400d8f17  or      edx, eax
0x1400d8f19  mov     [rsi+10h], edx
0x1400d8f1c  jmp     loc_1400D8CC9
0x1400d8f21  mov     edx, 50h ; 'P'
0x1400d8f26  mov     ecx, 40h ; '@'
0x1400d8f2b  mov     r8d, 57456354h
0x1400d8f31  call    cs:__imp_ExAllocatePool2
0x1400d8f38  nop     dword ptr [rax+rax+00h]
0x1400d8f3d  mov     rdi, rax
0x1400d8f40  test    rax, rax
0x1400d8f43  jz      loc_1400D9912
0x1400d8f49  mov     [rax+8], rsi
0x1400d8f4d  mov     r12d, 1
0x1400d8f53  lock xadd [rsi+8], r12
0x1400d8f59  inc     r12
0x1400d8f5c  cmp     r12, 1
0x1400d8f60  jle     loc_1400D909B
0x1400d8f66  mov     rcx, cs:EndpointReferenceHistory
0x1400d8f6d  test    rcx, rcx
0x1400d8f70  jz      short loc_1400D8F7D
0x1400d8f72  mov     edx, r12d
0x1400d8f75  mov     r8, rsi
0x1400d8f78  call    RhAppendHistory
0x1400d8f7d  movzx   edx, r13b; NewIrql
0x1400d8f81  mov     rcx, rsi; SpinLock
0x1400d8f84  call    cs:__imp_KeReleaseSpinLock
0x1400d8f8b  nop     dword ptr [rax+rax+00h]
0x1400d8f90  mov     rax, [rsp+180h+var_108]
0x1400d8f95  mov     rdx, [rsp+180h+var_138]
0x1400d8f9a  mov     [rdi+10h], rax
0x1400d8f9e  mov     rax, [rbp+80h+var_100]
0x1400d8fa2  mov     [rdi+18h], rax
0x1400d8fa6  mov     rax, [rbp+80h+arg_30]
0x1400d8fad  mov     [rdi+30h], rax
0x1400d8fb1  mov     rax, [rbp+80h+arg_40]
0x1400d8fb8  mov     [rdi+40h], rax
0x1400d8fbc  mov     [rdi+20h], ebx
0x1400d8fbf  mov     [rdi+28h], r15
0x1400d8fc3  mov     [rdi+38h], rdx
0x1400d8fc7  call    cs:__imp_KeGetCurrentIrql
0x1400d8fce  nop     dword ptr [rax+rax+00h]
0x1400d8fd3  test    al, al
0x1400d8fd5  jnz     loc_1400D96E7
0x1400d8fdb  mov     rcx, rdi; P
0x1400d8fde  mov     qword ptr [rdi], 0
0x1400d8fe5  call    TcpPortReservationWorkQueueRoutine
0x1400d8fea  mov     edi, 103h
0x1400d8fef  jmp     loc_1400D8CDE
0x1400d8ff4  mov     rax, qword ptr [rbp+80h+var_50+8]
0x1400d8ff8  mov     [rsp+180h+var_130], rax
0x1400d8ffd  mov     [r12], rax
0x1400d9001  test    edi, edi
0x1400d9003  js      short loc_1400D9018
0x1400d9005  test    r14d, r14d
0x1400d9008  jz      loc_1400D9358
0x1400d900e  cmp     r14d, 29h ; ')'
0x1400d9012  jz      loc_1400D9358
0x1400d9018  mov     rax, [rsi+58h]
0x1400d901c  mov     r12d, 1
0x1400d9022  test    rax, rax
0x1400d9025  jz      loc_1400D9900
0x1400d902b  mov     ecx, [rax]
0x1400d902d  mov     [rsp+180h+var_128], ecx
0x1400d9031  xor     ecx, ecx
0x1400d9033  cmp     r15, [rsi+20h]
0x1400d9037  cmovz   rcx, rax
0x1400d903b  mov     qword ptr [rbp+80h+var_50], rcx
0x1400d903f  movzx   edx, r13b; NewIrql
0x1400d9043  mov     rcx, rsi; SpinLock
0x1400d9046  call    cs:__imp_KeReleaseSpinLock
0x1400d904d  nop     dword ptr [rax+rax+00h]
0x1400d9052  test    edi, edi
0x1400d9054  js      loc_1400D8CDE
0x1400d905a  mov     edx, 50h ; 'P'
0x1400d905f  mov     ecx, 40h ; '@'
0x1400d9064  mov     r8d, 57456354h
0x1400d906a  call    cs:__imp_ExAllocatePool2
0x1400d9071  nop     dword ptr [rax+rax+00h]
0x1400d9076  mov     r13, rax
0x1400d9079  test    rax, rax
0x1400d907c  jz      loc_1400D92D0
0x1400d9082  mov     [rax+8], rsi
0x1400d9086  mov     r8, r12
0x1400d9089  lock xadd [rsi+8], r8
0x1400d908f  inc     r8
0x1400d9092  cmp     r8, r12
0x1400d9095  jg      loc_1400D937D
0x1400d909b  mov     ecx, 1Ch; BugCheckCode
0x1400d90a0  call    cs:__imp_KeBugCheck
0x1400d90ad  mov     [rsp+180h+var_130], rax
0x1400d90b2  mov     edi, r8d
0x1400d90b5  jmp     loc_1400D9005
0x1400d90ba  mov     r15, [r12+18h]
0x1400d90bf  test    r15, r15
0x1400d90c2  jnz     short loc_1400D913C
0x1400d90c4  mov     cl, 2; NewIrql
0x1400d90c6  call    cs:__imp_KfRaiseIrql
0x1400d90cd  nop     dword ptr [rax+rax+00h]
0x1400d90d2  lea     rcx, SpinLock; SpinLock
0x1400d90d9  movzx   edi, al
0x1400d90dc  call    RtlAcquireReadLockAtDpcLevel
0x1400d90e1  mov     r15, cs:qword_14022E250
0x1400d90e8  test    r15, r15
0x1400d90eb  jz      short loc_1400D911D
0x1400d90ed  mov     eax, gs:1A4h
0x1400d90f5  xor     edx, edx
0x1400d90f7  mov     r8, [r15+10h]
0x1400d90fb  div     dword ptr [r8+14h]
0x1400d90ff  mov     eax, 2
0x1400d9104  imul    edx, [r8+10h]
  ... truncated ...
```
