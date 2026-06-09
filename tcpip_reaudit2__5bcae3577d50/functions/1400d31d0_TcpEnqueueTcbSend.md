# TcpEnqueueTcbSend

- ea: `0x1400d31d0`
- end: `0x1400d3e23`
- name: `TcpEnqueueTcbSend`
- size: `3155`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, char, char)`
- caller_count: `4`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b8438`
- `0x1400d3160`
- `0x1400d3190`
- `0x14012c6f0`

## callees

- `0x14001edf0`
- `0x14002f4a0`
- `0x140035d80`
- `0x1400387d0`
- `0x140050a98`
- `0x1400540a4`
- `0x140094e3c`
- `0x140095af0`
- `0x1400ae7f8`
- `0x1400b7ca0`
- `0x1400b7d50`
- `0x1400d31d0`
- `0x1400d3e2c`
- `0x1400d3e7c`
- `0x1400d4018`
- `0x1401067a0`
- `0x140150b50`
- `0x140150c1c`
- `0x140163b20`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400d3a10`
- `ntoskrnl!KeBugCheckEx` at `0x1400d3a10`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401cce3b`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401cce3b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400d3318`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400d3318`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400d3212`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400d3212`
- `ntoskrnl!PsGetProcessId` at `0x1401ccddd`
- `ntoskrnl!PsGetProcessId` at `0x1401ccddd`
- `ntoskrnl!KeReadStateEvent` at `0x1400d3229`
- `ntoskrnl!KeReadStateEvent` at `0x1400d3229`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d36e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d3818`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d386c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d397a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d3aae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d36e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d3818`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d386c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d397a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d3aae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d3265`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d3265`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400d356f`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400d356f`
- `NETIO!WfpStreamInspectSend` at `0x1400d37c4`
- `NETIO!WfpStreamInspectSend` at `0x1400d37c4`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400d32a6`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400d39e6`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400d32a6`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400d39e6`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x1400d3c1b`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x1400d3c1b`

## pseudocode

