# HandleOperation

- ea: `0x14001e808`
- end: `0x14001f129`
- name: `HandleOperation`
- size: `2337`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001fd50`
- `0x14001fdc0`
- `0x14001ff30`

## callees

- `0x140001008`
- `0x140002604`
- `0x140002644`
- `0x140002868`
- `0x140002a9c`
- `0x140003554`
- `0x140003944`
- `0x140004124`
- `0x140004330`
- `0x14000439c`
- `0x140005544`
- `0x140006600`
- `0x14000dd24`
- `0x14000e488`
- `0x14000f900`
- `0x14001e808`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14001e84c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001e84c`
- `ntoskrnl!KeBugCheck` at `0x14001f084`
- `ntoskrnl!KeBugCheck` at `0x14001f084`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ecbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f026`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f044`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f0e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ecbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f026`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f044`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f0e0`
- `ntoskrnl!KeReleaseMutex` at `0x14001ed0b`
- `ntoskrnl!KeReleaseMutex` at `0x14001f0b2`
- `ntoskrnl!KeReleaseMutex` at `0x14001ed0b`
- `ntoskrnl!KeReleaseMutex` at `0x14001f0b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001eb31`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f06e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001eb31`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f06e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001f0c7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001f0f5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001f0c7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001f0f5`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14001e981`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14001ee14`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14001e981`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14001ee14`
- `FLTMGR!FltParseFileNameInformation` at `0x14001e906`
- `FLTMGR!FltParseFileNameInformation` at `0x14001e99e`
- `FLTMGR!FltParseFileNameInformation` at `0x14001ee3e`
- `FLTMGR!FltParseFileNameInformation` at `0x14001e906`
- `FLTMGR!FltParseFileNameInformation` at `0x14001e99e`
- `FLTMGR!FltParseFileNameInformation` at `0x14001ee3e`
- `FLTMGR!FltGetFileNameInformation` at `0x14001e8c5`
- `FLTMGR!FltGetFileNameInformation` at `0x14001e8c5`

## string_xrefs

- `0x14001eb92`: `PATH: %s%wZ%wZ%wZ%wZ, PROCESS: %wZ`
- `0x14001ec6e`: `PATH: %s%wZ%wZ%wZ%wZ, Target PATH: %s%wZ%wZ%wZ%wZ, PROCESS: %wZ`
- `0x14001ed3f`: `Log delete attempted; will deny. PATH: %wZ, PROCESS: %wZ`
- `0x14001ed76`: `Log move requested. PATH: %wZ, Target PATH: %wZ, PROCESS: %wZ`
- `0x14001eda9`: `WinSetupMon::HandleOperation: PreLogMove failed for %wZ -> %wZ (0x%08X)`
- `0x14001ee8f`: `WinSetupMon::HandleOperation: PostLogMove failed for %wZ (0x%08X)`

## pseudocode

```c
void __fastcall HandleOperation(
        struct _FLT_CALLBACK_DATA *a1,
        struct _UNICODE_STRING *a2,
        char a3,
        char a4,
        char a5,
        const struct _UNICODE_STRING *a6,
        __int64 a7)
{
  HANDLE CurrentProcessId; // rsi
  struct _UNICODE_STRING *v11; // rdi
  struct _UNICODE_STRING *v12; // r15
  PVOID EaBuffer; // r13
  int v14; // ebx
  NTSTATUS DestinationFileNameInformation; // eax
  const wchar_t *v16; // rdx
  __int64 v17; // rcx
  struct _UNICODE_STRING *v18; // rsi
  unsigned int *v19; // r9
  int v20; // eax
  int ProcessInfo; // eax
  unsigned __int8 v22; // al
  unsigned __int16 Length; // dx
  unsigned int v24; // edi
  UNICODE_STRING *p_Volume; // rcx
  unsigned __int16 MappedDosDrive; // ax
  void *v27; // rcx
  void *v28; // r9
  void *p_Share; // rdx
  void *v30; // r10
  void *v31; // rcx
  void *v32; // r9
  unsigned int *v33; // r9
  int v34; // eax
  int v35; // eax
  NTSTATUS v36; // eax
  NTSTATUS v37; // eax
  int v38; // eax
  const wchar_t *v39; // rax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ebx
  void *FileNameLength; // [rsp+20h] [rbp-E0h]
  void *FileNameLengtha; // [rsp+20h] [rbp-E0h]
  ULONG FileNameLengthb[2]; // [rsp+20h] [rbp-E0h]
  char v47; // [rsp+70h] [rbp-90h]
  const struct _UNICODE_STRING *LogSessionId; // [rsp+78h] [rbp-88h] BYREF
  PFLT_FILE_NAME_INFORMATION RetFileNameInformation; // [rsp+80h] [rbp-80h] BYREF
  const struct _UNICODE_STRING *MappedProcessName; // [rsp+88h] [rbp-78h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-70h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING *v53; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING SourceString; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING FullName; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING *v56; // [rsp+D0h] [rbp-30h] BYREF
  PFLT_CALLBACK_DATA CallbackData; // [rsp+D8h] [rbp-28h]
  UNICODE_STRING *p_ParentDir; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v59[2]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD v60[2]; // [rsp+F8h] [rbp-8h] BYREF
  void *v61; // [rsp+100h] [rbp+0h] BYREF

  LogSessionId = a6;
  v56 = a2;
  CallbackData = a1;
  CurrentProcessId = PsGetCurrentProcessId();
  v11 = 0;
  v12 = 0;
  v53 = 0;
  if ( a5 )
    EaBuffer = a1->Iopb->Parameters.Create.EaBuffer;
  else
    EaBuffer = 0;
  v14 = 1;
  FileNameInformation = 0;
  FullName = 0;
  v60[0] = 1;
  SourceString = 0;
  RetFileNameInformation = 0;
  v47 = 0;
  if ( !LogSessionId )
    goto LABEL_77;
  P[1] = &qword_140012AB8;
  P[0] = (PVOID)0x20000;
  DestinationFileNameInformation = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    if ( DestinationFileNameInformation == -1073741766 || DestinationFileNameInformation == -2147483642 )
      goto LABEL_10;
    v16 = L"WinSetupMon::HandleOperation: Failed to get file information (0x%08X)";
    v17 = 2;
    goto LABEL_9;
  }
  DestinationFileNameInformation = FltParseFileNameInformation(FileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    v16 = L"WinSetupMon::HandleOperation: Failed to parse file information (0x%08X)";
LABEL_13:
    v17 = 3;
LABEL_9:
    WriteLogMessage(v17, v16, (unsigned int)DestinationFileNameInformation);
LABEL_10:
    v18 = (struct _UNICODE_STRING *)LogSessionId;
LABEL_87:
    if ( (unsigned int)(v14 - 2) <= 2 )
    {
      *(_OWORD *)v59 = 0;
      *(_OWORD *)P = 0;
      if ( (int)Duplicate(&FullName, (PUNICODE_STRING)v59) >= 0
        && (!SourceString.Length || (int)Duplicate(&SourceString, (PUNICODE_STRING)P) >= 0)
        && RemovePIIFromString((struct _UNICODE_STRING *)v59)
        && (!LOWORD(P[0]) || RemovePIIFromString((struct _UNICODE_STRING *)P))
        && (unsigned int)dword_140019000 > 4
        && (qword_140019010 & 0x800000000000LL) != 0
        && (qword_140019018 & 0x800000000000LL) == qword_140019018 )
      {
        if ( v14 )
        {
          switch ( v14 )
          {
            case 1:
              v39 = L"Log";
              break;
            case 2:
              v39 = L"ProtectLog";
              break;
            case 3:
              v39 = L"ProtectDeny";
              break;
            case 4:
              v39 = L"ProtectBugcheck";
              break;
            default:
              v39 = L"Unknown";
              break;
          }
        }
        else
        {
          v39 = L"Skip";
        }
        p_ParentDir = (UNICODE_STRING *)v39;
        v53 = (struct _UNICODE_STRING *)P;
        MappedProcessName = (const struct _UNICODE_STRING *)v59;
        v56 = v11;
        LogSessionId = GetLogSessionId();
        v61 = (void *)0x80000000LL;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>>(
          v40,
          (unsigned int)byte_14001792D,
          v41,
          v42,
          (__int64)&v61,
          (__int64)&LogSessionId,
          (__int64)&MappedProcessName,
          (__int64)&v53,
          (__int64)&v56,
          (__int64)&p_ParentDir);
      }
      if ( P[1] )
      {
        ExFreePoolWithTag(P[1], 0x6E6D7377u);
        P[1] = 0;
      }
      if ( v59[1] )
        ExFreePoolWithTag(v59[1], 0x6E6D7377u);
    }
    v43 = v14 - 3;
    if ( v43 )
    {
      if ( v43 == 1 )
      {
        KeWaitForSingleObject(&stru_1400197F8, Executive, 0, 0, 0);
        StopLoggingToFile(0);
        KeBugCheck(4u);
      }
    }
    else
    {
      CallbackData->IoStatus.Status = -1073741790;
      *(_DWORD *)&v18->Length = 4;
    }
    goto LABEL_117;
  }
  FullName.MaximumLength = FileNameInformation->Volume.Length
                         + FileNameInformation->Share.Length
                         + FileNameInformation->FinalComponent.Length
                         + FileNameInformation->ParentDir.Length;
  FullName.Length = FullName.MaximumLength;
  FullName.Buffer = FileNameInformation->Volume.Buffer;
  if ( EaBuffer )
  {
    DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                       (PFLT_INSTANCE)v56[1].Buffer,
                                       *(PFILE_OBJECT *)&v56[2].Length,
                                       *((HANDLE *)EaBuffer + 1),
                                       (PWSTR)EaBuffer + 10,
                                       *((_DWORD *)EaBuffer + 4),
                                       0x102u,
                                       &RetFileNameInformation);
    if ( DestinationFileNameInformation < 0 )
    {
      v16 = L"WinSetupMon::HandleOperation: FltGetDestinationFileNameInformation (1) failed (0x%08X)";
      goto LABEL_13;
    }
    DestinationFileNameInformation = FltParseFileNameInformation(RetFileNameInformation);
    if ( DestinationFileNameInformation < 0 )
    {
      v16 = L"WinSetupMon::HandleOperation: FltParseFileNameInformation (target) (1) failed (0x%08X)";
      goto LABEL_13;
    }
    SourceString.MaximumLength = RetFileNameInformation->Volume.Length
                               + RetFileNameInformation->Share.Length
                               + RetFileNameInformation->FinalComponent.Length
                               + RetFileNameInformation->ParentDir.Length;
    SourceString.Length = SourceString.MaximumLength;
    SourceString.Buffer = RetFileNameInformation->Volume.Buffer;
  }
  if ( byte_1400194C0 )
  {
    MappedProcessName = GetMappedProcessName((ULONG_PTR)CurrentProcessId);
    v11 = (struct _UNICODE_STRING *)MappedProcessName;
    if ( !MappedProcessName )
    {
      v20 = MapProcess(CurrentProcessId);
      if ( v20 < 0 )
      {
        WriteLogMessage(
          3,
          L"WinSetupMon::HandleOperation: MapProcess failed for %p (0x%08X)",
          CurrentProcessId,
          (unsigned int)v20);
        goto LABEL_10;
      }
      MappedProcessName = GetMappedProcessName((ULONG_PTR)CurrentProcessId);
      v11 = (struct _UNICODE_STRING *)MappedProcessName;
      if ( !MappedProcessName )
      {
        WriteLogMessage(
          3,
          L"WinSetupMon::HandleOperation: Failed to get mapped process name for process ID %p",
          CurrentProcessId);
        goto LABEL_10;
      }
    }
  }
  else
  {
    ProcessInfo = GetProcessInfo(CurrentProcessId, &v53, 0, v19, FileNameLength);
    if ( ProcessInfo < 0 )
    {
      WriteLogMessage(
        3,
        L"WinSetupMon::HandleOperation: GetProcessInfo failed for %p (0x%08X)",
        CurrentProcessId,
        (unsigned int)ProcessInfo);
      v12 = v53;
      goto LABEL_10;
    }
    v12 = v53;
    v11 = v53;
    MappedProcessName = v53;
  }
  v22 = IsPathTracked(&FullName, v11, (enum _TRACKING_MODE *)v60);
  v14 = v60[0];
  if ( !v22 )
    goto LABEL_70;
  Length = SourceString.Length;
  if ( v60[0] )
  {
    if ( v60[0] == 2 )
    {
      v24 = 8;
    }
    else if ( (unsigned int)(v60[0] - 3) < 2 )
    {
      v24 = 9;
    }
    else
    {
      v24 = (SourceString.Length != 0) + 6;
    }
  }
  else
  {
    v24 = 0;
  }
  if ( a4 && (unsigned int)(v60[0] - 2) <= 2 )
  {
    v14 = 1;
    v24 = 5;
  }
  if ( a3 && (unsigned int)(v14 - 2) <= 2 )
  {
    v14 = 1;
    v24 = 4;
LABEL_44:
    if ( v14 == 4 )
    {
      KeWaitForSingleObject(&stru_1400197F8, Executive, 0, 0, 0);
      Length = SourceString.Length;
      v47 = 1;
    }
    p_Volume = &FileNameInformation->Volume;
    if ( Length )
    {
      LOWORD(v60[0]) = GetMappedDosDrive(p_Volume);
      *(_DWORD *)((char *)v60 + 2) = 58;
      LOWORD(v61) = GetMappedDosDrive(&RetFileNameInformation->Volume);
      *(_DWORD *)((char *)&v61 + 2) = 58;
      p_ParentDir = &RetFileNameInformation->ParentDir;
      p_Share = P;
      if ( (_WORD)v61 )
      {
        v30 = P;
      }
      else
      {
        v30 = &RetFileNameInformation->Volume;
        if ( RetFileNameInformation->Share.Length )
          p_Share = &RetFileNameInformation->Share;
      }
      if ( !LOWORD(v60[0]) && (v31 = &FileNameInformation->Share, FileNameInformation->Share.Length)
        || (v31 = P, v32 = P, !LOWORD(v60[0])) )
      {
        v32 = &FileNameInformation->Volume;
      }
      WriteLogMessage(
        v24,
        L"PATH: %s%wZ%wZ%wZ%wZ, Target PATH: %s%wZ%wZ%wZ%wZ, PROCESS: %wZ",
        v60,
        v32,
        v31,
        &FileNameInformation->ParentDir,
        &FileNameInformation->FinalComponent,
        &v61,
        v30,
        p_Share,
        p_ParentDir,
        &RetFileNameInformation->FinalComponent,
        MappedProcessName);
    }
    else
    {
      MappedDosDrive = GetMappedDosDrive(p_Volume);
      v27 = P;
      LOWORD(v60[0]) = MappedDosDrive;
      *(_DWORD *)((char *)v60 + 2) = 58;
      if ( MappedDosDrive )
      {
        v28 = P;
      }
      else
      {
        v28 = &FileNameInformation->Volume;
        if ( FileNameInformation->Share.Length )
          v27 = &FileNameInformation->Share;
      }
      WriteLogMessage(
        v24,
        L"PATH: %s%wZ%wZ%wZ%wZ, PROCESS: %wZ",
        v60,
        v28,
        v27,
        &FileNameInformation->ParentDir,
        &FileNameInformation->FinalComponent,
        MappedProcessName);
    }
    if ( v14 == 4 )
    {
      WriteLogMessage(1, L"Logging process tree for bugcheck");
      do
      {
        v61 = 0;
        if ( v12 )
        {
          ExFreePoolWithTag(v12, 0x6E6D7377u);
          v53 = 0;
        }
        v34 = GetProcessInfo(CurrentProcessId, &v53, &v61, v33, FileNameLengtha);
        v12 = v53;
        if ( v34 >= 0 )
        {
          WriteLogMessage(1, L" |- %wZ", v53);
          CurrentProcessId = v61;
        }
      }
      while ( v12 );
      KeReleaseMutex(&stru_1400197F8, 0);
      v47 = 0;
    }
    goto LABEL_69;
  }
  if ( v24 )
    goto LABEL_44;
