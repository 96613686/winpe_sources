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
        __int64 a3,
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
  __int64 v19; // rbx
  int PathInfoAf; // r12d
  char v21; // r12
  ADDRESS_FAMILY v22; // bx
  __int64 v23; // r8
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  struct _KSPIN_LOCK_QUEUE *v27; // rax
  struct _KSPIN_LOCK_QUEUE *volatile Next; // r14
  __int64 v29; // rdx
  int v30; // r8d
  __int64 v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r10
  _QWORD *v35; // rax
  unsigned __int16 v36; // r12
  __int64 v37; // rbx
  __int64 v38; // rax
  struct _KSPIN_LOCK_QUEUE *volatile v39; // rdi
  __int64 v40; // rsi
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // r9
  int v48; // edx
  unsigned __int8 ProcessId; // al
  __int64 v50; // rcx
  char v51; // bl
  UCHAR v52; // al
  char v53; // r8
  int v54; // r9d
  __int64 v55; // r10
  __int64 v56; // r11
  __int64 NextHopFromPath; // rax
  _QWORD *v58; // r14
  __int64 v59; // rbx
  unsigned int v60; // eax
  unsigned int v61; // eax
  __int64 v62; // rcx
  __int64 v63; // rax
  int v64; // edx
  __int64 v65; // rcx
  ADDRESS_FAMILY *v66; // rbx
  __int64 v67; // r9
  int v68; // esi
  int v69; // ebx
  int v70; // edx
  int v71; // edx
  __int64 v72; // rcx
  ADDRESS_FAMILY *v73; // r14
  ADDRESS_FAMILY v74; // cx
  int v75; // edi
  UCHAR v76; // al
  __int64 v77; // rdx
  int v78; // ebx
  __int64 v79; // rax
  char v80; // al
  bool v81; // zf
  char v82; // cl
  __int64 v83; // rcx
  ADDRESS_FAMILY *v84; // r14
  ADDRESS_FAMILY v85; // cx
  int v86; // edi
  UCHAR v87; // al
  __int64 v88; // rdx
  int v89; // ebx
  __int64 v90; // rax
  int v91; // edx
  __int64 v92; // rcx
  ADDRESS_FAMILY *v93; // r14
  ADDRESS_FAMILY v94; // cx
  int v95; // edi
  UCHAR v96; // al
  __int64 v97; // rdx
  int v98; // ebx
  __int64 v99; // rax
  char v100; // al
  __int64 (__fastcall *v101)(); // [rsp+20h] [rbp-100h]
  int v102; // [rsp+20h] [rbp-100h]
  int v103; // [rsp+38h] [rbp-E8h]
  int v104; // [rsp+40h] [rbp-E0h]
  char v105; // [rsp+50h] [rbp-D0h]
  int v106; // [rsp+58h] [rbp-C8h]
  int v107; // [rsp+60h] [rbp-C0h]
  int v108; // [rsp+70h] [rbp-B0h]
  unsigned int v110; // [rsp+A8h] [rbp-78h]
  __int64 v111; // [rsp+B0h] [rbp-70h]
  int v112; // [rsp+BCh] [rbp-64h] BYREF
  int v113; // [rsp+C0h] [rbp-60h] BYREF
  int v114; // [rsp+C4h] [rbp-5Ch]
  struct _KSPIN_LOCK_QUEUE *v115; // [rsp+C8h] [rbp-58h] BYREF
  int v116; // [rsp+D0h] [rbp-50h]
  int v117; // [rsp+D4h] [rbp-4Ch] BYREF
  int v118; // [rsp+D8h] [rbp-48h]
  __int64 v119; // [rsp+E0h] [rbp-40h]
  __int64 v120; // [rsp+E8h] [rbp-38h]
  ADDRESS_FAMILY *v121; // [rsp+F0h] [rbp-30h]
  __int64 v122; // [rsp+F8h] [rbp-28h]
  __int64 v123; // [rsp+100h] [rbp-20h]
  __int64 v124; // [rsp+108h] [rbp-18h]
  _QWORD v125[17]; // [rsp+110h] [rbp-10h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+1A0h] [rbp+80h] BYREF
  __int128 v127; // [rsp+1B8h] [rbp+98h] BYREF

  v17 = (__int64)a5;
  v19 = a7;
  PathInfoAf = a1;
  v123 = a13;
  v124 = a6;
  v122 = a9;
  v120 = a12;
  *(_QWORD *)&v127 = a5;
  v111 = a7;
  v113 = 0;
  if ( a1 < 0 )
    goto LABEL_37;
  if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
  {
    v42 = *a5;
    if ( *(_BYTE *)(*(_QWORD *)(*a5 + 8) + 88LL) )
    {
      LODWORD(v42) = HIDWORD(KeGetPcr()[1].LockArray);
      PathInfoAf = -1073741634;
      v43 = 320 * v42;
      ++*((_QWORD *)TcpipGlobalCounters + 40 * v42 + 10);
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) >= 0 )
      {
LABEL_37:
        v39 = 0;
        goto LABEL_28;
      }
      v62 = *(_QWORD *)(a3 + 40);
      LOBYTE(v43) = v62 != a4;
      v63 = InetFormatLocalSockAddrAtDispatchLevel(v62, v43, *(_QWORD *)(a3 + 104), *(unsigned __int16 *)(a3 + 168));
      v65 = *(_QWORD *)(a3 + 40);
      v66 = (ADDRESS_FAMILY *)v63;
      v67 = a5[2];
      v120 = v63;
      LOBYTE(v64) = v65 != a4;
      v115 = (struct _KSPIN_LOCK_QUEUE *)InetFormatSockAddrAtDispatchLevel(
                                           *(unsigned __int16 *)(v65 + 24),
                                           v64,
                                           1,
                                           v67,
                                           *((_DWORD *)a5 + 2),
                                           a8);
      if ( dword_1402241D4 )
      {
        LockHandle.LockQueue = 0;
        if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
        {
          PsGetProcessId(*(PEPROCESS *)(a3 + 48));
          LockHandle.LockQueue.Lock = 0;
          LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
          v68 = SOCKADDR_SIZE((ADDRESS_FAMILY)v115->Next);
          v69 = SOCKADDR_SIZE(*v66);
          PsGetProcessStartKey(*(_QWORD *)(a3 + 48));
          McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            v70,
            (unsigned int)&LockHandle,
            2,
            a3,
            v69,
            v120,
            v68,
            (__int64)v115);
          v17 = v127;
        }
      }
