# TcpCreateAndConnectTcb

- ea: `0x1400faf00`
- end: `0x1400fbda7`
- name: `TcpCreateAndConnectTcb`
- size: `3751`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400faed0`

## callees

- `0x1400158e0`
- `0x140017060`
- `0x1400175b0`
- `0x1400245b0`
- `0x14002f200`
- `0x140039860`
- `0x1400525d0`
- `0x140053d70`
- `0x140053e98`
- `0x1400aebd8`
- `0x1400b5b10`
- `0x1400b86c0`
- `0x1400d2720`
- `0x1400faf00`
- `0x1400ff4c0`
- `0x140109468`
- `0x140115368`
- `0x14011e5a8`
- `0x14012cfc4`
- `0x140130150`
- `0x14015f83c`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf640`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1400fbca1`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1400fbca1`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb5d3`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb8a0`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb9c3`
- `ntoskrnl!ObfReferenceObject` at `0x1400fbba8`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb5d3`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb8a0`
- `ntoskrnl!ObfReferenceObject` at `0x1400fb9c3`
- `ntoskrnl!ObfReferenceObject` at `0x1400fbba8`
- `ntoskrnl!KeBugCheck` at `0x1400fbd33`
- `ntoskrnl!KeBugCheck` at `0x1400fbd33`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb5af`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb74d`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb5af`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400fb74d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb356`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb429`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb356`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400fb429`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400fb305`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400fb305`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fb2ac`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fb2ac`
- `ntoskrnl!SeAccessCheck` at `0x1400fb2f2`
- `ntoskrnl!SeAccessCheck` at `0x1400fb2f2`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400fb2a0`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400fb2a0`
- `ntoskrnl!PsGetProcessId` at `0x1400fb33c`
- `ntoskrnl!PsGetProcessId` at `0x1400fb40f`
- `ntoskrnl!PsGetProcessId` at `0x1400fb33c`
- `ntoskrnl!PsGetProcessId` at `0x1400fb40f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400fbcd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400fbcd7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400fbc73`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400fbc73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400faf99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400faf99`
- `ntoskrnl!ExAllocatePool2` at `0x1400fb4c6`
- `ntoskrnl!ExAllocatePool2` at `0x1400fb4c6`
- `ntoskrnl!EtwWriteTransfer` at `0x1400fb14b`
- `ntoskrnl!EtwWriteTransfer` at `0x1400fb14b`
- `NETIO!NetioInsertWorkQueue` at `0x1400fbd87`
- `NETIO!NetioInsertWorkQueue` at `0x1400fbd87`
- `NETIO!KfdIsTfoIncompatibleFilterPresent` at `0x1400fb059`
- `NETIO!KfdIsTfoIncompatibleFilterPresent` at `0x1400fb059`
- `NETIO!NetioNrtAssociateContext` at `0x1400fbacc`
- `NETIO!NetioNrtAssociateContext` at `0x1400fbacc`
- `NETIO!RtlInsertElementGenericTableBasicAvl` at `0x1400fbcc4`
- `NETIO!RtlInsertElementGenericTableBasicAvl` at `0x1400fbcc4`

## string_xrefs

- `0x1400fb6bd`: `Initializing Template Connect TCB`

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
  __int64 (__fastcall *v56)(struct _SECURITY_SUBJECT_CONTEXT *); // rdx
  int v57; // eax
  unsigned __int8 v58; // cl
  void *v59; // rcx
  KSPIN_LOCK v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 (__fastcall *v63)(struct _SECURITY_SUBJECT_CONTEXT *); // rdx
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
          if ( !dword_1402244E0
            && !_InterlockedCompareExchange(&dword_1402244E0, 1, 0)
            && (unsigned int)dword_1402201F8 > 5
            && (qword_140220208 & 0x400000000000LL) != 0
            && (qword_140220210 & 0x400000000000LL) == qword_140220210 )
          {
            *(_DWORD *)&EventDescriptor.Level = 5;
            v91.ClientToken = off_140220200;
            EventDescriptor.Keyword = 0x400000000000LL;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            v91.ImpersonationLevel = *(unsigned __int16 *)off_140220200;
            v91.PrimaryToken = &byte_1401F2F57;
            *((_DWORD *)&v91.ImpersonationLevel + 1) = 2;
            v91.ProcessAuditId = (PVOID)0x10000001FLL;
            AccessStatus = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&v91);
          }
          if ( dword_1402201D4 && *((char *)&WPP_MAIN_CB.Reserved + 11) < 0 )
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
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
        PplFreeToLookasideList(TcpTcbPool);
        InetDereferenceAf(v16);
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
          v63 = *(__int64 (__fastcall **)(struct _SECURITY_SUBJECT_CONTEXT *))(v62 + 272);
          if ( (char *)v63 == (char *)IpNlpInheritSessionInfo )
            v64 = IpNlpInheritSessionInfo(&v91);
          else
            v64 = v63(&v91);
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
            if ( dword_1402201D4 )
            {
              if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 0x20) != 0 )
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
        if ( dword_1402201D4 )
        {
          if ( SBYTE2(WPP_MAIN_CB.Reserved) < 0 )
          {
            *(_QWORD *)&v91.ImpersonationLevel = 0;
            v91.ClientToken = v19;
            McTemplateK0p_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCP_SEND_TRACKER_ENABLED, &v91, v19);
          }
          if ( dword_1402201D4 )
          {
            if ( (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0) && (HIBYTE(WPP_MAIN_CB.Reserved) & 1) != 0 )
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
            if ( dword_1402201D4
              && (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
              && (BYTE1(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
            && dword_1402201D4
            && (!TcpipTraceFiltersExist || *((char *)v19 + 804) < 0)
            && *((char *)&WPP_MAIN_CB.Reserved + 11) < 0 )
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
              RhAppendHistory(EndpointReferenceHistory, (unsigned int)v81, v80);
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
      v56 = *(__int64 (__fastcall **)(struct _SECURITY_SUBJECT_CONTEXT *))(v55 + 272);
      if ( (char *)v56 == (char *)IpNlpInheritSessionInfo )
        v57 = IpNlpInheritSessionInfo(&v91);
      else
        v57 = v56(&v91);
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
    if ( dword_1402201D4 )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
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
    if ( dword_1402201D4 )
    {
      EventDescriptor = 0;
      if ( (BYTE1(WPP_MAIN_CB.Reserved) & 8) != 0 )
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
0x1400faf00  push    rbp
0x1400faf02  push    rbx
0x1400faf03  push    r12
0x1400faf05  push    r14
0x1400faf07  push    r15
0x1400faf09  lea     rbp, [rsp-37h]
0x1400faf0e  sub     rsp, 0C0h
0x1400faf15  mov     rax, cs:__security_cookie
0x1400faf1c  xor     rax, rsp
0x1400faf1f  mov     [rbp+57h+var_38], rax
0x1400faf23  xor     r15d, r15d
0x1400faf26  mov     r14, rdx
0x1400faf29  mov     rdx, [rdx+58h]
0x1400faf2d  mov     rbx, r8
0x1400faf30  mov     [rbp+57h+NodeOrParent], r15
0x1400faf34  mov     r12, rcx
0x1400faf37  mov     [rbp+57h+SearchResult], r15d
0x1400faf3b  mov     qword ptr [rbp+57h+EventDescriptor.Id], rbx
0x1400faf3f  cmp     [rdx+2], r15w
0x1400faf44  jz      loc_1400FBD9D
0x1400faf4a  movzx   ecx, word ptr [rdx]
0x1400faf4d  cmp     cx, 2
0x1400faf51  jz      short loc_1400FAF5D
0x1400faf53  cmp     cx, 17h
0x1400faf57  jnz     loc_1400FBD9D
0x1400faf5d  mov     eax, [r14+10h]
0x1400faf61  mov     [rsp+0E0h+arg_10], rsi
0x1400faf69  mov     [rsp+0E0h+var_28], rdi
0x1400faf71  mov     [rsp+0E0h+var_30], r13
0x1400faf79  mov     r13, r15
0x1400faf7c  test    eax, eax
0x1400faf7e  jns     loc_1400FB1B1
0x1400faf84  mov     rdi, [r14+18h]
0x1400faf88  mov     rcx, [rdi+128h]; P
0x1400faf8f  test    rcx, rcx
0x1400faf92  jz      short loc_1400FAFAC
0x1400faf94  mov     edx, 49546354h; Tag
0x1400faf99  call    cs:__imp_ExFreePoolWithTag
0x1400fafa0  nop     dword ptr [rax+rax+00h]
0x1400fafa5  mov     [rdi+128h], r15
0x1400fafac  mov     eax, [rdi+10h]
0x1400fafaf  test    al, 8
0x1400fafb1  jz      short loc_1400FB003
0x1400fafb3  mov     rax, [r14+58h]
0x1400fafb7  cmp     word ptr [rax], 17h
0x1400fafbb  jnz     short loc_1400FB003
0x1400fafbd  cmp     [rax+8], r13w
0x1400fafc2  jnz     loc_1400FB1F9
0x1400fafc8  cmp     [rax+0Ah], r13w
0x1400fafcd  jnz     loc_1400FB1F9
0x1400fafd3  cmp     [rax+0Ch], r13w
0x1400fafd8  jnz     loc_1400FB1F9
0x1400fafde  cmp     [rax+0Eh], r13w
0x1400fafe3  jnz     loc_1400FB1F9
0x1400fafe9  cmp     [rax+10h], r13w
0x1400fafee  jnz     loc_1400FB1F9
0x1400faff4  mov     ecx, 0FFFFh
0x1400faff9  cmp     [rax+12h], cx
0x1400faffd  jnz     loc_1400FB1F9
0x1400fb003  movzx   eax, byte ptr [rdi+0CDh]
0x1400fb00a  test    al, 4
0x1400fb00c  jz      short loc_1400FB048
0x1400fb00e  mov     eax, 0C0000184h
0x1400fb013  mov     rdi, [rsp+0E0h+var_28]
0x1400fb01b  mov     rsi, [rsp+0E0h+arg_10]
0x1400fb023  mov     r13, [rsp+0E0h+var_30]
0x1400fb02b  mov     rcx, [rbp+57h+var_38]
0x1400fb02f  xor     rcx, rsp; StackCookie
0x1400fb032  call    __security_check_cookie
0x1400fb037  add     rsp, 0C0h
0x1400fb03e  pop     r15
0x1400fb040  pop     r14
0x1400fb042  pop     r12
0x1400fb044  pop     rbx
0x1400fb045  pop     rbp
0x1400fb046  retn
0x1400fb048  test    rbx, rbx
0x1400fb04b  jz      loc_1400FB1AB
0x1400fb051  test    al, 10h
0x1400fb053  jz      loc_1400FB1A1
0x1400fb059  call    cs:__imp_KfdIsTfoIncompatibleFilterPresent
0x1400fb060  nop     dword ptr [rax+rax+00h]
0x1400fb065  test    al, al
0x1400fb067  jz      loc_1400FB1AB
0x1400fb06d  cmp     cs:dword_1402244E0, r13d
0x1400fb074  jnz     loc_1400FB15A
0x1400fb07a  xor     eax, eax
0x1400fb07c  mov     r15d, 1
0x1400fb082  lock cmpxchg cs:dword_1402244E0, r15d
0x1400fb08b  jnz     loc_1400FB157
0x1400fb091  mov     eax, cs:dword_1402201F8
0x1400fb097  cmp     eax, 5
0x1400fb09a  jbe     loc_1400FB157
0x1400fb0a0  mov     rcx, cs:qword_140220210
0x1400fb0a7  mov     rdx, 400000000000h
0x1400fb0b1  mov     rax, cs:qword_140220208
0x1400fb0b8  test    rdx, rax
0x1400fb0bb  jz      loc_1400FB157
0x1400fb0c1  mov     rax, rcx
0x1400fb0c4  and     rax, rdx
0x1400fb0c7  cmp     rax, rcx
0x1400fb0ca  jnz     loc_1400FB157
0x1400fb0d0  movzx   eax, cs:word_1401F2F4D
0x1400fb0d7  lea     rcx, _TraceLoggingMetadata
0x1400fb0de  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400fb0e1  xor     r9d, r9d; RelatedActivityId
0x1400fb0e4  mov     rax, cs:off_140220200
0x1400fb0eb  xor     r8d, r8d; ActivityId
0x1400fb0ee  mov     [rbp+57h+var_58.Ptr], rax
0x1400fb0f2  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x1400fb0f6  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400fb0fa  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400fb101  movzx   eax, word ptr [rax]
0x1400fb104  mov     [rbp+57h+var_58.Size], eax
0x1400fb107  lea     rax, byte_1401F2F57
0x1400fb10e  mov     qword ptr [rbp+57h+var_48], rax
0x1400fb112  lea     rax, _TraceLoggingMetadataEnd
0x1400fb119  sub     eax, ecx
0x1400fb11b  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x1400fb122  mov     dword ptr [rbp+57h+var_48+8], 1Fh
0x1400fb129  mov     dword ptr [rbp+57h+var_48+0Ch], r15d
0x1400fb12d  mov     [rbp+57h+var_80], eax
0x1400fb130  mov     eax, [rbp+57h+var_80]
0x1400fb133  mov     rcx, cs:RegHandle; RegHandle
0x1400fb13a  lea     rax, [rbp+57h+var_58]
0x1400fb13e  mov     [rsp+0E0h+UserData], rax; UserData
0x1400fb143  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x1400fb14b  call    cs:__imp_EtwWriteTransfer
0x1400fb152  nop     dword ptr [rax+rax+00h]
0x1400fb157  xor     r15d, r15d
0x1400fb15a  cmp     cs:dword_1402201D4, r13d
0x1400fb161  jz      short loc_1400FB18E
0x1400fb163  cmp     byte ptr cs:WPP_MAIN_CB+14Bh, r13b
0x1400fb16a  jge     short loc_1400FB18E
0x1400fb16c  mov     r9, rdi
0x1400fb16f  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400fb173  lea     r8, [rbp+57h+EventDescriptor]
0x1400fb177  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdi
0x1400fb17b  lea     rdx, TCP_FASTOPEN_INCOMPAT_CALLOUT
0x1400fb182  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400fb189  call    McTemplateK0p_EtwWriteTransfer
0x1400fb18e  movzx   eax, byte ptr [rdi+0CDh]
0x1400fb195  test    al, 10h
0x1400fb197  jz      short loc_1400FB1A1
0x1400fb199  and     al, 0EFh
0x1400fb19b  mov     [rdi+0CDh], al
0x1400fb1a1  mov     eax, 0C000022Dh
0x1400fb1a6  jmp     loc_1400FB013
0x1400fb1ab  mov     rbx, [rdi+20h]
0x1400fb1af  jmp     short loc_1400FB207
0x1400fb1b1  mov     rdi, r15
0x1400fb1b4  bt      eax, 1Eh
0x1400fb1b8  jnb     loc_1400FB271
0x1400fb1be  mov     r13, [r14+18h]
0x1400fb1c2  mov     eax, [r13+20h]
0x1400fb1c6  test    al, 8
0x1400fb1c8  jz      short loc_1400FB203
0x1400fb1ca  cmp     cx, 17h
0x1400fb1ce  jnz     short loc_1400FB203
0x1400fb1d0  cmp     [rdx+8], di
0x1400fb1d4  jnz     short loc_1400FB1F9
0x1400fb1d6  cmp     [rdx+0Ah], di
0x1400fb1da  jnz     short loc_1400FB1F9
0x1400fb1dc  cmp     [rdx+0Ch], di
0x1400fb1e0  jnz     short loc_1400FB1F9
0x1400fb1e2  cmp     [rdx+0Eh], di
0x1400fb1e6  jnz     short loc_1400FB1F9
0x1400fb1e8  cmp     [rdx+10h], di
0x1400fb1ec  jnz     short loc_1400FB1F9
0x1400fb1ee  mov     ecx, 0FFFFh
0x1400fb1f3  cmp     [rdx+12h], cx
0x1400fb1f7  jz      short loc_1400FB203
0x1400fb1f9  mov     eax, 0C000023Ch
0x1400fb1fe  jmp     loc_1400FB013
0x1400fb203  mov     rbx, [r13+30h]
0x1400fb207  mov     eax, gs:1A4h
0x1400fb20f  xor     edx, edx
0x1400fb211  mov     r8, [rbx+10h]
0x1400fb215  mov     ecx, 2
0x1400fb21a  div     dword ptr [r8+14h]
0x1400fb21e  imul    edx, [r8+10h]
0x1400fb223  mov     eax, edx
0x1400fb225  add     rax, [r8]
0x1400fb228  lock xadd [rax], rcx
0x1400fb22d  test    cl, 1
0x1400fb230  jz      short loc_1400FB238
0x1400fb232  lock add qword ptr [r8+18h], 2
0x1400fb238  mov     rcx, cs:TcpTcbPool
0x1400fb23f  call    PplAllocateFromLookasideList
0x1400fb244  mov     rsi, rax
0x1400fb247  test    rax, rax
0x1400fb24a  jnz     loc_1400FB4A2
0x1400fb250  mov     rcx, rbx
0x1400fb253  call    _InetDereferenceAf
0x1400fb258  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r15b
0x1400fb25f  jge     loc_1400FB518
0x1400fb265  lea     r9, aTcbAllocationT; "TCB allocation (TCP)"
0x1400fb26c  jmp     loc_1400FB505
0x1400fb271  mov     rsi, [r14+28h]
0x1400fb275  xorps   xmm0, xmm0
0x1400fb278  mov     [rbp+57h+var_80], r15d
0x1400fb27c  mov     [rbp+57h+var_78], r15d
0x1400fb280  movups  xmmword ptr [rbp+57h+var_58.Ptr], xmm0
0x1400fb284  movups  [rbp+57h+var_48], xmm0
0x1400fb288  test    rsi, rsi
0x1400fb28b  jnz     short loc_1400FB295
0x1400fb28d  call    InetGetClientProcess
0x1400fb292  mov     rsi, rax
0x1400fb295  mov     rcx, [r14+30h]; Thread
0x1400fb299  lea     r8, [rbp+57h+var_58]; SubjectContext
0x1400fb29d  mov     rdx, rsi; Process
0x1400fb2a0  call    cs:__imp_SeCaptureSubjectContextEx
0x1400fb2a7  nop     dword ptr [rax+rax+00h]
0x1400fb2ac  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400fb2b3  nop     dword ptr [rax+rax+00h]
0x1400fb2b8  lea     rcx, [rbp+57h+var_80]
0x1400fb2bc  mov     r9d, 1200A9h; DesiredAccess
0x1400fb2c2  mov     [rsp+0E0h+AccessStatus], rcx; AccessStatus
0x1400fb2c7  lea     rdx, [rbp+57h+var_58]; SubjectSecurityContext
0x1400fb2cb  lea     rcx, [rbp+57h+var_78]
0x1400fb2cf  xor     r8d, r8d; SubjectContextLocked
0x1400fb2d2  mov     [rsp+0E0h+GrantedAccess], rcx; GrantedAccess
0x1400fb2d7  lea     rcx, TcpipEndpointCreationSdData; SecurityDescriptor
0x1400fb2de  mov     [rsp+0E0h+AccessMode], 1; AccessMode
0x1400fb2e3  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x1400fb2e8  mov     [rsp+0E0h+UserData], r15; Privileges
0x1400fb2ed  mov     [rsp+0E0h+UserDataCount], r15d; PreviouslyGrantedAccess
0x1400fb2f2  call    cs:__imp_SeAccessCheck
0x1400fb2f9  nop     dword ptr [rax+rax+00h]
0x1400fb2fe  lea     rcx, [rbp+57h+var_58]; SubjectContext
0x1400fb302  movzx   ebx, al
0x1400fb305  call    cs:__imp_SeReleaseSubjectContext
0x1400fb30c  nop     dword ptr [rax+rax+00h]
0x1400fb311  test    bl, bl
0x1400fb313  jnz     loc_1400FB3CD
0x1400fb319  cmp     cs:dword_1402201D4, edi
0x1400fb31f  jz      loc_1400FB3C5
0x1400fb325  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 8
0x1400fb32c  xorps   xmm0, xmm0
0x1400fb32f  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x1400fb333  jz      loc_1400FB3C5
0x1400fb339  mov     rcx, rsi; Process
0x1400fb33c  call    cs:__imp_PsGetProcessId
0x1400fb343  nop     dword ptr [rax+rax+00h]
0x1400fb348  mov     rcx, rsi
0x1400fb34b  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400fb34f  mov     rbx, rax
0x1400fb352  mov     qword ptr [rbp+57h+EventDescriptor.Id], r15
0x1400fb356  call    cs:__imp_PsGetProcessStartKey
0x1400fb35d  nop     dword ptr [rax+rax+00h]
0x1400fb362  mov     r10, [r14+58h]
0x1400fb366  mov     rdx, rax
0x1400fb369  mov     r11, [r14+40h]
0x1400fb36d  movzx   ecx, word ptr [r10]; af
0x1400fb371  call    SOCKADDR_SIZE
0x1400fb376  movzx   ecx, word ptr [r11]; af
0x1400fb37a  movzx   r8d, al
0x1400fb37e  call    SOCKADDR_SIZE
0x1400fb383  mov     [rsp+0E0h+var_88], rdx
0x1400fb388  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400fb38f  mov     [rsp+0E0h+var_90], r15
0x1400fb394  lea     rdx, TCP_CONNECT_TCB_FAILED_ACCESS_V1
0x1400fb39b  mov     dword ptr [rsp+0E0h+AccessStatus], r15d
0x1400fb3a0  mov     dword ptr [rsp+0E0h+GrantedAccess], ebx
0x1400fb3a4  mov     dword ptr [rsp+0E0h+AccessMode], r15d
0x1400fb3a9  mov     [rsp+0E0h+GenericMapping], r10
0x1400fb3ae  mov     dword ptr [rsp+0E0h+UserData], r8d
0x1400fb3b3  lea     r8, [rbp+57h+EventDescriptor]
0x1400fb3b7  movzx   r9d, al
0x1400fb3bb  mov     qword ptr [rsp+0E0h+UserDataCount], r11
0x1400fb3c0  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x1400fb3c5  mov     eax, [rbp+57h+var_80]
0x1400fb3c8  jmp     loc_1400FB013
0x1400fb3cd  mov     rdx, [r14+40h]
0x1400fb3d1  lea     rcx, TcpInetTransport
0x1400fb3d8  movzx   edx, word ptr [rdx]
0x1400fb3db  call    InetFindAndReferenceAf
0x1400fb3e0  mov     rbx, rax
0x1400fb3e3  test    rax, rax
0x1400fb3e6  jnz     loc_1400FB238
0x1400fb3ec  cmp     cs:dword_1402201D4, edi
0x1400fb3f2  jz      loc_1400FB498
0x1400fb3f8  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 8
0x1400fb3ff  xorps   xmm0, xmm0
0x1400fb402  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x1400fb406  jz      loc_1400FB498
0x1400fb40c  mov     rcx, rsi; Process
0x1400fb40f  call    cs:__imp_PsGetProcessId
0x1400fb416  nop     dword ptr [rax+rax+00h]
0x1400fb41b  mov     rcx, rsi
0x1400fb41e  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1400fb422  mov     rbx, rax
0x1400fb425  mov     qword ptr [rbp+57h+EventDescriptor.Id], r15
0x1400fb429  call    cs:__imp_PsGetProcessStartKey
0x1400fb430  nop     dword ptr [rax+rax+00h]
0x1400fb435  mov     r10, [r14+58h]
0x1400fb439  mov     rdx, rax
0x1400fb43c  mov     r11, [r14+40h]
0x1400fb440  movzx   ecx, word ptr [r10]; af
0x1400fb444  call    SOCKADDR_SIZE
  ... truncated ...
```
