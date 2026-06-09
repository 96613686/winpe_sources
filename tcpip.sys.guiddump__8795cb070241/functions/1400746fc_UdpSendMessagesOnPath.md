# UdpSendMessagesOnPath

- ea: `0x1400746fc`
- end: `0x140074f23`
- name: `UdpSendMessagesOnPath`
- size: `2087`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400736f0`

## callees

- `0x140003490`
- `0x140003c60`
- `0x140004070`
- `0x140005410`
- `0x140005c40`
- `0x140016814`
- `0x140018578`
- `0x14001ea80`
- `0x14001eb30`
- `0x140044e10`
- `0x140049760`
- `0x140057040`
- `0x14005cb70`
- `0x140071ac0`
- `0x140072c40`
- `0x1400746fc`
- `0x1400b4570`
- `0x1400cd2c0`
- `0x1400edb70`
- `0x1400ff528`
- `0x140110de0`
- `0x140116a78`
- `0x140121ac8`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!PsGetProcessStartKey` at `0x140074c22`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401cad7d`
- `ntoskrnl!PsGetProcessStartKey` at `0x140074c22`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401cad7d`
- `ntoskrnl!PsGetProcessId` at `0x140074bfd`
- `ntoskrnl!PsGetProcessId` at `0x1401cad34`
- `ntoskrnl!PsGetProcessId` at `0x140074bfd`
- `ntoskrnl!PsGetProcessId` at `0x1401cad34`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140074de8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140074de8`
- `NETIO!RtlCompute37Hash` at `0x140074e22`
- `NETIO!RtlCompute37Hash` at `0x140074e39`
- `NETIO!RtlCompute37Hash` at `0x140074e51`
- `NETIO!RtlCompute37Hash` at `0x140074e22`
- `NETIO!RtlCompute37Hash` at `0x140074e39`
- `NETIO!RtlCompute37Hash` at `0x140074e51`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400747a8`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400747a8`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140074893`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140074893`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x140074f0f`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x140074f0f`

## pseudocode

```c
__int64 __fastcall UdpSendMessagesOnPath(
        int a1,
        char a2,
        __int64 NextHopFromPath,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        unsigned __int16 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        int a14,
        __int64 a15,
        __int64 a16)
{
  __int64 v17; // rsi
  __int64 v18; // r15
  __int64 v19; // rbx
  int PathInfoAf; // r12d
  char v21; // r12
  ADDRESS_FAMILY v22; // bx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  struct _KSPIN_LOCK_QUEUE *v26; // rax
  struct _KSPIN_LOCK_QUEUE *volatile Next; // r14
  __int64 v28; // rdx
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r10
  _QWORD *v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  struct _KSPIN_LOCK_QUEUE *volatile v36; // rdi
  __int64 v37; // rsi
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r9
  int v45; // edx
  unsigned __int8 ProcessId; // al
  __int64 v47; // rcx
  char v48; // bl
  UCHAR v49; // al
  char v50; // r8
  int v51; // r9d
  __int64 v52; // r10
  __int64 v53; // r11
  _QWORD *v54; // r14
  __int64 v55; // rbx
  unsigned int v56; // eax
  unsigned int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rcx
  ADDRESS_FAMILY *v61; // rbx
  __int64 v62; // r9
  int v63; // edx
  __int64 v64; // rax
  int v65; // esi
  int v66; // ebx
  int v67; // edx
  __int64 v68; // rdx
  __int64 v69; // rcx
  ADDRESS_FAMILY *v70; // r14
  ADDRESS_FAMILY v71; // cx
  int v72; // edi
  UCHAR v73; // al
  __int64 v74; // rdx
  int v75; // ebx
  __int64 v76; // rax
  char v77; // al
  bool v78; // zf
  char v79; // cl
  __int64 v80; // rcx
  ADDRESS_FAMILY *v81; // r14
  ADDRESS_FAMILY v82; // cx
  int v83; // edi
  UCHAR v84; // al
  __int64 v85; // rdx
  int v86; // ebx
  __int64 v87; // rax
  int v88; // edx
  __int64 v89; // rcx
  ADDRESS_FAMILY *v90; // r14
  ADDRESS_FAMILY v91; // cx
  int v92; // edi
  UCHAR v93; // al
  __int64 v94; // rdx
  int v95; // ebx
  __int64 v96; // rax
  char v97; // al
  int v98; // [rsp+20h] [rbp-100h]
  char v99; // [rsp+50h] [rbp-D0h]
  int v100; // [rsp+58h] [rbp-C8h]
  int v101; // [rsp+60h] [rbp-C0h]
  int v102; // [rsp+70h] [rbp-B0h]
  unsigned int v104; // [rsp+A8h] [rbp-78h]
  __int64 v105; // [rsp+B0h] [rbp-70h]
  int v106; // [rsp+BCh] [rbp-64h] BYREF
  int v107; // [rsp+C0h] [rbp-60h] BYREF
  unsigned int v108; // [rsp+C4h] [rbp-5Ch]
  __int64 v109; // [rsp+C8h] [rbp-58h] BYREF
  int v110; // [rsp+D0h] [rbp-50h]
  int v111; // [rsp+D4h] [rbp-4Ch] BYREF
  int v112; // [rsp+D8h] [rbp-48h]
  __int64 v113; // [rsp+E0h] [rbp-40h]
  __int64 v114; // [rsp+E8h] [rbp-38h]
  ADDRESS_FAMILY *v115; // [rsp+F0h] [rbp-30h]
  __int64 v116; // [rsp+F8h] [rbp-28h]
  __int64 v117; // [rsp+100h] [rbp-20h]
  __int64 v118; // [rsp+108h] [rbp-18h]
  _QWORD v119[17]; // [rsp+110h] [rbp-10h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+1A0h] [rbp+80h] BYREF
  __int128 v121; // [rsp+1B8h] [rbp+98h] BYREF

  v17 = (__int64)a5;
  v18 = NextHopFromPath;
  v19 = a7;
  PathInfoAf = a1;
  v117 = a13;
  v118 = a6;
  v116 = a9;
  v114 = a12;
  *(_QWORD *)&v121 = a5;
  v105 = a7;
  v107 = 0;
  if ( a1 < 0 )
    goto LABEL_36;
  if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
  {
    v39 = *a5;
    if ( *(_BYTE *)(*(_QWORD *)(*a5 + 8) + 88LL) )
    {
      LODWORD(v39) = HIDWORD(KeGetPcr()[1].LockArray);
      PathInfoAf = -1073741634;
      v40 = 320 * v39;
      ++*((_QWORD *)TcpipGlobalCounters + 40 * v39 + 10);
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) >= 0 )
      {
LABEL_36:
        v36 = 0;
        goto LABEL_27;
      }
      v58 = *(_QWORD *)(v18 + 40);
      LOBYTE(v40) = v58 != a4;
      v59 = InetFormatLocalSockAddrAtDispatchLevel(v58, v40, *(_QWORD *)(v18 + 104), *(unsigned __int16 *)(v18 + 168));
      v60 = *(_QWORD *)(v18 + 40);
      v61 = (ADDRESS_FAMILY *)v59;
      v62 = a5[2];
      v114 = v59;
      LOBYTE(v63) = v60 != a4;
      v64 = InetFormatSockAddrAtDispatchLevel(*(unsigned __int16 *)(v60 + 24), v63, 1, v62, *((_DWORD *)a5 + 2), a8);
      v109 = v64;
      if ( dword_1402241D4 )
      {
        LockHandle.LockQueue = 0;
        if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
        {
          PsGetProcessId(*(PEPROCESS *)(v18 + 48));
          LockHandle.LockQueue.Lock = 0;
          LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)v18;
          v65 = SOCKADDR_SIZE(*(_WORD *)v109);
          v66 = SOCKADDR_SIZE(*v61);
          PsGetProcessStartKey(*(_QWORD *)(v18 + 48));
          McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            v67,
            (unsigned int)&LockHandle,
            2,
            v18,
            v66,
            v114,
            v65,
            v109);
          v17 = v121;
        }
      }
