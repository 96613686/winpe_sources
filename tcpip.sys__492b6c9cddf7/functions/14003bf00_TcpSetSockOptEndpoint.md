# TcpSetSockOptEndpoint

- ea: `0x14003bf00`
- end: `0x14003cdcb`
- name: `TcpSetSockOptEndpoint`
- size: `3787`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b9f0`

## callees

- `0x140032740`
- `0x14003abd0`
- `0x14003bf00`
- `0x14003cde0`
- `0x140052390`
- `0x14005b600`
- `0x1400610b0`
- `0x1400806e0`
- `0x140081404`
- `0x140082090`
- `0x14009434c`
- `0x1400b4690`
- `0x1400b5b10`
- `0x1400e7390`
- `0x140111350`
- `0x140112be4`
- `0x140115740`
- `0x1401200f0`
- `0x140123f2c`
- `0x140125330`
- `0x140127534`
- `0x140152e74`
- `0x14015f83c`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14003c406`
- `ntoskrnl!KfRaiseIrql` at `0x14003c406`
- `ntoskrnl!KeLowerIrql` at `0x14003c468`
- `ntoskrnl!KeLowerIrql` at `0x14003c468`
- `ntoskrnl!IoFileObjectType` at `0x1401c31c2`
- `ntoskrnl!KeBugCheck` at `0x14003c3e0`
- `ntoskrnl!KeBugCheck` at `0x14003c3e0`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003c714`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003c8fa`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003c714`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003c8fa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003c723`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003c909`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003c723`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003c909`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c741`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c927`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c741`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c927`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c307`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c307`
- `ntoskrnl!RtlCompareMemory` at `0x14003cd7d`
- `ntoskrnl!RtlCompareMemory` at `0x14003cd7d`
- `ntoskrnl!PsGetProcessId` at `0x14003c532`
- `ntoskrnl!PsGetProcessId` at `0x14003c532`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401c31e9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401c31e9`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c3267`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c3267`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c012`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c2c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c386`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c491`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ca11`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ca49`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003caaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cb31`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cbb9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cca2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd04`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c3251`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c012`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c2c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c386`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c491`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ca11`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ca49`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003caaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cb31`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cbb9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cca2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd04`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c3251`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bf8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c4ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c9d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401c321f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bf8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c4ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c9d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401c321f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c94c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c94c`
- `ntoskrnl!ExAllocatePool2` at `0x14003c271`
- `ntoskrnl!ExAllocatePool2` at `0x14003c3aa`
- `ntoskrnl!ExAllocatePool2` at `0x14003c271`
- `ntoskrnl!ExAllocatePool2` at `0x14003c3aa`
- `NETIO!NetioInsertWorkQueue` at `0x14003ca31`
- `NETIO!NetioInsertWorkQueue` at `0x14003ca31`
- `NETIO!NetioNcmNotificationChannelContextRequest` at `0x14003c54d`
- `NETIO!NetioNcmNotificationChannelContextRequest` at `0x14003c54d`
- `NETIO!NetioNrtAssociateContext` at `0x1401c323d`
- `NETIO!NetioNrtAssociateContext` at `0x1401c323d`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401c3208`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401c3208`

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
  __int64 (__fastcall *v47)(_QWORD *); // rax
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
  __int64 v69; // r15
  int v70; // edx
  void *v71; // rcx
  _QWORD *v72; // r14
  KIRQL v73; // bl
  KIRQL v74; // [rsp+40h] [rbp-C0h]
  PVOID Object; // [rsp+50h] [rbp-B0h] BYREF
  int v76; // [rsp+58h] [rbp-A8h]
  _DWORD *v77; // [rsp+60h] [rbp-A0h]
  void *Source2; // [rsp+68h] [rbp-98h]
  _QWORD *v79; // [rsp+70h] [rbp-90h]
  __int64 v80; // [rsp+78h] [rbp-88h]
  __int64 v81; // [rsp+80h] [rbp-80h]
  _QWORD v82[3]; // [rsp+90h] [rbp-70h] BYREF
  int v83; // [rsp+A8h] [rbp-58h]
  int v84; // [rsp+ACh] [rbp-54h]
  __int64 v85; // [rsp+B0h] [rbp-50h]
  __int64 v86; // [rsp+B8h] [rbp-48h]
  PVOID v87; // [rsp+C0h] [rbp-40h]
  int v88; // [rsp+C8h] [rbp-38h]
  unsigned int v89; // [rsp+CCh] [rbp-34h]
  void *v90; // [rsp+D0h] [rbp-30h]
  int v91; // [rsp+D8h] [rbp-28h]
  int v92; // [rsp+DCh] [rbp-24h]
  _QWORD *v93; // [rsp+E0h] [rbp-20h]
  unsigned int v94; // [rsp+E8h] [rbp-18h]
  int v95; // [rsp+ECh] [rbp-14h]
  _QWORD *v96; // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v97)(PVOID); // [rsp+F8h] [rbp-8h]
  __int64 v98; // [rsp+100h] [rbp+0h]
  KSPIN_LOCK v99; // [rsp+108h] [rbp+8h]
  __int128 v100; // [rsp+110h] [rbp+10h]
  __int64 v101; // [rsp+120h] [rbp+20h]
  __int128 v102; // [rsp+130h] [rbp+30h] BYREF

  Source2 = a6;
  v79 = a10;
  v81 = a3;
  v80 = a2;
  if ( dword_1402201D4 )
  {
    v102 = 0;
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
    {
      *(_QWORD *)&v102 = SpinLock;
      v37 = a7;
      if ( !a6 )
        v37 = 0;
      McTemplateK0pqqqbr3_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_SETSOCKOPT,
        (unsigned int)&v102,
        SpinLock,
        a4,
        a5,
        v37,
        (__int64)a6);
    }
  }
  v74 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
  v12 = v74;
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
      DWORD2(v102) = 0;
      *(_QWORD *)&v102 = 0;
      LODWORD(v102) = (unsigned int)PsGetProcessId(v36);
      v13 = NetioNcmNotificationChannelContextRequest(&v102, 0, 2);
      if ( v13 < 0 )
        *(_BYTE *)(SpinLock + 204) &= ~4u;
    }
    goto LABEL_12;
  }
  switch ( a5 )
  {
    case 0x98000012:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
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
      LOBYTE(v69) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
      if ( Source2 && a7 >= 0x18 )
      {
        if ( RtlCompareMemory(&ASSOCIATE_NAMERES_CONTEXT, Source2, 0x10u) == 16 )
        {
          v71 = (void *)*((_QWORD *)Source2 + 2);
          Object = 0;
          v13 = ObReferenceObjectByHandle(v71, 0, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
          if ( v13 >= 0 )
          {
            v72 = Object;
            if ( (unsigned __int8)NetioNrtIsTrackerDevice(*((_QWORD *)Object + 1)) )
            {
              v69 = v72[3];
              v73 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
              v13 = NetioNrtAssociateContext(SpinLock, 0, v69, SpinLock + 288);
              KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v73);
            }
            else
            {
              v13 = -1073741816;
            }
            ObfDereferenceObject(v72);
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
      if ( dword_1402201D4 && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 0x20) != 0 )
      {
        v102 = SpinLock;
        McTemplateK0pqpq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          v70,
          (unsigned int)&v102,
          SpinLock,
          0,
          v69,
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
          RhAppendHistory(EndpointReferenceHistory, (unsigned int)v62, SpinLock);
        KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
        v63 = *(_QWORD *)(SpinLock + 80);
        v64 = a5 == -2013265909 ? QimInspectSetQoS(v63, a6, a7) : QimInspectAssociateQoS(v63, a6, a7);
        v13 = v64;
        v65 = _InterlockedDecrement64((volatile signed __int64 *)(SpinLock + 8));
        if ( v65 >= 0 )
        {
          if ( EndpointReferenceHistory )
            RhAppendHistory(EndpointReferenceHistory, (unsigned int)v65, SpinLock);
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
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
    return (unsigned int)InetInspectSocketOption(SpinLock, *(_QWORD *)(SpinLock + 80), a5, a6, a7, a8, a9, a10);
  }
  if ( a5 == 1476395213 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
    if ( *(_QWORD *)(SpinLock + 80) && a9 >= 8 && a8 )
    {
      v13 = 0;
      *a8 = WfpAleQueryOrInsertEndpointHandle();
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
        RhAppendHistory(EndpointReferenceHistory, (unsigned int)v27, SpinLock);
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
      v26[2] = v80;
      v26[3] = v81;
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
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
      if ( a9 )
      {
        v13 = 0;
        *(_BYTE *)a8 = (*((__int64 (**)(void))TcpRssControl + 4))();
        if ( a10 )
          *v79 = 1;
      }
      else
      {
        return (unsigned int)-1073741306;
      }
      return (unsigned int)v13;
    case 0x980000E8:
      v68 = TcpHandleSockOptSioWakeEndpoint((PKSPIN_LOCK)SpinLock);
      v14 = v74;
      v13 = v68;
      goto LABEL_13;
    case 0x980000E9:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
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
      v77 = 0;
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
    RtlAcquireReadLockAtDpcLevel(&qword_14022A190);
    v19 = qword_14022A210;
    if ( qword_14022A210 )
    {
      v34 = *(_QWORD *)(qword_14022A210 + 16);
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v34
                                        + (unsigned int)(*(_DWORD *)(v34 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v34 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v34 + 24), 2u);
    }
    _InterlockedDecrement(&dword_14022A198);
    KeLowerIrql(v33);
    *(_QWORD *)(SpinLock + 232) = v19;
  }
  v22 = (PKSPIN_LOCK)(SpinLock + 240);
  v20 = (PKSPIN_LOCK)(SpinLock + 224);
LABEL_45:
  v77 = v22;
  if ( !v19 )
    goto LABEL_42;
  if ( *v20 )
  {
    Object = (PVOID)*v20;
    v13 = 0;
  }
  else
  {
    v102 = *(unsigned __int64 *)(v19 + 40);
    v23 = *(__int64 (__fastcall **)(__int128 *))(*(_QWORD *)(v19 + 48) + 240LL);
    if ( (char *)v23 == (char *)IpNlpInitializeSessionInfo )
      v24 = IpNlpInitializeSessionInfo(&v102);
    else
      v24 = v23(&v102);
    v13 = v24;
    if ( v24 >= 0 )
    {
      Object = (PVOID)*((_QWORD *)&v102 + 1);
      *v20 = *((_QWORD *)&v102 + 1);
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
    v76 = *v28;
    v29 = 0;
    if ( v19 == *(_QWORD *)(SpinLock + 32) )
      v29 = v28;
    *(_QWORD *)&v102 = v29;
  }
  else
  {
    *(_QWORD *)&v102 = 0;
    v76 = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v74);
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
  v31[2] = v80;
  v31[3] = v81;
  v44 = *(_QWORD *)(SpinLock + 96);
  v45 = *(_QWORD *)(SpinLock + 80);
  v84 = 0;
  v86 = 0;
  v92 = 0;
  v95 = 0;
  v98 = 0;
  v101 = 0;
  v82[0] = *(_QWORD *)(v19 + 40);
  v82[2] = v102;
  v83 = v76;
  v100 = 0;
  if ( v44 )
    v85 = *(_QWORD *)(v44 + 8);
  else
    v85 = 0;
  v87 = Object;
  v97 = TcpSetSockOptEndpointSetSessionInfoComplete;
  v90 = Source2;
  v91 = a7;
  v99 = v45;
  v94 = a9;
  v46 = *(_QWORD *)(v19 + 48);
  v96 = v31;
  v88 = a4;
  v89 = a5;
  v93 = a8;
  v82[1] = 0;
  v47 = *(__int64 (__fastcall **)(_QWORD *))(v46 + 256);
  if ( (char *)v47 == (char *)IpNlpSetSessionInfo )
    v48 = IpNlpSetSessionInfo(v82);
  else
    v48 = v47(v82);
  v49 = v79;
  v50 = v48;
  if ( v48 >= 0 )
  {
    if ( v79 )
      *v79 = v94;
    if ( v77 )
      *v77 = v98;
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
    v49 = v79;
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
0x14003bf00  mov     [rsp-8+arg_8], rbx
0x14003bf05  push    rbp
0x14003bf06  push    rsi
0x14003bf07  push    rdi
0x14003bf08  push    r12
0x14003bf0a  push    r13
0x14003bf0c  push    r14
0x14003bf0e  push    r15
0x14003bf10  lea     rbp, [rsp-50h]
0x14003bf15  sub     rsp, 150h
0x14003bf1c  mov     rax, cs:__security_cookie
0x14003bf23  xor     rax, rsp
0x14003bf26  mov     [rbp+80h+var_40], rax
0x14003bf2a  cmp     cs:dword_1402201D4, 0
0x14003bf31  mov     r14d, r9d
0x14003bf34  mov     rax, [rbp+80h+arg_38]
0x14003bf3b  mov     rsi, rcx
0x14003bf3e  mov     r15, [rbp+80h+arg_28]
0x14003bf45  mov     r12, [rbp+80h+arg_48]
0x14003bf4c  mov     ebx, [rbp+80h+arg_20]
0x14003bf52  mov     rdi, [rbp+80h+arg_30]
0x14003bf59  mov     [rsp+180h+var_138], rax
0x14003bf5e  mov     [rsp+180h+Source2], r15
0x14003bf63  mov     [rsp+180h+var_110], r12
0x14003bf68  mov     [rbp+80h+var_100], r8
0x14003bf6c  mov     [rsp+180h+var_108], rdx
0x14003bf71  jz      short loc_14003BF87
0x14003bf73  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x14003bf7a  xorps   xmm0, xmm0
0x14003bf7d  movups  [rbp+80h+var_50], xmm0
0x14003bf81  jnz     loc_14003C62B
0x14003bf87  mov     rcx, rsi; SpinLock
0x14003bf8a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003bf91  nop     dword ptr [rax+rax+00h]
0x14003bf96  mov     [rsp+180h+var_140], al
0x14003bf9a  movzx   r13d, al
0x14003bf9e  cmp     r14d, 6
0x14003bfa2  jz      loc_14003C205
0x14003bfa8  cmp     r14d, 0FFFFh
0x14003bfaf  jz      loc_14003C56F
0x14003bfb5  cmp     r14d, 0FFFCh
0x14003bfbc  jz      loc_14003C048
0x14003bfc2  cmp     r14d, 29h ; ')'
0x14003bfc6  jnz     loc_14003C136
0x14003bfcc  cmp     ebx, 1Bh
0x14003bfcf  jnz     loc_14003C136
0x14003bfd5  cmp     [rbp+80h+arg_30], 4
0x14003bfdd  jb      loc_14003C66A
0x14003bfe3  mov     eax, [rsi+10h]
0x14003bfe6  test    al, 1
0x14003bfe8  jnz     loc_14003C9C3
0x14003bfee  mov     eax, [r15]
0x14003bff1  neg     eax
0x14003bff3  movzx   eax, byte ptr [rsi+0CAh]
0x14003bffa  sbb     cl, cl
0x14003bffc  and     al, 0FDh
0x14003bffe  and     cl, 2
0x14003c001  or      cl, al
0x14003c003  mov     [rsi+0CAh], cl
0x14003c009  xor     edi, edi
0x14003c00b  movzx   edx, r13b; NewIrql
0x14003c00f  mov     rcx, rsi; SpinLock
0x14003c012  call    cs:__imp_KeReleaseSpinLock
0x14003c019  nop     dword ptr [rax+rax+00h]
0x14003c01e  mov     eax, edi
0x14003c020  mov     rcx, [rbp+80h+var_40]
0x14003c024  xor     rcx, rsp; StackCookie
0x14003c027  call    __security_check_cookie
0x14003c02c  mov     rbx, [rsp+180h+arg_8]
0x14003c034  add     rsp, 150h
0x14003c03b  pop     r15
0x14003c03d  pop     r14
0x14003c03f  pop     r13
0x14003c041  pop     r12
0x14003c043  pop     rdi
0x14003c044  pop     rsi
0x14003c045  pop     rbp
0x14003c046  retn
0x14003c048  cmp     ebx, 98000004h
0x14003c04e  jz      loc_14003C4CA
0x14003c054  lea     eax, [rbx+67FFFFF0h]
0x14003c05a  cmp     eax, 1
0x14003c05d  jbe     loc_14003C4CA
0x14003c063  cmp     ebx, 98000012h
0x14003c069  jz      loc_14003C48A
0x14003c06f  cmp     ebx, 9800012Ch
0x14003c075  jz      loc_14003C4CA
0x14003c07b  cmp     ebx, 98000014h
0x14003c081  jz      loc_14003CDC1
0x14003c087  lea     eax, [rbx+67FFFFEAh]
0x14003c08d  cmp     eax, 2
0x14003c090  jbe     loc_14003C4CA
0x14003c096  cmp     ebx, 980000E6h
0x14003c09c  jz      loc_14003C4CA
0x14003c0a2  cmp     ebx, 98000013h
0x14003c0a8  jz      loc_14003CCF7
0x14003c0ae  cmp     ebx, 8800000Bh
0x14003c0b4  jz      loc_14003CA6D
0x14003c0ba  cmp     ebx, 8800001Ah
0x14003c0c0  jz      loc_14003CA6D
0x14003c0c6  cmp     ebx, 98000022h
0x14003c0cc  jz      loc_14003CD9A
0x14003c0d2  lea     eax, [rbx+67FFFF38h]
0x14003c0d8  cmp     eax, 1Fh
0x14003c0db  ja      short loc_14003C0EB
0x14003c0dd  mov     ecx, 8040001Dh
0x14003c0e2  bt      ecx, eax
0x14003c0e5  jb      loc_14003CB2A
0x14003c0eb  cmp     ebx, 0D80000C9h
0x14003c0f1  jz      loc_14003CB2A
0x14003c0f7  cmp     ebx, 580000CDh
0x14003c0fd  jz      loc_14003CC9B
0x14003c103  lea     eax, [rbx+67FFFF9Ch]
0x14003c109  cmp     eax, 2
0x14003c10c  jbe     loc_14003C261
0x14003c112  cmp     ebx, 580000D2h
0x14003c118  jz      loc_14003CA42
0x14003c11e  cmp     ebx, 980000E8h
0x14003c124  jz      loc_14003CC21
0x14003c12a  cmp     ebx, 980000E9h
0x14003c130  jz      loc_14003CBB2
0x14003c136  mov     ecx, [rsi+10h]
0x14003c139  xor     r8d, r8d
0x14003c13c  mov     [rsp+180h+var_130], r8
0x14003c141  test    cl, 1
0x14003c144  jnz     loc_14003C61A
0x14003c14a  mov     rax, [rsi+20h]
0x14003c14e  movzx   edx, word ptr [rax+18h]
0x14003c152  cmp     dx, 17h
0x14003c156  jnz     loc_14003C623
0x14003c15c  test    byte ptr [rsi+0CAh], 2
0x14003c163  jnz     loc_14003C623
0x14003c169  mov     eax, r8d
0x14003c16c  mov     r15, [rsi+20h]
0x14003c170  lea     r12, [rsi+0D0h]
0x14003c177  and     ecx, 8
0x14003c17a  test    ax, ax
0x14003c17d  jnz     short loc_14003C19E
0x14003c17f  test    r14d, r14d
0x14003c182  jz      loc_14003C3FA
0x14003c188  test    ecx, ecx
0x14003c18a  jz      short loc_14003C1A2
0x14003c18c  mov     r15, r8
0x14003c18f  mov     [rsp+180h+var_120], r8
0x14003c194  mov     edi, 0C0000010h
0x14003c199  jmp     loc_14003C358
0x14003c19e  test    ecx, ecx
0x14003c1a0  jnz     short loc_14003C17F
0x14003c1a2  lea     rax, [r12+8]
0x14003c1a7  mov     [rsp+180h+var_120], rax
0x14003c1ac  test    r15, r15
0x14003c1af  jz      short loc_14003C194
0x14003c1b1  mov     rax, [r12]
0x14003c1b5  test    rax, rax
0x14003c1b8  jnz     loc_14003C3ED
0x14003c1be  mov     rax, [r15+28h]
0x14003c1c2  lea     rcx, IpNlpInitializeSessionInfo
0x14003c1c9  mov     qword ptr [rbp+80h+var_50], rax
0x14003c1cd  mov     rax, [r15+30h]
0x14003c1d1  mov     qword ptr [rbp+80h+var_50+8], r8
0x14003c1d5  mov     rax, [rax+0F0h]
0x14003c1dc  cmp     rax, rcx
0x14003c1df  lea     rcx, [rbp+80h+var_50]
0x14003c1e3  jnz     loc_14003CB20
0x14003c1e9  call    IpNlpInitializeSessionInfo
0x14003c1ee  mov     edi, eax
0x14003c1f0  test    eax, eax
0x14003c1f2  jns     loc_14003C334
0x14003c1f8  mov     qword ptr [r12], 0
0x14003c200  jmp     loc_14003C341
0x14003c205  mov     r14, [rbp+80h+arg_30]
0x14003c20c  lea     rcx, [rsi+0A8h]
0x14003c213  mov     r9, r14
0x14003c216  mov     [rsp+180h+Object], 0
0x14003c21f  mov     r8, r15
0x14003c222  mov     edx, ebx
0x14003c224  call    TcpSetTcpLevelOption
0x14003c229  mov     edi, eax
0x14003c22b  test    eax, eax
0x14003c22d  js      loc_14003C00B
0x14003c233  cmp     ebx, 12h
0x14003c236  jnz     loc_14003C00B
0x14003c23c  cmp     r14, 1
0x14003c240  jb      loc_14003C66A
0x14003c246  movzx   eax, byte ptr [r15]
0x14003c24a  neg     al
0x14003c24c  mov     eax, [rsi+10h]
0x14003c24f  sbb     edx, edx
0x14003c251  and     eax, 0FFFFFFBFh
0x14003c254  and     edx, 40h
0x14003c257  or      edx, eax
0x14003c259  mov     [rsi+10h], edx
0x14003c25c  jmp     loc_14003C009
0x14003c261  mov     edx, 50h ; 'P'
0x14003c266  mov     ecx, 40h ; '@'
0x14003c26b  mov     r8d, 57456354h
0x14003c271  call    cs:__imp_ExAllocatePool2
0x14003c278  nop     dword ptr [rax+rax+00h]
0x14003c27d  mov     rdi, rax
0x14003c280  test    rax, rax
0x14003c283  jz      loc_14003CC52
0x14003c289  mov     [rax+8], rsi
0x14003c28d  mov     r12d, 1
0x14003c293  lock xadd [rsi+8], r12
0x14003c299  inc     r12
0x14003c29c  cmp     r12, 1
0x14003c2a0  jle     loc_14003C3DB
0x14003c2a6  mov     rcx, cs:EndpointReferenceHistory
0x14003c2ad  test    rcx, rcx
0x14003c2b0  jz      short loc_14003C2BD
0x14003c2b2  mov     edx, r12d
0x14003c2b5  mov     r8, rsi
0x14003c2b8  call    RhAppendHistory
0x14003c2bd  movzx   edx, r13b; NewIrql
0x14003c2c1  mov     rcx, rsi; SpinLock
0x14003c2c4  call    cs:__imp_KeReleaseSpinLock
0x14003c2cb  nop     dword ptr [rax+rax+00h]
0x14003c2d0  mov     rax, [rsp+180h+var_108]
0x14003c2d5  mov     rdx, [rsp+180h+var_138]
0x14003c2da  mov     [rdi+10h], rax
0x14003c2de  mov     rax, [rbp+80h+var_100]
0x14003c2e2  mov     [rdi+18h], rax
0x14003c2e6  mov     rax, [rbp+80h+arg_30]
0x14003c2ed  mov     [rdi+30h], rax
0x14003c2f1  mov     rax, [rbp+80h+arg_40]
0x14003c2f8  mov     [rdi+40h], rax
0x14003c2fc  mov     [rdi+20h], ebx
0x14003c2ff  mov     [rdi+28h], r15
0x14003c303  mov     [rdi+38h], rdx
0x14003c307  call    cs:__imp_KeGetCurrentIrql
0x14003c30e  nop     dword ptr [rax+rax+00h]
0x14003c313  test    al, al
0x14003c315  jnz     loc_14003CA27
0x14003c31b  mov     rcx, rdi; P
0x14003c31e  mov     qword ptr [rdi], 0
0x14003c325  call    TcpPortReservationWorkQueueRoutine
0x14003c32a  mov     edi, 103h
0x14003c32f  jmp     loc_14003C01E
0x14003c334  mov     rax, qword ptr [rbp+80h+var_50+8]
0x14003c338  mov     [rsp+180h+var_130], rax
0x14003c33d  mov     [r12], rax
0x14003c341  test    edi, edi
0x14003c343  js      short loc_14003C358
0x14003c345  test    r14d, r14d
0x14003c348  jz      loc_14003C698
0x14003c34e  cmp     r14d, 29h ; ')'
0x14003c352  jz      loc_14003C698
0x14003c358  mov     rax, [rsi+58h]
0x14003c35c  mov     r12d, 1
0x14003c362  test    rax, rax
0x14003c365  jz      loc_14003CC40
0x14003c36b  mov     ecx, [rax]
0x14003c36d  mov     [rsp+180h+var_128], ecx
0x14003c371  xor     ecx, ecx
0x14003c373  cmp     r15, [rsi+20h]
0x14003c377  cmovz   rcx, rax
0x14003c37b  mov     qword ptr [rbp+80h+var_50], rcx
0x14003c37f  movzx   edx, r13b; NewIrql
0x14003c383  mov     rcx, rsi; SpinLock
0x14003c386  call    cs:__imp_KeReleaseSpinLock
0x14003c38d  nop     dword ptr [rax+rax+00h]
0x14003c392  test    edi, edi
0x14003c394  js      loc_14003C01E
0x14003c39a  mov     edx, 50h ; 'P'
0x14003c39f  mov     ecx, 40h ; '@'
0x14003c3a4  mov     r8d, 57456354h
0x14003c3aa  call    cs:__imp_ExAllocatePool2
0x14003c3b1  nop     dword ptr [rax+rax+00h]
0x14003c3b6  mov     r13, rax
0x14003c3b9  test    rax, rax
0x14003c3bc  jz      loc_14003C610
0x14003c3c2  mov     [rax+8], rsi
0x14003c3c6  mov     r8, r12
0x14003c3c9  lock xadd [rsi+8], r8
0x14003c3cf  inc     r8
0x14003c3d2  cmp     r8, r12
0x14003c3d5  jg      loc_14003C6BD
0x14003c3db  mov     ecx, 1Ch; BugCheckCode
0x14003c3e0  call    cs:__imp_KeBugCheck
0x14003c3ed  mov     [rsp+180h+var_130], rax
0x14003c3f2  mov     edi, r8d
0x14003c3f5  jmp     loc_14003C345
0x14003c3fa  mov     r15, [r12+18h]
0x14003c3ff  test    r15, r15
0x14003c402  jnz     short loc_14003C47C
0x14003c404  mov     cl, 2; NewIrql
0x14003c406  call    cs:__imp_KfRaiseIrql
0x14003c40d  nop     dword ptr [rax+rax+00h]
0x14003c412  lea     rcx, qword_14022A190; SpinLock
0x14003c419  movzx   edi, al
0x14003c41c  call    RtlAcquireReadLockAtDpcLevel
0x14003c421  mov     r15, cs:qword_14022A210
0x14003c428  test    r15, r15
0x14003c42b  jz      short loc_14003C45D
0x14003c42d  mov     eax, gs:1A4h
0x14003c435  xor     edx, edx
0x14003c437  mov     r8, [r15+10h]
0x14003c43b  div     dword ptr [r8+14h]
0x14003c43f  mov     eax, 2
0x14003c444  imul    edx, [r8+10h]
  ... truncated ...
```
