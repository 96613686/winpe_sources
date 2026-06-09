# TcpSetSockOptEndpoint

- ea: `0x14003c1a0`
- end: `0x14003d06b`
- name: `TcpSetSockOptEndpoint`
- size: `3787`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003bc90`

## callees

- `0x1400329e0`
- `0x14003ae70`
- `0x14003c1a0`
- `0x14003d080`
- `0x140052630`
- `0x14005b8a0`
- `0x140061350`
- `0x140081590`
- `0x1400822b4`
- `0x140082f40`
- `0x1400951fc`
- `0x1400b42b0`
- `0x1400b5730`
- `0x1400e7280`
- `0x140111490`
- `0x140112d24`
- `0x140115880`
- `0x140120230`
- `0x14012406c`
- `0x140125470`
- `0x140127674`
- `0x140152fb4`
- `0x14015f97c`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14003c6a6`
- `ntoskrnl!KfRaiseIrql` at `0x14003c6a6`
- `ntoskrnl!KeLowerIrql` at `0x14003c708`
- `ntoskrnl!KeLowerIrql` at `0x14003c708`
- `ntoskrnl!IoFileObjectType` at `0x1401c3302`
- `ntoskrnl!KeBugCheck` at `0x14003c680`
- `ntoskrnl!KeBugCheck` at `0x14003c680`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003c9b4`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003cb9a`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003c9b4`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003cb9a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003c9c3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003cba9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003c9c3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003cba9`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c9e1`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003cbc7`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c9e1`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003cbc7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c5a7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c5a7`
- `ntoskrnl!RtlCompareMemory` at `0x14003d01d`
- `ntoskrnl!RtlCompareMemory` at `0x14003d01d`
- `ntoskrnl!PsGetProcessId` at `0x14003c7d2`
- `ntoskrnl!PsGetProcessId` at `0x14003c7d2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401c3329`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401c3329`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c33a7`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c33a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c2b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c564`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c626`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c731`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ccb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cce9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cdd1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ce59`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cf42`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cfa4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c3391`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c2b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c564`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c626`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c731`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ccb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cce9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cd4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cdd1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ce59`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cf42`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cfa4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c3391`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c22a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c74e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cc79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401c335f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c22a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c74e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cc79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401c335f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cbec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cbec`
- `ntoskrnl!ExAllocatePool2` at `0x14003c511`
- `ntoskrnl!ExAllocatePool2` at `0x14003c64a`
- `ntoskrnl!ExAllocatePool2` at `0x14003c511`
- `ntoskrnl!ExAllocatePool2` at `0x14003c64a`
- `NETIO!NetioInsertWorkQueue` at `0x14003ccd1`
- `NETIO!NetioInsertWorkQueue` at `0x14003ccd1`
- `NETIO!NetioNcmNotificationChannelContextRequest` at `0x14003c7ed`
- `NETIO!NetioNcmNotificationChannelContextRequest` at `0x14003c7ed`
- `NETIO!NetioNrtAssociateContext` at `0x1401c337d`
- `NETIO!NetioNrtAssociateContext` at `0x1401c337d`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401c3348`
- `NETIO!NetioNrtIsTrackerDevice` at `0x1401c3348`

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
        (unsigned int)&TCPIP_SETSOCKOPT,
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
        NetioInsertWorkQueue(&TcpPortReservationWorkQueue, v26);
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
    RtlAcquireReadLockAtDpcLevel(&qword_14022A110);
    v19 = qword_14022A190;
    if ( qword_14022A190 )
    {
      v34 = *(_QWORD *)(qword_14022A190 + 16);
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v34
                                        + (unsigned int)(*(_DWORD *)(v34 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v34 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v34 + 24), 2u);
    }
    _InterlockedDecrement(dword_14022A118);
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
0x14003c1a0  mov     [rsp-8+arg_8], rbx
0x14003c1a5  push    rbp
0x14003c1a6  push    rsi
0x14003c1a7  push    rdi
0x14003c1a8  push    r12
0x14003c1aa  push    r13
0x14003c1ac  push    r14
0x14003c1ae  push    r15
0x14003c1b0  lea     rbp, [rsp-50h]
0x14003c1b5  sub     rsp, 150h
0x14003c1bc  mov     rax, cs:__security_cookie
0x14003c1c3  xor     rax, rsp
0x14003c1c6  mov     [rbp+80h+var_40], rax
0x14003c1ca  cmp     cs:dword_1402201D4, 0
0x14003c1d1  mov     r14d, r9d
0x14003c1d4  mov     rax, [rbp+80h+arg_38]
0x14003c1db  mov     rsi, rcx
0x14003c1de  mov     r15, [rbp+80h+arg_28]
0x14003c1e5  mov     r12, [rbp+80h+arg_48]
0x14003c1ec  mov     ebx, [rbp+80h+arg_20]
0x14003c1f2  mov     rdi, [rbp+80h+arg_30]
0x14003c1f9  mov     [rsp+180h+var_138], rax
0x14003c1fe  mov     [rsp+180h+Source2], r15
0x14003c203  mov     [rsp+180h+var_110], r12
0x14003c208  mov     [rbp+80h+var_100], r8
0x14003c20c  mov     [rsp+180h+var_108], rdx
0x14003c211  jz      short loc_14003C227
0x14003c213  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x14003c21a  xorps   xmm0, xmm0
0x14003c21d  movups  [rbp+80h+var_50], xmm0
0x14003c221  jnz     loc_14003C8CB
0x14003c227  mov     rcx, rsi; SpinLock
0x14003c22a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003c231  nop     dword ptr [rax+rax+00h]
0x14003c236  mov     [rsp+180h+var_140], al
0x14003c23a  movzx   r13d, al
0x14003c23e  cmp     r14d, 6
0x14003c242  jz      loc_14003C4A5
0x14003c248  cmp     r14d, 0FFFFh
0x14003c24f  jz      loc_14003C80F
0x14003c255  cmp     r14d, 0FFFCh
0x14003c25c  jz      loc_14003C2E8
0x14003c262  cmp     r14d, 29h ; ')'
0x14003c266  jnz     loc_14003C3D6
0x14003c26c  cmp     ebx, 1Bh
0x14003c26f  jnz     loc_14003C3D6
0x14003c275  cmp     [rbp+80h+arg_30], 4
0x14003c27d  jb      loc_14003C90A
0x14003c283  mov     eax, [rsi+10h]
0x14003c286  test    al, 1
0x14003c288  jnz     loc_14003CC63
0x14003c28e  mov     eax, [r15]
0x14003c291  neg     eax
0x14003c293  movzx   eax, byte ptr [rsi+0CAh]
0x14003c29a  sbb     cl, cl
0x14003c29c  and     al, 0FDh
0x14003c29e  and     cl, 2
0x14003c2a1  or      cl, al
0x14003c2a3  mov     [rsi+0CAh], cl
0x14003c2a9  xor     edi, edi
0x14003c2ab  movzx   edx, r13b; NewIrql
0x14003c2af  mov     rcx, rsi; SpinLock
0x14003c2b2  call    cs:__imp_KeReleaseSpinLock
0x14003c2b9  nop     dword ptr [rax+rax+00h]
0x14003c2be  mov     eax, edi
0x14003c2c0  mov     rcx, [rbp+80h+var_40]
0x14003c2c4  xor     rcx, rsp; StackCookie
0x14003c2c7  call    __security_check_cookie
0x14003c2cc  mov     rbx, [rsp+180h+arg_8]
0x14003c2d4  add     rsp, 150h
0x14003c2db  pop     r15
0x14003c2dd  pop     r14
0x14003c2df  pop     r13
0x14003c2e1  pop     r12
0x14003c2e3  pop     rdi
0x14003c2e4  pop     rsi
0x14003c2e5  pop     rbp
0x14003c2e6  retn
0x14003c2e8  cmp     ebx, 98000004h
0x14003c2ee  jz      loc_14003C76A
0x14003c2f4  lea     eax, [rbx+67FFFFF0h]
0x14003c2fa  cmp     eax, 1
0x14003c2fd  jbe     loc_14003C76A
0x14003c303  cmp     ebx, 98000012h
0x14003c309  jz      loc_14003C72A
0x14003c30f  cmp     ebx, 9800012Ch
0x14003c315  jz      loc_14003C76A
0x14003c31b  cmp     ebx, 98000014h
0x14003c321  jz      loc_14003D061
0x14003c327  lea     eax, [rbx+67FFFFEAh]
0x14003c32d  cmp     eax, 2
0x14003c330  jbe     loc_14003C76A
0x14003c336  cmp     ebx, 980000E6h
0x14003c33c  jz      loc_14003C76A
0x14003c342  cmp     ebx, 98000013h
0x14003c348  jz      loc_14003CF97
0x14003c34e  cmp     ebx, 8800000Bh
0x14003c354  jz      loc_14003CD0D
0x14003c35a  cmp     ebx, 8800001Ah
0x14003c360  jz      loc_14003CD0D
0x14003c366  cmp     ebx, 98000022h
0x14003c36c  jz      loc_14003D03A
0x14003c372  lea     eax, [rbx+67FFFF38h]
0x14003c378  cmp     eax, 1Fh
0x14003c37b  ja      short loc_14003C38B
0x14003c37d  mov     ecx, 8040001Dh
0x14003c382  bt      ecx, eax
0x14003c385  jb      loc_14003CDCA
0x14003c38b  cmp     ebx, 0D80000C9h
0x14003c391  jz      loc_14003CDCA
0x14003c397  cmp     ebx, 580000CDh
0x14003c39d  jz      loc_14003CF3B
0x14003c3a3  lea     eax, [rbx+67FFFF9Ch]
0x14003c3a9  cmp     eax, 2
0x14003c3ac  jbe     loc_14003C501
0x14003c3b2  cmp     ebx, 580000D2h
0x14003c3b8  jz      loc_14003CCE2
0x14003c3be  cmp     ebx, 980000E8h
0x14003c3c4  jz      loc_14003CEC1
0x14003c3ca  cmp     ebx, 980000E9h
0x14003c3d0  jz      loc_14003CE52
0x14003c3d6  mov     ecx, [rsi+10h]
0x14003c3d9  xor     r8d, r8d
0x14003c3dc  mov     [rsp+180h+var_130], r8
0x14003c3e1  test    cl, 1
0x14003c3e4  jnz     loc_14003C8BA
0x14003c3ea  mov     rax, [rsi+20h]
0x14003c3ee  movzx   edx, word ptr [rax+18h]
0x14003c3f2  cmp     dx, 17h
0x14003c3f6  jnz     loc_14003C8C3
0x14003c3fc  test    byte ptr [rsi+0CAh], 2
0x14003c403  jnz     loc_14003C8C3
0x14003c409  mov     eax, r8d
0x14003c40c  mov     r15, [rsi+20h]
0x14003c410  lea     r12, [rsi+0D0h]
0x14003c417  and     ecx, 8
0x14003c41a  test    ax, ax
0x14003c41d  jnz     short loc_14003C43E
0x14003c41f  test    r14d, r14d
0x14003c422  jz      loc_14003C69A
0x14003c428  test    ecx, ecx
0x14003c42a  jz      short loc_14003C442
0x14003c42c  mov     r15, r8
0x14003c42f  mov     [rsp+180h+var_120], r8
0x14003c434  mov     edi, 0C0000010h
0x14003c439  jmp     loc_14003C5F8
0x14003c43e  test    ecx, ecx
0x14003c440  jnz     short loc_14003C41F
0x14003c442  lea     rax, [r12+8]
0x14003c447  mov     [rsp+180h+var_120], rax
0x14003c44c  test    r15, r15
0x14003c44f  jz      short loc_14003C434
0x14003c451  mov     rax, [r12]
0x14003c455  test    rax, rax
0x14003c458  jnz     loc_14003C68D
0x14003c45e  mov     rax, [r15+28h]
0x14003c462  lea     rcx, IpNlpInitializeSessionInfo
0x14003c469  mov     qword ptr [rbp+80h+var_50], rax
0x14003c46d  mov     rax, [r15+30h]
0x14003c471  mov     qword ptr [rbp+80h+var_50+8], r8
0x14003c475  mov     rax, [rax+0F0h]
0x14003c47c  cmp     rax, rcx
0x14003c47f  lea     rcx, [rbp+80h+var_50]
0x14003c483  jnz     loc_14003CDC0
0x14003c489  call    IpNlpInitializeSessionInfo
0x14003c48e  mov     edi, eax
0x14003c490  test    eax, eax
0x14003c492  jns     loc_14003C5D4
0x14003c498  mov     qword ptr [r12], 0
0x14003c4a0  jmp     loc_14003C5E1
0x14003c4a5  mov     r14, [rbp+80h+arg_30]
0x14003c4ac  lea     rcx, [rsi+0A8h]
0x14003c4b3  mov     r9, r14
0x14003c4b6  mov     [rsp+180h+Object], 0
0x14003c4bf  mov     r8, r15
0x14003c4c2  mov     edx, ebx
0x14003c4c4  call    TcpSetTcpLevelOption
0x14003c4c9  mov     edi, eax
0x14003c4cb  test    eax, eax
0x14003c4cd  js      loc_14003C2AB
0x14003c4d3  cmp     ebx, 12h
0x14003c4d6  jnz     loc_14003C2AB
0x14003c4dc  cmp     r14, 1
0x14003c4e0  jb      loc_14003C90A
0x14003c4e6  movzx   eax, byte ptr [r15]
0x14003c4ea  neg     al
0x14003c4ec  mov     eax, [rsi+10h]
0x14003c4ef  sbb     edx, edx
0x14003c4f1  and     eax, 0FFFFFFBFh
0x14003c4f4  and     edx, 40h
0x14003c4f7  or      edx, eax
0x14003c4f9  mov     [rsi+10h], edx
0x14003c4fc  jmp     loc_14003C2A9
0x14003c501  mov     edx, 50h ; 'P'
0x14003c506  mov     ecx, 40h ; '@'
0x14003c50b  mov     r8d, 57456354h
0x14003c511  call    cs:__imp_ExAllocatePool2
0x14003c518  nop     dword ptr [rax+rax+00h]
0x14003c51d  mov     rdi, rax
0x14003c520  test    rax, rax
0x14003c523  jz      loc_14003CEF2
0x14003c529  mov     [rax+8], rsi
0x14003c52d  mov     r12d, 1
0x14003c533  lock xadd [rsi+8], r12
0x14003c539  inc     r12
0x14003c53c  cmp     r12, 1
0x14003c540  jle     loc_14003C67B
0x14003c546  mov     rcx, cs:EndpointReferenceHistory
0x14003c54d  test    rcx, rcx
0x14003c550  jz      short loc_14003C55D
0x14003c552  mov     edx, r12d
0x14003c555  mov     r8, rsi
0x14003c558  call    RhAppendHistory
0x14003c55d  movzx   edx, r13b; NewIrql
0x14003c561  mov     rcx, rsi; SpinLock
0x14003c564  call    cs:__imp_KeReleaseSpinLock
0x14003c56b  nop     dword ptr [rax+rax+00h]
0x14003c570  mov     rax, [rsp+180h+var_108]
0x14003c575  mov     rdx, [rsp+180h+var_138]
0x14003c57a  mov     [rdi+10h], rax
0x14003c57e  mov     rax, [rbp+80h+var_100]
0x14003c582  mov     [rdi+18h], rax
0x14003c586  mov     rax, [rbp+80h+arg_30]
0x14003c58d  mov     [rdi+30h], rax
0x14003c591  mov     rax, [rbp+80h+arg_40]
0x14003c598  mov     [rdi+40h], rax
0x14003c59c  mov     [rdi+20h], ebx
0x14003c59f  mov     [rdi+28h], r15
0x14003c5a3  mov     [rdi+38h], rdx
0x14003c5a7  call    cs:__imp_KeGetCurrentIrql
0x14003c5ae  nop     dword ptr [rax+rax+00h]
0x14003c5b3  test    al, al
0x14003c5b5  jnz     loc_14003CCC7
0x14003c5bb  mov     rcx, rdi; P
0x14003c5be  mov     qword ptr [rdi], 0
0x14003c5c5  call    TcpPortReservationWorkQueueRoutine
0x14003c5ca  mov     edi, 103h
0x14003c5cf  jmp     loc_14003C2BE
0x14003c5d4  mov     rax, qword ptr [rbp+80h+var_50+8]
0x14003c5d8  mov     [rsp+180h+var_130], rax
0x14003c5dd  mov     [r12], rax
0x14003c5e1  test    edi, edi
0x14003c5e3  js      short loc_14003C5F8
0x14003c5e5  test    r14d, r14d
0x14003c5e8  jz      loc_14003C938
0x14003c5ee  cmp     r14d, 29h ; ')'
0x14003c5f2  jz      loc_14003C938
0x14003c5f8  mov     rax, [rsi+58h]
0x14003c5fc  mov     r12d, 1
0x14003c602  test    rax, rax
0x14003c605  jz      loc_14003CEE0
0x14003c60b  mov     ecx, [rax]
0x14003c60d  mov     [rsp+180h+var_128], ecx
0x14003c611  xor     ecx, ecx
0x14003c613  cmp     r15, [rsi+20h]
0x14003c617  cmovz   rcx, rax
0x14003c61b  mov     qword ptr [rbp+80h+var_50], rcx
0x14003c61f  movzx   edx, r13b; NewIrql
0x14003c623  mov     rcx, rsi; SpinLock
0x14003c626  call    cs:__imp_KeReleaseSpinLock
0x14003c62d  nop     dword ptr [rax+rax+00h]
0x14003c632  test    edi, edi
0x14003c634  js      loc_14003C2BE
0x14003c63a  mov     edx, 50h ; 'P'
0x14003c63f  mov     ecx, 40h ; '@'
0x14003c644  mov     r8d, 57456354h
0x14003c64a  call    cs:__imp_ExAllocatePool2
0x14003c651  nop     dword ptr [rax+rax+00h]
0x14003c656  mov     r13, rax
0x14003c659  test    rax, rax
0x14003c65c  jz      loc_14003C8B0
0x14003c662  mov     [rax+8], rsi
0x14003c666  mov     r8, r12
0x14003c669  lock xadd [rsi+8], r8
0x14003c66f  inc     r8
0x14003c672  cmp     r8, r12
0x14003c675  jg      loc_14003C95D
0x14003c67b  mov     ecx, 1Ch; BugCheckCode
0x14003c680  call    cs:__imp_KeBugCheck
0x14003c68d  mov     [rsp+180h+var_130], rax
0x14003c692  mov     edi, r8d
0x14003c695  jmp     loc_14003C5E5
0x14003c69a  mov     r15, [r12+18h]
0x14003c69f  test    r15, r15
0x14003c6a2  jnz     short loc_14003C71C
0x14003c6a4  mov     cl, 2; NewIrql
0x14003c6a6  call    cs:__imp_KfRaiseIrql
0x14003c6ad  nop     dword ptr [rax+rax+00h]
0x14003c6b2  lea     rcx, qword_14022A110; SpinLock
0x14003c6b9  movzx   edi, al
0x14003c6bc  call    RtlAcquireReadLockAtDpcLevel
0x14003c6c1  mov     r15, cs:qword_14022A190
0x14003c6c8  test    r15, r15
0x14003c6cb  jz      short loc_14003C6FD
0x14003c6cd  mov     eax, gs:1A4h
0x14003c6d5  xor     edx, edx
0x14003c6d7  mov     r8, [r15+10h]
0x14003c6db  div     dword ptr [r8+14h]
0x14003c6df  mov     eax, 2
0x14003c6e4  imul    edx, [r8+10h]
  ... truncated ...
```