LABEL_69:
  v11 = (struct _UNICODE_STRING *)MappedProcessName;
LABEL_70:
  if ( !IsLogPathUnderPath(&FullName) )
  {
LABEL_77:
    v18 = (struct _UNICODE_STRING *)LogSessionId;
    goto LABEL_78;
  }
  if ( SourceString.Length )
  {
    WriteLogMessage(1, L"Log move requested. PATH: %wZ, Target PATH: %wZ, PROCESS: %wZ", &FullName, &SourceString, v11);
    v35 = PreLogMove(&FullName, &SourceString);
    if ( v35 < 0 )
    {
      FileNameLengthb[0] = v35;
      WriteLogMessage(
        3,
        L"WinSetupMon::HandleOperation: PreLogMove failed for %wZ -> %wZ (0x%08X)",
        &FullName,
        &SourceString,
        *(_QWORD *)FileNameLengthb);
      v18 = (struct _UNICODE_STRING *)LogSessionId;
      goto LABEL_87;
    }
    v18 = (struct _UNICODE_STRING *)LogSessionId;
    *(_DWORD *)&LogSessionId->Length = 0;
  }
  else
  {
    WriteLogMessage(2, L"Log delete attempted; will deny. PATH: %wZ, PROCESS: %wZ", &FullName, v11);
    v18 = (struct _UNICODE_STRING *)LogSessionId;
    CallbackData->IoStatus.Status = -1073741790;
    *(_DWORD *)&v18->Length = 4;
  }
