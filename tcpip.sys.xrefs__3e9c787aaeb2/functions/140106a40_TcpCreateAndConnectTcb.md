# TcpCreateAndConnectTcb

- ea: `0x140106a40`
- end: `0x1401078e7`
- name: `TcpCreateAndConnectTcb`
- size: `3751`
- prototype: `__int64 __fastcall(KSPIN_LOCK, __int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140106a10`

## callees

- `0x140013140`
- `0x1400148e0`
- `0x140014a08`
- `0x140018578`
- `0x14001df40`
- `0x14001dfa8`
- `0x140021b50`
- `0x140023800`
- `0x140049760`
- `0x140056680`
- `0x1400579c0`
- `0x140071ac0`
- `0x1400d7980`
- `0x1400e0030`
- `0x140106a40`
- `0x14010ab78`
- `0x140113788`
- `0x140128dd8`
- `0x1401346f4`
- `0x140136e80`
- `0x1401615fc`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1401077e1`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1401077e1`
- `ntoskrnl!ObfReferenceObject` at `0x140107113`
- `ntoskrnl!ObfReferenceObject` at `0x1401073e0`
- `ntoskrnl!ObfReferenceObject` at `0x140107503`
- `ntoskrnl!ObfReferenceObject` at `0x1401076e8`
- `ntoskrnl!ObfReferenceObject` at `0x140107113`
- `ntoskrnl!ObfReferenceObject` at `0x1401073e0`
- `ntoskrnl!ObfReferenceObject` at `0x140107503`
- `ntoskrnl!ObfReferenceObject` at `0x1401076e8`
- `ntoskrnl!KeBugCheck` at `0x140107873`
- `ntoskrnl!KeBugCheck` at `0x140107873`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1401070ef`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14010728d`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1401070ef`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14010728d`
- `ntoskrnl!PsGetProcessStartKey` at `0x140106e96`
- `ntoskrnl!PsGetProcessStartKey` at `0x140106f69`
- `ntoskrnl!PsGetProcessStartKey` at `0x140106e96`
- `ntoskrnl!PsGetProcessStartKey` at `0x140106f69`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140106e45`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140106e45`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140106dec`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140106dec`
- `ntoskrnl!SeAccessCheck` at `0x140106e32`
- `ntoskrnl!SeAccessCheck` at `0x140106e32`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140106de0`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140106de0`
- `ntoskrnl!PsGetProcessId` at `0x140106e7c`
- `ntoskrnl!PsGetProcessId` at `0x140106f4f`
- `ntoskrnl!PsGetProcessId` at `0x140106e7c`
- `ntoskrnl!PsGetProcessId` at `0x140106f4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140107817`
- `ntoskrnl!KeReleaseSpinLock` at `0x140107817`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401077b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401077b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106ad9`
- `ntoskrnl!ExAllocatePool2` at `0x140107006`
- `ntoskrnl!ExAllocatePool2` at `0x140107006`
- `ntoskrnl!EtwWriteTransfer` at `0x140106c8b`
- `ntoskrnl!EtwWriteTransfer` at `0x140106c8b`
- `NETIO!NetioInsertWorkQueue` at `0x1401078c7`
- `NETIO!NetioInsertWorkQueue` at `0x1401078c7`
- `NETIO!KfdIsTfoIncompatibleFilterPresent` at `0x140106b99`
- `NETIO!KfdIsTfoIncompatibleFilterPresent` at `0x140106b99`
- `NETIO!NetioNrtAssociateContext` at `0x14010760c`
- `NETIO!NetioNrtAssociateContext` at `0x14010760c`
- `NETIO!RtlInsertElementGenericTableBasicAvl` at `0x140107804`
- `NETIO!RtlInsertElementGenericTableBasicAvl` at `0x140107804`

## string_xrefs

- `0x1401071fd`: `Initializing Template Connect TCB`

## pseudocode

```c
__int64 __fastcall TcpCreateAndConnectTcb(KSPIN_LOCK a1, __int64 a2, __int64 a3)
{
  __int16 *v4; // rdx
  __int16 v7; // cx
  int v8; // eax
  __int64 v9; // r13
  __int64 v10; // rdi
  void *v11; // rcx
  _WORD *v12; // rax
  char v13; // al
  char v15; // al
  __int64 v16; // rbx
  __int64 v17; // r8
  KSPIN_LOCK *v18; // rax
  KSPIN_LOCK *v19; // rsi
  __int64 v20; // r8
  const wchar_t *v21; // r9
  struct _KPROCESS *v22; // rsi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v24; // bl
  unsigned __int8 v25; // al
  char v26; // bl
  ADDRESS_FAMILY *v27; // r11
  UCHAR v28; // al
  char v29; // dl
  int v30; // r8d
  __int64 v31; // r10
  __int64 v32; // r11
  unsigned __int8 ProcessId; // al
  char v34; // bl
  ADDRESS_FAMILY *v35; // r11
  UCHAR v36; // al
  char v37; // dl
  int v38; // r8d
  __int64 v39; // r10
  __int64 v40; // r11
  __int64 Pool2; // rax
  int v42; // ecx
  KSPIN_LOCK v43; // rax
  unsigned __int8 v44; // dl
  int v45; // eax
  void *ClientProcess; // rax
  __int64 ProcessTag; // rax
  KSPIN_LOCK v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  KSPIN_LOCK v51; // rax
  void *v52; // rcx
  KSPIN_LOCK v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rax
  __int64 (__fastcall *v56)(__int64 *); // rdx
  int v57; // eax
  unsigned __int8 v58; // cl
  void *v59; // rcx
  KSPIN_LOCK v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 (__fastcall *v63)(__int64 *); // rdx
  int v64; // eax
  unsigned __int8 ProcessAuditId; // cl
  __int64 v66; // r8
  char v67; // al
  char v68; // al
  KSPIN_LOCK v69; // rcx
  void *v70; // rcx
  UCHAR v71; // al
  UCHAR v72; // al
  const void *v73; // rdx
  char *v74; // rdi
  KIRQL v75; // al
  void *v76; // rdx
  KIRQL v77; // r14
  KSPIN_LOCK v78; // r8
  __int64 v79; // rax
  __int64 v80; // r8
  __int64 v81; // r15
  _QWORD *v82; // rdx
  char UserDataCount; // [rsp+20h] [rbp-69h]
  char UserData; // [rsp+28h] [rbp-61h]
  PEVENT_DATA_DESCRIPTOR UserDataa; // [rsp+28h] [rbp-61h]
  int AccessStatus; // [rsp+60h] [rbp-29h] BYREF
  TABLE_SEARCH_RESULT SearchResult; // [rsp+64h] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-21h] BYREF
  PVOID NodeOrParent; // [rsp+70h] [rbp-19h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-11h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT v91; // [rsp+88h] [rbp-1h] BYREF

  v4 = *(__int16 **)(a2 + 88);
  NodeOrParent = 0;
  SearchResult = TableEmptyTree;
  *(_QWORD *)&EventDescriptor.Id = a3;
  if ( !v4[1] )
    return 3221225991LL;
  v7 = *v4;
  if ( *v4 != 2 && v7 != 23 )
    return 3221225991LL;
  v8 = *(_DWORD *)(a2 + 16);
  v9 = 0;
  if ( v8 < 0 )
  {
    v10 = *(_QWORD *)(a2 + 24);
    v11 = *(void **)(v10 + 296);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0x49546354u);
      *(_QWORD *)(v10 + 296) = 0;
    }
    if ( (*(_DWORD *)(v10 + 16) & 8) == 0
      || (v12 = *(_WORD **)(a2 + 88), *v12 != 23)
      || !v12[4] && !v12[5] && !v12[6] && !v12[7] && !v12[8] && v12[9] == 0xFFFF )
    {
      v13 = *(_BYTE *)(v10 + 205);
      if ( (v13 & 4) != 0 )
        return 3221225860LL;
      if ( a3 )
      {
        if ( (v13 & 0x10) == 0 )
          return 3221226029LL;
        if ( (unsigned __int8)KfdIsTfoIncompatibleFilterPresent() )
        {
          if ( !dword_140228520
            && !_InterlockedCompareExchange(&dword_140228520, 1, 0)
            && (unsigned int)dword_1402241F8 > 5
            && (qword_140224208 & 0x400000000000LL) != 0
            && (qword_140224210 & 0x400000000000LL) == qword_140224210 )
          {
            *(_DWORD *)&EventDescriptor.Level = 5;
            v91.ClientToken = off_140224200;
            EventDescriptor.Keyword = 0x400000000000LL;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            v91.ImpersonationLevel = *(unsigned __int16 *)off_140224200;
            v91.PrimaryToken = &byte_1401F6AD7;
            *((_DWORD *)&v91.ImpersonationLevel + 1) = 2;
            v91.ProcessAuditId = (PVOID)0x10000001FLL;
            AccessStatus = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&v91);
          }
          if ( dword_1402241D4 && SBYTE3(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            EventDescriptor.Keyword = 0;
            *(_QWORD *)&EventDescriptor.Id = v10;
            McTemplateK0p_EtwWriteTransfer(
              &MICROSOFT_TCPIP_PROVIDER_Context,
              TCP_FASTOPEN_INCOMPAT_CALLOUT,
              &EventDescriptor,
              v10);
          }
          v15 = *(_BYTE *)(v10 + 205);
          if ( (v15 & 0x10) != 0 )
            *(_BYTE *)(v10 + 205) = v15 & 0xEF;
          return 3221226029LL;
        }
      }
      v16 = *(_QWORD *)(v10 + 32);
      goto LABEL_44;
    }
    return 3221226044LL;
  }
  v10 = 0;
  if ( (v8 & 0x40000000) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 24);
    if ( (*(_DWORD *)(v9 + 32) & 8) == 0 || v7 != 23 || !v4[4] && !v4[5] && !v4[6] && !v4[7] && !v4[8] && v4[9] == -1 )
    {
      v16 = *(_QWORD *)(v9 + 48);
LABEL_44:
      v17 = *(_QWORD *)(v16 + 16);
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v17
                                        + (unsigned int)(*(_DWORD *)(v17 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v17 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v17 + 24), 2u);
LABEL_46:
      v18 = (KSPIN_LOCK *)PplAllocateFromLookasideList(TcpTcbPool);
      v19 = v18;
      if ( !v18 )
      {
        InetDereferenceAf(v16);
        if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        {
          v21 = L"TCB allocation (TCP)";
LABEL_64:
          McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v20, v21);
          return 3221225495LL;
        }
        return 3221225495LL;
      }
      TcpInitializeTcb(v18);
      *((_WORD *)v19 + 402) |= 0x80u;
      Pool2 = ExAllocatePool2(64, 368, 1380148052);
      v19[85] = Pool2;
      if ( !Pool2 )
      {
        PplFreeToLookasideList(TcpTcbPool, v19);
        InetDereferenceAf(v16);
        if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        {
          v21 = L"TCB Connect Request Pool (TCP)";
          goto LABEL_64;
        }
        return 3221225495LL;
      }
      TcpipTraceActivityIDStart(v19, 7);
      *((_DWORD *)v19 + 28) = 2;
      v19[3] = v16;
      v19[2] = a1;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= 1 )
        __fastfail(0xEu);
      v42 = *((_DWORD *)v19 + 202);
      v43 = v19[3];
      *((_DWORD *)v19 + 30) |= 1u;
      v44 = *(_BYTE *)(v43 + 162);
      v45 = v42 ^ ((unsigned __int16)v42 ^ (unsigned __int16)(v44 << 10)) & 0x400;
      *((_DWORD *)v19 + 202) = v45;
      if ( (v44 & 1) != 0 )
        *((_DWORD *)v19 + 202) = v45 | 0x1800;
      if ( v10 )
      {
        if ( !v9 )
        {
          v59 = *(void **)(v10 + 40);
          v19[106] = (KSPIN_LOCK)v59;
          ObfReferenceObject(v59);
          v60 = v19[3];
          v19[108] = *(_QWORD *)(v10 + 64);
          v19[112] = *(_QWORD *)(v10 + 72);
          if ( *(_QWORD *)(v10 + 32) == v60 )
          {
            v61 = *(_QWORD *)(v10 + 208);
          }
          else if ( v60 == *(_QWORD *)(v10 + 232) )
          {
            v61 = *(_QWORD *)(v10 + 224);
          }
          else
          {
            v61 = 0;
          }
          v91.ClientToken = *(PACCESS_TOKEN *)(v60 + 40);
          v62 = *(_QWORD *)(v60 + 48);
          *(_OWORD *)&v91.PrimaryToken = 0;
          *(_QWORD *)&v91.ImpersonationLevel = v61;
          v63 = *(__int64 (__fastcall **)(__int64 *))(v62 + 272);
          if ( v63 == IpNlpInheritSessionInfo )
            v64 = IpNlpInheritSessionInfo((__int64 *)&v91);
          else
            v64 = v63((__int64 *)&v91);
          if ( v64 < 0 )
          {
            v19[114] = 0;
            ProcessAuditId = 0;
          }
          else
          {
            ProcessAuditId = (unsigned __int8)v91.ProcessAuditId;
            v19[114] = (KSPIN_LOCK)v91.PrimaryToken;
          }
          *((_DWORD *)v19 + 202) ^= ((unsigned __int16)*((_DWORD *)v19 + 202)
                                   ^ (unsigned __int16)(ProcessAuditId << 15))
                                  & 0x8000;
          *(_OWORD *)(v19 + 95) = *(_OWORD *)(v10 + 168);
          *(_OWORD *)(v19 + 97) = *(_OWORD *)(v10 + 184);
          v19[99] = *(_QWORD *)(v10 + 200);
          v66 = *(_QWORD *)(v10 + 288);
          if ( v66 )
          {
            v67 = NetioNrtAssociateContext(v19, 0, v66, v19 + 139);
            if ( dword_1402241D4 )
            {
              if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
              {
                UserDataa = *(PEVENT_DATA_DESCRIPTOR *)(v10 + 288);
                *(_QWORD *)&v91.ImpersonationLevel = 0;
                v91.ClientToken = v19;
                McTemplateK0pqpq_EtwWriteTransfer(
                  (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                  v49,
                  (unsigned int)&v91,
                  (_DWORD)v19,
                  1,
                  (char)UserDataa,
                  v67);
              }
            }
          }
          if ( Microsoft_Windows_Networking_CorrelationEnabled )
            TcpipEtwTransferActivity(v19, v10, 6);
          goto LABEL_79;
        }
      }
      else if ( !v9 )
      {
        KeQuerySystemTimePrecise(v19 + 108);
        ClientProcess = *(void **)(a2 + 40);
        if ( !ClientProcess )
          ClientProcess = (void *)InetGetClientProcess();
        v19[106] = (KSPIN_LOCK)ClientProcess;
        ObfReferenceObject(ClientProcess);
        ProcessTag = InetGetProcessTag(*(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 48));
        v48 = v19[3];
        v19[112] = ProcessTag;
        TcpInitializeOptions(v48, v19 + 95);
        if ( (*(_DWORD *)(a2 + 16) & 0x20000000) != 0 )
          *((_BYTE *)v19 + 798) |= 0x40u;
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
        {
          v49 = *(_QWORD *)(a2 + 32);
          if ( v49 )
            TcpipEtwTransferActivity(v19, v49, 4);
        }
LABEL_79:
        *((_WORD *)v19 + 402) &= (*((_BYTE *)v19 + 798) >> 6 << 11) | 0xF7FF;
        if ( dword_1402241D4 )
        {
          if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
          {
            *(_QWORD *)&v91.ImpersonationLevel = 0;
            v91.ClientToken = v19;
            McTemplateK0p_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCP_SEND_TRACKER_ENABLED, &v91, v19);
          }
          if ( dword_1402241D4 )
          {
            if ( (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
              && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) != 0 )
            {
              UserDataCount = *((_BYTE *)v19 + 756);
              *(_QWORD *)&v91.ImpersonationLevel = 0;
              v91.ClientToken = v19;
              McTemplateK0pqz_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                v49,
                (unsigned int)&v91,
                (_DWORD)v19,
                UserDataCount,
                (__int64)L"Initializing Template Connect TCB");
            }
            if ( dword_1402241D4
              && (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
              && (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
            {
              UserData = *((_DWORD *)v19 + 35);
              *(_QWORD *)&v91.ImpersonationLevel = 0;
              v91.ClientToken = v19;
              McTemplateK0qqqp_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                v49,
                (unsigned int)&v91,
                0,
                2,
                UserData,
                (char)v19);
            }
          }
        }
        KeQuerySystemTimePrecise(v19 + 111);
        *(_QWORD *)v19[85] = *(_QWORD *)a2;
        *(_QWORD *)(v19[85] + 8) = *(_QWORD *)(a2 + 8);
        *(_QWORD *)(v19[85] + 56) = v19;
        *(_QWORD *)(v19[85] + 64) = v10;
        *(_QWORD *)(v19[85] + 72) = v9;
        *(_QWORD *)(v19[85] + 104) = *(_QWORD *)(a2 + 96);
        *(_QWORD *)(v19[85] + 120) = *(_QWORD *)(a2 + 72);
        *(_QWORD *)(v19[85] + 112) = *(_QWORD *)(a2 + 112);
        v50 = *(_QWORD *)&EventDescriptor.Id;
        if ( *(_QWORD *)&EventDescriptor.Id )
        {
          v51 = v19[85];
          *(_OWORD *)(v51 + 280) = *(_OWORD *)*(_QWORD *)&EventDescriptor.Id;
          *(_OWORD *)(v51 + 296) = *(_OWORD *)(v50 + 16);
          *(_OWORD *)(v51 + 312) = *(_OWORD *)(v50 + 32);
          *(_OWORD *)(v51 + 328) = *(_OWORD *)(v50 + 48);
          *(_OWORD *)(v51 + 344) = *(_OWORD *)(v50 + 64);
          *(_QWORD *)(v51 + 360) = *(_QWORD *)(v50 + 80);
          *((_WORD *)v19 + 64) |= 0x300u;
          if ( (*((_BYTE *)v19 + 797) & 0x10) != 0
            && dword_1402241D4
            && (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
            && SBYTE3(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
          {
            *(_QWORD *)&v91.ImpersonationLevel = 0;
            v91.ClientToken = v19;
            McTemplateK0p_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCP_FASTOPEN_REQUESTED, &v91, v19);
          }
        }
        else
        {
          v68 = *((_BYTE *)v19 + 797);
          if ( (v68 & 0x10) != 0 )
            *((_BYTE *)v19 + 797) = v68 & 0xEF;
        }
        if ( v10 || v9 )
        {
          v19[107] = 0;
          v69 = v19[85];
          if ( v9 )
            *(_QWORD *)(v69 + 88) = 0;
          else
            *(_QWORD *)(v69 + 88) = *(_QWORD *)(v10 + 48);
        }
        else
        {
          *(_QWORD *)(v19[85] + 88) = *(_QWORD *)(a2 + 48);
          v19[107] = *(_QWORD *)(a2 + 56);
        }
        v70 = *(void **)(v19[85] + 88);
        if ( v70 )
          ObfReferenceObject(v70);
        if ( !v9 && (!v10 || (*(_DWORD *)(v10 + 16) & 1) == 0) )
        {
          v71 = SOCKADDR_SIZE(*(_WORD *)(v19[3] + 24));
          memmove((void *)(v19[85] + 156), *(const void **)(a2 + 64), v71);
        }
        v72 = SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
        memmove((void *)(v19[85] + 184), v73, v72);
        *((_DWORD *)v19 + 168) = HIDWORD(KeGetPcr()[1].LockArray);
        *(_QWORD *)(v19[85] + 48) = 0;
        *(_DWORD *)(v19[85] + 48) = *((_DWORD *)v19 + 168);
        v74 = (char *)TcpCreateAndConnectTcbCancelQueue + 120 * *((unsigned int *)v19 + 168);
        *(_DWORD *)(v19[85] + 52) = _InterlockedExchangeAdd64((volatile signed __int64 *)v74 + 1, 1u) + 1;
        *(_QWORD *)(a2 + 104) = *(_QWORD *)(v19[85] + 48);
        v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v74);
        v76 = (void *)(v19[85] + 48);
        *((_BYTE *)v19 + 676) = 0;
        v77 = v75;
        RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)(v74 + 16), v76, &NodeOrParent, &SearchResult);
        RtlInsertElementGenericTableBasicAvl(v74 + 16, v19[85] + 16, NodeOrParent, (unsigned int)SearchResult);
        KeReleaseSpinLock((PKSPIN_LOCK)v74, v77);
        v78 = v19[85];
        v79 = *(_QWORD *)(v78 + 72);
        if ( v79 )
        {
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v79 + 24)) <= 1 )
            __fastfail(0xEu);
          *(_BYTE *)(v19[85] + 81) = 1;
        }
        else
        {
          v80 = *(_QWORD *)(v78 + 64);
          if ( v80 )
          {
            v81 = _InterlockedIncrement64((volatile signed __int64 *)(v80 + 8));
            if ( v81 <= 1 )
              KeBugCheck(0x1Cu);
            if ( EndpointReferenceHistory )
              RhAppendHistory(EndpointReferenceHistory, (unsigned int)v81);
            *(_BYTE *)(v19[85] + 80) = 1;
          }
        }
        v82 = v19 + 87;
        if ( v77 )
        {
          NetioInsertWorkQueue(TcpCreateAndConnectTcbWorkQueue, v82);
        }
        else
        {
          *v82 = 0;
          TcpCreateAndConnectTcbWorkQueueRoutine(v19 + 87);
        }
        return 259;
      }
      v52 = *(void **)(v9 + 56);
      v19[106] = (KSPIN_LOCK)v52;
      ObfReferenceObject(v52);
      v53 = v19[3];
      v19[108] = *(_QWORD *)(v9 + 72);
      v19[112] = *(_QWORD *)(v9 + 80);
      if ( *(_QWORD *)(v9 + 48) == v53 )
      {
        v54 = *(_QWORD *)(v9 + 280);
      }
      else if ( v53 == *(_QWORD *)(v9 + 304) )
      {
        v54 = *(_QWORD *)(v9 + 296);
      }
      else
      {
        v54 = 0;
      }
      v91.ClientToken = *(PACCESS_TOKEN *)(v53 + 40);
      v55 = *(_QWORD *)(v53 + 48);
      *(_OWORD *)&v91.PrimaryToken = 0;
      *(_QWORD *)&v91.ImpersonationLevel = v54;
      v56 = *(__int64 (__fastcall **)(__int64 *))(v55 + 272);
      if ( v56 == IpNlpInheritSessionInfo )
        v57 = IpNlpInheritSessionInfo((__int64 *)&v91);
      else
        v57 = v56((__int64 *)&v91);
      if ( v57 < 0 )
      {
        v19[114] = 0;
        v58 = 0;
      }
      else
      {
        v58 = (unsigned __int8)v91.ProcessAuditId;
        v19[114] = (KSPIN_LOCK)v91.PrimaryToken;
      }
      *((_DWORD *)v19 + 202) ^= ((unsigned __int16)*((_DWORD *)v19 + 202) ^ (unsigned __int16)(v58 << 15)) & 0x8000;
      *(_OWORD *)(v19 + 95) = *(_OWORD *)(v9 + 240);
      *(_OWORD *)(v19 + 97) = *(_OWORD *)(v9 + 256);
      v19[99] = *(_QWORD *)(v9 + 272);
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        TcpipEtwTransferActivity(v19, v9, 5);
      goto LABEL_79;
    }
    return 3221226044LL;
  }
  v22 = *(struct _KPROCESS **)(a2 + 40);
  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&v91, 0, sizeof(v91));
  if ( !v22 )
    v22 = (struct _KPROCESS *)InetGetClientProcess();
  SeCaptureSubjectContextEx(*(PETHREAD *)(a2 + 48), v22, &v91);
  GenericMapping = IoGetFileObjectGenericMapping();
  v24 = SeAccessCheck(
          TcpipEndpointCreationSdData,
          &v91,
          0,
          0x1200A9u,
          0,
          0,
          GenericMapping,
          1,
          &GrantedAccess,
          &AccessStatus);
  SeReleaseSubjectContext(&v91);
  if ( v24 )
  {
    v16 = InetFindAndReferenceAf(&TcpInetTransport, **(unsigned __int16 **)(a2 + 64));
    if ( v16 )
      goto LABEL_46;
    if ( dword_1402241D4 )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(v22);
        EventDescriptor.Keyword = 0;
        v34 = ProcessId;
        *(_QWORD *)&EventDescriptor.Id = 0;
        PsGetProcessStartKey(v22);
        SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
        v36 = SOCKADDR_SIZE(*v35);
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_FAILED_AF_V1,
          (unsigned int)&EventDescriptor,
          v36,
          v40,
          v38,
          v39,
          0,
          v34,
          0,
          0,
          v37);
      }
    }
    return 3221225488LL;
  }
  else
  {
    if ( dword_1402241D4 )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 8) != 0 )
      {
        v25 = (unsigned __int8)PsGetProcessId(v22);
        EventDescriptor.Keyword = 0;
        v26 = v25;
        *(_QWORD *)&EventDescriptor.Id = 0;
        PsGetProcessStartKey(v22);
        SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
        v28 = SOCKADDR_SIZE(*v27);
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CONNECT_TCB_FAILED_ACCESS_V1,
          (unsigned int)&EventDescriptor,
          v28,
          v32,
          v30,
          v31,
          0,
          v26,
          0,
          0,
          v29);
      }
    }
    return (unsigned int)AccessStatus;
  }
}

