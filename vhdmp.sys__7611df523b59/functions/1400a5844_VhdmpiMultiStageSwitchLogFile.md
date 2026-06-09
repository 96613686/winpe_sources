# VhdmpiMultiStageSwitchLogFile

- ea: `0x1400a5844`
- end: `0x1400a6549`
- name: `VhdmpiMultiStageSwitchLogFile`
- size: `3333`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, _QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001a1e8`

## callees

- `0x1400191d4`
- `0x14001b7fc`
- `0x14001bc68`
- `0x14001f58c`
- `0x140020874`
- `0x14002227c`
- `0x140023560`
- `0x140029334`
- `0x14002a4e8`
- `0x14002a9e8`
- `0x14002d80c`
- `0x14002da18`
- `0x140035e94`
- `0x140040504`
- `0x1400a40c0`
- `0x1400a4430`
- `0x1400a4d90`
- `0x1400a5844`
- `0x1400a6fa4`
- `0x1400a7078`
- `0x1400ebd40`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a5f83`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a6007`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a6017`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a5f83`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a6007`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a6017`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5f54`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5f6d`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5f54`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a5f6d`
- `ntoskrnl!KeClearEvent` at `0x1400a61d7`
- `ntoskrnl!KeClearEvent` at `0x1400a61d7`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400a61fb`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400a61fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a58a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a58bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a58a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a58bb`

## string_xrefs

- `0x1400a5997`: `VhdmpiMultiStageSwitchTracking: Failure getting VhdFilePath. Context = %p. VirtualDisk = %p`
- `0x1400a5a01`: `VhdmpiMultiStageSwitchLogFile: access is denied. Context = %p. VirtualDisk = %p`
- `0x1400a5bd4`: `VhdmpiMultiStageSwitchLogs: Incorrect FilePathOffset = %d. Context = %p. VirtualDisk = %p`
- `0x1400a5e1f`: `VhdmpiMultiStageSwitchTracking: Couldn't get absolute path for the log file. Context = %p. VirtualDisk = %p`

## pseudocode