LABEL_78:
  if ( a7 && EaBuffer )
  {
    v36 = FltGetDestinationFileNameInformation(
            (PFLT_INSTANCE)v56[1].Buffer,
            *(PFILE_OBJECT *)&v56[2].Length,
            *((HANDLE *)EaBuffer + 1),
            (PWSTR)EaBuffer + 10,
            *((_DWORD *)EaBuffer + 4),
            0x102u,
            &RetFileNameInformation);
    if ( v36 >= 0 )
    {
      v37 = FltParseFileNameInformation(RetFileNameInformation);
      if ( v37 >= 0 )
      {
        SourceString.MaximumLength = RetFileNameInformation->Volume.Length
                                   + RetFileNameInformation->Share.Length
                                   + RetFileNameInformation->FinalComponent.Length
                                   + RetFileNameInformation->ParentDir.Length;
        SourceString.Length = SourceString.MaximumLength;
        SourceString.Buffer = RetFileNameInformation->Volume.Buffer;
        v38 = PostLogMove(&SourceString);
        if ( v38 < 0 )
          WriteLogMessage(
            3,
            L"WinSetupMon::HandleOperation: PostLogMove failed for %wZ (0x%08X)",
            &SourceString,
            (unsigned int)v38);
      }
      else
      {
        WriteLogMessage(
          3,
          L"WinSetupMon::HandleOperation: FltParseFileNameInformation (target) (3) failed (0x%08X)",
          (unsigned int)v37);
      }
    }
    else
    {
      WriteLogMessage(
        3,
        L"WinSetupMon::HandleOperation: FltGetDestinationFileNameInformation (3) failed (0x%08X)",
        (unsigned int)v36);
    }
  }
  if ( v18 )
    goto LABEL_87;
