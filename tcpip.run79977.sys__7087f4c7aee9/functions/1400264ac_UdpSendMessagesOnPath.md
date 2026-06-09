# UdpSendMessagesOnPath

- ea: `0x1400264ac`
- end: `0x140027158`
- name: `UdpSendMessagesOnPath`
- size: `3244`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400254a0`

## callees

- `0x140012560`
- `0x140012d30`
- `0x140013140`
- `0x1400143c0`
- `0x140014bf0`
- `0x1400264ac`
- `0x14002f4a0`
- `0x140030620`
- `0x140039b00`
- `0x14003b920`
- `0x140055e64`
- `0x14005e920`
- `0x140095628`
- `0x140095c00`
- `0x1400ae7f8`
- `0x1400b7ca0`
- `0x1400b7d50`
- `0x1400c3440`
- `0x1400e7fb0`
- `0x1400f7378`
- `0x1401067a0`
- `0x14010d088`
- `0x14011798c`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!PsGetProcessStartKey` at `0x14002666d`
- `ntoskrnl!PsGetProcessStartKey` at `0x140026f42`
- `ntoskrnl!PsGetProcessStartKey` at `0x14002666d`
- `ntoskrnl!PsGetProcessStartKey` at `0x140026f42`
- `ntoskrnl!PsGetProcessId` at `0x140026624`
- `ntoskrnl!PsGetProcessId` at `0x140026f1d`
- `ntoskrnl!PsGetProcessId` at `0x140026624`
- `ntoskrnl!PsGetProcessId` at `0x140026f1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140026739`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140026739`
- `NETIO!RtlCompute37Hash` at `0x140026c75`
- `NETIO!RtlCompute37Hash` at `0x140026c8c`
- `NETIO!RtlCompute37Hash` at `0x140026ca4`
- `NETIO!RtlCompute37Hash` at `0x140026c75`
- `NETIO!RtlCompute37Hash` at `0x140026c8c`
- `NETIO!RtlCompute37Hash` at `0x140026ca4`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140026558`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140026558`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140026cdd`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140026cdd`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14002677e`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14002677e`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14002705a`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14002705a`

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
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  ADDRESS_FAMILY *v26; // rbx
  __int64 v27; // r9
  int v28; // edx
  int v29; // esi
  int v30; // ebx
  int v31; // edx
  struct _KSPIN_LOCK_QUEUE *volatile v32; // rdi
  __int64 v33; // rsi
  __int64 v34; // rbx
  char v35; // r12
  ADDRESS_FAMILY v36; // bx
  __int64 NextHopFromPath; // rax
  __int64 v38; // r8
  int v39; // edx
  __int64 v40; // rcx
  ADDRESS_FAMILY *v41; // r14
  ADDRESS_FAMILY v42; // cx
  int v43; // edi
  UCHAR v44; // al
  __int64 v45; // rdx
  int v46; // ebx
  __int64 v47; // rax
  char v48; // al
  bool v49; // zf
  char v50; // cl
  __int64 v51; // rcx
  ADDRESS_FAMILY *v52; // r14
  ADDRESS_FAMILY v53; // cx
  int v54; // edi
  UCHAR v55; // al
  __int64 v56; // rdx
  int v57; // ebx
  __int64 v58; // rax
  int v59; // edx
  __int64 v60; // rcx
  ADDRESS_FAMILY *v61; // r14
  ADDRESS_FAMILY v62; // cx
  int v63; // edi
  UCHAR v64; // al
  __int64 v65; // rdx
  int v66; // ebx
  __int64 v67; // rax
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // rax
  char v70; // al
  __int64 v71; // rdx
  unsigned int v72; // eax
  unsigned int v73; // eax
  struct _KSPIN_LOCK_QUEUE *v74; // rax
  struct _KSPIN_LOCK_QUEUE *volatile Next; // r14
  __int64 v76; // rdx
  __int64 v77; // rbx
  int v78; // r8d
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // r10
  _QWORD *v82; // rax
  _QWORD *v83; // r14
  __int64 v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rcx
  unsigned __int16 v87; // r12
  __int64 v88; // r9
  int v89; // edx
  unsigned __int8 ProcessId; // al
  __int64 v91; // rcx
  char v92; // bl
  UCHAR v93; // al
  __int64 v94; // rbx
  char v95; // r8
  int v96; // r9d
  __int64 v97; // r10
  __int64 v98; // r11
  __int64 v99; // rax
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
    goto LABEL_9;
  if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
  {
    v21 = *a5;
    if ( *(_BYTE *)(*(_QWORD *)(*a5 + 8) + 88LL) )
    {
      LODWORD(v21) = HIDWORD(KeGetPcr()[1].LockArray);
      PathInfoAf = -1073741634;
      v22 = 320 * v21;
      ++*((_QWORD *)TcpipGlobalCounters + 40 * v21 + 10);
      if ( *((char *)&WPP_MAIN_CB.Reserved + 8) >= 0 )
      {
LABEL_9:
        v32 = 0;
        goto LABEL_10;
      }
      v23 = *(_QWORD *)(a3 + 40);
      LOBYTE(v22) = v23 != a4;
      v24 = InetFormatLocalSockAddrAtDispatchLevel(v23, v22, *(_QWORD *)(a3 + 104), *(unsigned __int16 *)(a3 + 168));
      v25 = *(_QWORD *)(a3 + 40);
      v26 = (ADDRESS_FAMILY *)v24;
      v27 = a5[2];
      v120 = v24;
      LOBYTE(v28) = v25 != a4;
      v115 = (struct _KSPIN_LOCK_QUEUE *)InetFormatSockAddrAtDispatchLevel(
                                           *(unsigned __int16 *)(v25 + 24),
                                           v28,
                                           1,
                                           v27,
                                           *((_DWORD *)a5 + 2),
                                           a8);
      if ( dword_1402201D4 )
      {
        LockHandle.LockQueue = 0;
        if ( *((char *)&WPP_MAIN_CB.Reserved + 8) < 0 )
        {
          PsGetProcessId(*(PEPROCESS *)(a3 + 48));
          LockHandle.LockQueue.Lock = 0;
          LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
          v29 = SOCKADDR_SIZE((ADDRESS_FAMILY)v115->Next);
          v30 = SOCKADDR_SIZE(*v26);
          PsGetProcessStartKey(*(_QWORD *)(a3 + 48));
          McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            v31,
            (unsigned int)&LockHandle,
            2,
            a3,
            v30,
            v120,
            v29,
            (__int64)v115);
          v17 = v127;
        }
      }
LABEL_8:
      v19 = v111;
      goto LABEL_9;
    }
  }
  if ( a14 )
  {
    PathInfoAf = UdpParseAncillaryData(a3, *(unsigned __int16 *)(a4 + 24), v123, a14, a16);
    if ( PathInfoAf < 0 )
      goto LABEL_9;
  }
  v35 = a2;
  v36 = 23;
  if ( a2 )
  {
    LODWORD(v38) = a7;
  }
  else if ( (*(_DWORD *)(a3 + 24) & 0x80u) == 0 || *(_DWORD *)(a16 + 8) )
  {
    memset(v125, 0, sizeof(v125));
    v112 = 0;
    PathInfoAf = InetQueryPathInfoAf(a4, (_DWORD)a5, v120, (unsigned int)v125, (__int64)&v112);
    if ( PathInfoAf < 0 )
    {
      if ( *((char *)&WPP_MAIN_CB.Reserved + 10) < 0 )
      {
        v40 = *(_QWORD *)(a3 + 40);
        LOBYTE(v39) = v40 != a4;
        v41 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v40 + 24),
                                  v39,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402201D4 )
        {
          LockHandle.LockQueue = 0;
          if ( *((char *)&WPP_MAIN_CB.Reserved + 10) < 0 )
          {
            if ( (*(_DWORD *)(a3 + 24) & 0x20) == 0 )
              v36 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 24LL);
            v42 = *v41;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
            v43 = SOCKADDR_SIZE(v42);
            v44 = SOCKADDR_SIZE(v36);
            LOBYTE(v45) = (_DWORD)v45 != 0;
            v46 = v44;
            v47 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(a3 + 40),
                    v45,
                    *(_QWORD *)(a3 + 104),
                    *(unsigned __int16 *)(a3 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)&UDP_SEND_MESSAGES_PATH_AF_FAILURE,
              (unsigned int)&LockHandle,
              a3,
              v46,
              v47,
              v43,
              (__int64)v41,
              PathInfoAf);
          }
        }
      }
      goto LABEL_8;
    }
    v48 = (LOBYTE(v125[15]) != 0 ? 2 : 0) | *(_BYTE *)(a16 + 26) & 0xFD;
    v49 = v112 == 0;
    *(_BYTE *)(a16 + 26) = v48;
    if ( !v49 || *(_WORD *)(a4 + 24) == 23 && BYTE1(v125[15]) )
      v50 = 4;
    else
      v50 = 0;
    v38 = v125[14];
    v111 = v125[14];
    *(_BYTE *)(a16 + 26) = v50 | v48 & 0xFB;
    if ( !v38 )
    {
      if ( *((char *)&WPP_MAIN_CB.Reserved + 10) < 0 )
      {
        v51 = *(_QWORD *)(a3 + 40);
        LOBYTE(v39) = v51 != a4;
        v52 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v51 + 24),
                                  v39,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402201D4 )
        {
          LockHandle.LockQueue = 0;
          if ( *((char *)&WPP_MAIN_CB.Reserved + 10) < 0 )
          {
            if ( (*(_DWORD *)(a3 + 24) & 0x20) == 0 )
              v36 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 24LL);
            v53 = *v52;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
            v54 = SOCKADDR_SIZE(v53);
            v55 = SOCKADDR_SIZE(v36);
            LOBYTE(v56) = (_DWORD)v56 != 0;
            v57 = v55;
            v58 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(a3 + 40),
                    v56,
                    *(_QWORD *)(a3 + 104),
                    *(unsigned __int16 *)(a3 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)&UDP_SEND_MESSAGES_PATH_NEXT_HOP_MISSING_FAILURE,
              (unsigned int)&LockHandle,
              a3,
              v57,
              v58,
              v54,
              (__int64)v52,
              0);
          }
        }
      }
      PathInfoAf = -1073741251;
      goto LABEL_8;
    }
    if ( (*(_DWORD *)(a3 + 24) & 0x80u) == 0 && (unsigned int)NlppNextHopAddressType(v38) == 4 )
    {
      if ( *((char *)&WPP_MAIN_CB.Reserved + 10) < 0 )
      {
        v60 = *(_QWORD *)(a3 + 40);
        LOBYTE(v59) = v60 != a4;
        v61 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v60 + 24),
                                  v59,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  a8);
        if ( dword_1402201D4 )
        {
          LockHandle.LockQueue = 0;
          if ( *((char *)&WPP_MAIN_CB.Reserved + 10) < 0 )
          {
            if ( (*(_DWORD *)(a3 + 24) & 0x20) == 0 )
              v36 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 24LL);
            v62 = *v61;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a3;
            v63 = SOCKADDR_SIZE(v62);
            v64 = SOCKADDR_SIZE(v36);
            LOBYTE(v65) = (_DWORD)v65 != 0;
            v66 = v64;
            v67 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)(a3 + 40),
                    v65,
                    *(_QWORD *)(a3 + 104),
                    *(unsigned __int16 *)(a3 + 168));
            McTemplateK0pqbr1qbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)&UDP_SEND_MESSAGES_PATH_NEXT_HOP_ADDR_FAILURE,
              (unsigned int)&LockHandle,
              a3,
              v66,
              v67,
              v63,
              (__int64)v61,
              0);
          }
        }
      }
      PathInfoAf = -1073741790;
      goto LABEL_8;
    }
    v35 = 0;
  }
  else
  {
    NextHopFromPath = InetGetNextHopFromPath(a4, a5);
    LODWORD(v38) = NextHopFromPath;
    v111 = NextHopFromPath;
  }
  v68 = *(unsigned int *)(a16 + 8);
  v69 = 65527;
  if ( *(_WORD *)(a4 + 24) != 23 )
    v69 = 65507;
  if ( v68 > v69 )
  {
    PathInfoAf = -1073741811;
    goto LABEL_8;
  }
  v112 = 0;
  if ( (_DWORD)v68 )
  {
    v70 = *(_BYTE *)(a16 + 26);
    if ( (v70 & 1) == 0 )
    {
      UdpQueryOffloadSupport(a3, a4, (_DWORD)a5, v38, a8, (v70 & 4) != 0, a16 + 8);
      if ( *(_DWORD *)(a16 + 16) )
      {
        if ( !v35 )
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
  v71 = *(unsigned __int16 *)(a3 + 168);
  LOWORD(v113) = *(_WORD *)(a3 + 168);
  HIWORD(v113) = a8;
  if ( v35 )
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
             v71,
             a8);
    if ( *(_WORD *)(a4 + 24) == 23 )
    {
      v72 = RtlCompute37Hash(*(unsigned int *)(a3 + 324), *(_QWORD *)(*a5 + 16), *(unsigned __int16 *)(a4 + 72));
      v73 = RtlCompute37Hash(v72, a5 + 2, *(unsigned __int16 *)(a4 + 72));
      v112 = RtlCompute37Hash(v73, (char *)&v113 + 2, 2);
    }
  }
  v101 = UdpSendMessagesDatagramsComplete;
  v74 = (struct _KSPIN_LOCK_QUEUE *)NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData(qword_140224668, 80, 8);
  LockHandle.LockQueue.Next = v74;
  Next = v74;
  v115 = v74;
  v76 = (__int64)v74;
  if ( !v74 )
  {
    PathInfoAf = -1073741670;
    goto LABEL_8;
  }
  *(_QWORD *)&v127 = &v74->Lock;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v77 = a15;
    if ( a15 )
    {
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        TcpipEtwTransferActivity(a15, a3, 11);
        v76 = (__int64)v115;
      }
      v78 = 26;
    }
    else
    {
      v77 = a3;
      v78 = 27;
    }
  }
  else
  {
    v78 = 0;
    v77 = 0;
  }
  v79 = *(_QWORD *)(v76 + 16);
  PathInfoAf = 0;
  v114 = v78;
  v117 = 0;
  v80 = *(unsigned __int16 *)(v79 + 10);
  v81 = v80 + v79 + 24;
  v119 = v81;
  *(_QWORD *)(v80 + v79 + 16) = v81;
  *(_QWORD *)v81 = a10;
  *(_QWORD *)(v81 + 8) = a11;
  *(_QWORD *)(v81 + 16) = a3;
  *(_QWORD *)(v81 + 24) = 0;
  *(_QWORD *)(v81 + 32) = v76;
  *(_QWORD *)(v81 + 40) = 1;
  *(_DWORD *)(v81 + 48) = 0;
  *(_DWORD *)(v81 + 52) = *(_DWORD *)a16;
  v82 = (_QWORD *)v122;
  LODWORD(v76) = HIDWORD(KeGetPcr()[1].LockArray);
  v110 = v76;
  if ( v122 )
  {
    v83 = (_QWORD *)v122;
    do
    {
      PathInfoAf = UdpSegmentMessage(
                     (_DWORD)v83,
                     v81,
                     (unsigned int)&v115,
                     (unsigned int)&v127,
                     a3,
                     a4,
                     *(_WORD *)(a3 + 168),
                     a8,
                     v116,
                     a16,
                     v83 == v82,
                     *((_BYTE *)a5 + 40) >> 7,
                     (__int64)&v117,
                     v76,
                     v77,
                     v78);
      if ( PathInfoAf < 0 )
        break;
      v83 = (_QWORD *)*v83;
      LODWORD(v81) = v119;
      v78 = v114;
      v76 = v110;
      v82 = (_QWORD *)v122;
    }
    while ( v83 );
    Next = LockHandle.LockQueue.Next;
  }
  if ( (volatile PKSPIN_LOCK *)v127 == &Next->Lock )
  {
    v19 = v111;
    v32 = Next;
    HIDWORD(Next[8].Lock) = PathInfoAf;
    goto LABEL_10;
  }
  if ( SBYTE2(WPP_MAIN_CB.Reserved) >= 0 )
  {
    v87 = a8;
LABEL_101:
    v94 = v119;
    goto LABEL_102;
  }
  v84 = *(_QWORD *)(a3 + 40);
  LOBYTE(v76) = v84 != a4;
  v85 = InetFormatLocalSockAddrAtDispatchLevel(v84, v76, *(_QWORD *)(a3 + 104), *(unsigned __int16 *)(a3 + 168));
  v86 = *(_QWORD *)(a3 + 40);
  v87 = a8;
  v88 = a5[2];
  LOBYTE(v89) = v86 != a4;
  LODWORD(v86) = *(unsigned __int16 *)(v86 + 24);
  v102 = *((_DWORD *)a5 + 2);
  v121 = (ADDRESS_FAMILY *)v85;
  LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)InetFormatSockAddrAtDispatchLevel(
                                                                    v86,
                                                                    v89,
                                                                    1,
                                                                    v88,
                                                                    v102,
                                                                    a8);
  if ( !dword_1402201D4 )
    goto LABEL_101;
  v127 = 0;
  if ( SBYTE2(WPP_MAIN_CB.Reserved) >= 0 )
    goto LABEL_101;
  ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(a3 + 48));
  v91 = *(_QWORD *)(a3 + 48);
  v92 = ProcessId;
  v127 = (unsigned __int64)a3;
  PsGetProcessStartKey(v91);
  SOCKADDR_SIZE((ADDRESS_FAMILY)LockHandle.LockQueue.Next->Next);
  v93 = SOCKADDR_SIZE(*v121);
  v105 = v92;
  v94 = v119;
  McTemplateK0pqqqbr3qbr5qx_EtwWriteTransfer(
    (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
    (unsigned int)&UDP_ENDPOINT_SEND_MESSAGES_V1,
    (unsigned int)&v127,
    a3,
    v117,
    *(_DWORD *)(v119 + 24),
    v93,
    v97,
    v96,
    v98,
    v105,
    v95);
LABEL_102:
  if ( qword_140224478 )
  {
    LOWORD(v104) = v87;
    LOWORD(v103) = *(_WORD *)(a3 + 168);
    LOWORD(v101) = *(_WORD *)(a4 + 24);
    InetTraceBasicDataCore(
      &UdpInetTransport,
      2058,
      *(_QWORD *)(a3 + 48),
      *(unsigned int *)(v94 + 24),
      v101,
      **(_QWORD **)(*a5 + 16),
      a5[2],
      v103,
      v104);
  }
  if ( (*(_BYTE *)(a16 + 4) & 1) != 0 )
    LODWORD(v115[8].Next) |= 0x10000u;
  if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
  {
    LODWORD(v101) = 1;
    NdisNblTrackerTransferOwnership(Next, 0, UdpNblTracker, 159, v101);
  }
  v99 = *(_QWORD *)(v94 + 24);
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
    v99);
  PathInfoAf = 259;
  v32 = Next;
LABEL_10:
  if ( v17 )
    InetLeavePathAf(a4, v17);
  if ( v19 )
    InetDereferenceNextHopAf(a4);
  v33 = v124;
  if ( v124 )
  {
    if ( PathInfoAf == 259 && v124 != *(_QWORD *)(a3 + 104) )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      RtlAcquireWriteLock(a3, &LockHandle);
      v34 = *(_QWORD *)(a3 + 104);
      *(_QWORD *)(a3 + 104) = v33;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v33 = v34;
    }
    InetDereferenceLocalAddressAf(*(_QWORD *)(a3 + 112), v33);
  }
  if ( a4 != *(_QWORD *)(a3 + 112) && a4 )
    InetDereferenceAf(a4);
  if ( PathInfoAf != 259 )
  {
    if ( v32 )
    {
      NetioDereferenceNetBufferListChain(v32, 0);
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
0x1400264ac  mov     [rsp-8+arg_0], rbx
0x1400264b1  push    rbp
0x1400264b2  push    rsi
0x1400264b3  push    rdi
0x1400264b4  push    r12
0x1400264b6  push    r13
0x1400264b8  push    r14
0x1400264ba  push    r15
0x1400264bc  lea     rbp, [rsp-0B0h]
0x1400264c4  sub     rsp, 1D0h
0x1400264cb  mov     rax, cs:__security_cookie
0x1400264d2  xor     rax, rsp
0x1400264d5  mov     [rbp+0E0h+var_38], rax
0x1400264dc  mov     rax, [rbp+0E0h+arg_60]
0x1400264e3  mov     r13, r9
0x1400264e6  mov     rsi, [rbp+0E0h+arg_20]
0x1400264ed  mov     r15, r8
0x1400264f0  mov     rbx, [rbp+0E0h+arg_30]
0x1400264f7  mov     r12d, ecx
0x1400264fa  movzx   r14d, [rbp+0E0h+arg_38]
0x140026502  mov     rdi, [rbp+0E0h+arg_78]
0x140026509  mov     [rbp+0E0h+var_100], rax
0x14002650d  mov     rax, [rbp+0E0h+arg_28]
0x140026514  mov     [rbp+0E0h+var_F8], rax
0x140026518  mov     rax, [rbp+0E0h+arg_40]
0x14002651f  mov     [rbp+0E0h+var_108], rax
0x140026523  mov     rax, [rbp+0E0h+arg_58]
0x14002652a  mov     [rbp+0E0h+var_118], rax
0x14002652e  mov     [rbp+0E0h+var_160], dl
0x140026531  mov     qword ptr [rbp+0E0h+var_48], rsi
0x140026538  mov     [rbp+0E0h+var_150], rbx
0x14002653c  mov     [rbp+0E0h+var_148], r14w
0x140026541  mov     [rbp+0E0h+var_158], 0
0x140026549  mov     [rbp+0E0h+var_140], 0
0x140026550  test    ecx, ecx
0x140026552  js      loc_1400266CA
0x140026558  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14002655f  nop     dword ptr [rax+rax+00h]
0x140026564  test    al, al
0x140026566  jz      loc_140026792
0x14002656c  mov     rax, [rsi]
0x14002656f  mov     rcx, [rax+8]
0x140026573  cmp     byte ptr [rcx+58h], 0
0x140026577  jz      loc_140026792
0x14002657d  mov     eax, gs:1A4h
0x140026585  mov     r12d, 0C00000BEh
0x14002658b  lea     rdx, [rax+rax*4]
0x14002658f  mov     rax, cs:TcpipGlobalCounters
0x140026596  shl     rdx, 6
0x14002659a  inc     qword ptr [rdx+rax+50h]
0x14002659f  cmp     byte ptr cs:WPP_MAIN_CB+148h, 0
0x1400265a6  jge     loc_1400266CA
0x1400265ac  mov     rcx, [r15+28h]
0x1400265b0  movzx   r9d, word ptr [r15+0A8h]
0x1400265b8  cmp     rcx, r13
0x1400265bb  mov     r8, [r15+68h]
0x1400265bf  setnz   dl
0x1400265c2  call    InetFormatLocalSockAddrAtDispatchLevel
0x1400265c7  mov     rcx, [r15+28h]
0x1400265cb  mov     rbx, rax
0x1400265ce  mov     r9, [rsi+10h]
0x1400265d2  cmp     rcx, r13
0x1400265d5  mov     [rbp+0E0h+var_118], rax
0x1400265d9  mov     r8d, 1
0x1400265df  mov     eax, [rsi+8]
0x1400265e2  setnz   dl
0x1400265e5  movzx   ecx, word ptr [rcx+18h]
0x1400265e9  mov     word ptr [rsp+200h+var_1D8], r14w
0x1400265ef  mov     dword ptr [rsp+200h+var_1E0], eax
0x1400265f3  call    InetFormatSockAddrAtDispatchLevel
0x1400265f8  cmp     cs:dword_1402201D4, 0
0x1400265ff  mov     [rbp+0E0h+var_138], rax
0x140026603  jz      loc_1400266C6
0x140026609  cmp     byte ptr cs:WPP_MAIN_CB+148h, 0
0x140026610  xorps   xmm0, xmm0
0x140026613  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x14002661a  jge     loc_1400266C6
0x140026620  mov     rcx, [r15+30h]; Process
0x140026624  call    cs:__imp_PsGetProcessId
0x14002662b  nop     dword ptr [rax+rax+00h]
0x140026630  mov     rcx, [rsi]
0x140026633  mov     r14, rax
0x140026636  mov     [rbp+0E0h+LockHandle.LockQueue.Lock], 0
0x140026641  mov     [rbp+0E0h+LockHandle.LockQueue.Next], r15
0x140026648  mov     rdx, [rcx+8]
0x14002664c  mov     rcx, [rbp+0E0h+var_138]
0x140026650  mov     edi, [rdx+8]
0x140026653  movzx   ecx, word ptr [rcx]; af
0x140026656  call    SOCKADDR_SIZE
0x14002665b  movzx   ecx, word ptr [rbx]; af
0x14002665e  movzx   esi, al
0x140026661  call    SOCKADDR_SIZE
0x140026666  mov     rcx, [r15+30h]
0x14002666a  movzx   ebx, al
0x14002666d  call    cs:__imp_PsGetProcessStartKey
0x140026674  nop     dword ptr [rax+rax+00h]
0x140026679  mov     [rsp+200h+var_1A0], rax
0x14002667e  mov     r9d, 2
0x140026684  mov     rax, [rbp+0E0h+var_138]
0x140026688  lea     r8, [rbp+0E0h+LockHandle]
0x14002668f  mov     dword ptr [rsp+200h+var_1A8], edi
0x140026693  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14002669a  mov     dword ptr [rsp+200h+var_1B0], r14d
0x14002669f  mov     [rsp+200h+var_1C0], rax
0x1400266a4  mov     rax, [rbp+0E0h+var_118]
0x1400266a8  mov     dword ptr [rsp+200h+var_1C8], esi
0x1400266ac  mov     [rsp+200h+var_1D0], rax
0x1400266b1  mov     dword ptr [rsp+200h+var_1D8], ebx
0x1400266b5  mov     [rsp+200h+var_1E0], r15
0x1400266ba  call    McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer
0x1400266bf  mov     rsi, qword ptr [rbp+0E0h+var_48]
0x1400266c6  mov     rbx, [rbp+0E0h+var_150]
0x1400266ca  mov     rdi, [rbp+0E0h+var_158]
0x1400266ce  test    rsi, rsi
0x1400266d1  jz      short loc_1400266DE
0x1400266d3  mov     rdx, rsi
0x1400266d6  mov     rcx, r13
0x1400266d9  call    InetLeavePathAf
0x1400266de  test    rbx, rbx
0x1400266e1  jz      short loc_1400266EE
0x1400266e3  mov     rdx, rbx
0x1400266e6  mov     rcx, r13
0x1400266e9  call    InetDereferenceNextHopAf
0x1400266ee  mov     rsi, [rbp+0E0h+var_F8]
0x1400266f2  mov     r14d, 103h
0x1400266f8  test    rsi, rsi
0x1400266fb  jz      short loc_140026754
0x1400266fd  cmp     r12d, r14d
0x140026700  jnz     short loc_140026748
0x140026702  cmp     rsi, [r15+68h]
0x140026706  jz      short loc_140026748
0x140026708  xorps   xmm0, xmm0
0x14002670b  lea     rdx, [rbp+0E0h+LockHandle]
0x140026712  xor     eax, eax
0x140026714  mov     rcx, r15
0x140026717  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x14002671e  mov     qword ptr [rbp+0E0h+LockHandle.OldIrql], rax
0x140026725  call    RtlAcquireWriteLock
0x14002672a  mov     rbx, [r15+68h]
0x14002672e  lea     rcx, [rbp+0E0h+LockHandle]; LockHandle
0x140026735  mov     [r15+68h], rsi
0x140026739  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140026740  nop     dword ptr [rax+rax+00h]
0x140026745  mov     rsi, rbx
0x140026748  mov     rcx, [r15+70h]
0x14002674c  mov     rdx, rsi
0x14002674f  call    InetDereferenceLocalAddressAf
0x140026754  cmp     r13, [r15+70h]
0x140026758  jz      short loc_140026767
0x14002675a  test    r13, r13
0x14002675d  jz      short loc_140026767
0x14002675f  mov     rcx, r13
0x140026762  call    _InetDereferenceAf
0x140026767  cmp     r12d, r14d
0x14002676a  jz      loc_14002712A
0x140026770  test    rdi, rdi
0x140026773  jz      loc_140027122
0x140026779  xor     edx, edx
0x14002677b  mov     rcx, rdi
0x14002677e  call    cs:__imp_NetioDereferenceNetBufferListChain
0x140026785  nop     dword ptr [rax+rax+00h]
0x14002678a  mov     r12d, r14d
0x14002678d  jmp     loc_14002712A
0x140026792  mov     eax, [rbp+0E0h+arg_68]
0x140026798  test    eax, eax
0x14002679a  jz      short loc_1400267C0
0x14002679c  mov     r8, [rbp+0E0h+var_100]
0x1400267a0  mov     r9d, eax
0x1400267a3  movzx   edx, word ptr [r13+18h]
0x1400267a8  mov     rcx, r15
0x1400267ab  mov     [rsp+200h+var_1E0], rdi
0x1400267b0  call    UdpParseAncillaryData
0x1400267b5  mov     r12d, eax
0x1400267b8  test    eax, eax
0x1400267ba  js      loc_1400266CA
0x1400267c0  mov     r12b, [rbp+0E0h+var_160]
0x1400267c4  mov     ebx, 17h
0x1400267c9  test    r12b, r12b
0x1400267cc  jnz     loc_140026B4A
0x1400267d2  mov     eax, [r15+18h]
0x1400267d6  test    al, al
0x1400267d8  jns     short loc_1400267F7
0x1400267da  cmp     dword ptr [rdi+8], 0
0x1400267de  ja      short loc_1400267F7
0x1400267e0  mov     rdx, rsi
0x1400267e3  mov     rcx, r13
0x1400267e6  call    InetGetNextHopFromPath
0x1400267eb  mov     r8, rax
0x1400267ee  mov     [rbp+0E0h+var_150], rax
0x1400267f2  jmp     loc_140026B54
0x1400267f7  xor     edx, edx; Val
0x1400267f9  lea     rcx, [rbp+0E0h+var_F0]; void *
0x1400267fd  mov     r8d, 88h; Size
0x140026803  call    memset
0x140026808  mov     r8, [rbp+0E0h+var_118]
0x14002680c  lea     rax, [rbp+0E0h+var_144]
0x140026810  lea     r9, [rbp+0E0h+var_F0]
0x140026814  mov     [rsp+200h+var_1E0], rax
0x140026819  mov     rdx, rsi
0x14002681c  mov     [rbp+0E0h+var_144], 0
0x140026823  mov     rcx, r13
0x140026826  call    InetQueryPathInfoAf
0x14002682b  mov     r12d, eax
0x14002682e  test    eax, eax
0x140026830  jns     loc_140026916
0x140026836  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, 0
0x14002683d  jge     loc_1400266C6
0x140026843  mov     rcx, [r15+28h]
0x140026847  mov     r8d, 1
0x14002684d  mov     eax, [rsi+8]
0x140026850  cmp     rcx, r13
0x140026853  mov     r9, [rsi+10h]
0x140026857  setnz   dl
0x14002685a  mov     word ptr [rsp+200h+var_1D8], r14w
0x140026860  movzx   ecx, word ptr [rcx+18h]
0x140026864  mov     dword ptr [rsp+200h+var_1E0], eax
0x140026868  call    InetFormatSockAddrAtDispatchLevel
0x14002686d  cmp     cs:dword_1402201D4, 0
0x140026874  mov     r14, rax
0x140026877  jz      loc_1400266C6
0x14002687d  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, 0
0x140026884  xorps   xmm0, xmm0
0x140026887  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x14002688e  jge     loc_1400266C6
0x140026894  mov     edx, [r15+18h]
0x140026898  and     edx, 20h
0x14002689b  jnz     short loc_1400268A5
0x14002689d  mov     rax, [r15+28h]
0x1400268a1  movzx   ebx, word ptr [rax+18h]
0x1400268a5  movzx   ecx, word ptr [r14]; af
0x1400268a9  mov     [rbp+0E0h+LockHandle.LockQueue.Next], r15
0x1400268b0  call    SOCKADDR_SIZE
0x1400268b5  movzx   ecx, bx; af
0x1400268b8  movzx   edi, al
0x1400268bb  call    SOCKADDR_SIZE
0x1400268c0  movzx   r9d, word ptr [r15+0A8h]
0x1400268c8  test    edx, edx
0x1400268ca  mov     r8, [r15+68h]
0x1400268ce  mov     rcx, [r15+28h]
0x1400268d2  setnz   dl
0x1400268d5  movzx   ebx, al
0x1400268d8  call    InetFormatLocalSockAddrAtDispatchLevel
0x1400268dd  mov     dword ptr [rsp+200h+var_1C0], r12d
0x1400268e2  lea     r8, [rbp+0E0h+LockHandle]
0x1400268e9  mov     [rsp+200h+var_1C8], r14
0x1400268ee  lea     rdx, UDP_SEND_MESSAGES_PATH_AF_FAILURE
0x1400268f5  mov     dword ptr [rsp+200h+var_1D0], edi
0x1400268f9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140026900  mov     [rsp+200h+var_1D8], rax
0x140026905  mov     r9, r15
0x140026908  mov     dword ptr [rsp+200h+var_1E0], ebx
0x14002690c  call    McTemplateK0pqbr1qbr3q_EtwWriteTransfer
0x140026911  jmp     loc_1400266C6
0x140026916  mov     al, [rbp+0E0h+var_78]
0x140026919  neg     al
0x14002691b  mov     al, [rdi+1Ah]
0x14002691e  sbb     cl, cl
0x140026920  and     al, 0FDh
0x140026922  and     cl, 2
0x140026925  or      al, cl
0x140026927  cmp     [rbp+0E0h+var_144], 0
0x14002692b  mov     [rdi+1Ah], al
0x14002692e  ja      short loc_140026941
0x140026930  cmp     [r13+18h], bx
0x140026935  jnz     short loc_14002693D
0x140026937  cmp     [rbp+0E0h+var_77], 0
0x14002693b  jnz     short loc_140026941
0x14002693d  xor     cl, cl
0x14002693f  jmp     short loc_140026943
0x140026941  mov     cl, 4
0x140026943  mov     r8, [rbp+0E0h+var_80]
0x140026947  and     al, 0FBh
0x140026949  or      al, cl
0x14002694b  mov     [rbp+0E0h+var_150], r8
0x14002694f  mov     [rdi+1Ah], al
0x140026952  test    r8, r8
0x140026955  jnz     loc_140026A44
0x14002695b  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, r8b
0x140026962  jge     loc_140026A39
0x140026968  mov     rcx, [r15+28h]
0x14002696c  mov     r8d, 1
0x140026972  mov     eax, [rsi+8]
0x140026975  cmp     rcx, r13
0x140026978  mov     r9, [rsi+10h]
0x14002697c  setnz   dl
0x14002697f  mov     word ptr [rsp+200h+var_1D8], r14w
0x140026985  movzx   ecx, word ptr [rcx+18h]
0x140026989  mov     dword ptr [rsp+200h+var_1E0], eax
0x14002698d  call    InetFormatSockAddrAtDispatchLevel
0x140026992  cmp     cs:dword_1402201D4, 0
0x140026999  mov     r14, rax
0x14002699c  jz      loc_140026A39
0x1400269a2  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, 0
0x1400269a9  xorps   xmm0, xmm0
0x1400269ac  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x1400269b3  jge     loc_140026A39
0x1400269b9  mov     edx, [r15+18h]
0x1400269bd  and     edx, 20h
0x1400269c0  jnz     short loc_1400269CA
0x1400269c2  mov     rax, [r15+28h]
  ... truncated ...
```
