# UdpSendMessagesOnPath

- ea: `0x14002620c`
- end: `0x140026eb8`
- name: `UdpSendMessagesOnPath`
- size: `3244`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025200`

## callees

- `0x140012560`
- `0x140012d30`
- `0x140013140`
- `0x1400143c0`
- `0x140014bf0`
- `0x14002620c`
- `0x14002f200`
- `0x140030380`
- `0x140039860`
- `0x14003b680`
- `0x140055bc4`
- `0x14005e680`
- `0x140094778`
- `0x140094d50`
- `0x1400aebd8`
- `0x1400b8080`
- `0x1400b8130`
- `0x1400c3660`
- `0x1400e80c0`
- `0x1400f7488`
- `0x140106780`
- `0x14010cf48`
- `0x14011784c`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!PsGetProcessStartKey` at `0x1400263cd`
- `ntoskrnl!PsGetProcessStartKey` at `0x140026ca2`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400263cd`
- `ntoskrnl!PsGetProcessStartKey` at `0x140026ca2`
- `ntoskrnl!PsGetProcessId` at `0x140026384`
- `ntoskrnl!PsGetProcessId` at `0x140026c7d`
- `ntoskrnl!PsGetProcessId` at `0x140026384`
- `ntoskrnl!PsGetProcessId` at `0x140026c7d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140026499`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140026499`
- `NETIO!RtlCompute37Hash` at `0x1400269d5`
- `NETIO!RtlCompute37Hash` at `0x1400269ec`
- `NETIO!RtlCompute37Hash` at `0x140026a04`
- `NETIO!RtlCompute37Hash` at `0x1400269d5`
- `NETIO!RtlCompute37Hash` at `0x1400269ec`
- `NETIO!RtlCompute37Hash` at `0x140026a04`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400262b8`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400262b8`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140026a3d`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140026a3d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400264de`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400264de`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x140026dba`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x140026dba`

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
              (unsigned int)UDP_SEND_MESSAGES_PATH_AF_FAILURE,
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
              (unsigned int)UDP_SEND_MESSAGES_PATH_NEXT_HOP_MISSING_FAILURE,
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
              (unsigned int)UDP_SEND_MESSAGES_PATH_NEXT_HOP_ADDR_FAILURE,
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
  v74 = (struct _KSPIN_LOCK_QUEUE *)NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData(qword_1402246A8, 80, 8);
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
    (unsigned int)UDP_ENDPOINT_SEND_MESSAGES_V1,
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
  if ( qword_1402244B8 )
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
  if ( TcpipNblTrackerEnabled )
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
0x14002620c  mov     [rsp-8+arg_0], rbx
0x140026211  push    rbp
0x140026212  push    rsi
0x140026213  push    rdi
0x140026214  push    r12
0x140026216  push    r13
0x140026218  push    r14
0x14002621a  push    r15
0x14002621c  lea     rbp, [rsp-0B0h]
0x140026224  sub     rsp, 1D0h
0x14002622b  mov     rax, cs:__security_cookie
0x140026232  xor     rax, rsp
0x140026235  mov     [rbp+0E0h+var_38], rax
0x14002623c  mov     rax, [rbp+0E0h+arg_60]
0x140026243  mov     r13, r9
0x140026246  mov     rsi, [rbp+0E0h+arg_20]
0x14002624d  mov     r15, r8
0x140026250  mov     rbx, [rbp+0E0h+arg_30]
0x140026257  mov     r12d, ecx
0x14002625a  movzx   r14d, [rbp+0E0h+arg_38]
0x140026262  mov     rdi, [rbp+0E0h+arg_78]
0x140026269  mov     [rbp+0E0h+var_100], rax
0x14002626d  mov     rax, [rbp+0E0h+arg_28]
0x140026274  mov     [rbp+0E0h+var_F8], rax
0x140026278  mov     rax, [rbp+0E0h+arg_40]
0x14002627f  mov     [rbp+0E0h+var_108], rax
0x140026283  mov     rax, [rbp+0E0h+arg_58]
0x14002628a  mov     [rbp+0E0h+var_118], rax
0x14002628e  mov     [rbp+0E0h+var_160], dl
0x140026291  mov     qword ptr [rbp+0E0h+var_48], rsi
0x140026298  mov     [rbp+0E0h+var_150], rbx
0x14002629c  mov     [rbp+0E0h+var_148], r14w
0x1400262a1  mov     [rbp+0E0h+var_158], 0
0x1400262a9  mov     [rbp+0E0h+var_140], 0
0x1400262b0  test    ecx, ecx
0x1400262b2  js      loc_14002642A
0x1400262b8  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x1400262bf  nop     dword ptr [rax+rax+00h]
0x1400262c4  test    al, al
0x1400262c6  jz      loc_1400264F2
0x1400262cc  mov     rax, [rsi]
0x1400262cf  mov     rcx, [rax+8]
0x1400262d3  cmp     byte ptr [rcx+58h], 0
0x1400262d7  jz      loc_1400264F2
0x1400262dd  mov     eax, gs:1A4h
0x1400262e5  mov     r12d, 0C00000BEh
0x1400262eb  lea     rdx, [rax+rax*4]
0x1400262ef  mov     rax, cs:TcpipGlobalCounters
0x1400262f6  shl     rdx, 6
0x1400262fa  inc     qword ptr [rdx+rax+50h]
0x1400262ff  cmp     byte ptr cs:WPP_MAIN_CB+148h, 0
0x140026306  jge     loc_14002642A
0x14002630c  mov     rcx, [r15+28h]
0x140026310  movzx   r9d, word ptr [r15+0A8h]
0x140026318  cmp     rcx, r13
0x14002631b  mov     r8, [r15+68h]
0x14002631f  setnz   dl
0x140026322  call    InetFormatLocalSockAddrAtDispatchLevel
0x140026327  mov     rcx, [r15+28h]
0x14002632b  mov     rbx, rax
0x14002632e  mov     r9, [rsi+10h]
0x140026332  cmp     rcx, r13
0x140026335  mov     [rbp+0E0h+var_118], rax
0x140026339  mov     r8d, 1
0x14002633f  mov     eax, [rsi+8]
0x140026342  setnz   dl
0x140026345  movzx   ecx, word ptr [rcx+18h]
0x140026349  mov     word ptr [rsp+200h+var_1D8], r14w
0x14002634f  mov     dword ptr [rsp+200h+var_1E0], eax
0x140026353  call    InetFormatSockAddrAtDispatchLevel
0x140026358  cmp     cs:dword_1402201D4, 0
0x14002635f  mov     [rbp+0E0h+var_138], rax
0x140026363  jz      loc_140026426
0x140026369  cmp     byte ptr cs:WPP_MAIN_CB+148h, 0
0x140026370  xorps   xmm0, xmm0
0x140026373  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x14002637a  jge     loc_140026426
0x140026380  mov     rcx, [r15+30h]; Process
0x140026384  call    cs:__imp_PsGetProcessId
0x14002638b  nop     dword ptr [rax+rax+00h]
0x140026390  mov     rcx, [rsi]
0x140026393  mov     r14, rax
0x140026396  mov     [rbp+0E0h+LockHandle.LockQueue.Lock], 0
0x1400263a1  mov     [rbp+0E0h+LockHandle.LockQueue.Next], r15
0x1400263a8  mov     rdx, [rcx+8]
0x1400263ac  mov     rcx, [rbp+0E0h+var_138]
0x1400263b0  mov     edi, [rdx+8]
0x1400263b3  movzx   ecx, word ptr [rcx]; af
0x1400263b6  call    SOCKADDR_SIZE
0x1400263bb  movzx   ecx, word ptr [rbx]; af
0x1400263be  movzx   esi, al
0x1400263c1  call    SOCKADDR_SIZE
0x1400263c6  mov     rcx, [r15+30h]
0x1400263ca  movzx   ebx, al
0x1400263cd  call    cs:__imp_PsGetProcessStartKey
0x1400263d4  nop     dword ptr [rax+rax+00h]
0x1400263d9  mov     [rsp+200h+var_1A0], rax
0x1400263de  mov     r9d, 2
0x1400263e4  mov     rax, [rbp+0E0h+var_138]
0x1400263e8  lea     r8, [rbp+0E0h+LockHandle]
0x1400263ef  mov     dword ptr [rsp+200h+var_1A8], edi
0x1400263f3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400263fa  mov     dword ptr [rsp+200h+var_1B0], r14d
0x1400263ff  mov     [rsp+200h+var_1C0], rax
0x140026404  mov     rax, [rbp+0E0h+var_118]
0x140026408  mov     dword ptr [rsp+200h+var_1C8], esi
0x14002640c  mov     [rsp+200h+var_1D0], rax
0x140026411  mov     dword ptr [rsp+200h+var_1D8], ebx
0x140026415  mov     [rsp+200h+var_1E0], r15
0x14002641a  call    McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer
0x14002641f  mov     rsi, qword ptr [rbp+0E0h+var_48]
0x140026426  mov     rbx, [rbp+0E0h+var_150]
0x14002642a  mov     rdi, [rbp+0E0h+var_158]
0x14002642e  test    rsi, rsi
0x140026431  jz      short loc_14002643E
0x140026433  mov     rdx, rsi
0x140026436  mov     rcx, r13
0x140026439  call    InetLeavePathAf
0x14002643e  test    rbx, rbx
0x140026441  jz      short loc_14002644E
0x140026443  mov     rdx, rbx
0x140026446  mov     rcx, r13
0x140026449  call    InetDereferenceNextHopAf
0x14002644e  mov     rsi, [rbp+0E0h+var_F8]
0x140026452  mov     r14d, 103h
0x140026458  test    rsi, rsi
0x14002645b  jz      short loc_1400264B4
0x14002645d  cmp     r12d, r14d
0x140026460  jnz     short loc_1400264A8
0x140026462  cmp     rsi, [r15+68h]
0x140026466  jz      short loc_1400264A8
0x140026468  xorps   xmm0, xmm0
0x14002646b  lea     rdx, [rbp+0E0h+LockHandle]
0x140026472  xor     eax, eax
0x140026474  mov     rcx, r15
0x140026477  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x14002647e  mov     qword ptr [rbp+0E0h+LockHandle.OldIrql], rax
0x140026485  call    RtlAcquireWriteLock
0x14002648a  mov     rbx, [r15+68h]
0x14002648e  lea     rcx, [rbp+0E0h+LockHandle]; LockHandle
0x140026495  mov     [r15+68h], rsi
0x140026499  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400264a0  nop     dword ptr [rax+rax+00h]
0x1400264a5  mov     rsi, rbx
0x1400264a8  mov     rcx, [r15+70h]
0x1400264ac  mov     rdx, rsi
0x1400264af  call    InetDereferenceLocalAddressAf
0x1400264b4  cmp     r13, [r15+70h]
0x1400264b8  jz      short loc_1400264C7
0x1400264ba  test    r13, r13
0x1400264bd  jz      short loc_1400264C7
0x1400264bf  mov     rcx, r13
0x1400264c2  call    _InetDereferenceAf
0x1400264c7  cmp     r12d, r14d
0x1400264ca  jz      loc_140026E8A
0x1400264d0  test    rdi, rdi
0x1400264d3  jz      loc_140026E82
0x1400264d9  xor     edx, edx
0x1400264db  mov     rcx, rdi
0x1400264de  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1400264e5  nop     dword ptr [rax+rax+00h]
0x1400264ea  mov     r12d, r14d
0x1400264ed  jmp     loc_140026E8A
0x1400264f2  mov     eax, [rbp+0E0h+arg_68]
0x1400264f8  test    eax, eax
0x1400264fa  jz      short loc_140026520
0x1400264fc  mov     r8, [rbp+0E0h+var_100]
0x140026500  mov     r9d, eax
0x140026503  movzx   edx, word ptr [r13+18h]
0x140026508  mov     rcx, r15
0x14002650b  mov     [rsp+200h+var_1E0], rdi
0x140026510  call    UdpParseAncillaryData
0x140026515  mov     r12d, eax
0x140026518  test    eax, eax
0x14002651a  js      loc_14002642A
0x140026520  mov     r12b, [rbp+0E0h+var_160]
0x140026524  mov     ebx, 17h
0x140026529  test    r12b, r12b
0x14002652c  jnz     loc_1400268AA
0x140026532  mov     eax, [r15+18h]
0x140026536  test    al, al
0x140026538  jns     short loc_140026557
0x14002653a  cmp     dword ptr [rdi+8], 0
0x14002653e  ja      short loc_140026557
0x140026540  mov     rdx, rsi
0x140026543  mov     rcx, r13
0x140026546  call    InetGetNextHopFromPath
0x14002654b  mov     r8, rax
0x14002654e  mov     [rbp+0E0h+var_150], rax
0x140026552  jmp     loc_1400268B4
0x140026557  xor     edx, edx; Val
0x140026559  lea     rcx, [rbp+0E0h+var_F0]; void *
0x14002655d  mov     r8d, 88h; Size
0x140026563  call    memset
0x140026568  mov     r8, [rbp+0E0h+var_118]
0x14002656c  lea     rax, [rbp+0E0h+var_144]
0x140026570  lea     r9, [rbp+0E0h+var_F0]
0x140026574  mov     [rsp+200h+var_1E0], rax
0x140026579  mov     rdx, rsi
0x14002657c  mov     [rbp+0E0h+var_144], 0
0x140026583  mov     rcx, r13
0x140026586  call    InetQueryPathInfoAf
0x14002658b  mov     r12d, eax
0x14002658e  test    eax, eax
0x140026590  jns     loc_140026676
0x140026596  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, 0
0x14002659d  jge     loc_140026426
0x1400265a3  mov     rcx, [r15+28h]
0x1400265a7  mov     r8d, 1
0x1400265ad  mov     eax, [rsi+8]
0x1400265b0  cmp     rcx, r13
0x1400265b3  mov     r9, [rsi+10h]
0x1400265b7  setnz   dl
0x1400265ba  mov     word ptr [rsp+200h+var_1D8], r14w
0x1400265c0  movzx   ecx, word ptr [rcx+18h]
0x1400265c4  mov     dword ptr [rsp+200h+var_1E0], eax
0x1400265c8  call    InetFormatSockAddrAtDispatchLevel
0x1400265cd  cmp     cs:dword_1402201D4, 0
0x1400265d4  mov     r14, rax
0x1400265d7  jz      loc_140026426
0x1400265dd  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, 0
0x1400265e4  xorps   xmm0, xmm0
0x1400265e7  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x1400265ee  jge     loc_140026426
0x1400265f4  mov     edx, [r15+18h]
0x1400265f8  and     edx, 20h
0x1400265fb  jnz     short loc_140026605
0x1400265fd  mov     rax, [r15+28h]
0x140026601  movzx   ebx, word ptr [rax+18h]
0x140026605  movzx   ecx, word ptr [r14]; af
0x140026609  mov     [rbp+0E0h+LockHandle.LockQueue.Next], r15
0x140026610  call    SOCKADDR_SIZE
0x140026615  movzx   ecx, bx; af
0x140026618  movzx   edi, al
0x14002661b  call    SOCKADDR_SIZE
0x140026620  movzx   r9d, word ptr [r15+0A8h]
0x140026628  test    edx, edx
0x14002662a  mov     r8, [r15+68h]
0x14002662e  mov     rcx, [r15+28h]
0x140026632  setnz   dl
0x140026635  movzx   ebx, al
0x140026638  call    InetFormatLocalSockAddrAtDispatchLevel
0x14002663d  mov     dword ptr [rsp+200h+var_1C0], r12d
0x140026642  lea     r8, [rbp+0E0h+LockHandle]
0x140026649  mov     [rsp+200h+var_1C8], r14
0x14002664e  lea     rdx, UDP_SEND_MESSAGES_PATH_AF_FAILURE
0x140026655  mov     dword ptr [rsp+200h+var_1D0], edi
0x140026659  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140026660  mov     [rsp+200h+var_1D8], rax
0x140026665  mov     r9, r15
0x140026668  mov     dword ptr [rsp+200h+var_1E0], ebx
0x14002666c  call    McTemplateK0pqbr1qbr3q_EtwWriteTransfer
0x140026671  jmp     loc_140026426
0x140026676  mov     al, [rbp+0E0h+var_78]
0x140026679  neg     al
0x14002667b  mov     al, [rdi+1Ah]
0x14002667e  sbb     cl, cl
0x140026680  and     al, 0FDh
0x140026682  and     cl, 2
0x140026685  or      al, cl
0x140026687  cmp     [rbp+0E0h+var_144], 0
0x14002668b  mov     [rdi+1Ah], al
0x14002668e  ja      short loc_1400266A1
0x140026690  cmp     [r13+18h], bx
0x140026695  jnz     short loc_14002669D
0x140026697  cmp     [rbp+0E0h+var_77], 0
0x14002669b  jnz     short loc_1400266A1
0x14002669d  xor     cl, cl
0x14002669f  jmp     short loc_1400266A3
0x1400266a1  mov     cl, 4
0x1400266a3  mov     r8, [rbp+0E0h+var_80]
0x1400266a7  and     al, 0FBh
0x1400266a9  or      al, cl
0x1400266ab  mov     [rbp+0E0h+var_150], r8
0x1400266af  mov     [rdi+1Ah], al
0x1400266b2  test    r8, r8
0x1400266b5  jnz     loc_1400267A4
0x1400266bb  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, r8b
0x1400266c2  jge     loc_140026799
0x1400266c8  mov     rcx, [r15+28h]
0x1400266cc  mov     r8d, 1
0x1400266d2  mov     eax, [rsi+8]
0x1400266d5  cmp     rcx, r13
0x1400266d8  mov     r9, [rsi+10h]
0x1400266dc  setnz   dl
0x1400266df  mov     word ptr [rsp+200h+var_1D8], r14w
0x1400266e5  movzx   ecx, word ptr [rcx+18h]
0x1400266e9  mov     dword ptr [rsp+200h+var_1E0], eax
0x1400266ed  call    InetFormatSockAddrAtDispatchLevel
0x1400266f2  cmp     cs:dword_1402201D4, 0
0x1400266f9  mov     r14, rax
0x1400266fc  jz      loc_140026799
0x140026702  cmp     byte ptr cs:WPP_MAIN_CB+14Ah, 0
0x140026709  xorps   xmm0, xmm0
0x14002670c  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x140026713  jge     loc_140026799
0x140026719  mov     edx, [r15+18h]
0x14002671d  and     edx, 20h
0x140026720  jnz     short loc_14002672A
0x140026722  mov     rax, [r15+28h]
  ... truncated ...
```