LABEL_72:
      v19 = v105;
      goto LABEL_36;
    }
  }
  if ( a14 )
  {
    PathInfoAf = UdpParseAncillaryData(v18, *(unsigned __int16 *)(a4 + 24), v117, a14, a16);
    if ( PathInfoAf < 0 )
      goto LABEL_36;
  }
  v21 = a2;
  v22 = 23;
  if ( a2 )
  {
    NextHopFromPath = a7;
  }
  else if ( (*(_DWORD *)(v18 + 24) & 0x80u) == 0 || *(_DWORD *)(a16 + 8) )
  {
    memset(v119, 0, sizeof(v119));
    v106 = 0;
    PathInfoAf = InetQueryPathInfoAf(a4, (_DWORD)a5, v114, (unsigned int)v119, (__int64)&v106);
    if ( PathInfoAf < 0 )
    {
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        v69 = *(_QWORD *)(v18 + 40);
        LOBYTE(v68) = v69 != a4;
        v70 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v69 + 24),
                                  v68,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402241D4 )
        {
          LockHandle.LockQueue = 0;
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            if ( (*(_DWORD *)(v18 + 24) & 0x20) == 0 )
              v22 = *(_WORD *)(*(_QWORD *)(v18 + 40) + 24LL);
            v71 = *v70;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)v18;
            v72 = SOCKADDR_SIZE(v71);
            v73 = SOCKADDR_SIZE(v22);
            LOBYTE(v74) = (_DWORD)v74 != 0;
            v75 = v73;
            v76 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(v18 + 40),
                    v74,
                    *(_QWORD *)(v18 + 104),
                    *(unsigned __int16 *)(v18 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_SEND_MESSAGES_PATH_AF_FAILURE,
              (unsigned int)&LockHandle,
              v18,
              v75,
              v76,
              v72,
              (__int64)v70,
              PathInfoAf);
          }
        }
      }
      goto LABEL_72;
    }
    v77 = (LOBYTE(v119[15]) != 0 ? 2 : 0) | *(_BYTE *)(a16 + 26) & 0xFD;
    v78 = v106 == 0;
    *(_BYTE *)(a16 + 26) = v77;
    if ( !v78 || *(_WORD *)(a4 + 24) == 23 && BYTE1(v119[15]) )
      v79 = 4;
    else
      v79 = 0;
    NextHopFromPath = v119[14];
    v105 = v119[14];
    *(_BYTE *)(a16 + 26) = v79 | v77 & 0xFB;
    if ( !NextHopFromPath )
    {
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        v80 = *(_QWORD *)(v18 + 40);
        LOBYTE(v68) = v80 != a4;
        v81 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v80 + 24),
                                  v68,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402241D4 )
        {
          LockHandle.LockQueue = 0;
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            if ( (*(_DWORD *)(v18 + 24) & 0x20) == 0 )
              v22 = *(_WORD *)(*(_QWORD *)(v18 + 40) + 24LL);
            v82 = *v81;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)v18;
            v83 = SOCKADDR_SIZE(v82);
            v84 = SOCKADDR_SIZE(v22);
            LOBYTE(v85) = (_DWORD)v85 != 0;
            v86 = v84;
            v87 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(v18 + 40),
                    v85,
                    *(_QWORD *)(v18 + 104),
                    *(unsigned __int16 *)(v18 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_SEND_MESSAGES_PATH_NEXT_HOP_MISSING_FAILURE,
              (unsigned int)&LockHandle,
              v18,
              v86,
              v87,
              v83,
              (__int64)v81,
              0);
          }
        }
      }
      PathInfoAf = -1073741251;
      goto LABEL_72;
    }
    if ( (*(_DWORD *)(v18 + 24) & 0x80u) == 0 && (unsigned int)NlppNextHopAddressType(NextHopFromPath, v68) == 4 )
    {
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        v89 = *(_QWORD *)(v18 + 40);
        LOBYTE(v88) = v89 != a4;
        v90 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v89 + 24),
                                  v88,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402241D4 )
        {
          LockHandle.LockQueue = 0;
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            if ( (*(_DWORD *)(v18 + 24) & 0x20) == 0 )
              v22 = *(_WORD *)(*(_QWORD *)(v18 + 40) + 24LL);
            v91 = *v90;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)v18;
            v92 = SOCKADDR_SIZE(v91);
            v93 = SOCKADDR_SIZE(v22);
            LOBYTE(v94) = (_DWORD)v94 != 0;
            v95 = v93;
            v96 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(v18 + 40),
                    v94,
                    *(_QWORD *)(v18 + 104),
                    *(unsigned __int16 *)(v18 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_SEND_MESSAGES_PATH_NEXT_HOP_ADDR_FAILURE,
              (unsigned int)&LockHandle,
              v18,
              v95,
              v96,
              v92,
              (__int64)v90,
              0);
          }
        }
      }
      PathInfoAf = -1073741790;
      goto LABEL_72;
    }
    v21 = 0;
  }
  else
  {
    NextHopFromPath = InetGetNextHopFromPath(a4, a5);
    v105 = NextHopFromPath;
  }
  v23 = *(unsigned int *)(a16 + 8);
  v24 = 65527;
  if ( *(_WORD *)(a4 + 24) != 23 )
    v24 = 65507;
  if ( v23 > v24 )
  {
    PathInfoAf = -1073741811;
    goto LABEL_72;
  }
  v106 = 0;
  if ( (_DWORD)v23 )
  {
    v97 = *(_BYTE *)(a16 + 26);
    if ( (v97 & 1) == 0 )
    {
      UdpQueryOffloadSupport(v18, a4, (_DWORD)a5, NextHopFromPath, a8, (v97 & 4) != 0, a16 + 8);
      if ( *(_DWORD *)(a16 + 16) )
      {
        if ( !v21 )
          *(_WORD *)(a16 + 24) = InetChecksumPseudoHeaderAf(a4, **(_QWORD **)(*a5 + 16), a5[2], 17);
      }
    }
  }
  if ( (*(_DWORD *)(v18 + 24) & 0x40) == 0 || *(_WORD *)(a4 + 24) == 23 )
  {
    LOWORD(v112) = 6;
  }
  else
  {
    v112 = 0xFFFF;
    *(_WORD *)(a16 + 24) = 0;
  }
  v25 = *(unsigned __int16 *)(v18 + 168);
  LOWORD(v107) = *(_WORD *)(v18 + 168);
  HIWORD(v107) = a8;
  if ( v21 )
  {
    v110 = *(_DWORD *)(v18 + 284);
    if ( *(_WORD *)(a4 + 24) == 23 )
      v106 = *(_DWORD *)(v18 + 320);
  }
  else
  {
    v110 = *((_DWORD *)a5 + 3)
         ^ (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD))UdpRssHash + 1))(
             *(unsigned __int16 *)(a4 + 24),
             v25,
             a8);
    if ( *(_WORD *)(a4 + 24) == 23 )
    {
      v56 = RtlCompute37Hash(*(unsigned int *)(v18 + 324), *(_QWORD *)(*a5 + 16), *(unsigned __int16 *)(a4 + 72));
      v57 = RtlCompute37Hash(v56, a5 + 2, *(unsigned __int16 *)(a4 + 72));
      v106 = RtlCompute37Hash(v57, (char *)&v107 + 2, 2);
    }
  }
  v26 = (struct _KSPIN_LOCK_QUEUE *)NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData(
                                      qword_1402286E8,
                                      80,
                                      8,
                                      64,
                                      UdpSendMessagesDatagramsComplete,
                                      0);
  LockHandle.LockQueue.Next = v26;
  Next = v26;
  v109 = (__int64)v26;
  v28 = (__int64)v26;
  if ( !v26 )
  {
    PathInfoAf = -1073741670;
    goto LABEL_72;
  }
  *(_QWORD *)&v121 = &v26->Lock;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v29 = a15;
    if ( a15 )
    {
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        TcpipEtwTransferActivity(a15, v18, 11);
        v28 = v109;
      }
      NextHopFromPath = 26;
    }
    else
    {
      v29 = v18;
      NextHopFromPath = 27;
    }
  }
  else
  {
    NextHopFromPath = 0;
    v29 = 0;
  }
  v30 = *(_QWORD *)(v28 + 16);
  PathInfoAf = 0;
  v108 = NextHopFromPath;
  v111 = 0;
  v31 = *(unsigned __int16 *)(v30 + 10);
  v32 = v31 + v30 + 24;
  v113 = v32;
  *(_QWORD *)(v31 + v30 + 16) = v32;
  *(_QWORD *)v32 = a10;
  *(_QWORD *)(v32 + 8) = a11;
  *(_QWORD *)(v32 + 16) = v18;
  *(_QWORD *)(v32 + 24) = 0;
  *(_QWORD *)(v32 + 32) = v28;
  *(_QWORD *)(v32 + 40) = 1;
  *(_DWORD *)(v32 + 48) = 0;
  *(_DWORD *)(v32 + 52) = *(_DWORD *)a16;
  v33 = (_QWORD *)v116;
  LODWORD(v28) = HIDWORD(KeGetPcr()[1].LockArray);
  v104 = v28;
  if ( v116 )
  {
    v54 = (_QWORD *)v116;
    do
    {
      PathInfoAf = UdpSegmentMessage(
                     (_DWORD)v54,
                     v32,
                     (unsigned int)&v109,
                     (unsigned int)&v121,
                     v18,
                     a4,
                     *(_WORD *)(v18 + 168),
                     a8,
                     v110,
                     a16,
                     v54 == v33,
                     *((_BYTE *)a5 + 40) >> 7,
                     (__int64)&v111,
                     v28,
                     v29,
                     NextHopFromPath);
      if ( PathInfoAf < 0 )
        break;
      v54 = (_QWORD *)*v54;
      LODWORD(v32) = v113;
      NextHopFromPath = v108;
      v28 = v104;
      v33 = (_QWORD *)v116;
    }
    while ( v54 );
    Next = LockHandle.LockQueue.Next;
  }
  if ( (volatile PKSPIN_LOCK *)v121 == &Next->Lock )
  {
    v19 = v105;
    v36 = Next;
    HIDWORD(Next[8].Lock) = PathInfoAf;
  }
  else
  {
    if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) >= 0 )
      goto LABEL_21;
    v41 = *(_QWORD *)(v18 + 40);
    LOBYTE(v28) = v41 != a4;
    v42 = InetFormatLocalSockAddrAtDispatchLevel(v41, v28, *(_QWORD *)(v18 + 104), *(unsigned __int16 *)(v18 + 168));
    v43 = *(_QWORD *)(v18 + 40);
    v44 = a5[2];
    LOBYTE(v45) = v43 != a4;
    LODWORD(v43) = *(unsigned __int16 *)(v43 + 24);
    v98 = *((_DWORD *)a5 + 2);
    v115 = (ADDRESS_FAMILY *)v42;
    LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)InetFormatSockAddrAtDispatchLevel(
                                                                      v43,
                                                                      v45,
                                                                      1,
                                                                      v44,
                                                                      v98,
                                                                      a8);
    if ( !dword_1402241D4 )
      goto LABEL_21;
    v121 = 0;
    if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(v18 + 48));
      v47 = *(_QWORD *)(v18 + 48);
      v48 = ProcessId;
      v121 = (unsigned __int64)v18;
      PsGetProcessStartKey(v47);
      SOCKADDR_SIZE((ADDRESS_FAMILY)LockHandle.LockQueue.Next->Next);
      v49 = SOCKADDR_SIZE(*v115);
      v99 = v48;
      v34 = v113;
      McTemplateK0pqqqbr3qbr5qx_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)UDP_ENDPOINT_SEND_MESSAGES_V1,
        (unsigned int)&v121,
        v18,
        v111,
        *(_DWORD *)(v113 + 24),
        v49,
        v52,
        v51,
        v53,
        v99,
        v50);
    }
    else
    {
LABEL_21:
      v34 = v113;
    }
    if ( qword_1402284F8 )
      InetTraceBasicDataCore(&UdpInetTransport, 2058, *(_QWORD *)(v18 + 48));
    if ( (*(_BYTE *)(a16 + 4) & 1) != 0 )
      *(_DWORD *)(v109 + 128) |= 0x10000u;
    v35 = *(_QWORD *)(v34 + 24);
    v19 = v105;
    LOWORD(v102) = *(_WORD *)(a16 + 24);
    LOWORD(v101) = 0;
    LOWORD(v100) = v112;
    InetFastSendDatagramsOnPathAf(
      a4,
      Next,
      v117 & -(__int64)((*(_BYTE *)(a16 + 26) & 8) != 0),
      a14 & (unsigned int)-((*(_BYTE *)(a16 + 26) & 8) != 0),
      v114,
      a5,
      v105,
      17,
      *(_QWORD *)(v18 + 72),
      &v107,
      8,
      v100,
      v101,
      0,
      v102,
      v106,
      1,
      a2,
      *(_QWORD *)(v18 + 48),
      v35);
    PathInfoAf = 259;
    v36 = Next;
  }