LABEL_117:
  if ( v47 )
    KeReleaseMutex(&stru_1400197F8, 0);
  if ( RetFileNameInformation )
    FltReleaseFileNameInformation(RetFileNameInformation);
  if ( v12 )
    ExFreePoolWithTag(v12, 0x6E6D7377u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
}

```

## disassembly

```asm
0x14001e808  mov     [rsp-8+arg_10], rbx
0x14001e80d  push    rbp
0x14001e80e  push    rsi
0x14001e80f  push    rdi
0x14001e810  push    r12
0x14001e812  push    r13
0x14001e814  push    r14
0x14001e816  push    r15
0x14001e818  lea     rbp, [rsp-10h]
0x14001e81d  sub     rsp, 110h
0x14001e824  mov     rax, cs:__security_cookie
0x14001e82b  xor     rax, rsp
0x14001e82e  mov     [rbp+40h+var_38], rax
0x14001e832  mov     rax, [rbp+40h+arg_28]
0x14001e836  mov     r14b, r9b
0x14001e839  mov     [rsp+140h+var_C8], rax
0x14001e83e  mov     r12b, r8b
0x14001e841  mov     [rbp+40h+var_70], rdx
0x14001e845  mov     rbx, rcx
0x14001e848  mov     [rbp+40h+CallbackData], rcx
0x14001e84c  call    cs:__imp_PsGetCurrentProcessId
0x14001e853  nop     dword ptr [rax+rax+00h]
0x14001e858  xor     ecx, ecx
0x14001e85a  mov     rsi, rax
0x14001e85d  mov     edi, ecx
0x14001e85f  mov     r15d, ecx
0x14001e862  mov     [rbp+40h+var_98], rcx
0x14001e866  cmp     [rbp+40h+arg_20], cl
0x14001e869  jz      short loc_14001E875
0x14001e86b  mov     rax, [rbx+10h]
0x14001e86f  mov     r13, [rax+38h]
0x14001e873  jmp     short loc_14001E878
0x14001e875  mov     r13, rcx
0x14001e878  xorps   xmm0, xmm0
0x14001e87b  xorps   xmm1, xmm1
0x14001e87e  mov     ebx, 1
0x14001e883  mov     [rbp+40h+FileNameInformation], rcx
0x14001e887  movups  xmmword ptr [rbp+40h+FullName.Length], xmm0
0x14001e88b  mov     dword ptr [rbp+40h+var_48], ebx
0x14001e88e  movups  xmmword ptr [rbp+40h+SourceString.Length], xmm1
0x14001e892  mov     [rbp+40h+var_C0], rcx
0x14001e896  mov     [rsp+140h+var_D0], cl
0x14001e89a  cmp     [rsp+140h+var_C8], rcx
0x14001e89f  jz      loc_14001EDC9
0x14001e8a5  mov     rcx, [rbp+40h+CallbackData]; CallbackData
0x14001e8a9  lea     rax, qword_140012AB8
0x14001e8b0  lea     r8, [rbp+40h+FileNameInformation]; FileNameInformation
0x14001e8b4  mov     [rbp+40h+P+8], rax
0x14001e8b8  mov     edx, 101h; NameOptions
0x14001e8bd  mov     [rbp+40h+P], 20000h
0x14001e8c5  call    cs:__imp_FltGetFileNameInformation
0x14001e8cc  nop     dword ptr [rax+rax+00h]
0x14001e8d1  test    eax, eax
0x14001e8d3  jns     short loc_14001E902
0x14001e8d5  cmp     eax, 0C000003Ah
0x14001e8da  jz      short loc_14001E8F5
0x14001e8dc  cmp     eax, 80000006h
0x14001e8e1  jz      short loc_14001E8F5
0x14001e8e3  lea     rdx, aWinsetupmonHan_6; "WinSetupMon::HandleOperation: Failed to"...
0x14001e8ea  lea     ecx, [rbx+1]
0x14001e8ed  mov     r8d, eax
0x14001e8f0  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14001e8f5  mov     rsi, [rsp+140h+var_C8]
0x14001e8fa  xor     r14d, r14d
0x14001e8fd  jmp     loc_14001EEA9
0x14001e902  mov     rcx, [rbp+40h+FileNameInformation]; FileNameInformation
0x14001e906  call    cs:__imp_FltParseFileNameInformation
0x14001e90d  nop     dword ptr [rax+rax+00h]
0x14001e912  xor     r8d, r8d
0x14001e915  test    eax, eax
0x14001e917  jns     short loc_14001E927
0x14001e919  lea     rdx, aWinsetupmonHan_0; "WinSetupMon::HandleOperation: Failed to"...
0x14001e920  mov     ecx, 3
0x14001e925  jmp     short loc_14001E8ED
0x14001e927  mov     rdx, [rbp+40h+FileNameInformation]
0x14001e92b  movzx   ecx, word ptr [rdx+68h]
0x14001e92f  add     cx, [rdx+58h]
0x14001e933  add     cx, [rdx+28h]
0x14001e937  add     cx, [rdx+18h]
0x14001e93b  mov     [rbp+40h+FullName.MaximumLength], cx
0x14001e93f  mov     [rbp+40h+FullName.Length], cx
0x14001e943  mov     rax, [rdx+20h]
0x14001e947  mov     [rbp+40h+FullName.Buffer], rax
0x14001e94b  test    r13, r13
0x14001e94e  jz      loc_14001E9E1
0x14001e954  mov     r8, [r13+8]; RootDirectory
0x14001e958  lea     rax, [rbp+40h+var_C0]
0x14001e95c  mov     [rsp+140h+RetFileNameInformation], rax; RetFileNameInformation
0x14001e961  lea     r9, [r13+14h]; FileName
0x14001e965  mov     eax, [r13+10h]
0x14001e969  mov     [rsp+140h+NameOptions], 102h; NameOptions
0x14001e971  mov     [rsp+140h+FileNameLength], eax; ProcessHandle
0x14001e975  mov     rax, [rbp+40h+var_70]
0x14001e979  mov     rdx, [rax+20h]; FileObject
0x14001e97d  mov     rcx, [rax+18h]; Instance
0x14001e981  call    cs:__imp_FltGetDestinationFileNameInformation
0x14001e988  nop     dword ptr [rax+rax+00h]
0x14001e98d  test    eax, eax
0x14001e98f  jns     short loc_14001E99A
0x14001e991  lea     rdx, aWinsetupmonHan_2; "WinSetupMon::HandleOperation: FltGetDes"...
0x14001e998  jmp     short loc_14001E920
0x14001e99a  mov     rcx, [rbp+40h+var_C0]; FileNameInformation
0x14001e99e  call    cs:__imp_FltParseFileNameInformation
0x14001e9a5  nop     dword ptr [rax+rax+00h]
0x14001e9aa  xor     r8d, r8d
0x14001e9ad  test    eax, eax
0x14001e9af  jns     short loc_14001E9BD
0x14001e9b1  lea     rdx, aWinsetupmonHan_3; "WinSetupMon::HandleOperation: FltParseF"...
0x14001e9b8  jmp     loc_14001E920
0x14001e9bd  mov     rdx, [rbp+40h+var_C0]
0x14001e9c1  movzx   ecx, word ptr [rdx+68h]
0x14001e9c5  add     cx, [rdx+58h]
0x14001e9c9  add     cx, [rdx+28h]
0x14001e9cd  add     cx, [rdx+18h]
0x14001e9d1  mov     [rbp+40h+SourceString.MaximumLength], cx
0x14001e9d5  mov     [rbp+40h+SourceString.Length], cx
0x14001e9d9  mov     rax, [rdx+20h]
0x14001e9dd  mov     [rbp+40h+SourceString.Buffer], rax
0x14001e9e1  cmp     cs:byte_1400194C0, r8b
0x14001e9e8  mov     rcx, rsi; void *
0x14001e9eb  jz      short loc_14001EA53
0x14001e9ed  call    ?GetMappedProcessName@@YAPEBU_UNICODE_STRING@@PEAX@Z; GetMappedProcessName(void *)
0x14001e9f2  mov     [rbp+40h+var_B8], rax
0x14001e9f6  mov     rdi, rax
0x14001e9f9  test    rax, rax
0x14001e9fc  jnz     loc_14001EA8E
0x14001ea02  mov     rcx, rsi; void *
0x14001ea05  call    ?MapProcess@@YAJPEAX@Z; MapProcess(void *)
0x14001ea0a  test    eax, eax
0x14001ea0c  jns     short loc_14001EA28
0x14001ea0e  mov     r9d, eax
0x14001ea11  lea     rdx, aWinsetupmonHan_4; "WinSetupMon::HandleOperation: MapProces"...
0x14001ea18  mov     r8, rsi
0x14001ea1b  lea     ecx, [rdi+3]
0x14001ea1e  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14001ea23  jmp     loc_14001E8F5
0x14001ea28  mov     rcx, rsi; Signature
0x14001ea2b  call    ?GetMappedProcessName@@YAPEBU_UNICODE_STRING@@PEAX@Z; GetMappedProcessName(void *)
0x14001ea30  mov     [rbp+40h+var_B8], rax
0x14001ea34  mov     rdi, rax
0x14001ea37  test    rax, rax
0x14001ea3a  jnz     short loc_14001EA8E
0x14001ea3c  mov     r8, rsi
0x14001ea3f  lea     rdx, aWinsetupmonHan_9; "WinSetupMon::HandleOperation: Failed to"...
0x14001ea46  lea     ecx, [rax+3]
0x14001ea49  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14001ea4e  jmp     loc_14001E8F5
0x14001ea53  xor     r8d, r8d; void **
0x14001ea56  lea     rdx, [rbp+40h+var_98]; struct _UNICODE_STRING **
0x14001ea5a  call    ?GetProcessInfo@@YAJPEAXPEAPEAU_UNICODE_STRING@@PEAPEAXPEAKPEAE@Z; GetProcessInfo(void *,_UNICODE_STRING * *,void * *,ulong *,uchar *)
0x14001ea5f  test    eax, eax
0x14001ea61  jns     short loc_14001EA83
0x14001ea63  mov     r9d, eax
0x14001ea66  lea     rdx, aWinsetupmonHan; "WinSetupMon::HandleOperation: GetProces"...
0x14001ea6d  mov     r8, rsi
0x14001ea70  mov     ecx, 3
0x14001ea75  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14001ea7a  mov     r15, [rbp+40h+var_98]
0x14001ea7e  jmp     loc_14001E8F5
0x14001ea83  mov     r15, [rbp+40h+var_98]
0x14001ea87  mov     rdi, r15
0x14001ea8a  mov     [rbp+40h+var_B8], r15
0x14001ea8e  lea     r8, [rbp+40h+var_48]; enum _TRACKING_MODE *
0x14001ea92  mov     rdx, rdi; String2
0x14001ea95  lea     rcx, [rbp+40h+FullName]; FullName
0x14001ea99  call    ?IsPathTracked@@YAEPEBU_UNICODE_STRING@@0PEAW4_TRACKING_MODE@@@Z; IsPathTracked(_UNICODE_STRING const *,_UNICODE_STRING const *,_TRACKING_MODE *)
0x14001ea9e  mov     ebx, dword ptr [rbp+40h+var_48]
0x14001eaa1  xor     r8d, r8d; WaitMode
0x14001eaa4  test    al, al
0x14001eaa6  jz      loc_14001ED68
0x14001eaac  movzx   edx, [rbp+40h+SourceString.Length]
0x14001eab0  mov     ecx, ebx
0x14001eab2  test    ebx, ebx
0x14001eab4  jz      short loc_14001EAE2
0x14001eab6  sub     ecx, 2
0x14001eab9  jz      short loc_14001EADB
0x14001eabb  sub     ecx, 1
0x14001eabe  jz      short loc_14001EAD4
0x14001eac0  cmp     ecx, 1
0x14001eac3  jz      short loc_14001EAD4
0x14001eac5  test    dx, dx
0x14001eac8  mov     edi, r8d
0x14001eacb  setnz   dil
0x14001eacf  add     edi, 6
0x14001ead2  jmp     short loc_14001EAE5
0x14001ead4  mov     edi, 9
0x14001ead9  jmp     short loc_14001EAE5
0x14001eadb  mov     edi, 8
0x14001eae0  jmp     short loc_14001EAE5
0x14001eae2  mov     edi, r8d
0x14001eae5  test    r14b, r14b
0x14001eae8  jz      short loc_14001EAFA
0x14001eaea  lea     eax, [rbx-2]
0x14001eaed  cmp     eax, 2
0x14001eaf0  ja      short loc_14001EAFA
0x14001eaf2  mov     ebx, 1
0x14001eaf7  lea     edi, [rbx+4]
0x14001eafa  xor     r14d, r14d
0x14001eafd  test    r12b, r12b
0x14001eb00  jz      short loc_14001EB13
0x14001eb02  lea     eax, [rbx-2]
0x14001eb05  cmp     eax, 2
0x14001eb08  ja      short loc_14001EB13
0x14001eb0a  lea     ebx, [r14+1]
0x14001eb0e  lea     edi, [rbx+3]
0x14001eb11  jmp     short loc_14001EB1B
0x14001eb13  test    edi, edi
0x14001eb15  jz      loc_14001ED1C
0x14001eb1b  cmp     ebx, 4
0x14001eb1e  jnz     short loc_14001EB46
0x14001eb20  xor     r9d, r9d; Alertable
0x14001eb23  mov     qword ptr [rsp+140h+FileNameLength], r14; Timeout
0x14001eb28  xor     edx, edx; WaitReason
0x14001eb2a  lea     rcx, stru_1400197F8; Object
0x14001eb31  call    cs:__imp_KeWaitForSingleObject
0x14001eb38  nop     dword ptr [rax+rax+00h]
0x14001eb3d  movzx   edx, [rbp+40h+SourceString.Length]
0x14001eb41  mov     [rsp+140h+var_D0], 1
0x14001eb46  mov     rcx, [rbp+40h+FileNameInformation]
0x14001eb4a  add     rcx, 18h; String1
0x14001eb4e  test    dx, dx
0x14001eb51  jnz     short loc_14001EBBD
0x14001eb53  call    ?GetMappedDosDrive@@YAGPEBU_UNICODE_STRING@@@Z; GetMappedDosDrive(_UNICODE_STRING const *)
0x14001eb58  mov     rdx, [rbp+40h+FileNameInformation]
0x14001eb5c  lea     rcx, [rbp+40h+P]
0x14001eb60  mov     word ptr [rbp+40h+var_48], ax
0x14001eb64  mov     dword ptr [rbp+40h+var_48+2], 3Ah ; ':'
0x14001eb6b  lea     r8, [rdx+58h]
0x14001eb6f  lea     r10, [rdx+68h]
0x14001eb73  test    ax, ax
0x14001eb76  jz      short loc_14001EB7E
0x14001eb78  lea     r9, [rbp+40h+P]
0x14001eb7c  jmp     short loc_14001EB8E
0x14001eb7e  lea     rax, [rdx+28h]
0x14001eb82  cmp     [rax], r14w
0x14001eb86  lea     r9, [rdx+18h]
0x14001eb8a  cmova   rcx, rax
0x14001eb8e  mov     rax, [rbp+40h+var_B8]
0x14001eb92  lea     rdx, aPathSWzWzWzWzP; "PATH: %s%wZ%wZ%wZ%wZ, PROCESS: %wZ"
0x14001eb99  mov     [rsp+140h+var_108], rax
0x14001eb9e  mov     [rsp+140h+RetFileNameInformation], r8
0x14001eba3  lea     r8, [rbp+40h+var_48]
0x14001eba7  mov     qword ptr [rsp+140h+NameOptions], r10
0x14001ebac  mov     qword ptr [rsp+140h+FileNameLength], rcx
0x14001ebb1  mov     ecx, edi
0x14001ebb3  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14001ebb8  jmp     loc_14001EC98
0x14001ebbd  call    ?GetMappedDosDrive@@YAGPEBU_UNICODE_STRING@@@Z; GetMappedDosDrive(_UNICODE_STRING const *)
0x14001ebc2  mov     rcx, [rbp+40h+var_C0]
0x14001ebc6  add     rcx, 18h; String1
0x14001ebca  mov     word ptr [rbp+40h+var_48], ax
0x14001ebce  mov     dword ptr [rbp+40h+var_48+2], 3Ah ; ':'
0x14001ebd5  call    ?GetMappedDosDrive@@YAGPEBU_UNICODE_STRING@@@Z; GetMappedDosDrive(_UNICODE_STRING const *)
0x14001ebda  mov     rcx, [rbp+40h+var_C0]
0x14001ebde  xor     r9d, r9d
0x14001ebe1  mov     word ptr [rbp+40h+var_40], ax
0x14001ebe5  mov     dword ptr [rbp+40h+var_40+2], 3Ah ; ':'
0x14001ebec  lea     rdx, [rcx+68h]
0x14001ebf0  mov     [rbp+40h+var_60], rdx
0x14001ebf4  lea     rdx, [rbp+40h+P]
0x14001ebf8  lea     r12, [rcx+58h]
0x14001ebfc  test    ax, ax
0x14001ebff  jz      short loc_14001EC07
0x14001ec01  lea     r10, [rbp+40h+P]
0x14001ec05  jmp     short loc_14001EC17
0x14001ec07  lea     rax, [rcx+28h]
0x14001ec0b  cmp     [rax], r9w
0x14001ec0f  lea     r10, [rcx+18h]
0x14001ec13  cmova   rdx, rax
0x14001ec17  mov     rax, [rbp+40h+FileNameInformation]
0x14001ec1b  movzx   r8d, word ptr [rbp+40h+var_48]
0x14001ec20  lea     r11, [rax+58h]
0x14001ec24  lea     r14, [rax+68h]
0x14001ec28  test    r8w, r8w
0x14001ec2c  jnz     short loc_14001EC38
0x14001ec2e  lea     rcx, [rax+28h]
0x14001ec32  cmp     [rcx], r9w
0x14001ec36  ja      short loc_14001EC46
0x14001ec38  lea     rcx, [rbp+40h+P]
0x14001ec3c  lea     r9, [rbp+40h+P]
0x14001ec40  test    r8w, r8w
0x14001ec44  jnz     short loc_14001EC4A
0x14001ec46  lea     r9, [rax+18h]
0x14001ec4a  mov     rax, [rbp+40h+var_B8]
0x14001ec4e  lea     r8, [rbp+40h+var_48]
0x14001ec52  mov     [rsp+140h+var_E0], rax
0x14001ec57  mov     rax, [rbp+40h+var_60]
0x14001ec5b  mov     [rsp+140h+var_E8], r12
0x14001ec60  mov     [rsp+140h+var_F0], rax
0x14001ec65  lea     rax, [rbp+40h+var_40]
0x14001ec69  mov     [rsp+140h+var_F8], rdx
0x14001ec6e  lea     rdx, aPathSWzWzWzWzT; "PATH: %s%wZ%wZ%wZ%wZ, Target PATH: %s%w"...
0x14001ec75  mov     [rsp+140h+var_100], r10
0x14001ec7a  mov     [rsp+140h+var_108], rax
0x14001ec7f  mov     [rsp+140h+RetFileNameInformation], r11
0x14001ec84  mov     qword ptr [rsp+140h+NameOptions], r14
0x14001ec89  mov     qword ptr [rsp+140h+FileNameLength], rcx; ProcessHandle
0x14001ec8e  mov     ecx, edi
0x14001ec90  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14001ec95  xor     r14d, r14d
  ... truncated ...
```