LABEL_73:
      v19 = v111;
      goto LABEL_37;
    }
  }
  if ( a14 )
  {
    PathInfoAf = UdpParseAncillaryData(a3, *(unsigned __int16 *)(a4 + 24), v123, a14, a16);
    if ( PathInfoAf < 0 )
      goto LABEL_37;
  }
  v21 = a2;
  v22 = 23;
  if ( a2 )
  {
    LODWORD(v23) = a7;
  }
  else if ( (*(_DWORD *)(a3 + 24) & 0x80u) == 0 || *(_DWORD *)(a16 + 8) )
  {
    memset(v125, 0, sizeof(v125));
    v112 = 0;
    PathInfoAf = InetQueryPathInfoAf(a4, (_DWORD)a5, v120, (unsigned int)v125, (__int64)&v112);
    if ( PathInfoAf < 0 )
    {
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        v72 = *(_QWORD *)(a3 + 40);
        LOBYTE(v71) = v72 != a4;
        v73 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v72 + 24),
                                  v71,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402241D4 )
        {
          LockHandle.LockQueue = 0;
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            if ( (*(_DWORD *)(a3 + 24) & 0x20) == 0 )
              v22 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 24LL);
            v74 = *v73;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
            v75 = SOCKADDR_SIZE(v74);
            v76 = SOCKADDR_SIZE(v22);
            LOBYTE(v77) = (_DWORD)v77 != 0;
            v78 = v76;
            v79 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(a3 + 40),
                    v77,
                    *(_QWORD *)(a3 + 104),
                    *(unsigned __int16 *)(a3 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_SEND_MESSAGES_PATH_AF_FAILURE,
              (unsigned int)&LockHandle,
              a3,
              v78,
              v79,
              v75,
              (__int64)v73,
              PathInfoAf);
          }
        }
      }
      goto LABEL_73;
    }
    v80 = (LOBYTE(v125[15]) != 0 ? 2 : 0) | *(_BYTE *)(a16 + 26) & 0xFD;
    v81 = v112 == 0;
    *(_BYTE *)(a16 + 26) = v80;
    if ( !v81 || *(_WORD *)(a4 + 24) == 23 && BYTE1(v125[15]) )
      v82 = 4;
    else
      v82 = 0;
    v23 = v125[14];
    v111 = v125[14];
    *(_BYTE *)(a16 + 26) = v82 | v80 & 0xFB;
    if ( !v23 )
    {
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        v83 = *(_QWORD *)(a3 + 40);
        LOBYTE(v71) = v83 != a4;
        v84 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v83 + 24),
                                  v71,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402241D4 )
        {
          LockHandle.LockQueue = 0;
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            if ( (*(_DWORD *)(a3 + 24) & 0x20) == 0 )
              v22 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 24LL);
            v85 = *v84;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
            v86 = SOCKADDR_SIZE(v85);
            v87 = SOCKADDR_SIZE(v22);
            LOBYTE(v88) = (_DWORD)v88 != 0;
            v89 = v87;
            v90 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(a3 + 40),
                    v88,
                    *(_QWORD *)(a3 + 104),
                    *(unsigned __int16 *)(a3 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_SEND_MESSAGES_PATH_NEXT_HOP_MISSING_FAILURE,
              (unsigned int)&LockHandle,
              a3,
              v89,
              v90,
              v86,
              (__int64)v84,
              0);
          }
        }
      }
      PathInfoAf = -1073741251;
      goto LABEL_73;
    }
    if ( (*(_DWORD *)(a3 + 24) & 0x80u) == 0 && (unsigned int)NlppNextHopAddressType(v23) == 4 )
    {
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        v92 = *(_QWORD *)(a3 + 40);
        LOBYTE(v91) = v92 != a4;
        v93 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v92 + 24),
                                  v91,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402241D4 )
        {
          LockHandle.LockQueue = 0;
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            if ( (*(_DWORD *)(a3 + 24) & 0x20) == 0 )
              v22 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 24LL);
            v94 = *v93;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
            v95 = SOCKADDR_SIZE(v94);
            v96 = SOCKADDR_SIZE(v22);
            LOBYTE(v97) = (_DWORD)v97 != 0;
            v98 = v96;
            v99 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(a3 + 40),
                    v97,
                    *(_QWORD *)(a3 + 104),
                    *(unsigned __int16 *)(a3 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_SEND_MESSAGES_PATH_NEXT_HOP_ADDR_FAILURE,
              (unsigned int)&LockHandle,
              a3,
              v98,
              v99,
              v95,
              (__int64)v93,
              0);
          }
        }
      }
      PathInfoAf = -1073741790;
      goto LABEL_73;
    }
    v21 = 0;
  }
  else
  {
    NextHopFromPath = InetGetNextHopFromPath(a4, a5);
    LODWORD(v23) = NextHopFromPath;
    v111 = NextHopFromPath;
  }
  v24 = *(unsigned int *)(a16 + 8);
  v25 = 65527;
  if ( *(_WORD *)(a4 + 24) != 23 )
    v25 = 65507;
  if ( v24 > v25 )
  {
    PathInfoAf = -1073741811;
    goto LABEL_73;
  }
  v112 = 0;
  if ( (_DWORD)v24 )
  {
    v100 = *(_BYTE *)(a16 + 26);
    if ( (v100 & 1) == 0 )
    {
      UdpQueryOffloadSupport(a3, a4, (_DWORD)a5, v23, a8, (v100 & 4) != 0, a16 + 8);
      if ( *(_DWORD *)(a16 + 16) )
      {
        if ( !v21 )
          *(_WORD *)(a16 + 24) = InetChecksumPseudoHeaderAf(a4, **(_QWORD **)(*a5 + 16), a5[2], 17);
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 24) & 0x40) == 0 || *(_WORD *)(a4 + 24) == 23 )
  {
    LOWORD(v118) = 6;
  }
  else
  {
    v118 = 0xFFFF;
    *(_WORD *)(a16 + 24) = 0;
  }
  v26 = *(unsigned __int16 *)(a3 + 168);
  LOWORD(v113) = *(_WORD *)(a3 + 168);
  HIWORD(v113) = a8;
  if ( v21 )
  {
    v116 = *(_DWORD *)(a3 + 284);
    if ( *(_WORD *)(a4 + 24) == 23 )
      v112 = *(_DWORD *)(a3 + 320);
  }
  else
  {
    v116 = *((_DWORD *)a5 + 3)
         ^ (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD))UdpRssHash + 1))(
             *(unsigned __int16 *)(a4 + 24),
             v26,
             a8);
    if ( *(_WORD *)(a4 + 24) == 23 )
    {
      v60 = RtlCompute37Hash(*(unsigned int *)(a3 + 324), *(_QWORD *)(*a5 + 16), *(unsigned __int16 *)(a4 + 72));
      v61 = RtlCompute37Hash(v60, a5 + 2, *(unsigned __int16 *)(a4 + 72));
      v112 = RtlCompute37Hash(v61, (char *)&v113 + 2, 2);
    }
  }
  v101 = UdpSendMessagesDatagramsComplete;
  v27 = (struct _KSPIN_LOCK_QUEUE *)NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData(qword_1402286E8, 80, 8);
  LockHandle.LockQueue.Next = v27;
  Next = v27;
  v115 = v27;
  v29 = (__int64)v27;
  if ( !v27 )
  {
    PathInfoAf = -1073741670;
    goto LABEL_73;
  }
  *(_QWORD *)&v127 = &v27->Lock;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v31 = a15;
    if ( a15 )
    {
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        TcpipEtwTransferActivity(a15, a3, 11);
        v29 = (__int64)v115;
      }
      v30 = 26;
    }
    else
    {
      v31 = a3;
      v30 = 27;
    }
  }
  else
  {
    v30 = 0;
    v31 = 0;
  }
  v32 = *(_QWORD *)(v29 + 16);
  PathInfoAf = 0;
  v114 = v30;
  v117 = 0;
  v33 = *(unsigned __int16 *)(v32 + 10);
  v34 = v33 + v32 + 24;
  v119 = v34;
  *(_QWORD *)(v33 + v32 + 16) = v34;
  *(_QWORD *)v34 = a10;
  *(_QWORD *)(v34 + 8) = a11;
  *(_QWORD *)(v34 + 16) = a3;
  *(_QWORD *)(v34 + 24) = 0;
  *(_QWORD *)(v34 + 32) = v29;
  *(_QWORD *)(v34 + 40) = 1;
  *(_DWORD *)(v34 + 48) = 0;
  *(_DWORD *)(v34 + 52) = *(_DWORD *)a16;
  v35 = (_QWORD *)v122;
  LODWORD(v29) = HIDWORD(KeGetPcr()[1].LockArray);
  v110 = v29;
  if ( v122 )
  {
    v58 = (_QWORD *)v122;
    do
    {
      PathInfoAf = UdpSegmentMessage(
                     (_DWORD)v58,
                     v34,
                     (unsigned int)&v115,
                     (unsigned int)&v127,
                     a3,
                     a4,
                     *(_WORD *)(a3 + 168),
                     a8,
                     v116,
                     a16,
                     v58 == v35,
                     *((_BYTE *)a5 + 40) >> 7,
                     (__int64)&v117,
                     v29,
                     v31,
                     v30);
      if ( PathInfoAf < 0 )
        break;
      v58 = (_QWORD *)*v58;
      LODWORD(v34) = v119;
      v30 = v114;
      v29 = v110;
      v35 = (_QWORD *)v122;
    }
    while ( v58 );
    Next = LockHandle.LockQueue.Next;
  }
  if ( (volatile PKSPIN_LOCK *)v127 == &Next->Lock )
  {
    v19 = v111;
    v39 = Next;
    HIDWORD(Next[8].Lock) = PathInfoAf;
    goto LABEL_28;
  }
  if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
  {
    v44 = *(_QWORD *)(a3 + 40);
    LOBYTE(v29) = v44 != a4;
    v45 = InetFormatLocalSockAddrAtDispatchLevel(v44, v29, *(_QWORD *)(a3 + 104), *(unsigned __int16 *)(a3 + 168));
    v46 = *(_QWORD *)(a3 + 40);
    v36 = a8;
    v47 = a5[2];
    LOBYTE(v48) = v46 != a4;
    LODWORD(v46) = *(unsigned __int16 *)(v46 + 24);
    v102 = *((_DWORD *)a5 + 2);
    v121 = (ADDRESS_FAMILY *)v45;
    LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)InetFormatSockAddrAtDispatchLevel(
                                                                      v46,
                                                                      v48,
                                                                      1,
                                                                      v47,
                                                                      v102,
                                                                      a8);
    if ( dword_1402241D4 )
    {
      v127 = 0;
      if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(a3 + 48));
        v50 = *(_QWORD *)(a3 + 48);
        v51 = ProcessId;
        v127 = (unsigned __int64)a3;
        PsGetProcessStartKey(v50);
        SOCKADDR_SIZE((ADDRESS_FAMILY)LockHandle.LockQueue.Next->Next);
        v52 = SOCKADDR_SIZE(*v121);
        v105 = v51;
        v37 = v119;
        McTemplateK0pqqqbr3qbr5qx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)UDP_ENDPOINT_SEND_MESSAGES_V1,
          (unsigned int)&v127,
          a3,
          v117,
          *(_DWORD *)(v119 + 24),
          v52,
          v55,
          v54,
          v56,
          v105,
          v53);
        goto LABEL_23;
      }
    }
  }
  else
  {
    v36 = a8;
  }
  v37 = v119;