```c
__int64 __fastcall VhdmpiMultiStageSwitchLogFile(struct _VHD_HANDLE_CONTEXT *a1, _QWORD *a2)
{
  __int64 v2; // r14
  __int64 v3; // rdi
  __int64 v5; // r13
  int v6; // edx
  int AbsoluteLogFilePath; // ebx
  __int64 v8; // rdx
  const GUID *v9; // r8
  char v10; // r12
  char v11; // r10
  unsigned int v12; // r11d
  int v13; // r11d
  char v14; // si
  int v15; // r11d
  unsigned int v16; // esi
  int v17; // r11d
  unsigned int v18; // ebx
  int v19; // r11d
  int v20; // edx
  char *v21; // rax
  int v22; // r9d
  char v23; // r9
  int v24; // r11d
  int v25; // r11d
  int v26; // r14d
  unsigned int v27; // r9d
  int v28; // eax
  int v29; // r10d
  int v30; // r10d
  int v31; // r10d
  int v32; // r10d
  int v33; // eax
  bool v34; // zf
  int v35; // r10d
  int v36; // edx
  char *v37; // rax
  int v38; // eax
  const GUID *v39; // r14
  int v40; // eax
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rax
  GUID v44; // xmm0
  __int64 v45; // rdx
  __int64 v46; // r8
  char v47; // al
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v51; // [rsp+50h] [rbp-69h]
  char v52; // [rsp+58h] [rbp-61h]
  char v53; // [rsp+59h] [rbp-60h]
  const GUID *v54; // [rsp+60h] [rbp-59h]
  unsigned int FeatureFlags; // [rsp+68h] [rbp-51h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-49h] BYREF
  __int64 v57; // [rsp+80h] [rbp-39h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+88h] [rbp-31h] BYREF
  struct _UNICODE_STRING v59; // [rsp+98h] [rbp-21h] BYREF
  UNICODE_STRING Source; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-1h]
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp+7h] BYREF
  char v63; // [rsp+120h] [rbp+67h]
  bool v65; // [rsp+130h] [rbp+77h]
  char v66; // [rsp+138h] [rbp+7Fh]

  v2 = a2[23];
  a2[7] = 0;
  v3 = *((_QWORD *)a1 + 7);
  v57 = 0;
  v63 = 0;
  v59 = 0;
  v5 = 0;
  v66 = 0;
  Source = 0;
  v53 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  GuidString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&Source, 0);
  v52 = 0;
  VhdmpiAcquirePassiveLockShared(v3 + 128);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    TraceEvents(
      (int)"VhdmpiMultiStageSwitchLogFile",
      2134,
      v6,
      v6,
      "VhdmpiMultiStageSwitchLogFile called for file %S.Context = %p. VirtualDisk = %p",
      *(_QWORD *)(*(_QWORD *)(v3 + 144) + 120LL));
  AbsoluteLogFilePath = VhdmpiDuplicateFilePath(0);
  VhdmpiReleasePassiveLockShared(v3 + 128);
  v10 = 1;
  v11 = 0;
  v12 = 2;
  if ( AbsoluteLogFilePath < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    {
      TraceEvents(
        (int)"VhdmpiMultiStageSwitchLogFile",
        2150,
        v13,
        4,
        "VhdmpiMultiStageSwitchTracking: Failure getting VhdFilePath. Context = %p. VirtualDisk = %p",
        (char)a1);
LABEL_8:
      v14 = 0;
      goto LABEL_149;
    }
LABEL_148:
    v14 = v11;
    goto LABEL_149;
  }
  if ( (*((_DWORD *)a1 + 1) & 1) != 0 && (*((_DWORD *)a1 + 2) & 0x200000) == 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      TraceEvents(
        (int)"VhdmpiMultiStageSwitchLogFile",
        2167,
        v15,
        4,
        "VhdmpiMultiStageSwitchLogFile: access is denied. Context = %p. VirtualDisk = %p",
        (char)a1);
    AbsoluteLogFilePath = -1073741790;
    goto LABEL_8;
  }
  v16 = *(_DWORD *)(v2 + 16);
  if ( v16 < 0x1C )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      TraceEvents(
        (int)"VhdmpiMultiStageSwitchLogFile",
        2186,
        v17,
        4,
        "VhdmpiMultiStageSwitchCTLogFile: input buffer too small. Context = %p. VirtualDisk = %p",
        (char)a1);
    AbsoluteLogFilePath = -1073741306;
    goto LABEL_8;
  }
  v5 = a2[3];
  v61 = v5;
  v18 = *(_DWORD *)v5;
  if ( *(_DWORD *)v5 == 64 )
  {
    if ( v16 < 0x40 )
    {
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
        goto LABEL_26;
      v20 = 2207;
      v21 = "VhdmpiMultiStageSwitchCTLogFile: input buffer smaller than STORAGE_CHANGE_CTLOG_FILE_V2_REQUEST. Context = %"
            "p. VirtualDisk = %p";
      v22 = 4;
LABEL_25:
      TraceEvents((int)"VhdmpiMultiStageSwitchLogFile", v20, v19, v22, v21, (char)a1);
LABEL_26:
      AbsoluteLogFilePath = -1073741306;
LABEL_27:
      v5 = 0;
      goto LABEL_8;
    }
    v65 = *(_BYTE *)(*((_QWORD *)a1 + 7) + 93LL) != 0;
    FeatureFlags = VhdmpiCtGetFeatureFlags((struct _VHD_VIRTUAL_DISK *)v3, *(_DWORD *)(v5 + 28));
    if ( v23 && *(_OWORD *)(v5 + 32) == *(_OWORD *)&VhdmpZeroGuid )
    {
      if ( dword_140087708 > v12 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
        TraceEvents(
          (int)"VhdmpiMultiStageSwitchLogFile",
          2226,
          v24,
          4,
          "VhdmpiMultiStageSwitchCTLogFile: Snapshot ID is NULL_GUID for VhdSet in V2 request.                     Contex"
          "t = %p. VirtualDisk = %p",
          (char)a1);
LABEL_33:
      AbsoluteLogFilePath = -1073741811;
      goto LABEL_27;
    }
    v54 = (const GUID *)v5;
  }
  else
  {
    if ( v18 != 28 )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
        TraceEvents(
          (int)"VhdmpiMultiStageSwitchLogFile",
          2240,
          v25,
          4,
          "VhdmpiMultiStageSwitchLogs: Incorrect FilePathOffset = %d. Context = %p. VirtualDisk = %p",
          v18);
      goto LABEL_33;
    }
    v54 = 0;
    FeatureFlags = 0;
    v65 = 0;
  }
  v8 = 4;
  if ( *(_DWORD *)(v2 + 8) < 4u )
  {
    if ( dword_140087708 <= v12 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      goto LABEL_26;
    v21 = "VhdmpiMultiStageSwitchCTLogFile: output buffer too small. Context = %p. VirtualDisk = %p";
    v22 = v8;
    v20 = 2254;
    goto LABEL_25;
  }
  v26 = *(_DWORD *)(v5 + 24);
  v51 = v5;
  if ( (unsigned int)(v26 - 1) > 3 )
  {
    AbsoluteLogFilePath = -1073741811;
    goto LABEL_148;
  }
  VhdmpiAcquirePassiveLock(v3 + 1888, 4, v9);
  v66 = 1;
  if ( v26 == 1 )
  {
    v27 = *(_DWORD *)(v5 + 4);
    if ( (v27 & 0xFFFFFFFD) != 0 || *(_DWORD *)v5 != 64 )
    {
      if ( !VhdmpiValidateFileName(v5, v18, v16, v27, *(_DWORD *)v5, &v59, (char)"VhdmpiMultiStageSwitchLogFile: ") )
      {
LABEL_52:
        AbsoluteLogFilePath = -1073741811;
LABEL_53:
        v14 = v63;
        goto LABEL_149;
      }
      AbsoluteLogFilePath = VhdmpiCtGetAbsoluteLogFilePath(&Source, &v59, &DestinationString.Length);
      if ( AbsoluteLogFilePath < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
          TraceEvents(
            (int)"VhdmpiMultiStageSwitchLogFile",
            2353,
            v30,
            v30 + 2,
            "VhdmpiMultiStageSwitchTracking: Couldn't get absolute path for the log file. Context = %p. VirtualDisk = %p",
            (char)a1);
        goto LABEL_53;
      }
    }
    else
    {
      if ( !*(_BYTE *)(*((_QWORD *)a1 + 7) + 93LL) )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
          TraceEvents(
            (int)"VhdmpiMultiStageSwitchLogFile",
            2309,
            2,
            4,
            "VhdmpiMultiStageSwitchCTLogFile: expected to be VhdSet. Context = %p. VirtualDisk = %p",
            (char)a1);
        goto LABEL_52;
      }
      AbsoluteLogFilePath = VhdmpiCtCreateNewLogFile(a1, &DestinationString, &v59);
      if ( AbsoluteLogFilePath < 0 )
        goto LABEL_53;
      v52 = 1;
    }
  }
  VhdmpiAcquirePassiveLock(v3 + 1872, v8, v9);
  v28 = *(_DWORD *)(v3 + 1856);
  v14 = 1;
  if ( v28 == 2 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      TraceEvents(
        (int)"VhdmpiMultiStageSwitchLogFile",
        2378,
        v29,
        v29 + 2,
        "VhdmpiMultiStageSwitchCTLogFile: state is disabled. Context = %p. VirtualDisk = %p",
        (char)a1);
    AbsoluteLogFilePath = -1069940704;
    goto LABEL_149;
  }
  if ( v28 != 1 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      TraceEvents(
        (int)"VhdmpiMultiStageSwitchLogFile",
        2395,
        v31,
        4,
        "VhdmpiMultiStageSwitchCTLogFile: state is not enabled. Context = %p. VirtualDisk = %p",
        (char)a1);
    AbsoluteLogFilePath = -1069940701;
    goto LABEL_149;
  }
  if ( !*(_BYTE *)(v3 + 2080) )
  {
    v9 = v54;
    switch ( v26 )
    {
      case 1:
        v33 = *(_DWORD *)(v3 + 2132);
        if ( v33 != 1 )
          goto LABEL_94;
        LOBYTE(v8) = v65;
        break;
      case 2:
        v33 = *(_DWORD *)(v3 + 2132);
        if ( v33 != 2 )
          goto LABEL_94;
        break;
      case 3:
        v33 = *(_DWORD *)(v3 + 2132);
        v34 = v33 == 3;
        goto LABEL_106;
      default:
        LOBYTE(v8) = v65;
        if ( v65 )
        {
          if ( *(_QWORD *)(v3 + 2400) != *(_QWORD *)&v54[2].Data1 || *(_QWORD *)(v3 + 2408) != *(_QWORD *)v54[2].Data4 )
          {
            AbsoluteLogFilePath = RtlStringFromGUID((const GUID *const)(v3 + 2400), &GuidString);
            if ( AbsoluteLogFilePath < 0 )
            {
LABEL_83:
              v5 = v51;
              v14 = 1;
              goto LABEL_149;
            }
            AbsoluteLogFilePath = RtlStringFromGUID(v54 + 2, &UnicodeString);
            if ( AbsoluteLogFilePath < 0 )
            {
              RtlFreeUnicodeString(&GuidString);
              goto LABEL_83;
            }
            if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
              TraceEvents(
                (int)"VhdmpiMultiStageSwitchLogFile",
                2445,
                2,
                4,
                "VhdmpiMultiStageSwitchCTLogFile: Snapshot ID in the request is not matching the Snapshot ID of the curre"
                "nt switch.             SwitchLogFileAction = 0x%08x. Context = %p. VirtualDisk = %p. SwitchLogFileSnapsh"
                "otID = %S. RequestSnapshotID = %S",
                v26);
            RtlFreeUnicodeString(&UnicodeString);
            RtlFreeUnicodeString(&GuidString);
LABEL_88:
            AbsoluteLogFilePath = -1073741811;
            goto LABEL_83;
          }
          v5 = v61;
        }
        break;
    }
    if ( v26 != 4 )
    {
      if ( v26 == 1 )
        goto LABEL_113;
      goto LABEL_109;
    }
    v33 = *(_DWORD *)(v3 + 2132);
    v34 = v33 == 4;
LABEL_106:
    if ( !v34 )
    {
LABEL_94:
      if ( v65
        && v33 == 1
        && *(_QWORD *)(v3 + 2400) == *(_QWORD *)&v54[2].Data1
        && *(_QWORD *)(v3 + 2408) == *(_QWORD *)v54[2].Data4 )
      {
        if ( v26 == 3 )
        {
          if ( *(_DWORD *)(v3 + 2396) == 2 )
          {
            *(_DWORD *)(v3 + 2396) = 3;
LABEL_101:
            AbsoluteLogFilePath = -1073741643;
            goto LABEL_83;
          }
        }
        else if ( v26 == 4 && *(_DWORD *)(v3 + 2396) == 3 )
        {
          *(_DWORD *)(v3 + 2396) = 0;
          *(_OWORD *)(v3 + 2400) = *(_OWORD *)&VhdmpZeroGuid;
          goto LABEL_101;
        }
      }
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
        goto LABEL_88;
      v36 = 2532;
      v37 = "VhdmpiMultiStageSwitchCTLogFile: change tracking state is not matching for action (0x%08x) . Context = %p. VirtualDisk = %p";
LABEL_146:
      TraceEvents((int)"VhdmpiMultiStageSwitchLogFile", v36, v35, 4, v37, v26);
      goto LABEL_88;
    }
LABEL_109:
    if ( *(struct _VHD_HANDLE_CONTEXT **)(v3 + 2136) != a1 )
    {
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
        goto LABEL_88;
      v36 = 2551;
      v37 = "VhdmpiMultiStageSwitchCTLogFile: HandleContext is not matching for action (0x%08x) . Context = %p. VirtualDisk = %p";
      goto LABEL_146;
    }
LABEL_113:
    if ( (_BYTE)v8 )
    {
      if ( v26 == 1 )
      {
        v38 = *(_DWORD *)(v3 + 2396);
        if ( v38 == 1 )
        {
          AbsoluteLogFilePath = -2147483631;
          goto LABEL_83;
        }
        if ( (unsigned int)(v38 - 2) <= 1 )
        {
          *(_DWORD *)(v3 + 2396) = 0;
          *(_OWORD *)(v3 + 2400) = *(_OWORD *)&VhdmpZeroGuid;
        }
        v39 = v54;
        AbsoluteLogFilePath = VhdmpiPrepareAndCommitCdpSnapshot(*((struct _VHDS_STATE **)a1 + 38));
        if ( AbsoluteLogFilePath < 0 )
          goto LABEL_83;
        v53 = 1;
        goto LABEL_136;
      }
    }
    else if ( v26 == 1 )
    {
LABEL_135:
      v39 = v54;
LABEL_136:
      AbsoluteLogFilePath = VhdmpiCTLogCreateBackingStore(
                              &DestinationString,
                              0,
                              v5 + 8,
                              *(_QWORD *)(v3 + 1536) + 144LL,
                              (struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 248),
                              0,
                              &v57,
                              FeatureFlags);
      if ( !v57 )
        goto LABEL_83;
      *(_QWORD *)(v3 + 2120) = v57;
      *(_QWORD *)(v3 + 2136) = a1;
      *(_DWORD *)(v3 + 2132) = 2;
      if ( v65 )
      {
        v44 = v39[2];
        *(_DWORD *)(v3 + 2396) = 0;
        *(GUID *)(v3 + 2400) = v44;
      }
LABEL_139:
      AbsoluteLogFilePath = 0;
      goto LABEL_83;
    }
    switch ( v26 )
    {
      case 2:
        *(_BYTE *)(v3 + 2128) = 1;
        *(_DWORD *)(v3 + 2132) = 3;
        if ( (_BYTE)v8 )
        {
          v40 = -dword_14008E360;
          *(_DWORD *)(v3 + 2396) = 1;
          v41 = 10000LL * v40;
          *(_BYTE *)(v3 + 2392) = 0;
          KeClearEvent((PRKEVENT)(v3 + 2368));
          KeSetCoalescableTimer((PKTIMER)(v3 + 2200), (LARGE_INTEGER)v41, 0, 0x20u, (PKDPC)(v3 + 2264));
        }
        goto LABEL_139;
      case 3:
        if ( (_BYTE)v8 )
          VhdmpiCancelServerTimeoutHandling(v3, v8, v54);
        AbsoluteLogFilePath = 0;
        *(_OWORD *)(*(_QWORD *)(v3 + 2120) + 160LL) = *(_OWORD *)(*(_QWORD *)(v3 + 1536) + 144LL);
        v42 = *(_QWORD *)(v3 + 2120);
        v43 = *(_QWORD *)(v3 + 1536);
        *(_QWORD *)(v3 + 1536) = v42;
        *(_QWORD *)(v3 + 2120) = v43;
        *(_QWORD *)(v42 + 72) = v3;
        *(_BYTE *)(v3 + 2128) = 0;
        *(_DWORD *)(v3 + 2132) = 4;
        VhdmpiTriggerCTLogSrbProcessingRoutine(v3, v8, v9);
        goto LABEL_83;
      case 4:
        VhdmpiReleasePassiveLock(v3 + 1872);
        v63 = 0;
        AbsoluteLogFilePath = VhdmpiCTLogCloseBackingStore(*(struct _CTLOG_BACKING_STORE **)(v3 + 2120));
        if ( AbsoluteLogFilePath < 0 )
        {
          VhdmpiAcquirePassiveLock(v3 + 1872, v8, v9);
          v63 = 1;
          VhdmpiCTLogProcessTrackingError(v3, (unsigned int)AbsoluteLogFilePath);
        }
        if ( v65 )
          *(_OWORD *)(v3 + 2400) = *(_OWORD *)&VhdmpZeroGuid;
        v5 = v51;
        *(_QWORD *)(v3 + 2120) = 0;
        *(_QWORD *)(v3 + 2136) = 0;
        *(_DWORD *)(v3 + 2132) = 1;
        goto LABEL_53;
    }
    goto LABEL_135;
  }
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    TraceEvents(
      (int)"VhdmpiMultiStageSwitchLogFile",
      2412,
      v32,
      4,
      "VhdmpiMultiStageSwitchCTLogFile: CT Log operations are not allowed. Context = %p. VirtualDisk = %p",
      (char)a1);
  AbsoluteLogFilePath = -2147483631;
LABEL_149:
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    TraceEvents(
      (int)"VhdmpiMultiStageSwitchLogFile",
      2805,
      4,
      4,
      "VhdmpiMultiStageSwitchCTLogFile: leaving... (0x%08x). Context = %p. VirtualDisk = %p STL stage = (0x%08x)",
      AbsoluteLogFilePath);
  if ( v5 )
  {
    *(_DWORD *)v5 = 0;
    *(_DWORD *)v5 = *(_DWORD *)(v3 + 1860);
    a2[7] = 4;
  }
  if ( v14 )
    VhdmpiReleasePassiveLock(v3 + 1872);
  if ( v66 )
    VhdmpiReleasePassiveLock(v3 + 1888);
  VhdmpiTriggerCTLogSrbProcessingRoutine(v3, v8, v9);
  if ( AbsoluteLogFilePath < 0 )
  {
    if ( v52 )
      VhdmpiDeleteFile(&DestinationString);
    if ( AbsoluteLogFilePath != -1073741643 )
    {
      if ( !*(_BYTE *)(*((_QWORD *)a1 + 7) + 93LL) || (v47 = 1, (unsigned int)(*(_DWORD *)(v3 + 2132) - 2) > 1) )
        v47 = 0;
      if ( !v53 && !v47 )
        v10 = 0;
      LOBYTE(v46) = v10;
      VhdmpiAbortMultiStageSwitchLogFileInternal(a1, 0, v46, 0);
    }
  }
  VhdmpiFreeFilePath(&Source, v45, v46);
  VhdmpiFreeFilePath(&DestinationString, v48, v49);
  return (unsigned int)AbsoluteLogFilePath;
}

```