```

## disassembly

```asm
0x140106a40  push    rbp
0x140106a42  push    rbx
0x140106a43  push    r12
0x140106a45  push    r14
0x140106a47  push    r15
0x140106a49  lea     rbp, [rsp-37h]
0x140106a4e  sub     rsp, 0C0h
0x140106a55  mov     rax, cs:__security_cookie
0x140106a5c  xor     rax, rsp
0x140106a5f  mov     [rbp+57h+var_38], rax
0x140106a63  xor     r15d, r15d
0x140106a66  mov     r14, rdx
0x140106a69  mov     rdx, [rdx+58h]
0x140106a6d  mov     rbx, r8
0x140106a70  mov     [rbp+57h+NodeOrParent], r15
0x140106a74  mov     r12, rcx
0x140106a77  mov     [rbp+57h+SearchResult], r15d
0x140106a7b  mov     qword ptr [rbp+57h+EventDescriptor.Id], rbx
0x140106a7f  cmp     [rdx+2], r15w
0x140106a84  jz      loc_1401078DD
0x140106a8a  movzx   ecx, word ptr [rdx]
0x140106a8d  cmp     cx, 2
0x140106a91  jz      short loc_140106A9D
0x140106a93  cmp     cx, 17h
0x140106a97  jnz     loc_1401078DD
0x140106a9d  mov     eax, [r14+10h]
0x140106aa1  mov     [rsp+0E0h+arg_10], rsi
0x140106aa9  mov     [rsp+0E0h+var_28], rdi
0x140106ab1  mov     [rsp+0E0h+var_30], r13
0x140106ab9  mov     r13, r15
0x140106abc  test    eax, eax
0x140106abe  jns     loc_140106CF1
0x140106ac4  mov     rdi, [r14+18h]
0x140106ac8  mov     rcx, [rdi+128h]; P
0x140106acf  test    rcx, rcx
0x140106ad2  jz      short loc_140106AEC
0x140106ad4  mov     edx, 49546354h; Tag
0x140106ad9  call    cs:__imp_ExFreePoolWithTag
0x140106ae0  nop     dword ptr [rax+rax+00h]
0x140106ae5  mov     [rdi+128h], r15
0x140106aec  mov     eax, [rdi+10h]
0x140106aef  test    al, 8
0x140106af1  jz      short loc_140106B43
0x140106af3  mov     rax, [r14+58h]
0x140106af7  cmp     word ptr [rax], 17h
0x140106afb  jnz     short loc_140106B43
0x140106afd  cmp     [rax+8], r13w
0x140106b02  jnz     loc_140106D39
0x140106b08  cmp     [rax+0Ah], r13w
0x140106b0d  jnz     loc_140106D39
0x140106b13  cmp     [rax+0Ch], r13w
0x140106b18  jnz     loc_140106D39
0x140106b1e  cmp     [rax+0Eh], r13w
0x140106b23  jnz     loc_140106D39
0x140106b29  cmp     [rax+10h], r13w
0x140106b2e  jnz     loc_140106D39
0x140106b34  mov     ecx, 0FFFFh
0x140106b39  cmp     [rax+12h], cx
0x140106b3d  jnz     loc_140106D39
0x140106b43  movzx   eax, byte ptr [rdi+0CDh]
0x140106b4a  test    al, 4
0x140106b4c  jz      short loc_140106B88
0x140106b4e  mov     eax, 0C0000184h
0x140106b53  mov     rdi, [rsp+0E0h+var_28]
0x140106b5b  mov     rsi, [rsp+0E0h+arg_10]
0x140106b63  mov     r13, [rsp+0E0h+var_30]
0x140106b6b  mov     rcx, [rbp+57h+var_38]
0x140106b6f  xor     rcx, rsp; StackCookie
0x140106b72  call    __security_check_cookie
0x140106b77  add     rsp, 0C0h
0x140106b7e  pop     r15
0x140106b80  pop     r14
0x140106b82  pop     r12
0x140106b84  pop     rbx
0x140106b85  pop     rbp
0x140106b86  retn
0x140106b88  test    rbx, rbx
0x140106b8b  jz      loc_140106CEB
0x140106b91  test    al, 10h
0x140106b93  jz      loc_140106CE1
0x140106b99  call    cs:__imp_KfdIsTfoIncompatibleFilterPresent
0x140106ba0  nop     dword ptr [rax+rax+00h]
0x140106ba5  test    al, al
0x140106ba7  jz      loc_140106CEB
0x140106bad  cmp     cs:dword_140228520, r13d
0x140106bb4  jnz     loc_140106C9A
0x140106bba  xor     eax, eax
0x140106bbc  mov     r15d, 1
0x140106bc2  lock cmpxchg cs:dword_140228520, r15d
0x140106bcb  jnz     loc_140106C97
0x140106bd1  mov     eax, cs:dword_1402241F8
0x140106bd7  cmp     eax, 5
0x140106bda  jbe     loc_140106C97
0x140106be0  mov     rcx, cs:qword_140224210
0x140106be7  mov     rdx, 400000000000h
0x140106bf1  mov     rax, cs:qword_140224208
0x140106bf8  test    rdx, rax
0x140106bfb  jz      loc_140106C97
0x140106c01  mov     rax, rcx
0x140106c04  and     rax, rdx
0x140106c07  cmp     rax, rcx
0x140106c0a  jnz     loc_140106C97
0x140106c10  movzx   eax, cs:word_1401F6ACD
0x140106c17  lea     rcx, _TraceLoggingMetadata
0x140106c1e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140106c21  xor     r9d, r9d; RelatedActivityId
0x140106c24  mov     rax, cs:off_140224200
0x140106c2b  xor     r8d, r8d; ActivityId
0x140106c2e  mov     [rbp+57h+var_58.Ptr], rax
0x140106c32  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x140106c36  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140106c3a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140106c41  movzx   eax, word ptr [rax]
0x140106c44  mov     [rbp+57h+var_58.Size], eax
0x140106c47  lea     rax, byte_1401F6AD7
0x140106c4e  mov     qword ptr [rbp+57h+var_48], rax
0x140106c52  lea     rax, _TraceLoggingMetadataEnd
0x140106c59  sub     eax, ecx
0x140106c5b  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x140106c62  mov     dword ptr [rbp+57h+var_48+8], 1Fh
0x140106c69  mov     dword ptr [rbp+57h+var_48+0Ch], r15d
0x140106c6d  mov     [rbp+57h+var_80], eax
0x140106c70  mov     eax, [rbp+57h+var_80]
0x140106c73  mov     rcx, cs:RegHandle; RegHandle
0x140106c7a  lea     rax, [rbp+57h+var_58]
0x140106c7e  mov     [rsp+0E0h+UserData], rax; UserData
0x140106c83  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x140106c8b  call    cs:__imp_EtwWriteTransfer
0x140106c92  nop     dword ptr [rax+rax+00h]
0x140106c97  xor     r15d, r15d
0x140106c9a  cmp     cs:dword_1402241D4, r13d
0x140106ca1  jz      short loc_140106CCE
0x140106ca3  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+3, r13b
0x140106caa  jge     short loc_140106CCE
0x140106cac  mov     r9, rdi
0x140106caf  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x140106cb3  lea     r8, [rbp+57h+EventDescriptor]
0x140106cb7  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdi
0x140106cbb  lea     rdx, TCP_FASTOPEN_INCOMPAT_CALLOUT
0x140106cc2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140106cc9  call    McTemplateK0p_EtwWriteTransfer
0x140106cce  movzx   eax, byte ptr [rdi+0CDh]
0x140106cd5  test    al, 10h
0x140106cd7  jz      short loc_140106CE1
0x140106cd9  and     al, 0EFh
0x140106cdb  mov     [rdi+0CDh], al
0x140106ce1  mov     eax, 0C000022Dh
0x140106ce6  jmp     loc_140106B53
0x140106ceb  mov     rbx, [rdi+20h]
0x140106cef  jmp     short loc_140106D47
0x140106cf1  mov     rdi, r15
0x140106cf4  bt      eax, 1Eh
0x140106cf8  jnb     loc_140106DB1
0x140106cfe  mov     r13, [r14+18h]
0x140106d02  mov     eax, [r13+20h]
0x140106d06  test    al, 8
0x140106d08  jz      short loc_140106D43
0x140106d0a  cmp     cx, 17h
0x140106d0e  jnz     short loc_140106D43
0x140106d10  cmp     [rdx+8], di
0x140106d14  jnz     short loc_140106D39
0x140106d16  cmp     [rdx+0Ah], di
0x140106d1a  jnz     short loc_140106D39
0x140106d1c  cmp     [rdx+0Ch], di
0x140106d20  jnz     short loc_140106D39
0x140106d22  cmp     [rdx+0Eh], di
0x140106d26  jnz     short loc_140106D39
0x140106d28  cmp     [rdx+10h], di
0x140106d2c  jnz     short loc_140106D39
0x140106d2e  mov     ecx, 0FFFFh
0x140106d33  cmp     [rdx+12h], cx
0x140106d37  jz      short loc_140106D43
0x140106d39  mov     eax, 0C000023Ch
0x140106d3e  jmp     loc_140106B53
0x140106d43  mov     rbx, [r13+30h]
0x140106d47  mov     eax, gs:1A4h
0x140106d4f  xor     edx, edx
0x140106d51  mov     r8, [rbx+10h]
0x140106d55  mov     ecx, 2
0x140106d5a  div     dword ptr [r8+14h]
0x140106d5e  imul    edx, [r8+10h]
0x140106d63  mov     eax, edx
0x140106d65  add     rax, [r8]
0x140106d68  lock xadd [rax], rcx
0x140106d6d  test    cl, 1
0x140106d70  jz      short loc_140106D78
0x140106d72  lock add qword ptr [r8+18h], 2
0x140106d78  mov     rcx, cs:TcpTcbPool
0x140106d7f  call    PplAllocateFromLookasideList
0x140106d84  mov     rsi, rax
0x140106d87  test    rax, rax
0x140106d8a  jnz     loc_140106FE2
0x140106d90  mov     rcx, rbx
0x140106d93  call    _InetDereferenceAf
0x140106d98  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r15b
0x140106d9f  jge     loc_140107058
0x140106da5  lea     r9, aTcbAllocationT; "TCB allocation (TCP)"
0x140106dac  jmp     loc_140107045
0x140106db1  mov     rsi, [r14+28h]
0x140106db5  xorps   xmm0, xmm0
0x140106db8  mov     [rbp+57h+var_80], r15d
0x140106dbc  mov     [rbp+57h+var_78], r15d
0x140106dc0  movups  xmmword ptr [rbp+57h+var_58.Ptr], xmm0
0x140106dc4  movups  [rbp+57h+var_48], xmm0
0x140106dc8  test    rsi, rsi
0x140106dcb  jnz     short loc_140106DD5
0x140106dcd  call    InetGetClientProcess
0x140106dd2  mov     rsi, rax
0x140106dd5  mov     rcx, [r14+30h]; Thread
0x140106dd9  lea     r8, [rbp+57h+var_58]; SubjectContext
0x140106ddd  mov     rdx, rsi; Process
0x140106de0  call    cs:__imp_SeCaptureSubjectContextEx
0x140106de7  nop     dword ptr [rax+rax+00h]
0x140106dec  call    cs:__imp_IoGetFileObjectGenericMapping
0x140106df3  nop     dword ptr [rax+rax+00h]
0x140106df8  lea     rcx, [rbp+57h+var_80]
0x140106dfc  mov     r9d, 1200A9h; DesiredAccess
0x140106e02  mov     [rsp+0E0h+AccessStatus], rcx; AccessStatus
0x140106e07  lea     rdx, [rbp+57h+var_58]; SubjectSecurityContext
0x140106e0b  lea     rcx, [rbp+57h+var_78]
0x140106e0f  xor     r8d, r8d; SubjectContextLocked
0x140106e12  mov     [rsp+0E0h+GrantedAccess], rcx; GrantedAccess
0x140106e17  lea     rcx, TcpipEndpointCreationSdData; SecurityDescriptor
0x140106e1e  mov     [rsp+0E0h+AccessMode], 1; AccessMode
0x140106e23  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x140106e28  mov     [rsp+0E0h+UserData], r15; Privileges
0x140106e2d  mov     [rsp+0E0h+UserDataCount], r15d; PreviouslyGrantedAccess
0x140106e32  call    cs:__imp_SeAccessCheck
0x140106e39  nop     dword ptr [rax+rax+00h]
0x140106e3e  lea     rcx, [rbp+57h+var_58]; SubjectContext
0x140106e42  movzx   ebx, al
0x140106e45  call    cs:__imp_SeReleaseSubjectContext
0x140106e4c  nop     dword ptr [rax+rax+00h]
0x140106e51  test    bl, bl
0x140106e53  jnz     loc_140106F0D
0x140106e59  cmp     cs:dword_1402241D4, edi
0x140106e5f  jz      loc_140106F05
0x140106e65  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, 8
0x140106e6c  xorps   xmm0, xmm0
0x140106e6f  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x140106e73  jz      loc_140106F05
0x140106e79  mov     rcx, rsi; Process
0x140106e7c  call    cs:__imp_PsGetProcessId
0x140106e83  nop     dword ptr [rax+rax+00h]
0x140106e88  mov     rcx, rsi
0x140106e8b  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x140106e8f  mov     rbx, rax
0x140106e92  mov     qword ptr [rbp+57h+EventDescriptor.Id], r15
0x140106e96  call    cs:__imp_PsGetProcessStartKey
0x140106e9d  nop     dword ptr [rax+rax+00h]
0x140106ea2  mov     r10, [r14+58h]
0x140106ea6  mov     rdx, rax
0x140106ea9  mov     r11, [r14+40h]
0x140106ead  movzx   ecx, word ptr [r10]; af
0x140106eb1  call    SOCKADDR_SIZE
0x140106eb6  movzx   ecx, word ptr [r11]; af
0x140106eba  movzx   r8d, al
0x140106ebe  call    SOCKADDR_SIZE
0x140106ec3  mov     [rsp+0E0h+var_88], rdx
0x140106ec8  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140106ecf  mov     [rsp+0E0h+var_90], r15
0x140106ed4  lea     rdx, TCP_CONNECT_TCB_FAILED_ACCESS_V1
0x140106edb  mov     dword ptr [rsp+0E0h+AccessStatus], r15d
0x140106ee0  mov     dword ptr [rsp+0E0h+GrantedAccess], ebx
0x140106ee4  mov     dword ptr [rsp+0E0h+AccessMode], r15d
0x140106ee9  mov     [rsp+0E0h+GenericMapping], r10
0x140106eee  mov     dword ptr [rsp+0E0h+UserData], r8d
0x140106ef3  lea     r8, [rbp+57h+EventDescriptor]
0x140106ef7  movzx   r9d, al
0x140106efb  mov     qword ptr [rsp+0E0h+UserDataCount], r11
0x140106f00  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x140106f05  mov     eax, [rbp+57h+var_80]
0x140106f08  jmp     loc_140106B53
0x140106f0d  mov     rdx, [r14+40h]
0x140106f11  lea     rcx, TcpInetTransport
0x140106f18  movzx   edx, word ptr [rdx]
0x140106f1b  call    InetFindAndReferenceAf
0x140106f20  mov     rbx, rax
0x140106f23  test    rax, rax
0x140106f26  jnz     loc_140106D78
0x140106f2c  cmp     cs:dword_1402241D4, edi
0x140106f32  jz      loc_140106FD8
0x140106f38  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, 8
0x140106f3f  xorps   xmm0, xmm0
0x140106f42  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x140106f46  jz      loc_140106FD8
0x140106f4c  mov     rcx, rsi; Process
0x140106f4f  call    cs:__imp_PsGetProcessId
0x140106f56  nop     dword ptr [rax+rax+00h]
0x140106f5b  mov     rcx, rsi
0x140106f5e  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x140106f62  mov     rbx, rax
0x140106f65  mov     qword ptr [rbp+57h+EventDescriptor.Id], r15
0x140106f69  call    cs:__imp_PsGetProcessStartKey
0x140106f70  nop     dword ptr [rax+rax+00h]
0x140106f75  mov     r10, [r14+58h]
0x140106f79  mov     rdx, rax
0x140106f7c  mov     r11, [r14+40h]
0x140106f80  movzx   ecx, word ptr [r10]; af
0x140106f84  call    SOCKADDR_SIZE
  ... truncated ...
```