LABEL_27:
  if ( v17 )
    InetLeavePathAf(a4, v17, NextHopFromPath);
  if ( v19 )
    InetDereferenceNextHopAf(a4);
  v37 = v118;
  if ( v118 )
  {
    if ( PathInfoAf == 259 && v118 != *(_QWORD *)(v18 + 104) )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      RtlAcquireWriteLock(v18, &LockHandle);
      v55 = *(_QWORD *)(v18 + 104);
      *(_QWORD *)(v18 + 104) = v37;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v37 = v55;
    }
    InetDereferenceLocalAddressAf(*(_QWORD *)(v18 + 112), v37);
  }
  if ( a4 != *(_QWORD *)(v18 + 112) && a4 )
    InetDereferenceAf(a4);
  if ( PathInfoAf != 259 )
  {
    if ( v36 )
    {
      NetioDereferenceNetBufferListChain(v36, 0);
      return 259;
    }
    else
    {
      UdpDereferenceEndpoint(v18);
    }
  }
  return (unsigned int)PathInfoAf;
}

```

## disassembly

```asm
0x1400746fc  mov     [rsp-8+arg_0], rbx
0x140074701  push    rbp
0x140074702  push    rsi
0x140074703  push    rdi
0x140074704  push    r12
0x140074706  push    r13
0x140074708  push    r14
0x14007470a  push    r15
0x14007470c  lea     rbp, [rsp-0B0h]
0x140074714  sub     rsp, 1D0h
0x14007471b  mov     rax, cs:__security_cookie
0x140074722  xor     rax, rsp
0x140074725  mov     [rbp+0E0h+var_38], rax
0x14007472c  mov     rax, [rbp+0E0h+arg_60]
0x140074733  mov     r13, r9
0x140074736  mov     rsi, [rbp+0E0h+arg_20]
0x14007473d  mov     r15, r8
0x140074740  mov     rbx, [rbp+0E0h+arg_30]
0x140074747  mov     r12d, ecx
0x14007474a  movzx   r14d, [rbp+0E0h+arg_38]
0x140074752  mov     rdi, [rbp+0E0h+arg_78]
0x140074759  mov     [rbp+0E0h+var_100], rax
0x14007475d  mov     rax, [rbp+0E0h+arg_28]
0x140074764  mov     [rbp+0E0h+var_F8], rax
0x140074768  mov     rax, [rbp+0E0h+arg_40]
0x14007476f  mov     [rbp+0E0h+var_108], rax
0x140074773  mov     rax, [rbp+0E0h+arg_58]
0x14007477a  mov     [rbp+0E0h+var_118], rax
0x14007477e  mov     [rbp+0E0h+var_160], dl
0x140074781  mov     qword ptr [rbp+0E0h+var_48], rsi
0x140074788  mov     [rbp+0E0h+var_150], rbx
0x14007478c  mov     [rbp+0E0h+var_148], r14w
0x140074791  mov     [rbp+0E0h+var_158], 0
0x140074799  mov     [rbp+0E0h+var_140], 0
0x1400747a0  test    ecx, ecx
0x1400747a2  js      loc_140074B34
0x1400747a8  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x1400747af  nop     dword ptr [rax+rax+00h]
0x1400747b4  test    al, al
0x1400747b6  jnz     loc_140074B3D
0x1400747bc  mov     eax, [rbp+0E0h+arg_68]
0x1400747c2  test    eax, eax
0x1400747c4  jnz     loc_140074B10
0x1400747ca  mov     r12b, [rbp+0E0h+var_160]
0x1400747ce  mov     ebx, 17h
0x1400747d3  test    r12b, r12b
0x1400747d6  jz      loc_140074CBF
0x1400747dc  mov     r8, [rbp+0E0h+var_150]
0x1400747e0  cmp     [r13+18h], bx
0x1400747e5  lea     rdx, [rdi+8]
0x1400747e9  mov     ecx, [rdx]
0x1400747eb  mov     eax, 0FFF7h
0x1400747f0  lea     r9d, [rax-14h]
0x1400747f4  cmovnz  eax, r9d
0x1400747f8  cmp     rcx, rax
0x1400747fb  ja      loc_140074E65
0x140074801  mov     [rbp+0E0h+var_144], 0
0x140074808  test    ecx, ecx
0x14007480a  jnz     loc_1401CB137
0x140074810  mov     eax, [r15+18h]
0x140074814  test    al, 40h
0x140074816  jnz     loc_140074E70
0x14007481c  mov     eax, 6
0x140074821  mov     word ptr [rbp+0E0h+var_128], ax
0x140074825  movzx   edx, word ptr [r15+0A8h]
0x14007482d  mov     word ptr [rbp+0E0h+var_140], dx
0x140074831  mov     word ptr [rbp+0E0h+var_140+2], r14w
0x140074836  test    r12b, r12b
0x140074839  jnz     loc_140074D89
0x14007483f  mov     rax, cs:UdpRssHash
0x140074846  movzx   r8d, r14w
0x14007484a  movzx   ecx, word ptr [r13+18h]
0x14007484f  mov     rax, [rax+8]
0x140074853  call    _guard_dispatch_icall
0x140074858  xor     eax, [rsi+0Ch]
0x14007485b  mov     [rbp+0E0h+var_130], eax
0x14007485e  cmp     [r13+18h], bx
0x140074863  jz      loc_140074E0F
0x140074869  mov     rcx, cs:qword_1402286E8
0x140074870  lea     rax, UdpSendMessagesDatagramsComplete
0x140074877  mov     r9d, 40h ; '@'
0x14007487d  mov     [rsp+200h+var_1D8], 0
0x140074886  mov     [rsp+200h+var_1E0], rax
0x14007488b  lea     edx, [r9+10h]
0x14007488f  lea     r8d, [r9-38h]
0x140074893  call    cs:__imp_NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData
0x14007489a  nop     dword ptr [rax+rax+00h]
0x14007489f  mov     [rbp+0E0h+LockHandle.LockQueue.Next], rax
0x1400748a6  mov     r14, rax
0x1400748a9  mov     [rbp+0E0h+var_138], rax
0x1400748ad  mov     rdx, rax
0x1400748b0  test    rax, rax
0x1400748b3  jz      loc_140074E8D
0x1400748b9  add     rax, 8
0x1400748bd  mov     qword ptr [rbp+0E0h+var_48], rax
0x1400748c4  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400748ca  test    eax, eax
0x1400748cc  jnz     loc_140074E98
0x1400748d2  xor     r8d, r8d
0x1400748d5  xor     ebx, ebx
0x1400748d7  mov     rcx, [rdx+10h]
0x1400748db  xor     r12d, r12d
0x1400748de  mov     [rbp+0E0h+var_13C], r8d
0x1400748e2  mov     [rbp+0E0h+var_12C], r12d
0x1400748e6  movzx   eax, word ptr [rcx+0Ah]
0x1400748ea  lea     r10, [rcx+18h]
0x1400748ee  add     r10, rax
0x1400748f1  mov     [rbp+0E0h+var_120], r10
0x1400748f5  mov     [rax+rcx+10h], r10
0x1400748fa  mov     rax, [rbp+0E0h+arg_48]
0x140074901  mov     [r10], rax
0x140074904  mov     rax, [rbp+0E0h+arg_50]
0x14007490b  mov     [r10+8], rax
0x14007490f  mov     [r10+10h], r15
0x140074913  mov     qword ptr [r10+18h], 0
0x14007491b  mov     [r10+20h], rdx
0x14007491f  mov     qword ptr [r10+28h], 1
0x140074927  mov     dword ptr [r10+30h], 0
0x14007492f  mov     eax, [rdi]
0x140074931  mov     [r10+34h], eax
0x140074935  mov     rax, [rbp+0E0h+var_108]
0x140074939  mov     edx, gs:1A4h
0x140074941  mov     dword ptr [rbp+0E0h+var_158], edx
0x140074944  test    rax, rax
0x140074947  jnz     loc_140074D02
0x14007494d  lea     rax, [r14+8]
0x140074951  cmp     qword ptr [rbp+0E0h+var_48], rax
0x140074958  jz      loc_140074DFC
0x14007495e  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 0
0x140074965  jl      loc_140074B7E
0x14007496b  movzx   r12d, [rbp+0E0h+var_148]
0x140074970  mov     rbx, [rbp+0E0h+var_120]
0x140074974  mov     rax, cs:qword_1402284F8
0x14007497b  test    rax, rax
0x14007497e  jnz     loc_140074ABD
0x140074984  test    byte ptr [rdi+4], 1
0x140074988  jnz     loc_140074EF0
0x14007498e  mov     cl, [rdi+1Ah]
0x140074991  xor     edx, edx
0x140074993  and     cl, 8
0x140074996  mov     al, cl
0x140074998  neg     al
0x14007499a  mov     rax, [rbx+18h]
0x14007499e  mov     rbx, [rbp+0E0h+var_150]
0x1400749a2  sbb     r9d, r9d
0x1400749a5  and     r9d, [rbp+0E0h+arg_68]
0x1400749ac  mov     [rsp+200h+var_168], rax
0x1400749b4  neg     cl
0x1400749b6  mov     rax, [r15+30h]
0x1400749ba  mov     rcx, r13
0x1400749bd  mov     [rsp+200h+var_170], rax
0x1400749c5  sbb     r8, r8
0x1400749c8  mov     al, [rbp+0E0h+var_160]
0x1400749cb  and     r8, [rbp+0E0h+var_100]
0x1400749cf  mov     [rsp+200h+var_178], al
0x1400749d6  mov     eax, [rbp+0E0h+var_144]
0x1400749d9  mov     [rsp+200h+var_180], 1
0x1400749e1  mov     [rsp+200h+var_188], eax
0x1400749e5  movzx   eax, word ptr [rdi+18h]
0x1400749e9  mov     word ptr [rsp+200h+var_190], ax
0x1400749ee  mov     eax, [rbp+0E0h+var_128]
0x1400749f1  mov     [rsp+200h+var_198], edx
0x1400749f5  mov     word ptr [rsp+200h+var_1A0], dx
0x1400749fa  mov     rdx, r14
0x1400749fd  mov     word ptr [rsp+200h+var_1A8], ax
0x140074a02  lea     rax, [rbp+0E0h+var_140]
0x140074a06  mov     dword ptr [rsp+200h+var_1B0], 8
0x140074a0e  mov     [rsp+200h+var_1B8], rax
0x140074a13  mov     rax, [r15+48h]
0x140074a17  mov     [rsp+200h+var_1C0], rax
0x140074a1c  mov     rax, [rbp+0E0h+var_118]
0x140074a20  mov     dword ptr [rsp+200h+var_1C8], 11h
0x140074a28  mov     [rsp+200h+var_1D0], rbx
0x140074a2d  mov     [rsp+200h+var_1D8], rsi
0x140074a32  mov     [rsp+200h+var_1E0], rax
0x140074a37  call    InetFastSendDatagramsOnPathAf
0x140074a3c  mov     r12d, 103h
0x140074a42  mov     rdi, r14
0x140074a45  test    rsi, rsi
0x140074a48  jnz     short loc_140074AA3
0x140074a4a  test    rbx, rbx
0x140074a4d  jnz     short loc_140074AB0
0x140074a4f  mov     rsi, [rbp+0E0h+var_F8]
0x140074a53  mov     r14d, 103h
0x140074a59  test    rsi, rsi
0x140074a5c  jnz     loc_140074CA5
0x140074a62  cmp     r13, [r15+70h]
0x140074a66  jnz     loc_140074CEC
0x140074a6c  cmp     r12d, r14d
0x140074a6f  jnz     loc_140074F01
0x140074a75  mov     eax, r12d
0x140074a78  mov     rcx, [rbp+0E0h+var_38]
0x140074a7f  xor     rcx, rsp; StackCookie
0x140074a82  call    __security_check_cookie
0x140074a87  mov     rbx, [rsp+200h+arg_0]
0x140074a8f  add     rsp, 1D0h
0x140074a96  pop     r15
0x140074a98  pop     r14
0x140074a9a  pop     r13
0x140074a9c  pop     r12
0x140074a9e  pop     rdi
0x140074a9f  pop     rsi
0x140074aa0  pop     rbp
0x140074aa1  retn
0x140074aa3  mov     rdx, rsi
0x140074aa6  mov     rcx, r13
0x140074aa9  call    InetLeavePathAf
0x140074aae  jmp     short loc_140074A4A
0x140074ab0  mov     rdx, rbx
0x140074ab3  mov     rcx, r13
0x140074ab6  call    InetDereferenceNextHopAf
0x140074abb  jmp     short loc_140074A4F
0x140074abd  mov     rax, [rsi]
0x140074ac0  mov     edx, 80Ah
0x140074ac5  mov     r9d, [rbx+18h]
0x140074ac9  mov     r8, [r15+30h]
0x140074acd  mov     word ptr [rsp+200h+var_1C0], r12w
0x140074ad3  mov     rcx, [rax+10h]
0x140074ad7  movzx   eax, word ptr [r15+0A8h]
0x140074adf  mov     word ptr [rsp+200h+var_1C8], ax
0x140074ae4  mov     rax, [rsi+10h]
0x140074ae8  mov     [rsp+200h+var_1D0], rax
0x140074aed  mov     rax, [rcx]
0x140074af0  lea     rcx, UdpInetTransport
0x140074af7  mov     [rsp+200h+var_1D8], rax
0x140074afc  movzx   eax, word ptr [r13+18h]
0x140074b01  mov     word ptr [rsp+200h+var_1E0], ax
0x140074b06  call    InetTraceBasicDataCore
0x140074b0b  jmp     loc_140074984
0x140074b10  mov     r8, [rbp+0E0h+var_100]
0x140074b14  mov     r9d, eax
0x140074b17  movzx   edx, word ptr [r13+18h]
0x140074b1c  mov     rcx, r15
0x140074b1f  mov     [rsp+200h+var_1E0], rdi
0x140074b24  call    UdpParseAncillaryData
0x140074b29  mov     r12d, eax
0x140074b2c  test    eax, eax
0x140074b2e  jns     loc_1400747CA
0x140074b34  mov     rdi, [rbp+0E0h+var_158]
0x140074b38  jmp     loc_140074A45
0x140074b3d  mov     rax, [rsi]
0x140074b40  mov     rcx, [rax+8]
0x140074b44  cmp     byte ptr [rcx+58h], 0
0x140074b48  jz      loc_1400747BC
0x140074b4e  mov     eax, gs:1A4h
0x140074b56  mov     r12d, 0C00000BEh
0x140074b5c  lea     rdx, [rax+rax*4]
0x140074b60  mov     rax, cs:TcpipGlobalCounters
0x140074b67  shl     rdx, 6
0x140074b6b  inc     qword ptr [rdx+rax+50h]
0x140074b70  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x140074b77  jge     short loc_140074B34
0x140074b79  jmp     loc_1401CACBC
0x140074b7e  mov     rcx, [r15+28h]
0x140074b82  movzx   r9d, word ptr [r15+0A8h]
0x140074b8a  cmp     rcx, r13
0x140074b8d  mov     r8, [r15+68h]
0x140074b91  setnz   dl
0x140074b94  call    InetFormatLocalSockAddrAtDispatchLevel
0x140074b99  mov     rcx, [r15+28h]
0x140074b9d  mov     r8d, [rsi+8]
0x140074ba1  cmp     rcx, r13
0x140074ba4  movzx   r12d, [rbp+0E0h+var_148]
0x140074ba9  mov     r9, [rsi+10h]
0x140074bad  setnz   dl
0x140074bb0  movzx   ecx, word ptr [rcx+18h]
0x140074bb4  mov     word ptr [rsp+200h+var_1D8], r12w
0x140074bba  mov     dword ptr [rsp+200h+var_1E0], r8d
0x140074bbf  mov     r8d, 1
0x140074bc5  mov     [rbp+0E0h+var_110], rax
0x140074bc9  call    InetFormatSockAddrAtDispatchLevel
0x140074bce  cmp     cs:dword_1402241D4, 0
0x140074bd5  mov     [rbp+0E0h+LockHandle.LockQueue.Next], rax
0x140074bdc  jz      loc_140074970
0x140074be2  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 0
0x140074be9  xorps   xmm0, xmm0
0x140074bec  movups  [rbp+0E0h+var_48], xmm0
0x140074bf3  jge     loc_140074970
0x140074bf9  mov     rcx, [r15+30h]; Process
0x140074bfd  call    cs:__imp_PsGetProcessId
0x140074c04  nop     dword ptr [rax+rax+00h]
0x140074c09  mov     rcx, [r15+30h]
0x140074c0d  mov     rbx, rax
0x140074c10  mov     qword ptr [rbp+0E0h+var_48+8], 0
0x140074c1b  mov     qword ptr [rbp+0E0h+var_48], r15
0x140074c22  call    cs:__imp_PsGetProcessStartKey
0x140074c29  nop     dword ptr [rax+rax+00h]
0x140074c2e  mov     r11, [rbp+0E0h+LockHandle.LockQueue.Next]
0x140074c35  mov     r8, rax
0x140074c38  movzx   ecx, word ptr [r11]; af
0x140074c3c  call    SOCKADDR_SIZE
0x140074c41  mov     r10, [rbp+0E0h+var_110]
0x140074c45  movzx   r9d, al
0x140074c49  movzx   ecx, word ptr [r10]; af
0x140074c4d  call    SOCKADDR_SIZE
0x140074c52  mov     [rsp+200h+var_1A8], r8
0x140074c57  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140074c5e  mov     dword ptr [rsp+200h+var_1B0], ebx
0x140074c62  lea     r8, [rbp+0E0h+var_48]
0x140074c69  mov     rbx, [rbp+0E0h+var_120]
  ... truncated ...
```
