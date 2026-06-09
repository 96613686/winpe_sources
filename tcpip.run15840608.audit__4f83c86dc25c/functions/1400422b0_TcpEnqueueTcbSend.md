# TcpEnqueueTcbSend

- ea: `0x1400422b0`
- end: `0x140042f03`
- name: `TcpEnqueueTcbSend`
- size: `3155`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, char, char)`
- caller_count: `4`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140041da0`
- `0x140042270`
- `0x140057c48`
- `0x140133ce0`

## callees

- `0x14000de40`
- `0x14000f128`
- `0x140014974`
- `0x140018578`
- `0x14001ea80`
- `0x14001eb30`
- `0x140034500`
- `0x14003782c`
- `0x1400422b0`
- `0x1400438b0`
- `0x14005d040`
- `0x140071ac0`
- `0x1400fe57c`
- `0x140104d74`
- `0x140110de0`
- `0x140111204`
- `0x1401528fc`
- `0x1401529c8`
- `0x1401657a0`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140042af0`
- `ntoskrnl!KeBugCheckEx` at `0x140042af0`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c59ad`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c59ad`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400423f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400423f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400422f2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400422f2`
- `ntoskrnl!PsGetProcessId` at `0x1401c594f`
- `ntoskrnl!PsGetProcessId` at `0x1401c594f`
- `ntoskrnl!KeReadStateEvent` at `0x140042309`
- `ntoskrnl!KeReadStateEvent` at `0x140042309`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400427c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400428f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004294c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042a5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042b8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400427c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400428f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004294c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042a5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042b8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042345`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042345`
- `NETIO!NetioDereferenceNetBufferList` at `0x14004264f`
- `NETIO!NetioDereferenceNetBufferList` at `0x14004264f`
- `NETIO!WfpStreamInspectSend` at `0x1400428a4`
- `NETIO!WfpStreamInspectSend` at `0x1400428a4`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140042386`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140042ac6`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140042386`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140042ac6`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140042cfb`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140042cfb`

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
  if ( KeGetCurrentIrql() < 2u && !KeReadStateEvent(HighNonPagedPoolEvent) )
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
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_0b5b2f2c595439716ae49b445584f4d5_Traceguids, SpinLock);
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
    if ( dword_1402241D4
      && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
      && (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
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
        LOBYTE(v94) = (__int64)WPP_MAIN_CB.Dpc.DeferredContext & 0x80;
        if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) < 0
          && dword_1402241D4
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
      if ( dword_1402241D4 )
      {
        v97 = 0;
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
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
            if ( dword_1402241D4
              && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
              && SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
                if ( dword_1402241D4
                  && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
                  && SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
      if ( dword_1402241D4
        && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
        && (BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
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
0x1400422b0  push    rbp
0x1400422b2  push    rbx
0x1400422b3  push    rdi
0x1400422b4  push    r12
0x1400422b6  push    r14
0x1400422b8  lea     rbp, [rsp-27h]
0x1400422bd  sub     rsp, 0E0h
0x1400422c4  mov     rax, cs:__security_cookie
0x1400422cb  xor     rax, rsp
0x1400422ce  mov     [rbp+47h+var_40], rax
0x1400422d2  movzx   ebx, r8b
0x1400422d6  mov     [rbp+47h+var_60], r9
0x1400422da  mov     [rbp+47h+var_70], bl
0x1400422dd  mov     r12, r9
0x1400422e0  mov     r14, rdx
0x1400422e3  mov     [rbp+47h+var_6F], 0
0x1400422e7  mov     rdi, rcx
0x1400422ea  mov     [rbp+47h+var_58], 0
0x1400422f2  call    cs:__imp_KeGetCurrentIrql
0x1400422f9  nop     dword ptr [rax+rax+00h]
0x1400422fe  cmp     al, 2
0x140042300  jnb     short loc_14004231D
0x140042302  mov     rcx, cs:HighNonPagedPoolEvent; Event
0x140042309  call    cs:__imp_KeReadStateEvent
0x140042310  nop     dword ptr [rax+rax+00h]
0x140042315  test    eax, eax
0x140042317  jz      loc_140042D9B
0x14004231d  mov     [rsp+100h+arg_10], rsi
0x140042325  mov     [rsp+100h+var_28], r13
0x14004232d  mov     [rsp+100h+var_30], r15
0x140042335  test    r12, r12
0x140042338  jnz     short loc_140042379
0x14004233a  lea     r12, [rbp+47h+var_6F]
0x14004233e  mov     rcx, rdi; SpinLock
0x140042341  mov     [rbp+47h+var_60], r12
0x140042345  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004234c  nop     dword ptr [rax+rax+00h]
0x140042351  mov     [rbp+47h+var_6F], al
0x140042354  movzx   esi, al
0x140042357  test    bl, bl
0x140042359  jnz     loc_140042AFD
0x14004235f  mov     ecx, [rdi+70h]
0x140042362  lea     eax, [rcx-3]
0x140042365  test    eax, 0FFFFFFFAh
0x14004236a  jnz     loc_140042DCD
0x140042370  cmp     ecx, 8
0x140042373  jz      loc_140042DCD
0x140042379  test    byte ptr [rdi+324h], 8
0x140042380  jnz     loc_140042B81
0x140042386  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14004238d  nop     dword ptr [rax+rax+00h]
0x140042392  test    al, al
0x140042394  jnz     loc_140042777
0x14004239a  mov     r15d, 1
0x1400423a0  mov     eax, r15d
0x1400423a3  lock xadd [rdi+8], rax
0x1400423a9  inc     rax
0x1400423ac  cmp     rax, r15
0x1400423af  jle     loc_140042D1C
0x1400423b5  test    dword ptr [rdi+328h], 100h
0x1400423bf  jnz     loc_140042868
0x1400423c5  mov     r13d, gs:1A4h
0x1400423ce  mov     rcx, cs:TcpSendRequestPool
0x1400423d5  lea     ebx, [r13+1]
0x1400423d9  shl     rbx, 7
0x1400423dd  add     rbx, rcx
0x1400423e0  movzx   eax, byte ptr [rbx+0B0h]
0x1400423e7  test    al, al
0x1400423e9  jnz     short loc_1400423F4
0x1400423eb  lea     rdx, [rbx+40h]
0x1400423ef  call    PplpLazyInitializeLookasideList
0x1400423f4  lea     rcx, [rbx+40h]; Lookaside
0x1400423f8  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400423ff  nop     dword ptr [rax+rax+00h]
0x140042404  mov     rsi, rax
0x140042407  test    rax, rax
0x14004240a  jz      loc_140042A52
0x140042410  mov     rax, [r14]
0x140042413  xor     edx, edx
0x140042415  mov     [rsi+20h], rax
0x140042419  mov     rax, [r14+10h]
0x14004241d  mov     [rsi+30h], rax
0x140042421  mov     rax, [r14+20h]
0x140042425  mov     [rsi+8], rax
0x140042429  mov     rax, [r14+30h]
0x14004242d  mov     [rsi+40h], rax
0x140042431  mov     rax, [r14+30h]
0x140042435  mov     [rsi+18h], rax
0x140042439  mov     eax, [r14+28h]
0x14004243d  mov     [rsi+10h], eax
0x140042440  mov     [rsi+28h], r15
0x140042444  mov     [rsi], rdx
0x140042447  mov     [rsi+48h], edx
0x14004244a  mov     rcx, [r14+38h]
0x14004244e  mov     [rsi+60h], rcx
0x140042452  mov     [rsi+68h], r13d
0x140042456  mov     eax, [r14+18h]
0x14004245a  test    eax, eax
0x14004245c  jz      short loc_140042489
0x14004245e  test    r15b, al
0x140042461  jnz     loc_140042E39
0x140042467  mov     eax, [r14+18h]
0x14004246b  test    al, 2
0x14004246d  jnz     loc_14004291F
0x140042473  mov     eax, [r14+18h]
0x140042477  test    al, 4
0x140042479  jz      short loc_140042489
0x14004247b  or      edx, 8
0x14004247e  mov     [rsi+48h], edx
0x140042481  mov     rax, [r14+8]
0x140042485  mov     [rsi+20h], rax
0x140042489  mov     [rsi+50h], rdi
0x14004248d  test    rcx, rcx
0x140042490  jz      short loc_1400424A0
0x140042492  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140042498  test    eax, eax
0x14004249a  jnz     loc_140042E46
0x1400424a0  test    cs:TcpStartedModules, 100h
0x1400424ab  jz      loc_140042BC8
0x1400424b1  mov     eax, r13d
0x1400424b4  mov     rbx, 0FFFFF78000000008h
0x1400424be  imul    rcx, rax, 0F0h
0x1400424c5  mov     rbx, [rbx]
0x1400424c8  add     rcx, cs:TimerTable
0x1400424cf  mov     [rbp+47h+var_68], rcx
0x1400424d3  lea     rax, [rcx+10h]
0x1400424d7  mov     [rbp+47h+var_60], rax
0x1400424db  cmp     rbx, [rcx+18h]
0x1400424df  jnz     loc_140042A70
0x1400424e5  mov     rbx, [rax]
0x1400424e8  mov     rax, 624DD2F1A9FBE77h
0x1400424f2  mul     rbx
0x1400424f5  sub     rbx, rdx
0x1400424f8  shr     rbx, 1
0x1400424fb  add     rbx, rdx
0x1400424fe  shr     rbx, 9
0x140042502  cmp     qword ptr [rdi+1C8h], 0
0x14004250a  jz      loc_140042691
0x140042510  mov     rax, [rdi+1D0h]
0x140042517  movzx   r10d, [rbp+47h+var_70]
0x14004251c  mov     [rax], rsi
0x14004251f  mov     [rdi+1D0h], rsi
0x140042526  mov     rax, [rsi+40h]
0x14004252a  add     [rdi+1C0h], rax
0x140042531  mov     r11, [rdi+1C0h]
0x140042538  cmp     cs:dword_1402241D4, 0
0x14004253f  jz      short loc_14004255B
0x140042541  cmp     cs:TcpipTraceFiltersExist, 0
0x140042548  jnz     loc_140042E71
0x14004254e  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+5, 40h
0x140042555  jnz     loc_140042C19
0x14004255b  mov     rdx, [rdi+18h]
0x14004255f  lea     rcx, ds:0[r13*2]
0x140042567  mov     rax, [rsi+40h]
0x14004256b  add     rcx, r13
0x14004256e  shl     rcx, 6
0x140042572  add     rcx, [rdx+80h]
0x140042579  add     [rcx+58h], rax
0x14004257d  cmp     qword ptr [rdi+28h], 0
0x140042582  jnz     loc_140042A9A
0x140042588  mov     [rsi+58h], ebx
0x14004258b  mov     rax, [rdi+1D0h]
0x140042592  cmp     [rdi+1C8h], rax
0x140042599  jnz     loc_1400427D8
0x14004259f  mov     [rdi+1D8h], rsi
0x1400425a6  lea     r8, [rdi+319h]
0x1400425ad  mov     rax, [rsi+18h]
0x1400425b1  mov     [rdi+1E0h], rax
0x1400425b8  mov     rax, [rsi+8]
0x1400425bc  mov     [rdi+1E8h], rax
0x1400425c3  mov     eax, [rsi+10h]
0x1400425c6  mov     [rdi+1F0h], eax
0x1400425cc  movzx   edx, r15b
0x1400425d0  mov     eax, [rsi+48h]
0x1400425d3  test    al, 2
0x1400425d5  jnz     loc_140042E85
0x1400425db  test    byte ptr [rdi+308h], 8
0x1400425e2  jnz     loc_140042EBE
0x1400425e8  test    dl, dl
0x1400425ea  jz      loc_140042944
0x1400425f0  cmp     [rbp+47h+arg_28], 0
0x1400425f4  jnz     loc_140042944
0x1400425fa  mov     eax, [rdi+78h]
0x1400425fd  bt      eax, 14h
0x140042601  jb      loc_14004293A
0x140042607  bt      eax, 15h
0x14004260b  jb      loc_140042EF1
0x140042611  lock xadd [rdi+8], r15
0x140042617  inc     r15
0x14004261a  cmp     r15, 1
0x14004261e  jle     loc_140042D28
0x140042624  movzx   edx, byte ptr [r12]
0x140042629  mov     r9d, ebx
0x14004262c  mov     r8d, r13d
0x14004262f  mov     rcx, rdi; SpinLock
0x140042632  call    TcpTcbSend
0x140042637  mov     rcx, rdi
0x14004263a  call    TcpDereferenceTcb
0x14004263f  mov     ebx, 103h
0x140042644  mov     rcx, [rbp+47h+var_58]
0x140042648  test    rcx, rcx
0x14004264b  jz      short loc_14004265B
0x14004264d  mov     dl, 1
0x14004264f  call    cs:__imp_NetioDereferenceNetBufferList
0x140042656  nop     dword ptr [rax+rax+00h]
0x14004265b  mov     r15, [rsp+100h+var_30]
0x140042663  mov     eax, ebx
0x140042665  mov     r13, [rsp+100h+var_28]
0x14004266d  mov     rsi, [rsp+100h+arg_10]
0x140042675  mov     rcx, [rbp+47h+var_40]
0x140042679  xor     rcx, rsp; StackCookie
0x14004267c  call    __security_check_cookie
0x140042681  add     rsp, 0E0h
0x140042688  pop     r14
0x14004268a  pop     r12
0x14004268c  pop     rdi
0x14004268d  pop     rbx
0x14004268e  pop     rbp
0x14004268f  retn
0x140042691  mov     r9d, [rdi+1D0h]
0x140042698  test    r9d, r9d
0x14004269b  jz      loc_140042735
0x1400426a1  cmp     r9d, ebx
0x1400426a4  jns     loc_140042735
0x1400426aa  mov     r10d, [rdi+70h]
0x1400426ae  movzx   r11d, byte ptr [rdi+2F0h]
0x1400426b6  cmp     r10d, 4
0x1400426ba  jl      loc_14004295D
0x1400426c0  movzx   r8d, word ptr [rdi+30Ah]
0x1400426c8  mov     eax, 10624DD3h
0x1400426cd  mov     ecx, [rdi+2C8h]
0x1400426d3  shr     ecx, 3
0x1400426d6  add     ecx, [rdi+2CCh]
0x1400426dc  mul     ecx
0x1400426de  mov     ecx, r11d
0x1400426e1  shr     edx, 6
0x1400426e4  cmp     r8d, edx
0x1400426e7  cmovbe  r8d, edx
0x1400426eb  shl     r8d, cl
0x1400426ee  lea     eax, [rdx+38h]
0x1400426f1  cmp     eax, r8d
0x1400426f4  cmova   r8d, eax
0x1400426f8  mov     ecx, [rdi+304h]
0x1400426fe  lea     eax, [rcx-1]
0x140042701  cmp     eax, 0FFFFFFFDh
0x140042704  jbe     loc_140042A35
0x14004270a  cmp     r10d, 4
0x14004270e  jl      loc_140042BD7
0x140042714  mov     eax, 0EA60h
0x140042719  mov     ecx, ebx
0x14004271b  cmp     r8d, eax
0x14004271e  cmova   r8d, eax
0x140042722  sub     ecx, r9d
0x140042725  mov     [rbp+47h+var_6C], r8d
0x140042729  lea     eax, [r8+0Ah]
0x14004272d  cmp     ecx, eax
0x14004272f  ja      loc_140042970
0x140042735  cmp     dword ptr [rdi+70h], 2
0x140042739  movzx   r10d, [rbp+47h+var_70]
0x14004273e  mov     [rdi+1C8h], rsi
0x140042745  mov     [rdi+1D0h], rsi
0x14004274c  mov     r11, [rsi+40h]
0x140042750  mov     [rdi+1C0h], r11
0x140042757  jnz     loc_140042538
0x14004275d  test    r10b, r10b
0x140042760  jnz     loc_140042538
0x140042766  mov     eax, 0FDFFh
0x14004276b  and     [rdi+80h], ax
0x140042772  jmp     loc_140042538
0x140042777  mov     rax, [rdi+20h]
0x14004277b  mov     rcx, [rax]
0x14004277e  mov     rax, [rcx+8]
0x140042782  cmp     byte ptr [rax+58h], 0
0x140042786  jz      loc_14004239A
0x14004278c  mov     eax, gs:1A4h
0x140042794  mov     ebx, 0C00000BEh
0x140042799  lea     rdx, [rax+rax*4]
0x14004279d  mov     rax, cs:TcpipGlobalCounters
0x1400427a4  shl     rdx, 6
0x1400427a8  inc     qword ptr [rdx+rax+50h]
0x1400427ad  movzx   eax, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext
0x1400427b4  and     al, 80h
0x1400427b6  mov     byte ptr [rbp+47h+var_68], al
0x1400427b9  jnz     loc_140042DE4
0x1400427bf  movzx   edx, byte ptr [r12]; NewIrql
0x1400427c4  mov     rcx, rdi; SpinLock
0x1400427c7  call    cs:__imp_KeReleaseSpinLock
0x1400427ce  nop     dword ptr [rax+rax+00h]
0x1400427d3  jmp     loc_140042644
0x1400427d8  cmp     qword ptr [rdi+1D8h], 0
0x1400427e0  jnz     short loc_140042808
0x1400427e2  mov     [rdi+1D8h], rsi
0x1400427e9  mov     rax, [rsi+18h]
0x1400427ed  mov     [rdi+1E0h], rax
0x1400427f4  mov     rax, [rsi+8]
0x1400427f8  mov     [rdi+1E8h], rax
0x1400427ff  mov     eax, [rsi+10h]
0x140042802  mov     [rdi+1F0h], eax
0x140042808  lea     r8, [rdi+319h]
0x14004280f  movzx   ecx, byte ptr [r8]
  ... truncated ...
```