```c
__int64 __fastcall TcpEnqueueTcbSend(unsigned __int16 *SpinLock, __int64 a2, char a3, KIRQL *a4, char a5, char a6)
{
  __int64 v6; // r13
  KIRQL *v8; // r12
  KIRQL v11; // si
  int v12; // ecx
  unsigned __int64 v13; // rbx
  _QWORD *v14; // rax
  KSPIN_LOCK v15; // rsi
  int v16; // edx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rbx
  char *v20; // rcx
  unsigned __int64 *v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rbx
  char v24; // r10
  KSPIN_LOCK v25; // r11
  __int64 v26; // rcx
  unsigned __int8 *v27; // r8
  char v28; // dl
  int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // ebx
  int v33; // r9d
  int v34; // r10d
  char v35; // r11
  unsigned int v36; // r8d
  unsigned int v37; // edx
  unsigned int v38; // r8d
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  bool v41; // zf
  __int64 v42; // rax
  KIRQL v43; // dl
  unsigned __int64 v44; // rcx
  KSPIN_LOCK v45; // rbx
  int v46; // esi
  unsigned __int8 v47; // cf
  int v48; // r9d
  int v49; // edx
  int v50; // edx
  int v51; // edx
  unsigned int v52; // ecx
  unsigned int v53; // edx
  int v54; // edx
  __int64 v55; // rax
  KIRQL *v56; // rcx
  int v57; // eax
  int v58; // ecx
  int v59; // r9d
  const wchar_t *v60; // rdx
  int v61; // r8d
  int v62; // ecx
  __int64 BindingHandleByTcb; // rax
  int v64; // eax
  int v65; // eax
  unsigned int v66; // r8d
  __int64 v67; // rcx
  int v68; // ebx
  int v69; // ebx
  int v70; // r14d
  struct _KPROCESS *v71; // rcx
  char *ProcessId; // rax
  KSPIN_LOCK v73; // r9
  bool v74; // r13
  int v75; // edx
  __int64 v76; // r9
  int v77; // ecx
  __int64 v78; // rax
  KSPIN_LOCK v79; // rcx
  __int64 v80; // r12
  int v81; // r14d
  int v82; // ebx
  __int64 v83; // r8
  __int64 v84; // rax
  int v85; // edx
  char v86; // [rsp+28h] [rbp-91h]
  __int16 v87; // [rsp+28h] [rbp-91h]
  char v88; // [rsp+40h] [rbp-79h]
  int v89; // [rsp+40h] [rbp-79h]
  KIRQL v91; // [rsp+91h] [rbp-28h] BYREF
  char v92[2]; // [rsp+92h] [rbp-27h] BYREF
  int v93; // [rsp+94h] [rbp-25h]
  char *v94; // [rsp+98h] [rbp-21h]
  KIRQL *v95; // [rsp+A0h] [rbp-19h]
  __int64 v96; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v97; // [rsp+B0h] [rbp-9h] BYREF

  v95 = a4;
  v8 = a4;
  v91 = 0;
  v96 = 0;
  if ( KeGetCurrentIrql() < 2u && !KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType) )
    TcpMppNppEvaluationHelper();
  if ( !v8 )
  {
    v8 = &v91;
    v95 = &v91;
    v91 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
    v11 = v91;
    if ( !a3 )
    {
      v12 = *((_DWORD *)SpinLock + 28);
      if ( ((v12 - 3) & 0xFFFFFFFA) == 0 && v12 != 8 )
        goto LABEL_8;
      v64 = *((_DWORD *)SpinLock + 30);
      if ( (v64 & 0x100) != 0 )
      {
        v31 = -1073741299;
      }
      else
      {
        v31 = -1073741436;
        if ( (v64 & 0x200) != 0 )
          v31 = -1073741247;
      }
LABEL_125:
      v43 = v11;
LABEL_68:
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v43);
      goto LABEL_47;
    }
    if ( (*((_DWORD *)SpinLock + 31) & 2) != 0
      || (v57 = *((_DWORD *)SpinLock + 28), (unsigned int)(v57 - 2) > 2) && v57 != 7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_2f3e4d20c14e3d719f15a9885d09f3c5_Traceguids, SpinLock);
      }
      v31 = -1073741436;
      goto LABEL_125;
    }
  }
LABEL_8:
  if ( (SpinLock[402] & 8) != 0 )
  {
    v31 = -1073741436;
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, *v8);
    if ( dword_1402201D4
      && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
      && (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
    {
      v97 = (unsigned __int64)SpinLock;
      McTemplateK0pqp_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_SILENTMODE,
        (unsigned int)&v97,
        (_DWORD)SpinLock,
        1,
        a2);
    }
  }
  else
  {
    if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
    {
      v42 = *(_QWORD *)(**((_QWORD **)SpinLock + 4) + 8LL);
      if ( *(_BYTE *)(v42 + 88) )
      {
        LODWORD(v42) = HIDWORD(KeGetPcr()[1].LockArray);
        v31 = -1073741634;
        ++*((_QWORD *)TcpipGlobalCounters + 40 * v42 + 10);
        LOBYTE(v94) = *(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 0x80;
        if ( *((char *)&WPP_MAIN_CB.Reserved + 8) < 0
          && dword_1402201D4
          && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
        {
          v68 = *((_DWORD *)SpinLock + 30);
          v97 = 0;
          v69 = v68 & 8;
          if ( v69 )
            v70 = 23;
          else
            v70 = *(unsigned __int16 *)(*((_QWORD *)SpinLock + 3) + 24LL);
          v71 = (struct _KPROCESS *)*((_QWORD *)SpinLock + 106);
          v93 = v70;
          ProcessId = (char *)PsGetProcessId(v71);
          v73 = *((_QWORD *)SpinLock + 4);
          v74 = v69 != 0;
          v87 = SpinLock[59];
          v75 = *(_DWORD *)(v73 + 8);
          v76 = *(_QWORD *)(v73 + 16);
          v77 = *(unsigned __int16 *)(*((_QWORD *)SpinLock + 3) + 24LL);
          v94 = ProcessId;
          v78 = InetFormatSockAddrAtDispatchLevel(v77, v69 != 0, 1, v76, v75, v87);
          v79 = *((_QWORD *)SpinLock + 106);
          v80 = v78;
          v97 = (unsigned __int64)SpinLock;
          PsGetProcessStartKey(v79);
          v81 = SOCKADDR_SIZE(v70);
          v82 = SOCKADDR_SIZE(v93);
          v84 = InetFormatLocalSockAddrAtDispatchLevel(*((_QWORD *)SpinLock + 3), v74, v83, SpinLock[58]);
          McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            v85,
            (unsigned int)&v97,
            1,
            (char)SpinLock,
            v82,
            v84,
            v81,
            v80);
          v8 = v95;
          v31 = -1073741634;
        }
        v43 = *v8;
        goto LABEL_68;
      }
    }
    if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
      __fastfail(0xEu);
    if ( (*((_DWORD *)SpinLock + 202) & 0x100) != 0 && a5 )
    {
      v45 = *((_QWORD *)SpinLock + 113);
      v92[0] = 0;
      if ( (*(_DWORD *)(v45 + 48) & 0x200) != 0 )
        v6 = 0;
      else
        v6 = InitializeEndpointContextFromParentContext(v45);
      if ( (int)v6 < 0 )
        v46 = 0;
      else
        v46 = WfpStreamInspectSend(v45, a2, v92, &v96);
      if ( dword_1402201D4 )
      {
        v97 = 0;
        if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
        {
          *(_QWORD *)&v97 = SpinLock;
          McTemplateK0ppqqq_EtwWriteTransfer(
            &MICROSOFT_TCPIP_PROVIDER_Context,
            INET_INSPECT,
            &v97,
            SpinLock,
            v45,
            0,
            v46,
            v6);
        }
      }
      if ( v92[0] )
        *((_DWORD *)SpinLock + 202) &= ~0x100u;
      if ( v46 != 1 )
      {
        if ( v46 != 2 || *((_DWORD *)SpinLock + 28) != 2 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, *v8);
          if ( v46 != 2 )
          {
            TcpDereferenceTcb(SpinLock);
            v31 = -1073741790;
            goto LABEL_47;
          }
LABEL_46:
          v31 = 259;
          goto LABEL_47;
        }
        SpinLock[64] &= ~0x200u;
LABEL_92:
        KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, *v8);
        goto LABEL_46;
      }
    }
    LODWORD(v6) = HIDWORD(KeGetPcr()[1].LockArray);
    v13 = TcpSendRequestPool + ((unsigned __int64)(unsigned int)(v6 + 1) << 7);
    if ( !*(_BYTE *)(v13 + 176) )
      PplpLazyInitializeLookasideList(TcpSendRequestPool, v13 + 64);
    v14 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 64));
    v15 = (KSPIN_LOCK)v14;
    if ( v14 )
    {
      v16 = 0;
      v14[4] = *(_QWORD *)a2;
      v14[6] = *(_QWORD *)(a2 + 16);
      v14[1] = *(_QWORD *)(a2 + 32);
      v14[8] = *(_QWORD *)(a2 + 48);
      v14[3] = *(_QWORD *)(a2 + 48);
      *((_DWORD *)v14 + 4) = *(_DWORD *)(a2 + 40);
      v14[5] = 1;
      *v14 = 0;
      *((_DWORD *)v14 + 18) = 0;
      v17 = *(_QWORD *)(a2 + 56);
      v14[12] = v17;
      *((_DWORD *)v14 + 26) = v6;
      v18 = *(_DWORD *)(a2 + 24);
      if ( v18 )
      {
        if ( (v18 & 1) != 0 )
        {
          v16 = 2;
          *(_DWORD *)(v15 + 72) = 2;
        }
        if ( (*(_DWORD *)(a2 + 24) & 2) != 0 )
        {
          v16 |= 4u;
          *(_DWORD *)(v15 + 72) = v16;
        }
        if ( (*(_DWORD *)(a2 + 24) & 4) != 0 )
        {
          *(_DWORD *)(v15 + 72) = v16 | 8;
          *(_QWORD *)(v15 + 32) = *(_QWORD *)(a2 + 8);
        }
      }
      *(_QWORD *)(v15 + 80) = SpinLock;
      if ( v17 && Microsoft_Windows_Networking_CorrelationEnabled )
        TcpipEtwTransferActivity(*(_QWORD *)(v15 + 96), SpinLock, 10);
      if ( (TcpStartedModules & 0x100) != 0 )
      {
        v19 = MEMORY[0xFFFFF78000000008];
        v20 = (char *)TimerTable + 240 * (unsigned int)v6;
        v94 = v20;
        v21 = (unsigned __int64 *)(v20 + 16);
        v95 = (KIRQL *)(v20 + 16);
        if ( MEMORY[0xFFFFF78000000008] != *((_QWORD *)v20 + 3) )
        {
          v55 = TcpConvertPerformanceCounterToMicroseconds(v20);
          v56 = v95;
          *(_QWORD *)v95 = v55;
          *((_QWORD *)v94 + 3) = v19;
          v21 = (unsigned __int64 *)v56;
        }
        v22 = *v21;
      }
      else
      {
        v22 = TcpConvertPerformanceCounterToMicroseconds(0);
      }
      v23 = v22 / 0x3E8;
      if ( *((_QWORD *)SpinLock + 57) )
      {
        v24 = a3;
        **((_QWORD **)SpinLock + 58) = v15;
        *((_QWORD *)SpinLock + 58) = v15;
        *((_QWORD *)SpinLock + 56) += *(_QWORD *)(v15 + 64);
        v25 = *((_QWORD *)SpinLock + 56);
      }
      else
      {
        v33 = *((_DWORD *)SpinLock + 116);
        if ( v33 && v33 - (int)v23 < 0 )
        {
          v34 = *((_DWORD *)SpinLock + 28);
          v35 = *((_BYTE *)SpinLock + 752);
          if ( v34 < 4 )
          {
            v38 = SpinLock[390] << v35;
          }
          else
          {
            v36 = SpinLock[389];
            v37 = (*((_DWORD *)SpinLock + 179) + (*((_DWORD *)SpinLock + 178) >> 3)) / 0x3E8u;
            if ( v36 <= v37 )
              v36 = (*((_DWORD *)SpinLock + 179) + (*((_DWORD *)SpinLock + 178) >> 3)) / 0x3E8u;
            v38 = v36 << v35;
            if ( v37 + 56 > v38 )
              v38 = v37 + 56;
          }
          v39 = *((_DWORD *)SpinLock + 193);
          if ( v39 - 1 > 0xFFFFFFFD || (v54 = *((_DWORD *)SpinLock + 187), v39 >= v54 + v38) )
          {
            if ( v34 < 4 && SpinLock[390] == 1000 && *((_BYTE *)SpinLock + 789) == 4 )
            {
              v58 = *((_DWORD *)SpinLock + 187);
              if ( v58 + v38 > 0x5208 )
                v38 = 21000 - v58;
            }
          }
          else
          {
            v38 = v39 - v54;
          }
          if ( v38 > 0xEA60 )
            v38 = 60000;
          v40 = v23 - v33;
          v93 = v38;
          if ( (int)v23 - v33 > v38 + 10 )
          {
            *((_DWORD *)SpinLock + 30) &= ~0x8000000u;
            v47 = _bittest16((const signed __int16 *)SpinLock + 402, 9u);
            v48 = *((_DWORD *)SpinLock + 49);
            LODWORD(v94) = v48;
            if ( v47 )
            {
              v49 = SpinLock[396] & 7;
              if ( v49 != 1 && (v50 = v49 - 2) != 0 && (v51 = v50 - 3) != 0 )
              {
                if ( v51 == 1 )
                {
                  Bbr2OnCWndEvent(SpinLock);
                  LOBYTE(v38) = v93;
                  LOBYTE(v48) = (_BYTE)v94;
                }
              }
              else
              {
                *((_QWORD *)SpinLock + 26) += v40;
              }
            }
            if ( dword_1402201D4
              && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
              && SBYTE2(WPP_MAIN_CB.Reserved) < 0 )
            {
              v88 = *((_DWORD *)SpinLock + 116);
              v86 = *((_DWORD *)SpinLock + 49);
              v97 = (unsigned __int64)SpinLock;
              McTemplateK0pqqqqqq_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                (unsigned int)TCP_SEND_IDLE_END,
                (unsigned int)&v97,
                (_DWORD)SpinLock,
                v48,
                v86,
                v6,
                v23,
                v88,
                v38);
            }
            if ( (SpinLock[398] & 2) != 0 )
            {
              v52 = *((_DWORD *)SpinLock + 44) * SpinLock[391];
              v53 = *((_DWORD *)SpinLock + 49);
              if ( v53 > v52 )
              {
                if ( dword_1402201D4
                  && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
                  && SBYTE2(WPP_MAIN_CB.Reserved) < 0 )
                {
                  v89 = *((_DWORD *)SpinLock + 116);
                  v97 = (unsigned __int64)SpinLock;
                  McTemplateK0pqqqqqq_EtwWriteTransfer(
                    (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                    (unsigned int)TCP_CWND_RESTART,
                    (unsigned int)&v97,
                    (_DWORD)SpinLock,
                    v53,
                    v52,
                    v6,
                    v23,
                    v89,
                    v93);
                }
                *((_DWORD *)SpinLock + 49) = *((_DWORD *)SpinLock + 44) * SpinLock[391];
              }
            }
          }
        }
        v41 = *((_DWORD *)SpinLock + 28) == 2;
        v24 = a3;
        *((_QWORD *)SpinLock + 57) = v15;
        *((_QWORD *)SpinLock + 58) = v15;
        v25 = *(_QWORD *)(v15 + 64);
        *((_QWORD *)SpinLock + 56) = v25;
        if ( v41 && !a3 )
          SpinLock[64] &= ~0x200u;
      }
      if ( dword_1402201D4
        && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
        && (BYTE5(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
      {
        v59 = *(_DWORD *)(a2 + 48);
        v60 = L"injected";
        v61 = v25 + *((_DWORD *)SpinLock + 34) - v59;
        v62 = *((_DWORD *)SpinLock + 178) >> 3;
        v97 = (unsigned __int64)SpinLock;
        if ( !v24 )
          v60 = L"posted";
        McTemplateK0pzqqqpxxxqqqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (_DWORD)v60,
          (unsigned int)&v97,
          (_DWORD)SpinLock,
          (__int64)v60,
          v59,
          v61,
          v25,
          *(_QWORD *)(a2 + 56),
          *((_QWORD *)SpinLock + 50),
          *((_QWORD *)SpinLock + 52),
          *((_QWORD *)SpinLock + 54),
          *((_DWORD *)SpinLock + 49),
          v62,
          *((_DWORD *)SpinLock + 281),
          *((_DWORD *)SpinLock + 283),
          *((_DWORD *)SpinLock + 284));
      }
      v26 = *(_QWORD *)(*((_QWORD *)SpinLock + 3) + 128LL) + 192 * v6;
      *(_QWORD *)(v26 + 88) += *(_QWORD *)(v15 + 64);
      if ( !*((_QWORD *)SpinLock + 5) || SpinLock[406] )
      {
LABEL_35:
        *(_DWORD *)(v15 + 88) = v23;
        if ( *((_QWORD *)SpinLock + 57) == *((_QWORD *)SpinLock + 58) )
        {
          *((_QWORD *)SpinLock + 59) = v15;
          v27 = (unsigned __int8 *)SpinLock + 793;
          *((_QWORD *)SpinLock + 60) = *(_QWORD *)(v15 + 24);
          *((_QWORD *)SpinLock + 61) = *(_QWORD *)(v15 + 8);
          *((_DWORD *)SpinLock + 124) = *(_DWORD *)(v15 + 16);
        }
        else
        {
          if ( !*((_QWORD *)SpinLock + 59) )
          {
            *((_QWORD *)SpinLock + 59) = v15;
            *((_QWORD *)SpinLock + 60) = *(_QWORD *)(v15 + 24);
            *((_QWORD *)SpinLock + 61) = *(_QWORD *)(v15 + 8);
            *((_DWORD *)SpinLock + 124) = *(_DWORD *)(v15 + 16);
          }
          v27 = (unsigned __int8 *)SpinLock + 793;
          if ( (((*(_BYTE *)(v15 + 72) & 4) == 0) & (unsigned __int8)~(*((_BYTE *)SpinLock + 793) >> 5)) != 0 )
          {
            v44 = *((_QWORD *)SpinLock + 56) - (unsigned int)(*((_DWORD *)SpinLock + 36) - *((_DWORD *)SpinLock + 34));
            if ( *((unsigned int *)SpinLock + 44) > v44 && v44 < (unsigned __int64)*((unsigned int *)SpinLock + 41) >> 1 )
            {
              v28 = 0;
              goto LABEL_38;
            }
          }
        }
        v28 = 1;
LABEL_38:
        if ( (*(_DWORD *)(v15 + 72) & 2) != 0 )
        {
          v28 = 1;
          v65 = *((_DWORD *)SpinLock + 30);
          *((_DWORD *)SpinLock + 37) = *((_DWORD *)SpinLock + 112) + *((_DWORD *)SpinLock + 34) - (*v27 >> 7);
          if ( (v65 & 0x800) == 0 )
            *((_DWORD *)SpinLock + 30) = v65 | 0x1800;
        }
        if ( (SpinLock[388] & 8) != 0 )
        {
          v66 = *((_DWORD *)SpinLock + 112) + *((_DWORD *)SpinLock + 34) - *((_DWORD *)SpinLock + 36);
          v67 = *(_QWORD *)(*((_QWORD *)SpinLock + 116) + 24LL);
          if ( *(_DWORD *)(v67 + 4) < v66 )
            *(_DWORD *)(v67 + 4) = v66;
        }
        if ( v28 && !a6 )
        {
          v29 = *((_DWORD *)SpinLock + 30);
          if ( (v29 & 0x100000) != 0 )
          {
            **((_BYTE **)SpinLock + 69) |= 8u;
          }
          else
          {
            if ( (v29 & 0x200000) == 0 )
            {
              if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
                __fastfail(0xEu);
              TcpTcbSend((PKSPIN_LOCK)SpinLock);
              TcpDereferenceTcb(SpinLock);
              goto LABEL_46;
            }
            ***((_BYTE ***)SpinLock + 82) |= 8u;
          }
        }
        goto LABEL_92;
      }
      if ( *((_QWORD *)SpinLock + 56) == *(_QWORD *)(v15 + 64) )
      {
        if ( (SpinLock[402] & 0x20) == 0 )
        {
LABEL_139:
          BindingHandleByTcb = OlmQueryBindingHandleByTcb(SpinLock);
          if ( (unsigned __int8)NetioNcmFastActiveReferenceRequest(11, 0, BindingHandleByTcb) )
            SpinLock[402] |= 0x20u;
          goto LABEL_35;
        }
        if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
          KeBugCheckEx(0x150u, 0, 0, 0, 0);
      }
      if ( (SpinLock[402] & 0x20) != 0 )
        goto LABEL_35;
      goto LABEL_139;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, *v8);
    v31 = -1073741801;
  }
LABEL_47:
  if ( v96 )
  {
    LOBYTE(v30) = 1;
    NetioDereferenceNetBufferList(v96, v30);
  }
  return v31;
}

```