LABEL_23:
  if ( qword_1402284F8 )
  {
    LOWORD(v104) = v36;
    LOWORD(v103) = *(_WORD *)(a3 + 168);
    LOWORD(v101) = *(_WORD *)(a4 + 24);
    InetTraceBasicDataCore(
      &UdpInetTransport,
      2058,
      *(_QWORD *)(a3 + 48),
      *(unsigned int *)(v37 + 24),
      v101,
      **(_QWORD **)(*a5 + 16),
      a5[2],
      v103,
      v104);
  }
  if ( (*(_BYTE *)(a16 + 4) & 1) != 0 )
    LODWORD(v115[8].Next) |= 0x10000u;
  v38 = *(_QWORD *)(v37 + 24);
  v19 = v111;
  LOWORD(v108) = *(_WORD *)(a16 + 24);
  LOWORD(v107) = 0;
  LOWORD(v106) = v118;
  InetFastSendDatagramsOnPathAf(
    a4,
    Next,
    v123 & -(__int64)((*(_BYTE *)(a16 + 26) & 8) != 0),
    a14 & (unsigned int)-((*(_BYTE *)(a16 + 26) & 8) != 0),
    v120,
    a5,
    v111,
    17,
    *(_QWORD *)(a3 + 72),
    &v113,
    8,
    v106,
    v107,
    0,
    v108,
    v112,
    1,
    a2,
    *(_QWORD *)(a3 + 48),
    v38);
  PathInfoAf = 259;
  v39 = Next;
LABEL_28:
  if ( v17 )
    InetLeavePathAf(a4, v17);
  if ( v19 )
    InetDereferenceNextHopAf(a4);
  v40 = v124;
  if ( v124 )
  {
    if ( PathInfoAf == 259 && v124 != *(_QWORD *)(a3 + 104) )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      RtlAcquireWriteLock(a3, &LockHandle);
      v59 = *(_QWORD *)(a3 + 104);
      *(_QWORD *)(a3 + 104) = v40;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v40 = v59;
    }
    InetDereferenceLocalAddressAf(*(_QWORD *)(a3 + 112), v40);
  }
  if ( a4 != *(_QWORD *)(a3 + 112) && a4 )
    InetDereferenceAf(a4);
  if ( PathInfoAf != 259 )
  {
    if ( v39 )
    {
      NetioDereferenceNetBufferListChain(v39, 0);
      return 259;
    }
    else
    {
      UdpDereferenceEndpoint(a3);
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