## disassembly

```asm
0x1400a5844  mov     [rsp-8+arg_8], rdx
0x1400a5849  push    rbp
0x1400a584a  push    rbx
0x1400a584b  push    rsi
0x1400a584c  push    rdi
0x1400a584d  push    r12
0x1400a584f  push    r13
0x1400a5851  push    r14
0x1400a5853  push    r15
0x1400a5855  lea     rbp, [rsp-1Fh]
0x1400a585a  sub     rsp, 0D8h
0x1400a5861  mov     r14, [rdx+0B8h]
0x1400a5868  xor     ebx, ebx
0x1400a586a  xorps   xmm0, xmm0
0x1400a586d  mov     [rdx+38h], rbx
0x1400a5871  mov     rdi, [rcx+38h]
0x1400a5875  xorps   xmm1, xmm1
0x1400a5878  mov     r15, rcx
0x1400a587b  mov     [rbp+57h+var_C0], rbx
0x1400a587f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a5883  mov     [rbp+57h+var_90], rbx
0x1400a5887  xor     edx, edx; SourceString
0x1400a5889  mov     [rbp+57h+arg_0], bl
0x1400a588c  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x1400a5890  mov     r13d, ebx
0x1400a5893  mov     [rbp+57h+arg_18], bl
0x1400a5896  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x1400a589a  mov     [rbp+57h+var_B7], bl
0x1400a589d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400a58a1  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x1400a58a5  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400a58a9  call    cs:__imp_RtlInitUnicodeString
0x1400a58b0  nop     dword ptr [rax+rax+00h]
0x1400a58b5  xor     edx, edx; SourceString
0x1400a58b7  lea     rcx, [rbp+57h+Source]; DestinationString
0x1400a58bb  call    cs:__imp_RtlInitUnicodeString
0x1400a58c2  nop     dword ptr [rax+rax+00h]
0x1400a58c7  lea     rsi, [rdi+80h]
0x1400a58ce  mov     [rbp+57h+var_B8], bl
0x1400a58d1  mov     rcx, rsi
0x1400a58d4  call    VhdmpiAcquirePassiveLockShared
0x1400a58d9  mov     eax, cs:dword_140087708
0x1400a58df  lea     edx, [rbx+4]
0x1400a58e2  cmp     eax, edx
0x1400a58e4  jbe     short loc_1400A5935
0x1400a58e6  lea     rcx, dword_140087708
0x1400a58ed  call    _tlgKeywordOn
0x1400a58f2  test    al, al
0x1400a58f4  jz      short loc_1400A5935
0x1400a58f6  mov     rax, [rdi+90h]
0x1400a58fd  mov     ecx, 856h
0x1400a5902  mov     qword ptr [rsp+110h+var_D8], rdi
0x1400a5907  mov     r9d, edx; int
0x1400a590a  mov     qword ptr [rsp+110h+var_E0], r15
0x1400a590f  mov     r8d, edx; int
0x1400a5912  mov     edx, ecx; int
0x1400a5914  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a591b  mov     rax, [rax+78h]
0x1400a591f  mov     [rsp+110h+var_E8], rax; char
0x1400a5924  lea     rax, aVhdmpimultista_17; "VhdmpiMultiStageSwitchLogFile called fo"...
0x1400a592b  mov     [rsp+110h+Dpc], rax; char *
0x1400a5930  call    TraceEvents
0x1400a5935  mov     rdx, [rdi+90h]
0x1400a593c  lea     r9, [rbp+57h+Source]
0x1400a5940  add     rdx, 48h ; 'H'
0x1400a5944  xor     r8d, r8d
0x1400a5947  xor     ecx, ecx; Source
0x1400a5949  call    VhdmpiDuplicateFilePath
0x1400a594e  mov     rcx, rsi
0x1400a5951  mov     ebx, eax
0x1400a5953  call    VhdmpiReleasePassiveLockShared
0x1400a5958  mov     r12d, 1
0x1400a595e  xor     r10d, r10d
0x1400a5961  lea     r11d, [r12+1]
0x1400a5966  test    ebx, ebx
0x1400a5968  jns     short loc_1400A59C9
0x1400a596a  mov     ecx, cs:dword_140087708
0x1400a5970  cmp     ecx, r11d
0x1400a5973  jbe     loc_1400A641A
0x1400a5979  lea     edx, [r12+3]
0x1400a597e  lea     rcx, dword_140087708
0x1400a5985  call    _tlgKeywordOn
0x1400a598a  test    al, al
0x1400a598c  jz      loc_1400A641A
0x1400a5992  mov     qword ptr [rsp+110h+var_E0], rdi
0x1400a5997  lea     rax, aVhdmpimultista_14; "VhdmpiMultiStageSwitchTracking: Failure"...
0x1400a599e  mov     [rsp+110h+var_E8], r15; char
0x1400a59a3  lea     r9d, [r12+3]; int
0x1400a59a8  mov     edx, 866h; int
0x1400a59ad  mov     [rsp+110h+Dpc], rax; char *
0x1400a59b2  mov     r8d, r11d; int
0x1400a59b5  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a59bc  call    TraceEvents
0x1400a59c1  mov     sil, r13b
0x1400a59c4  jmp     loc_1400A641D
0x1400a59c9  mov     eax, [r15+4]
0x1400a59cd  test    r12b, al
0x1400a59d0  jz      short loc_1400A5A33
0x1400a59d2  test    dword ptr [r15+8], 200000h
0x1400a59da  jnz     short loc_1400A5A33
0x1400a59dc  mov     eax, cs:dword_140087708
0x1400a59e2  cmp     eax, r11d
0x1400a59e5  jbe     short loc_1400A5A2C
0x1400a59e7  mov     edx, 4
0x1400a59ec  lea     rcx, dword_140087708
0x1400a59f3  call    _tlgKeywordOn
0x1400a59f8  test    al, al
0x1400a59fa  jz      short loc_1400A5A2C
0x1400a59fc  mov     qword ptr [rsp+110h+var_E0], rdi
0x1400a5a01  lea     rax, aVhdmpimultista_15; "VhdmpiMultiStageSwitchLogFile: access i"...
0x1400a5a08  mov     [rsp+110h+var_E8], r15; char
0x1400a5a0d  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a5a14  mov     edx, 877h; int
0x1400a5a19  mov     [rsp+110h+Dpc], rax; char *
0x1400a5a1e  mov     r9d, 4; int
0x1400a5a24  mov     r8d, r11d; int
0x1400a5a27  call    TraceEvents
0x1400a5a2c  mov     ebx, 0C0000022h
0x1400a5a31  jmp     short loc_1400A59C1
0x1400a5a33  mov     esi, [r14+10h]
0x1400a5a37  cmp     esi, 1Ch
0x1400a5a3a  jnb     short loc_1400A5A96
0x1400a5a3c  mov     eax, cs:dword_140087708
0x1400a5a42  cmp     eax, r11d
0x1400a5a45  jbe     short loc_1400A5A8C
0x1400a5a47  mov     edx, 4
0x1400a5a4c  lea     rcx, dword_140087708
0x1400a5a53  call    _tlgKeywordOn
0x1400a5a58  test    al, al
0x1400a5a5a  jz      short loc_1400A5A8C
0x1400a5a5c  mov     qword ptr [rsp+110h+var_E0], rdi
0x1400a5a61  lea     rax, aVhdmpimultista_5; "VhdmpiMultiStageSwitchCTLogFile: input "...
0x1400a5a68  mov     [rsp+110h+var_E8], r15; char
0x1400a5a6d  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a5a74  mov     edx, 88Ah; int
0x1400a5a79  mov     [rsp+110h+Dpc], rax; char *
0x1400a5a7e  mov     r9d, 4; int
0x1400a5a84  mov     r8d, r11d; int
0x1400a5a87  call    TraceEvents
0x1400a5a8c  mov     ebx, 0C0000206h
0x1400a5a91  jmp     loc_1400A59C1
0x1400a5a96  mov     r13, [rbp+57h+arg_8]
0x1400a5a9a  mov     r13, [r13+18h]
0x1400a5a9e  mov     [rbp+57h+var_58], r13
0x1400a5aa2  mov     ebx, [r13+0]
0x1400a5aa6  cmp     ebx, 40h ; '@'
0x1400a5aa9  jnz     loc_1400A5BAA
0x1400a5aaf  cmp     esi, ebx
0x1400a5ab1  jnb     short loc_1400A5B0D
0x1400a5ab3  mov     eax, cs:dword_140087708
0x1400a5ab9  cmp     eax, r11d
0x1400a5abc  jbe     short loc_1400A5AFF
0x1400a5abe  lea     edx, [rbx-3Ch]
0x1400a5ac1  lea     rcx, dword_140087708
0x1400a5ac8  call    _tlgKeywordOn
0x1400a5acd  test    al, al
0x1400a5acf  jz      short loc_1400A5AFF
0x1400a5ad1  mov     edx, 89Fh; int
0x1400a5ad6  lea     rax, aVhdmpimultista_6; "VhdmpiMultiStageSwitchCTLogFile: input "...
0x1400a5add  lea     r9d, [rbx-3Ch]; int
0x1400a5ae1  mov     qword ptr [rsp+110h+var_E0], rdi
0x1400a5ae6  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a5aed  mov     [rsp+110h+var_E8], r15; char
0x1400a5af2  mov     r8d, r11d; int
0x1400a5af5  mov     [rsp+110h+Dpc], rax; char *
0x1400a5afa  call    TraceEvents
0x1400a5aff  mov     ebx, 0C0000206h
0x1400a5b04  mov     r13, [rbp+57h+var_C0]
0x1400a5b08  jmp     loc_1400A59C1
0x1400a5b0d  mov     rax, [r15+38h]
0x1400a5b11  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400a5b14  mov     edx, [r13+1Ch]; unsigned int
0x1400a5b18  mov     r9b, [rax+5Dh]
0x1400a5b1c  test    r9b, r9b
0x1400a5b1f  setnz   [rbp+57h+arg_10]
0x1400a5b23  call    ?VhdmpiCtGetFeatureFlags@@YAKPEAU_VHD_VIRTUAL_DISK@@K@Z; VhdmpiCtGetFeatureFlags(_VHD_VIRTUAL_DISK *,ulong)
0x1400a5b28  mov     [rbp+57h+var_A8], eax
0x1400a5b2b  test    r9b, r9b
0x1400a5b2e  jz      short loc_1400A5BA4
0x1400a5b30  mov     rcx, [r13+20h]
0x1400a5b34  cmp     rcx, qword ptr cs:VhdmpZeroGuid
0x1400a5b3b  jnz     short loc_1400A5BA4
0x1400a5b3d  mov     rcx, [r13+28h]
0x1400a5b41  cmp     rcx, qword ptr cs:VhdmpZeroGuid+8
0x1400a5b48  jnz     short loc_1400A5BA4
0x1400a5b4a  mov     eax, cs:dword_140087708
0x1400a5b50  cmp     eax, r11d
0x1400a5b53  jbe     short loc_1400A5B9A
0x1400a5b55  mov     edx, 4
0x1400a5b5a  lea     rcx, dword_140087708
0x1400a5b61  call    _tlgKeywordOn
0x1400a5b66  test    al, al
0x1400a5b68  jz      short loc_1400A5B9A
0x1400a5b6a  mov     qword ptr [rsp+110h+var_E0], rdi
0x1400a5b6f  lea     rax, aVhdmpimultista_4; "VhdmpiMultiStageSwitchCTLogFile: Snapsh"...
0x1400a5b76  mov     [rsp+110h+var_E8], r15; char
0x1400a5b7b  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a5b82  mov     edx, 8B2h; int
0x1400a5b87  mov     [rsp+110h+Dpc], rax; char *
0x1400a5b8c  mov     r9d, 4; int
0x1400a5b92  mov     r8d, r11d; int
0x1400a5b95  call    TraceEvents
0x1400a5b9a  mov     ebx, 0C000000Dh
0x1400a5b9f  jmp     loc_1400A5B04
0x1400a5ba4  mov     [rbp+57h+var_B0], r13
0x1400a5ba8  jmp     short loc_1400A5C11
0x1400a5baa  cmp     ebx, 1Ch
0x1400a5bad  jz      short loc_1400A5C05
0x1400a5baf  mov     eax, cs:dword_140087708
0x1400a5bb5  cmp     eax, r11d
0x1400a5bb8  jbe     short loc_1400A5B9A
0x1400a5bba  mov     edx, 4
0x1400a5bbf  lea     rcx, dword_140087708
0x1400a5bc6  call    _tlgKeywordOn
0x1400a5bcb  test    al, al
0x1400a5bcd  jz      short loc_1400A5B9A
0x1400a5bcf  mov     qword ptr [rsp+110h+var_D8], rdi
0x1400a5bd4  lea     rax, aVhdmpimultista_12; "VhdmpiMultiStageSwitchLogs: Incorrect F"...
0x1400a5bdb  mov     qword ptr [rsp+110h+var_E0], r15
0x1400a5be0  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a5be7  mov     dword ptr [rsp+110h+var_E8], ebx; char
0x1400a5beb  mov     edx, 8C0h; int
0x1400a5bf0  mov     r9d, 4; int
0x1400a5bf6  mov     [rsp+110h+Dpc], rax; char *
0x1400a5bfb  mov     r8d, r11d; int
0x1400a5bfe  call    TraceEvents
0x1400a5c03  jmp     short loc_1400A5B9A
0x1400a5c05  mov     [rbp+57h+var_B0], r10
0x1400a5c09  mov     [rbp+57h+var_A8], r10d
0x1400a5c0d  mov     [rbp+57h+arg_10], r10b
0x1400a5c11  mov     edx, 4
0x1400a5c16  cmp     [r14+8], edx
0x1400a5c1a  jnb     short loc_1400A5C55
0x1400a5c1c  mov     eax, cs:dword_140087708
0x1400a5c22  cmp     eax, r11d
0x1400a5c25  jbe     loc_1400A5AFF
0x1400a5c2b  lea     rcx, dword_140087708
0x1400a5c32  call    _tlgKeywordOn
0x1400a5c37  test    al, al
0x1400a5c39  jz      loc_1400A5AFF
0x1400a5c3f  mov     ecx, 8CEh
0x1400a5c44  lea     rax, aVhdmpimultista_9; "VhdmpiMultiStageSwitchCTLogFile: output"...
0x1400a5c4b  mov     r9d, edx
0x1400a5c4e  mov     edx, ecx
0x1400a5c50  jmp     loc_1400A5AE1
0x1400a5c55  mov     r14d, [r13+18h]
0x1400a5c59  mov     [rbp+57h+var_C0], r13
0x1400a5c5d  lea     eax, [r14-1]
0x1400a5c61  cmp     eax, 3
0x1400a5c64  ja      loc_1400A6415
0x1400a5c6a  lea     rcx, [rdi+760h]
0x1400a5c71  call    VhdmpiAcquirePassiveLock
0x1400a5c76  mov     [rbp+57h+arg_18], r12b
0x1400a5c7a  cmp     r14d, r12d
0x1400a5c7d  jnz     loc_1400A5D22
0x1400a5c83  mov     r9d, [r13+4]; int
0x1400a5c87  test    r9d, 0FFFFFFFDh
0x1400a5c8e  jnz     loc_1400A5DA0
0x1400a5c94  cmp     dword ptr [r13+0], 40h ; '@'
0x1400a5c99  jnz     loc_1400A5DA0
0x1400a5c9f  mov     rax, [r15+38h]
0x1400a5ca3  cmp     byte ptr [rax+5Dh], 0
0x1400a5ca7  jnz     short loc_1400A5D08
0x1400a5ca9  mov     eax, cs:dword_140087708
0x1400a5caf  cmp     eax, 2
0x1400a5cb2  jbe     short loc_1400A5CFA
0x1400a5cb4  mov     edx, 4
0x1400a5cb9  lea     rcx, dword_140087708
0x1400a5cc0  call    _tlgKeywordOn
0x1400a5cc5  test    al, al
0x1400a5cc7  jz      short loc_1400A5CFA
0x1400a5cc9  mov     r9d, 4; int
0x1400a5ccf  mov     qword ptr [rsp+110h+var_E0], rdi
0x1400a5cd4  lea     rax, aVhdmpimultista_8; "VhdmpiMultiStageSwitchCTLogFile: expect"...
0x1400a5cdb  mov     [rsp+110h+var_E8], r15; char
0x1400a5ce0  mov     edx, 905h; int
0x1400a5ce5  mov     [rsp+110h+Dpc], rax; char *
0x1400a5cea  lea     rcx, aVhdmpimultista_16; "VhdmpiMultiStageSwitchLogFile"
0x1400a5cf1  lea     r8d, [r9-2]; int
0x1400a5cf5  call    TraceEvents
0x1400a5cfa  mov     ebx, 0C000000Dh
0x1400a5cff  mov     sil, [rbp+57h+arg_0]
0x1400a5d03  jmp     loc_1400A641D
0x1400a5d08  lea     r8, [rbp+57h+var_78]; struct _UNICODE_STRING *
0x1400a5d0c  mov     rcx, r15; struct _VHD_HANDLE_CONTEXT *
0x1400a5d0f  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x1400a5d13  call    ?VhdmpiCtCreateNewLogFile@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_UNICODE_STRING@@1@Z; VhdmpiCtCreateNewLogFile(_VHD_HANDLE_CONTEXT *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1400a5d18  mov     ebx, eax
0x1400a5d1a  test    eax, eax
0x1400a5d1c  js      short loc_1400A5CFF
0x1400a5d1e  mov     [rbp+57h+var_B8], r12b
0x1400a5d22  lea     rbx, [rdi+750h]
0x1400a5d29  mov     rcx, rbx
0x1400a5d2c  call    VhdmpiAcquirePassiveLock
0x1400a5d31  mov     eax, [rdi+740h]
0x1400a5d37  mov     r10d, 2
0x1400a5d3d  mov     sil, r12b
0x1400a5d40  cmp     eax, r10d
0x1400a5d43  jnz     loc_1400A5E4D
0x1400a5d49  mov     eax, cs:dword_140087708
  ... truncated ...
```