## disassembly

```asm
0x1400d31d0  push    rbp
0x1400d31d2  push    rbx
0x1400d31d3  push    rdi
0x1400d31d4  push    r12
0x1400d31d6  push    r14
0x1400d31d8  lea     rbp, [rsp-27h]
0x1400d31dd  sub     rsp, 0E0h
0x1400d31e4  mov     rax, cs:__security_cookie
0x1400d31eb  xor     rax, rsp
0x1400d31ee  mov     [rbp+47h+var_40], rax
0x1400d31f2  movzx   ebx, r8b
0x1400d31f6  mov     [rbp+47h+var_60], r9
0x1400d31fa  mov     [rbp+47h+var_70], bl
0x1400d31fd  mov     r12, r9
0x1400d3200  mov     r14, rdx
0x1400d3203  mov     [rbp+47h+var_6F], 0
0x1400d3207  mov     rdi, rcx
0x1400d320a  mov     [rbp+47h+var_58], 0
0x1400d3212  call    cs:__imp_KeGetCurrentIrql
0x1400d3219  nop     dword ptr [rax+rax+00h]
0x1400d321e  cmp     al, 2
0x1400d3220  jnb     short loc_1400D323D
0x1400d3222  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; Event
0x1400d3229  call    cs:__imp_KeReadStateEvent
0x1400d3230  nop     dword ptr [rax+rax+00h]
0x1400d3235  test    eax, eax
0x1400d3237  jz      loc_1400D3CBB
0x1400d323d  mov     [rsp+100h+arg_10], rsi
0x1400d3245  mov     [rsp+100h+var_28], r13
0x1400d324d  mov     [rsp+100h+var_30], r15
0x1400d3255  test    r12, r12
0x1400d3258  jnz     short loc_1400D3299
0x1400d325a  lea     r12, [rbp+47h+var_6F]
0x1400d325e  mov     rcx, rdi; SpinLock
0x1400d3261  mov     [rbp+47h+var_60], r12
0x1400d3265  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d326c  nop     dword ptr [rax+rax+00h]
0x1400d3271  mov     [rbp+47h+var_6F], al
0x1400d3274  movzx   esi, al
0x1400d3277  test    bl, bl
0x1400d3279  jnz     loc_1400D3A1D
0x1400d327f  mov     ecx, [rdi+70h]
0x1400d3282  lea     eax, [rcx-3]
0x1400d3285  test    eax, 0FFFFFFFAh
0x1400d328a  jnz     loc_1400D3CED
0x1400d3290  cmp     ecx, 8
0x1400d3293  jz      loc_1400D3CED
0x1400d3299  test    byte ptr [rdi+324h], 8
0x1400d32a0  jnz     loc_1400D3AA1
0x1400d32a6  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x1400d32ad  nop     dword ptr [rax+rax+00h]
0x1400d32b2  test    al, al
0x1400d32b4  jnz     loc_1400D3697
0x1400d32ba  mov     r15d, 1
0x1400d32c0  mov     eax, r15d
0x1400d32c3  lock xadd [rdi+8], rax
0x1400d32c9  inc     rax
0x1400d32cc  cmp     rax, r15
0x1400d32cf  jle     loc_1400D3C3C
0x1400d32d5  test    dword ptr [rdi+328h], 100h
0x1400d32df  jnz     loc_1400D3788
0x1400d32e5  mov     r13d, gs:1A4h
0x1400d32ee  mov     rcx, cs:TcpSendRequestPool
0x1400d32f5  lea     ebx, [r13+1]
0x1400d32f9  shl     rbx, 7
0x1400d32fd  add     rbx, rcx
0x1400d3300  movzx   eax, byte ptr [rbx+0B0h]
0x1400d3307  test    al, al
0x1400d3309  jnz     short loc_1400D3314
0x1400d330b  lea     rdx, [rbx+40h]
0x1400d330f  call    PplpLazyInitializeLookasideList
0x1400d3314  lea     rcx, [rbx+40h]; Lookaside
0x1400d3318  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400d331f  nop     dword ptr [rax+rax+00h]
0x1400d3324  mov     rsi, rax
0x1400d3327  test    rax, rax
0x1400d332a  jz      loc_1400D3972
0x1400d3330  mov     rax, [r14]
0x1400d3333  xor     edx, edx
0x1400d3335  mov     [rsi+20h], rax
0x1400d3339  mov     rax, [r14+10h]
0x1400d333d  mov     [rsi+30h], rax
0x1400d3341  mov     rax, [r14+20h]
0x1400d3345  mov     [rsi+8], rax
0x1400d3349  mov     rax, [r14+30h]
0x1400d334d  mov     [rsi+40h], rax
0x1400d3351  mov     rax, [r14+30h]
0x1400d3355  mov     [rsi+18h], rax
0x1400d3359  mov     eax, [r14+28h]
0x1400d335d  mov     [rsi+10h], eax
0x1400d3360  mov     [rsi+28h], r15
0x1400d3364  mov     [rsi], rdx
0x1400d3367  mov     [rsi+48h], edx
0x1400d336a  mov     rcx, [r14+38h]
0x1400d336e  mov     [rsi+60h], rcx
0x1400d3372  mov     [rsi+68h], r13d
0x1400d3376  mov     eax, [r14+18h]
0x1400d337a  test    eax, eax
0x1400d337c  jz      short loc_1400D33A9
0x1400d337e  test    r15b, al
0x1400d3381  jnz     loc_1400D3D59
0x1400d3387  mov     eax, [r14+18h]
0x1400d338b  test    al, 2
0x1400d338d  jnz     loc_1400D383F
0x1400d3393  mov     eax, [r14+18h]
0x1400d3397  test    al, 4
0x1400d3399  jz      short loc_1400D33A9
0x1400d339b  or      edx, 8
0x1400d339e  mov     [rsi+48h], edx
0x1400d33a1  mov     rax, [r14+8]
0x1400d33a5  mov     [rsi+20h], rax
0x1400d33a9  mov     [rsi+50h], rdi
0x1400d33ad  test    rcx, rcx
0x1400d33b0  jz      short loc_1400D33C0
0x1400d33b2  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400d33b8  test    eax, eax
0x1400d33ba  jnz     loc_1400D3D66
0x1400d33c0  test    cs:TcpStartedModules, 100h
0x1400d33cb  jz      loc_1400D3AE8
0x1400d33d1  mov     eax, r13d
0x1400d33d4  mov     rbx, 0FFFFF78000000008h
0x1400d33de  imul    rcx, rax, 0F0h
0x1400d33e5  mov     rbx, [rbx]
0x1400d33e8  add     rcx, cs:TimerTable
0x1400d33ef  mov     [rbp+47h+var_68], rcx
0x1400d33f3  lea     rax, [rcx+10h]
0x1400d33f7  mov     [rbp+47h+var_60], rax
0x1400d33fb  cmp     rbx, [rcx+18h]
0x1400d33ff  jnz     loc_1400D3990
0x1400d3405  mov     rbx, [rax]
0x1400d3408  mov     rax, 624DD2F1A9FBE77h
0x1400d3412  mul     rbx
0x1400d3415  sub     rbx, rdx
0x1400d3418  shr     rbx, 1
0x1400d341b  add     rbx, rdx
0x1400d341e  shr     rbx, 9
0x1400d3422  cmp     qword ptr [rdi+1C8h], 0
0x1400d342a  jz      loc_1400D35B1
0x1400d3430  mov     rax, [rdi+1D0h]
0x1400d3437  movzx   r10d, [rbp+47h+var_70]
0x1400d343c  mov     [rax], rsi
0x1400d343f  mov     [rdi+1D0h], rsi
0x1400d3446  mov     rax, [rsi+40h]
0x1400d344a  add     [rdi+1C0h], rax
0x1400d3451  mov     r11, [rdi+1C0h]
0x1400d3458  cmp     cs:dword_1402201D4, 0
0x1400d345f  jz      short loc_1400D347B
0x1400d3461  cmp     cs:TcpipTraceFiltersExist, 0
0x1400d3468  jnz     loc_1400D3D91
0x1400d346e  test    byte ptr cs:WPP_MAIN_CB.Reserved+5, 40h
0x1400d3475  jnz     loc_1400D3B39
0x1400d347b  mov     rdx, [rdi+18h]
0x1400d347f  lea     rcx, ds:0[r13*2]
0x1400d3487  mov     rax, [rsi+40h]
0x1400d348b  add     rcx, r13
0x1400d348e  shl     rcx, 6
0x1400d3492  add     rcx, [rdx+80h]
0x1400d3499  add     [rcx+58h], rax
0x1400d349d  cmp     qword ptr [rdi+28h], 0
0x1400d34a2  jnz     loc_1400D39BA
0x1400d34a8  mov     [rsi+58h], ebx
0x1400d34ab  mov     rax, [rdi+1D0h]
0x1400d34b2  cmp     [rdi+1C8h], rax
0x1400d34b9  jnz     loc_1400D36F8
0x1400d34bf  mov     [rdi+1D8h], rsi
0x1400d34c6  lea     r8, [rdi+319h]
0x1400d34cd  mov     rax, [rsi+18h]
0x1400d34d1  mov     [rdi+1E0h], rax
0x1400d34d8  mov     rax, [rsi+8]
0x1400d34dc  mov     [rdi+1E8h], rax
0x1400d34e3  mov     eax, [rsi+10h]
0x1400d34e6  mov     [rdi+1F0h], eax
0x1400d34ec  movzx   edx, r15b
0x1400d34f0  mov     eax, [rsi+48h]
0x1400d34f3  test    al, 2
0x1400d34f5  jnz     loc_1400D3DA5
0x1400d34fb  test    byte ptr [rdi+308h], 8
0x1400d3502  jnz     loc_1400D3DDE
0x1400d3508  test    dl, dl
0x1400d350a  jz      loc_1400D3864
0x1400d3510  cmp     [rbp+47h+arg_28], 0
0x1400d3514  jnz     loc_1400D3864
0x1400d351a  mov     eax, [rdi+78h]
0x1400d351d  bt      eax, 14h
0x1400d3521  jb      loc_1400D385A
0x1400d3527  bt      eax, 15h
0x1400d352b  jb      loc_1400D3E11
0x1400d3531  lock xadd [rdi+8], r15
0x1400d3537  inc     r15
0x1400d353a  cmp     r15, 1
0x1400d353e  jle     loc_1400D3C48
0x1400d3544  movzx   edx, byte ptr [r12]
0x1400d3549  mov     r9d, ebx
0x1400d354c  mov     r8d, r13d
0x1400d354f  mov     rcx, rdi; SpinLock
0x1400d3552  call    TcpTcbSend
0x1400d3557  mov     rcx, rdi
0x1400d355a  call    TcpDereferenceTcb
0x1400d355f  mov     ebx, 103h
0x1400d3564  mov     rcx, [rbp+47h+var_58]
0x1400d3568  test    rcx, rcx
0x1400d356b  jz      short loc_1400D357B
0x1400d356d  mov     dl, 1
0x1400d356f  call    cs:__imp_NetioDereferenceNetBufferList
0x1400d3576  nop     dword ptr [rax+rax+00h]
0x1400d357b  mov     r15, [rsp+100h+var_30]
0x1400d3583  mov     eax, ebx
0x1400d3585  mov     r13, [rsp+100h+var_28]
0x1400d358d  mov     rsi, [rsp+100h+arg_10]
0x1400d3595  mov     rcx, [rbp+47h+var_40]
0x1400d3599  xor     rcx, rsp; StackCookie
0x1400d359c  call    __security_check_cookie
0x1400d35a1  add     rsp, 0E0h
0x1400d35a8  pop     r14
0x1400d35aa  pop     r12
0x1400d35ac  pop     rdi
0x1400d35ad  pop     rbx
0x1400d35ae  pop     rbp
0x1400d35af  retn
0x1400d35b1  mov     r9d, [rdi+1D0h]
0x1400d35b8  test    r9d, r9d
0x1400d35bb  jz      loc_1400D3655
0x1400d35c1  cmp     r9d, ebx
0x1400d35c4  jns     loc_1400D3655
0x1400d35ca  mov     r10d, [rdi+70h]
0x1400d35ce  movzx   r11d, byte ptr [rdi+2F0h]
0x1400d35d6  cmp     r10d, 4
0x1400d35da  jl      loc_1400D387D
0x1400d35e0  movzx   r8d, word ptr [rdi+30Ah]
0x1400d35e8  mov     eax, 10624DD3h
0x1400d35ed  mov     ecx, [rdi+2C8h]
0x1400d35f3  shr     ecx, 3
0x1400d35f6  add     ecx, [rdi+2CCh]
0x1400d35fc  mul     ecx
0x1400d35fe  mov     ecx, r11d
0x1400d3601  shr     edx, 6
0x1400d3604  cmp     r8d, edx
0x1400d3607  cmovbe  r8d, edx
0x1400d360b  shl     r8d, cl
0x1400d360e  lea     eax, [rdx+38h]
0x1400d3611  cmp     eax, r8d
0x1400d3614  cmova   r8d, eax
0x1400d3618  mov     ecx, [rdi+304h]
0x1400d361e  lea     eax, [rcx-1]
0x1400d3621  cmp     eax, 0FFFFFFFDh
0x1400d3624  jbe     loc_1400D3955
0x1400d362a  cmp     r10d, 4
0x1400d362e  jl      loc_1400D3AF7
0x1400d3634  mov     eax, 0EA60h
0x1400d3639  mov     ecx, ebx
0x1400d363b  cmp     r8d, eax
0x1400d363e  cmova   r8d, eax
0x1400d3642  sub     ecx, r9d
0x1400d3645  mov     [rbp+47h+var_6C], r8d
0x1400d3649  lea     eax, [r8+0Ah]
0x1400d364d  cmp     ecx, eax
0x1400d364f  ja      loc_1400D3890
0x1400d3655  cmp     dword ptr [rdi+70h], 2
0x1400d3659  movzx   r10d, [rbp+47h+var_70]
0x1400d365e  mov     [rdi+1C8h], rsi
0x1400d3665  mov     [rdi+1D0h], rsi
0x1400d366c  mov     r11, [rsi+40h]
0x1400d3670  mov     [rdi+1C0h], r11
0x1400d3677  jnz     loc_1400D3458
0x1400d367d  test    r10b, r10b
0x1400d3680  jnz     loc_1400D3458
0x1400d3686  mov     eax, 0FDFFh
0x1400d368b  and     [rdi+80h], ax
0x1400d3692  jmp     loc_1400D3458
0x1400d3697  mov     rax, [rdi+20h]
0x1400d369b  mov     rcx, [rax]
0x1400d369e  mov     rax, [rcx+8]
0x1400d36a2  cmp     byte ptr [rax+58h], 0
0x1400d36a6  jz      loc_1400D32BA
0x1400d36ac  mov     eax, gs:1A4h
0x1400d36b4  mov     ebx, 0C00000BEh
0x1400d36b9  lea     rdx, [rax+rax*4]
0x1400d36bd  mov     rax, cs:TcpipGlobalCounters
0x1400d36c4  shl     rdx, 6
0x1400d36c8  inc     qword ptr [rdx+rax+50h]
0x1400d36cd  movzx   eax, byte ptr cs:WPP_MAIN_CB+148h
0x1400d36d4  and     al, 80h
0x1400d36d6  mov     byte ptr [rbp+47h+var_68], al
0x1400d36d9  jnz     loc_1400D3D04
0x1400d36df  movzx   edx, byte ptr [r12]; NewIrql
0x1400d36e4  mov     rcx, rdi; SpinLock
0x1400d36e7  call    cs:__imp_KeReleaseSpinLock
0x1400d36ee  nop     dword ptr [rax+rax+00h]
0x1400d36f3  jmp     loc_1400D3564
0x1400d36f8  cmp     qword ptr [rdi+1D8h], 0
0x1400d3700  jnz     short loc_1400D3728
0x1400d3702  mov     [rdi+1D8h], rsi
0x1400d3709  mov     rax, [rsi+18h]
0x1400d370d  mov     [rdi+1E0h], rax
0x1400d3714  mov     rax, [rsi+8]
0x1400d3718  mov     [rdi+1E8h], rax
0x1400d371f  mov     eax, [rsi+10h]
0x1400d3722  mov     [rdi+1F0h], eax
0x1400d3728  lea     r8, [rdi+319h]
0x1400d372f  movzx   ecx, byte ptr [r8]
  ... truncated ...
```
