# MpDlpCheckFileAccess

- ea: `0x1400408b0`
- end: `0x1400425de`
- name: `MpDlpCheckFileAccess`
- size: `7470`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64, __int64, __int64, size_t Size, __int64, __int64)`
- caller_count: `4`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140002080`
- `0x14003f700`
- `0x14003fe70`
- `0x140047ad0`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x1400026c0`
- `0x140003950`
- `0x140003c70`
- `0x140004654`
- `0x140004be4`
- `0x1400051bc`
- `0x140010194`
- `0x140011890`
- `0x1400118d0`
- `0x140011900`
- `0x140038710`
- `0x1400408b0`
- `0x1400425e0`
- `0x140042be0`
- `0x140043190`
- `0x1400434e8`
- `0x140043ed0`
- `0x1400444b0`
- `0x140048140`
- `0x140048908`
- `0x140054230`
- `0x140054ad0`
- `0x1400732c0`
- `0x140086418`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140041061`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140041061`
- `ntoskrnl!KeQueryPriorityThread` at `0x140040de4`
- `ntoskrnl!KeQueryPriorityThread` at `0x140040de4`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400410ac`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400410ac`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140041024`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140041024`
- `ntoskrnl!_stricmp` at `0x140040c84`
- `ntoskrnl!_stricmp` at `0x140041620`
- `ntoskrnl!_stricmp` at `0x1400416b5`
- `ntoskrnl!_stricmp` at `0x140040c84`
- `ntoskrnl!_stricmp` at `0x140041620`
- `ntoskrnl!_stricmp` at `0x1400416b5`
- `ntoskrnl!SeTokenObjectType` at `0x140041030`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400413c0`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400413c0`
- `ntoskrnl!PsInitialSystemProcess` at `0x140040aa3`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x140040c55`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x1400415e9`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x140041681`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x140040c55`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x1400415e9`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x140041681`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400409e8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400409e8`
- `ntoskrnl!IoThreadToProcess` at `0x140040a51`
- `ntoskrnl!IoThreadToProcess` at `0x140040a7d`
- `ntoskrnl!IoThreadToProcess` at `0x140040a51`
- `ntoskrnl!IoThreadToProcess` at `0x140040a7d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400412eb`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140041314`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400412eb`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140041314`
- `ntoskrnl!ZwClose` at `0x140041098`
- `ntoskrnl!ZwClose` at `0x140041098`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400415b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f68`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400415b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f68`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140041a09`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140041a09`
- `FLTMGR!FltReleaseContext` at `0x140041439`
- `FLTMGR!FltReleaseContext` at `0x1400414b9`
- `FLTMGR!FltReleaseContext` at `0x140041439`
- `FLTMGR!FltReleaseContext` at `0x1400414b9`
- `FLTMGR!FltGetFileNameInformation` at `0x140040b8a`
- `FLTMGR!FltGetFileNameInformation` at `0x140041362`
- `FLTMGR!FltGetFileNameInformation` at `0x140041801`
- `FLTMGR!FltGetFileNameInformation` at `0x1400419cf`
- `FLTMGR!FltGetFileNameInformation` at `0x1400421a4`
- `FLTMGR!FltGetFileNameInformation` at `0x140040b8a`
- `FLTMGR!FltGetFileNameInformation` at `0x140041362`
- `FLTMGR!FltGetFileNameInformation` at `0x140041801`
- `FLTMGR!FltGetFileNameInformation` at `0x1400419cf`
- `FLTMGR!FltGetFileNameInformation` at `0x1400421a4`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400413ed`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400413ed`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140040dc7`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140040dc7`
- `FLTMGR!FltGetStreamContext` at `0x14004189b`
- `FLTMGR!FltGetStreamContext` at `0x14004189b`
- `FLTMGR!FltParseFileName` at `0x140040d05`
- `FLTMGR!FltParseFileName` at `0x140040d05`
- `FLTMGR!FltGetFileSystemType` at `0x140040b21`
- `FLTMGR!FltGetFileSystemType` at `0x140040b21`
- `FLTMGR!FltParseFileNameInformation` at `0x14004171e`
- `FLTMGR!FltParseFileNameInformation` at `0x14004171e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140041476`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004254f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140041476`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004254f`

## pseudocode

```c
__int64 __fastcall MpDlpCheckFileAccess(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        void *a6,
        __int64 a7,
        size_t Size,
        void *a9,
        __int64 a10)
{
  __int64 v12; // rbx
  PFLT_FILE_NAME_INFORMATION v13; // r13
  _OWORD *v14; // r12
  struct _KPROCESS *v16; // rdi
  struct _KPROCESS *v17; // rdi
  __int64 v18; // rcx
  struct _KPROCESS *RequestorProcess; // rdx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  UCHAR MajorFunction; // dl
  _QWORD *v23; // rdx
  __int64 v24; // rdi
  int v25; // edi
  bool v26; // cl
  FLT_FILE_NAME_OPTIONS v27; // edx
  NTSTATUS v28; // ecx
  __int64 v29; // rdx
  unsigned __int64 v30; // r8
  ULONG v31; // r12d
  char v32; // di
  char v33; // di
  const char *i; // rcx
  __int64 v35; // rax
  char v36; // r12
  ULONG v37; // edx
  NTSTATUS v38; // eax
  unsigned int v39; // ecx
  unsigned int v40; // edi
  __int64 PoolWithTag; // rax
  __int64 v42; // rdx
  struct _FILE_OBJECT *v43; // rdx
  NTSTATUS v44; // eax
  ULONG PriorityThread; // eax
  IO_PRIORITY_HINT IoPriority; // ecx
  UCHAR v47; // cl
  int v48; // eax
  __int64 v49; // rdi
  __int64 v50; // rdi
  int v51; // eax
  __int64 v52; // rdi
  struct _KPROCESS *v53; // rax
  PACCESS_TOKEN v54; // rdi
  NTSTATUS v55; // r12d
  volatile signed __int32 *v56; // rax
  char v57; // di
  volatile signed __int32 *v58; // rax
  char v59; // r12
  const UNICODE_STRING *v60; // rcx
  int v61; // eax
  PFLT_CONTEXT v62; // r8
  int v63; // eax
  int v64; // r8d
  char v65; // cl
  FLT_FILE_NAME_OPTIONS v66; // edx
  NTSTATUS v67; // ecx
  int v68; // eax
  PFLT_IO_PARAMETER_BLOCK v69; // rax
  __int64 v70; // rax
  ULONG v71; // ecx
  const char *j; // rdx
  __int64 v73; // rax
  ULONG v74; // ecx
  const char *k; // rdx
  __int64 v76; // rax
  volatile signed __int32 *v77; // rax
  int StreamContext; // r8d
  __int64 v79; // rdx
  unsigned int *v80; // r12
  int v81; // eax
  union _SLIST_HEADER *v82; // rcx
  int v83; // eax
  bool v84; // zf
  volatile signed __int32 *v85; // rax
  __int64 v86; // r12
  int v87; // eax
  int v88; // eax
  PFLT_IO_PARAMETER_BLOCK v89; // rax
  NTSTATUS v90; // eax
  unsigned int *v91; // r12
  unsigned int *v92; // r12
  __int64 v93; // rdx
  int ObjectType; // [rsp+20h] [rbp-E0h]
  char v95; // [rsp+50h] [rbp-B0h] BYREF
  char v96; // [rsp+51h] [rbp-AFh]
  char v97; // [rsp+52h] [rbp-AEh]
  char v98; // [rsp+53h] [rbp-ADh] BYREF
  char v99; // [rsp+54h] [rbp-ACh]
  int v100; // [rsp+58h] [rbp-A8h]
  ULONG EaLength[4]; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v102; // [rsp+70h] [rbp-90h]
  unsigned int v103; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int *v104; // [rsp+78h] [rbp-88h]
  unsigned int *v105; // [rsp+80h] [rbp-80h]
  __int64 v106; // [rsp+88h] [rbp-78h]
  __int64 v107; // [rsp+90h] [rbp-70h]
  PSLIST_ENTRY ListEntry; // [rsp+98h] [rbp-68h] BYREF
  PFLT_CONTEXT v109; // [rsp+A0h] [rbp-60h]
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT v111; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_FILE_NAME_INFORMATION v112; // [rsp+B8h] [rbp-48h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE Src; // [rsp+C8h] [rbp-38h] BYREF
  PFLT_FILE_NAME_INFORMATION v115; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v116; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+E8h] [rbp-18h] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+F8h] [rbp-8h] BYREF
  ULONG ErrorOffset; // [rsp+FCh] [rbp-4h] BYREF
  ULONG v120; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_PRIORITY_INFO PriorityInfo; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v122[7]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v123; // [rsp+190h] [rbp+90h]
  unsigned int *v124; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v125; // [rsp+1A8h] [rbp+A8h]
  UNICODE_STRING v126; // [rsp+1B0h] [rbp+B0h] BYREF
  int v127; // [rsp+1C0h] [rbp+C0h]
  int v128; // [rsp+1C4h] [rbp+C4h]
  int v129; // [rsp+1C8h] [rbp+C8h]
  unsigned int **v130; // [rsp+1D0h] [rbp+D0h]

  v106 = a2;
  v107 = a7;
  Src = a9;
  v12 = 0;
  v13 = 0;
  *(_QWORD *)&v116 = a10;
  v14 = 0;
  v100 = a4;
  v109 = a6;
  v104 = 0;
  v124 = 0;
  v105 = 0;
  v99 = 0;
  v97 = 0;
  v96 = 0;
  v103 = 0;
  v123 = 0;
  Context = a6;
  v111 = 0;
  v98 = 0;
  ListEntry = 0;
  v95 = 0;
  LOBYTE(v102) = 0;
  v112 = 0;
  *(_OWORD *)EaLength = 0;
  memset(v122, 0, sizeof(v122));
  FinalComponent = 0;
  if ( !CallbackData )
    return 0;
  if ( !a2 )
    return 0;
  if ( !a3 )
    return 0;
  *(_QWORD *)&PriorityInfo.Size = CallbackData;
  FileNameInformation = (PFLT_FILE_NAME_INFORMATION)IoGetCurrentProcess();
  if ( !MpDlpData )
    return 0;
  if ( (unsigned __int64)(&CallbackData[-1].RequestorMode + 7) <= 1 )
    *(_QWORD *)&PriorityInfo.Size = 0;
  if ( !*((_BYTE *)MpDlpData + 32)
    || (*(_DWORD *)(MpData + 864) & 0x400) == 0
    || !*(_QWORD *)(MpData + 320) && !*(_QWORD *)(MpData + 336) )
  {
    return 0;
  }
  v16 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v16
    || (v17 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v17) )
  {
    if ( (unsigned __int64)(&CallbackData[-1].RequestorMode + 7) <= 1 )
      goto LABEL_20;
    return 0;
  }
  v18 = *(_QWORD *)&PriorityInfo.Size;
  if ( !*(_QWORD *)&PriorityInfo.Size )
  {
    RequestorProcess = (struct _KPROCESS *)FileNameInformation;
    goto LABEL_15;
  }
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(*(_QWORD *)&PriorityInfo.Size);
  if ( !RequestorProcess )
    return 0;
  v18 = *(_QWORD *)&PriorityInfo.Size;
LABEL_15:
  if ( PsInitialSystemProcess == RequestorProcess
    && !(unsigned __int8)MpIsPotentialRemoteOpen(v18)
    && CallbackData != (PFLT_CALLBACK_DATA)2 )
  {
    return 0;
  }
  if ( (*(_DWORD *)(a3 + 56) & 0x40000000) != 0 || *(_DWORD *)(a3 + 240) == 33 )
    return 0;
LABEL_20:
  Iopb = CallbackData->Iopb;
  MajorFunction = Iopb->MajorFunction;
  if ( !MajorFunction && (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 0x20) != 0 )
    return 0;
  if ( !(_DWORD)Size || !Src )
  {
    if ( !MajorFunction && (v100 & 0x10) != 0 && v107 && *(_QWORD *)(v107 + 8) )
    {
      v23 = Context;
    }
    else
    {
      v23 = Context;
      if ( !Context || !*((_QWORD *)Context + 10) || (*((_DWORD *)Context + 10) & 0x80u) == 0 )
      {
        v24 = v106;
        FileSystemType = FLT_FSTYPE_UNKNOWN;
        FltGetFileSystemType(*(PVOID *)(v106 + 24), &FileSystemType);
        if ( FileSystemType == FLT_FSTYPE_MUP
          && (v95 = 0, (int)MpIsLoopbackByObj(v106, 0, &v95) >= 0)
          && !v95
          && *((_BYTE *)MpDlpData + 241) )
        {
          if ( *(_QWORD *)(MpData + 160) )
          {
            ErrorOffset = 0x4000;
            FileNameInformation = (PFLT_FILE_NAME_INFORMATION)MpAllocatePoolWithTag(1, 0x4000, 1634029645);
            if ( FileNameInformation )
            {
              v25 = (*(__int64 (__fastcall **)(_QWORD, PFLT_FILE_NAME_INFORMATION, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, char, ULONG *))(MpData + 160))(
                      *(_QWORD *)(v24 + 32),
                      FileNameInformation,
                      ErrorOffset,
                      0,
                      0,
                      0,
                      0,
                      1,
                      &ErrorOffset);
              if ( v25 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  _mm_lfence();
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    87,
                    WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                    KeGetCurrentThread(),
                    v25);
                }
                ExFreePoolWithTag(FileNameInformation, 0x6165504Du);
              }
              else
              {
                *(_QWORD *)&EaLength[2] = FileNameInformation;
                v25 = 0;
                EaLength[0] = ErrorOffset;
                v98 = 1;
              }
            }
            else
            {
              v25 = -1073741670;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  86,
                  WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                  KeGetCurrentThread(),
                  -1073741670);
              }
            }
          }
          else
          {
            v25 = -1073741637;
          }
        }
        else
        {
          v25 = MpDlpQueryEa(CallbackData, *(_QWORD *)(v24 + 24), *(_QWORD *)(v24 + 32), EaLength, &v98);
        }
        v26 = v102;
LABEL_27:
        if ( v25 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
            KeGetCurrentThread(),
            v25);
          v26 = v102;
        }
        if ( v26 )
        {
          *(_OWORD *)((char *)v122 + 8) = *v14;
          v13 = (PFLT_FILE_NAME_INFORMATION)v122;
          if ( (int)MpParseFileName(v14, 0, (char *)&v122[3] + 8, (char *)&v122[4] + 8, (char *)&v122[5] + 8) < 0 )
            v13 = 0;
        }
        else
        {
          v27 = 513;
          FileNameInformation = 0;
          if ( !byte_1400269F8 && (v100 & 0x11) == 0 )
            v27 = 257;
          v28 = FltGetFileNameInformation(CallbackData, v27, &FileNameInformation);
          if ( v28 < 0 )
          {
            _mm_lfence();
            v28 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
          }
          if ( FileNameInformation )
            v13 = FileNameInformation;
          if ( v28 < 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_102;
            }
            v79 = 27;
            ObjectType = v28;
            goto LABEL_409;
          }
        }
        FileSystemType = FLT_FSTYPE_UNKNOWN;
        if ( a5 )
        {
          v29 = *(unsigned int *)(a5 + 184);
        }
        else if ( FltParseFileNameInformation(v13) >= 0 )
        {
          _mm_lfence();
          if ( (int)MpGetFileExtensionId(&v13->Extension) < 0 )
            v29 = 0;
          else
            v29 = (unsigned int)FileSystemType;
        }
        else
        {
          v29 = 0;
        }
        v30 = 0x140000000uLL;
        if ( *((_BYTE *)MpDlpData + 267) )
        {
LABEL_38:
          v31 = EaLength[0];
        }
        else
        {
          if ( (_DWORD)v29 != 51 )
          {
            switch ( (int)v29 )
            {
              case 1:
              case 37:
              case 44:
              case 45:
              case 46:
              case 47:
              case 48:
              case 49:
              case 50:
              case 52:
              case 53:
                break;
              default:
                goto LABEL_38;
            }
          }
          v31 = EaLength[0];
          if ( !EaLength[0] )
            goto LABEL_102;
        }
        v32 = 0;
        if ( *(int *)(MpData + 868) < 0 )
          v32 = *((_BYTE *)MpDlpData + 264);
        if ( (_DWORD)v29 == 36 )
        {
LABEL_44:
          if ( (unsigned __int8)MpIsOfficeApplication(a3, v29, 0x140000000uLL)
            || *(_DWORD *)(a3 + 240) == 16
            || (unsigned __int8)MpIsCloudSyncType(a3)
            || v32 )
          {
LABEL_45:
            v33 = 1;
            goto LABEL_46;
          }
        }
        else
        {
          v29 = (unsigned int)(v29 - 2);
          switch ( (int)v29 )
          {
            case 0:
              v83 = *(_DWORD *)(a3 + 240);
              if ( v83 == 5 || ((v83 - 4) & 0xFFFFFFFD) == 0 )
                goto LABEL_45;
              v84 = v32 == 0;
              break;
            case 2:
            case 3:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 9:
            case 10:
            case 11:
            case 12:
            case 13:
            case 14:
            case 15:
            case 16:
            case 17:
            case 18:
            case 19:
            case 20:
            case 21:
            case 22:
            case 23:
            case 24:
            case 25:
            case 26:
            case 28:
            case 29:
            case 30:
              goto LABEL_44;
            case 27:
              if ( (unsigned __int8)MpIsOfficeApplication(a3, v29, 0x140000000uLL) )
                goto LABEL_45;
              v87 = *(_DWORD *)(a3 + 240);
              if ( v87 == 10 )
                goto LABEL_45;
              if ( v87 == 16 )
                goto LABEL_45;
              if ( (unsigned __int8)MpIsCloudSyncType(a3) )
                goto LABEL_45;
              v88 = *(_DWORD *)(a3 + 240);
              if ( v88 == 13 || v88 == 14 )
                goto LABEL_45;
              goto LABEL_43;
            case 36:
            case 37:
            case 38:
            case 39:
            case 40:
            case 41:
              if ( *(_DWORD *)(a3 + 240) == 16 )
                goto LABEL_45;
              v84 = (unsigned __int8)MpIsCloudSyncType(a3) == 0;
              break;
            default:
              goto LABEL_43;
          }
          if ( !v84 )
            goto LABEL_45;
        }
LABEL_43:
        v33 = 0;
LABEL_46:
        v95 = v33;
        if ( v31 )
        {
          FileSystemType = FLT_FSTYPE_UNKNOWN;
          if ( *(_QWORD *)&EaLength[2] )
          {
            if ( IoCheckEaBufferValidity(*(PFILE_FULL_EA_INFORMATION *)&EaLength[2], v31, (PULONG)&FileSystemType) < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  108,
                  WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                  KeGetCurrentThread(),
                  FileSystemType);
              }
            }
            else
            {
              for ( i = *(const char **)&EaLength[2]; ; i = (char *)v104 + v35 )
              {
                v104 = (unsigned int *)i;
                if ( v31 < 0xC )
                  break;
                if ( !_stricmp(i + 8, "$Kernel.SEC.EndpointDlp") )
                {
                  if ( !v104 )
                    goto LABEL_54;
                  v36 = 1;
                  v99 = 1;
                  goto LABEL_55;
                }
                v35 = *v104;
                if ( !(_DWORD)v35 )
                  break;
                v31 -= v35;
              }
            }
          }
          v104 = 0;
LABEL_54:
          v36 = 0;
          v99 = 0;
        }
        else
        {
          if ( !v33 && !*((_BYTE *)MpDlpData + 265) && !*((_BYTE *)MpDlpData + 266) )
            goto LABEL_102;
          v36 = 0;
        }
LABEL_55:
        v37 = EaLength[0];
        if ( *((_BYTE *)MpDlpData + 266) && EaLength[0] )
        {
          ErrorOffset = 0;
          if ( *(_QWORD *)&EaLength[2] )
          {
            if ( IoCheckEaBufferValidity(*(PFILE_FULL_EA_INFORMATION *)&EaLength[2], EaLength[0], &ErrorOffset) < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  108,
                  WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                  KeGetCurrentThread(),
                  ErrorOffset);
              }
            }
            else
            {
              v71 = EaLength[0];
              for ( j = *(const char **)&EaLength[2]; ; j = (char *)v124 + v73 )
              {
                v124 = (unsigned int *)j;
                v120 = v71;
                if ( v71 < 0xC )
                  break;
                if ( !_stricmp(j + 8, "$Kernel.SEC.MarkOfWeb") )
                {
                  if ( !v124 )
                    goto LABEL_191;
                  v37 = EaLength[0];
                  v97 = 1;
                  goto LABEL_193;
                }
                v73 = *v124;
                if ( !(_DWORD)v73 )
                  break;
                v71 = v120 - v73;
              }
            }
            v124 = 0;
LABEL_191:
            v37 = EaLength[0];
          }
          else
          {
            v124 = 0;
          }
          v97 = 0;
LABEL_193:
          v120 = 0;
          if ( *(_QWORD *)&EaLength[2] )
          {
            if ( IoCheckEaBufferValidity(*(PFILE_FULL_EA_INFORMATION *)&EaLength[2], v37, &v120) < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  108,
                  WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                  KeGetCurrentThread(),
                  v120);
              }
            }
            else
            {
              v74 = EaLength[0];
              for ( k = *(const char **)&EaLength[2]; ; k = (char *)v105 + v76 )
              {
                v105 = (unsigned int *)k;
                PriorityInfo.Size = v74;
                if ( v74 < 0xC )
                  break;
                if ( !_stricmp(k + 8, "$Kernel.SEC.ApplicationSource") )
                {
                  if ( !v105 )
                    goto LABEL_212;
                  v96 = 1;
                  goto LABEL_213;
                }
                v76 = *v105;
                if ( !(_DWORD)v76 )
                  break;
                v74 = PriorityInfo.Size - v76;
              }
            }
          }
          v105 = 0;
LABEL_212:
          v96 = 0;
LABEL_213:
          v37 = EaLength[0];
        }
        if ( !v36
          && v33
          && a5
          && *(_DWORD *)(a3 + 240) == 16
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_dZZ(WPP_GLOBAL_Control->AttachedDevice, v37, v30, v37 != 0, *(_QWORD *)(a3 + 128), a5 + 240);
        }
        goto LABEL_57;
      }
    }
    if ( v23 && v23[10] )
    {
      v14 = (_OWORD *)v23[10];
    }
    else if ( v107 && *(_QWORD *)(v107 + 8) )
    {
      v14 = *(_OWORD **)(v107 + 8);
    }
    v89 = CallbackData->Iopb;
    if ( (v89->MajorFunction || (*(_DWORD *)(v89->Parameters.WMI.ProviderId + 16) & 8) == 0)
      && (!v23 || (v23[11] & 8) == 0)
      || (v25 = MpDlpQueryEa(0, *(_QWORD *)(v106 + 24), *(_QWORD *)(v106 + 32), EaLength, &v98),
          (int)(v25 + 0x80000000) >= 0)
      && v25 != -1073741745 )
    {
      v25 = MpDlpQueryEaByName(v14, EaLength, &v98);
    }
    v26 = v25 >= 0;
    v102 = v25 >= 0;
    goto LABEL_27;
  }
  v66 = 513;
  v115 = 0;
  if ( !byte_1400269F8 && (v100 & 0x11) == 0 )
    v66 = 257;
  v67 = FltGetFileNameInformation(CallbackData, v66, &v115);
  if ( v67 < 0 )
  {
    _mm_lfence();
    v67 = FltGetFileNameInformation(CallbackData, 0x102u, &v115);
  }
  if ( v115 )
    v13 = v115;
  if ( v67 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_102;
    v79 = 29;
    ObjectType = v67;
    goto LABEL_409;
  }
  v36 = 1;
  v99 = 1;
LABEL_57:
  if ( *(_DWORD *)(MpData + 4144) )
  {
    v65 = 1;
    if ( a5 )
    {
      v70 = *(_QWORD *)(a5 + 8);
      if ( v70 )
        v65 = *(_BYTE *)(v70 + 80) & 1;
    }
    if ( *((_QWORD *)MpDlpData + 35)
      && *((_QWORD *)MpDlpData + 36)
      && v13
      && v65
      && RtlPrefixUnicodeString(*((PCUNICODE_STRING *)MpDlpData + 35), &v13->Name, 1u)
      && !RtlPrefixUnicodeString(*((PCUNICODE_STRING *)MpDlpData + 36), &v13->Name, 1u) )
    {
      goto LABEL_102;
    }
  }
  if ( !v36 && !v95 && !*((_BYTE *)MpDlpData + 265) && !v97 && !v96 )
    goto LABEL_102;
  v38 = FltParseFileName(*(PCUNICODE_STRING *)(a3 + 128), 0, 0, &FinalComponent);
  if ( v38 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_102;
    v79 = 30;
    ObjectType = v38;
    goto LABEL_409;
  }
  v39 = v13->Name.Length + 166;
  if ( v39 < 0xA4 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_102;
    v79 = 31;
    goto LABEL_408;
  }
  v40 = v39 + FinalComponent.Length + 2;
  if ( v40 < v39 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_102;
    v79 = 32;
    goto LABEL_408;
  }
  if ( v36 )
  {
    if ( (_DWORD)Size && Src )
    {
      if ( v40 + (unsigned int)Size < v40 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_102;
        v79 = 33;
        goto LABEL_408;
      }
      v40 += Size;
    }
    else
    {
      if ( v40 + *((unsigned __int16 *)v104 + 3) < v40 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_102;
        v79 = 34;
        goto LABEL_408;
      }
      v40 += *((unsigned __int16 *)v104 + 3);
    }
  }
  if ( v97 )
  {
    if ( v40 + *((unsigned __int16 *)v124 + 3) < v40 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_102;
      v79 = 35;
      goto LABEL_408;
    }
    v40 += *((unsigned __int16 *)v124 + 3);
  }
  if ( v96 )
  {
    if ( v40 + *((unsigned __int16 *)v105 + 3) < v40 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_102;
      v79 = 36;
      goto LABEL_408;
    }
    v40 += *((unsigned __int16 *)v105 + 3);
  }
  if ( v102 )
  {
    v90 = FltGetFileNameInformation(CallbackData, 0x102u, &v112);
    if ( v90 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_102;
      v79 = 37;
      ObjectType = v90;
      goto LABEL_409;
    }
    if ( v40 + v112->Name.Length + 2 >= v40 )
    {
      v40 += v112->Name.Length + 2;
      goto LABEL_66;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_102;
    v79 = 38;
LABEL_408:
    ObjectType = -1073741675;
    goto LABEL_409;
  }
LABEL_66:
  PoolWithTag = MpAllocatePoolWithTag(1, v40, 1818513485);
  v12 = PoolWithTag;
  if ( !PoolWithTag )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_102;
    v79 = 39;
    ObjectType = -1073741670;
    goto LABEL_410;
  }
  v42 = v106;
  *(_DWORD *)(PoolWithTag + 4) = v40;
  *(_DWORD *)PoolWithTag = 262565;
  PriorityInfo.Size = 16;
  v43 = *(struct _FILE_OBJECT **)(v42 + 32);
  *(_OWORD *)(PoolWithTag + 8) = 0;
  *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
  PriorityInfo.IoPriority = IoPriorityNormal;
  v44 = FltRetrieveIoPriorityInfo(CallbackData, v43, KeGetCurrentThread(), &PriorityInfo);
  if ( v44 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids, (unsigned int)v44);
  }
  PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
  IoPriority = PriorityInfo.IoPriority;
  *(_DWORD *)(v12 + 12) = PriorityThread;
  PriorityInfo.ThreadPriority = PriorityThread;
  *(_DWORD *)(v12 + 16) = PriorityInfo.PagePriority;
  *(_DWORD *)(v12 + 8) = IoPriority;
  v47 = CallbackData->Iopb->MajorFunction;
  if ( v47 )
  {
    if ( v47 == 0xFF )
    {
      v48 = 2;
    }
    else if ( v47 == 3 )
    {
      v48 = 3;
    }
    else
    {
      v48 = 0;
      if ( v47 == 8 )
        v48 = 5;
    }
  }
  else
  {
    v48 = 1;
  }
  *(_DWORD *)(v12 + 24) = v48;
  *(_DWORD *)(v12 + 96) = *(_DWORD *)(a3 + 24);
  *(_DWORD *)(v12 + 100) = *(_DWORD *)(a3 + 240);
  if ( a5 )
  {
    *(_QWORD *)(v12 + 120) = *(_QWORD *)(a5 + 168);
    *(_OWORD *)(v12 + 104) = *(_OWORD *)(*(_QWORD *)(a5 + 8) + 56LL);
  }
  else
  {
    *(_QWORD *)(v12 + 120) = 0;
  }
  *(_QWORD *)(v12 + 32) = MpFileTimeToUlong64(*(_QWORD *)(a3 + 32));
  *(_DWORD *)(v12 + 128) = *(_DWORD *)(a3 + 256);
  *(_DWORD *)(v12 + 148) = v100;
  *(_QWORD *)(v12 + 40) = 164;
  memmove((void *)(v12 + 164), FinalComponent.Buffer, FinalComponent.Length);
  *(_WORD *)(v12 + 2 * ((unsigned __int64)FinalComponent.Length >> 1) + *(_QWORD *)(v12 + 40)) = 0;
  *(_DWORD *)(v12 + 132) = FinalComponent.Length;
  v49 = FinalComponent.Length + 166LL;
  *(_QWORD *)(v12 + 48) = v49;
  memmove((void *)(v12 + v49), v13->Name.Buffer, v13->Name.Length);
  *(_WORD *)(v12 + 2 * ((unsigned __int64)v13->Name.Length >> 1) + *(_QWORD *)(v12 + 48)) = 0;
  *(_DWORD *)(v12 + 136) = v13->Name.Length;
  v50 = v13->Name.Length + v49 + 2;
  *(_QWORD *)(v12 + 56) = 0;
  *(_QWORD *)&PriorityInfo.Size = v50;
  *(_DWORD *)(v12 + 140) = 0;
  if ( v102 && v112 )
  {
    *(_QWORD *)(v12 + 56) = v50;
    memmove((void *)(v12 + v50), v112->Name.Buffer, v112->Name.Length);
    *(_WORD *)(v12 + 2 * ((unsigned __int64)v112->Name.Length >> 1) + *(_QWORD *)(v12 + 56)) = 0;
    *(_DWORD *)(v12 + 140) = v112->Name.Length;
    v50 += v112->Name.Length + 2LL;
    *(_QWORD *)&PriorityInfo.Size = v50;
  }
  *(_QWORD *)(v12 + 64) = 0;
  *(_DWORD *)(v12 + 144) = 0;
  if ( v36 )
  {
    *(_QWORD *)(v12 + 64) = v50;
    if ( (_DWORD)Size && Src )
    {
      v86 = *(_QWORD *)&PriorityInfo.Size;
      memmove((void *)(v12 + *(_QWORD *)&PriorityInfo.Size), Src, (unsigned int)Size);
      v50 = v86 + (unsigned int)Size;
      *(_DWORD *)(v12 + 144) = Size;
    }
    else
    {
      v80 = v104;
      memmove((void *)(v12 + v50), (char *)v104 + *((unsigned __int8 *)v104 + 5) + 9, *((unsigned __int16 *)v104 + 3));
      *(_DWORD *)(v12 + 144) = *((unsigned __int16 *)v80 + 3);
      v50 += *((unsigned __int16 *)v80 + 3);
    }
  }
  *(_QWORD *)(v12 + 80) = 0;
  *(_DWORD *)(v12 + 156) = 0;
  if ( v96 )
  {
    v91 = v105;
    *(_QWORD *)(v12 + 80) = v50;
    memmove((void *)(v12 + v50), (char *)v91 + *((unsigned __int8 *)v91 + 5) + 9, *((unsigned __int16 *)v91 + 3));
    *(_DWORD *)(v12 + 156) = *((unsigned __int16 *)v91 + 3);
    v50 += *((unsigned __int16 *)v91 + 3);
  }
  v84 = v97 == 0;
  *(_QWORD *)(v12 + 88) = 0;
  *(_DWORD *)(v12 + 160) = 0;
  if ( !v84 )
  {
    v92 = v124;
    *(_QWORD *)(v12 + 88) = v50;
    memmove((void *)(v12 + v50), (char *)v92 + *((unsigned __int8 *)v92 + 5) + 9, *((unsigned __int16 *)v92 + 3));
    *(_DWORD *)(v12 + 160) = *((unsigned __int16 *)v92 + 3);
  }
  v51 = MpDlpQueryService((unsigned int)v100, v12, &v103, v116);
  if ( v51 >= 0 )
  {
    if ( (v103 & 0xFFFFFFFD) == 0 )
      goto LABEL_102;
    v52 = v106;
    if ( !a5 && FltGetStreamContext(*(PFLT_INSTANCE *)(v106 + 24), *(PFILE_OBJECT *)(v106 + 32), &v111) < 0 )
    {
      StreamContext = MpCreateStreamContext(CallbackData, 0, (__int64)&v111);
      if ( (int)(StreamContext + 0x80000000) >= 0 && StreamContext != -1071906814 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_102;
        v79 = 41;
        ObjectType = StreamContext;
        goto LABEL_409;
      }
    }
    if ( !Context && FltGetStreamHandleContext(*(PFLT_INSTANCE *)(v52 + 24), *(PFILE_OBJECT *)(v52 + 32), &Context) < 0 )
    {
      v68 = MpCreateHandleContext(v52, &Context, 0);
      if ( v68 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_102;
        v79 = 42;
        ObjectType = v68;
        goto LABEL_409;
      }
      v69 = CallbackData->Iopb;
      if ( !v69->MajorFunction )
        *((_DWORD *)Context + 22) = *(_DWORD *)(v69->Parameters.WMI.ProviderId + 16);
    }
    v53 = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
    v124 = 0;
    v125 = 0;
    Src = 0;
    v116 = 0;
    if ( !v53 )
    {
      v55 = -1073741811;
LABEL_399:
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_102;
      v79 = 43;
      ObjectType = v55;
      goto LABEL_409;
    }
    v124 = *(unsigned int **)(a3 + 24);
    v125 = *(_QWORD *)(a3 + 32);
    v127 = 2;
    v129 = 2;
    v130 = &v124;
    *((_QWORD *)&v116 + 1) = &v126;
    v126 = String2;
    v128 = 65;
    *(_QWORD *)&v116 = 0x100000001LL;
    v54 = PsReferencePrimaryToken(v53);
    v55 = ObOpenObjectByPointer(v54, 0x200u, 0, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &Src);
    if ( v55 >= 0 )
    {
      PriorityInfo.Size = 4;
      v55 = SeSetSecurityAttributesToken(Src, 0, &PriorityInfo, &v116);
      if ( v55 >= 0 )
      {
        v55 = 0;
        goto LABEL_85;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v93 = 72;
        goto LABEL_387;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v93 = 71;
LABEL_387:
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v93,
        WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
        KeGetCurrentThread(),
        v55);
    }
LABEL_85:
    if ( Src )
      ZwClose(Src);
    if ( v54 )
      PsDereferencePrimaryToken(v54);
    if ( v55 >= 0 )
    {
      _mm_lfence();
      _InterlockedOr((volatile signed __int32 *)Context + 10, 0x40u);
      if ( a5 )
        v56 = (volatile signed __int32 *)(a5 + 48);
      else
        v56 = (volatile signed __int32 *)((char *)v111 + 48);
      _InterlockedOr(v56, 0x10000u);
      v57 = v99;
      if ( v99 )
      {
        if ( a5 )
        {
          _InterlockedOr((volatile signed __int32 *)(a5 + 48), 0x200000u);
          v77 = (volatile signed __int32 *)(a5 + 48);
        }
        else
        {
          _InterlockedOr((volatile signed __int32 *)v111 + 12, 0x200000u);
          v77 = (volatile signed __int32 *)((char *)v111 + 48);
        }
        _InterlockedAnd(v77, 0xFFBFFFFF);
        v59 = v95;
      }
      else
      {
        if ( a5 )
          v58 = (volatile signed __int32 *)(a5 + 48);
        else
          v58 = (volatile signed __int32 *)((char *)v111 + 48);
        _InterlockedAnd(v58, 0xFFDFFFFF);
        v59 = v95;
        if ( v95 )
        {
          if ( a5 )
            v85 = (volatile signed __int32 *)(a5 + 48);
          else
            v85 = (volatile signed __int32 *)((char *)v111 + 48);
          _InterlockedOr(v85, 0x400000u);
        }
      }
      if ( !CallbackData->Iopb->MajorFunction )
      {
        if ( v107 )
        {
          v60 = *(const UNICODE_STRING **)(v107 + 8);
          if ( v60 )
          {
            if ( (int)MpDuplicateString(v60) >= 0 )
              _InterlockedOr((volatile signed __int32 *)Context + 10, 0x80u);
          }
        }
      }
      if ( CallbackData->Iopb->MajorFunction == 0xFF )
      {
        v81 = MpCreateDlpProcessEntry(0, &v13->Name, &ListEntry);
        if ( v81 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_102;
          }
          v79 = 45;
          ObjectType = v81;
          goto LABEL_409;
        }
        if ( a5 )
          v82 = (union _SLIST_HEADER *)(a5 + 272);
        else
          v82 = (union _SLIST_HEADER *)((char *)v111 + 272);
        ExpInterlockedPushEntrySList(v82, ListEntry);
      }
      else
      {
        _mm_lfence();
        v61 = MpDlpSetProcessEntryFlags(CallbackData, v13, v100, 1);
        if ( v61 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_102;
          }
          v79 = 44;
          ObjectType = v61;
          goto LABEL_409;
        }
        _mm_lfence();
        if ( *(_BYTE *)(a3 + 196) )
          __debugbreak();
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 192));
      }
      if ( v103 == 3 )
      {
        _InterlockedOr((volatile signed __int32 *)(a3 + 52), 0x1000u);
        v103 = 1;
      }
      if ( v57 || v59 )
      {
        v62 = v111;
        if ( a5 )
          v62 = (PFLT_CONTEXT)a5;
        v63 = MpDlpRegisterForPolicyUpdate(a3, &v13->Name, v62, 0);
        if ( v63 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qZZDD(
            WPP_GLOBAL_Control->AttachedDevice,
            (unsigned int)&WPP_GLOBAL_Control,
            v64,
            (unsigned int)KeGetCurrentThread(),
            (__int64)&v13->Name,
            *(_QWORD *)(a3 + 128),
            *(_DWORD *)(a3 + 24),
            v63);
        }
      }
      goto LABEL_102;
    }
    goto LABEL_399;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    goto LABEL_102;
  v79 = 40;
  ObjectType = v51;
LABEL_409:
  _mm_lfence();
LABEL_410:
  WPP_SF_qD(
    WPP_GLOBAL_Control->AttachedDevice,
    v79,
    WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
    KeGetCurrentThread(),
    ObjectType);
LABEL_102:
  if ( *(_QWORD *)&EaLength[2] && v98 )
    ExFreePoolWithTag(*(PVOID *)&EaLength[2], 0x6165504Du);
  if ( v12 )
    ExFreePoolWithTag((PVOID)v12, 0x6C64504Du);
  if ( v111 )
    FltReleaseContext(v111);
  if ( Context && Context != v109 )
    FltReleaseContext(Context);
  if ( v13 && v13 != (PFLT_FILE_NAME_INFORMATION)v122 )
    FltReleaseFileNameInformation(v13);
  if ( v112 )
    FltReleaseFileNameInformation(v112);
  return v103;
}

```

## disassembly

```asm
0x1400408b0  mov     [rsp-8+arg_18], rbx
0x1400408b5  push    rbp
0x1400408b6  push    rsi
0x1400408b7  push    rdi
0x1400408b8  push    r12
0x1400408ba  push    r13
0x1400408bc  push    r14
0x1400408be  push    r15
0x1400408c0  lea     rbp, [rsp-0E0h]
0x1400408c8  sub     rsp, 1E0h
0x1400408cf  mov     rax, cs:__security_cookie
0x1400408d6  xor     rax, rsp
0x1400408d9  mov     [rbp+110h+var_38], rax
0x1400408e0  mov     r14, [rbp+110h+arg_20]
0x1400408e7  xorps   xmm0, xmm0
0x1400408ea  mov     rax, rdx
0x1400408ed  mov     [rbp+110h+var_188], rdx
0x1400408f1  mov     rdx, [rbp+110h+arg_30]
0x1400408f8  xor     dil, dil
0x1400408fb  mov     [rbp+110h+var_180], rdx
0x1400408ff  mov     rsi, rcx
0x140040902  mov     rdx, [rbp+110h+arg_40]
0x140040909  mov     r15, r8
0x14004090c  mov     rcx, [rbp+110h+arg_28]
0x140040913  xor     r8d, r8d
0x140040916  mov     [rbp+110h+Src], rdx
0x14004091a  mov     ebx, r8d
0x14004091d  mov     rdx, [rbp+110h+arg_48]
0x140040924  mov     r13d, r8d
0x140040927  mov     qword ptr [rbp+110h+var_138], rdx
0x14004092b  mov     r12d, r8d
0x14004092e  xor     edx, edx
0x140040930  mov     [rsp+210h+var_1B8], r9d
0x140040935  mov     [rbp+110h+var_170], rcx
0x140040939  mov     [rsp+210h+var_198], r8
0x14004093e  mov     [rbp+110h+var_70], r8
0x140040945  mov     [rbp+110h+var_190], r8
0x140040949  mov     [rsp+210h+var_1BC], dil
0x14004094e  mov     [rsp+210h+var_1BE], dil
0x140040953  mov     [rsp+210h+var_1BF], dil
0x140040958  mov     [rsp+210h+var_19C], r8d
0x14004095d  mov     [rbp+110h+var_80], rdx
0x140040964  mov     [rbp+110h+Context], rcx
0x140040968  mov     [rbp+110h+var_160], r8
0x14004096c  mov     [rsp+210h+var_1BD], dl
0x140040970  mov     [rbp+110h+ListEntry], r8
0x140040974  mov     [rsp+210h+var_1C0], dl
0x140040978  mov     byte ptr [rsp+210h+var_1A0], dl
0x14004097c  mov     [rbp+110h+var_158], r8
0x140040980  movups  xmmword ptr [rsp+210h+EaLength], xmm0
0x140040985  movups  [rbp+110h+var_F0], xmm0
0x140040989  movups  [rbp+110h+var_E0], xmm0
0x14004098d  movups  [rbp+110h+var_D0], xmm0
0x140040991  movups  [rbp+110h+var_C0], xmm0
0x140040995  movups  [rbp+110h+var_B0], xmm0
0x140040999  movups  [rbp+110h+var_A0], xmm0
0x14004099d  movups  [rbp+110h+var_90], xmm0
0x1400409a4  movups  xmmword ptr [rbp+110h+FinalComponent.Length], xmm0
0x1400409a8  test    rsi, rsi
0x1400409ab  jnz     short loc_1400409DA
0x1400409ad  xor     eax, eax
0x1400409af  mov     rcx, [rbp+110h+var_38]
0x1400409b6  xor     rcx, rsp; StackCookie
0x1400409b9  call    __security_check_cookie
0x1400409be  mov     rbx, [rsp+210h+arg_18]
0x1400409c6  add     rsp, 1E0h
0x1400409cd  pop     r15
0x1400409cf  pop     r14
0x1400409d1  pop     r13
0x1400409d3  pop     r12
0x1400409d5  pop     rdi
0x1400409d6  pop     rsi
0x1400409d7  pop     rbp
0x1400409d8  retn
0x1400409da  test    rax, rax
0x1400409dd  jz      short loc_1400409AD
0x1400409df  test    r15, r15
0x1400409e2  jz      short loc_1400409AD
0x1400409e4  mov     qword ptr [rbp+110h+PriorityInfo.Size], rsi
0x1400409e8  call    cs:__imp_IoGetCurrentProcess
0x1400409ef  nop     dword ptr [rax+rax+00h]
0x1400409f4  mov     rdx, cs:MpDlpData
0x1400409fb  mov     [rbp+110h+FileNameInformation], rax
0x1400409ff  test    rdx, rdx
0x140040a02  jz      short loc_1400409AD
0x140040a04  lea     rcx, [rsi-1]
0x140040a08  cmp     rcx, 1
0x140040a0c  jbe     loc_140041B7D
0x140040a12  movzx   ecx, byte ptr [rdx+20h]
0x140040a16  test    cl, cl
0x140040a18  jz      short loc_1400409AD
0x140040a1a  mov     rcx, cs:MpData
0x140040a21  test    dword ptr [rcx+360h], 400h
0x140040a2b  jz      short loc_1400409AD
0x140040a2d  cmp     [rcx+140h], rbx
0x140040a34  jz      loc_140041B22
0x140040a3a  mov     rcx, gs:188h; Thread
0x140040a43  mov     rax, cs:MpData
0x140040a4a  mov     rdi, [rax+0E8h]
0x140040a51  call    cs:__imp_IoThreadToProcess
0x140040a58  nop     dword ptr [rax+rax+00h]
0x140040a5d  cmp     rax, rdi
0x140040a60  jz      loc_140041487
0x140040a66  mov     rcx, gs:188h; Thread
0x140040a6f  mov     rax, cs:MpData
0x140040a76  mov     rdi, [rax+100h]
0x140040a7d  call    cs:__imp_IoThreadToProcess
0x140040a84  nop     dword ptr [rax+rax+00h]
0x140040a89  cmp     rax, rdi
0x140040a8c  jz      loc_140041487
0x140040a92  mov     rcx, qword ptr [rbp+110h+PriorityInfo.Size]
0x140040a96  test    rcx, rcx
0x140040a99  jnz     loc_14004158F
0x140040a9f  mov     rdx, [rbp+110h+FileNameInformation]
0x140040aa3  mov     rax, cs:__imp_PsInitialSystemProcess
0x140040aaa  cmp     [rax], rdx
0x140040aad  jz      loc_140041A84
0x140040ab3  test    dword ptr [r15+38h], 40000000h
0x140040abb  jnz     loc_1400419B8
0x140040ac1  cmp     dword ptr [r15+0F0h], 21h ; '!'
0x140040ac9  jz      loc_1400419B8
0x140040acf  xor     dil, dil
0x140040ad2  test    dil, dil
0x140040ad5  jnz     loc_1400409AD
0x140040adb  mov     rax, [rsi+10h]
0x140040adf  movzx   edx, byte ptr [rax+4]
0x140040ae3  test    dl, dl
0x140040ae5  jz      loc_14004149A
0x140040aeb  cmp     dword ptr [rbp+110h+Size], ebx
0x140040af1  jnz     loc_14004133A
0x140040af7  mov     rcx, [rbp+110h+var_180]
0x140040afb  test    dl, dl
0x140040afd  jz      loc_1400414DC
0x140040b03  mov     rdx, [rbp+110h+Context]
0x140040b07  test    rdx, rdx
0x140040b0a  jnz     loc_140041985
0x140040b10  mov     rdi, [rbp+110h+var_188]
0x140040b14  lea     rdx, [rbp+110h+FileSystemType]; FileSystemType
0x140040b18  xor     eax, eax
0x140040b1a  mov     [rbp+110h+FileSystemType], eax
0x140040b1d  mov     rcx, [rdi+18h]; FltObject
0x140040b21  call    cs:__imp_FltGetFileSystemType
0x140040b28  nop     dword ptr [rax+rax+00h]
0x140040b2d  cmp     [rbp+110h+FileSystemType], 0Dh
0x140040b31  jz      loc_140041DCC
0x140040b37  mov     r8, [rdi+20h]
0x140040b3b  lea     rax, [rsp+210h+var_1BD]
0x140040b40  mov     rdx, [rdi+18h]
0x140040b44  lea     r9, [rsp+210h+EaLength]
0x140040b49  mov     rcx, rsi
0x140040b4c  mov     [rsp+210h+ObjectType], rax
0x140040b51  call    MpDlpQueryEa
0x140040b56  mov     edi, eax
0x140040b58  xor     eax, eax
0x140040b5a  mov     ecx, [rsp+210h+var_1A0]
0x140040b5e  test    edi, edi
0x140040b60  js      loc_140041F79
0x140040b66  test    cl, cl
0x140040b68  jnz     loc_140041FCA
0x140040b6e  cmp     cs:byte_1400269F8, bl
0x140040b74  mov     edx, 201h; NameOptions
0x140040b79  mov     [rbp+110h+FileNameInformation], rax
0x140040b7d  jz      loc_140041399
0x140040b83  lea     r8, [rbp+110h+FileNameInformation]; FileNameInformation
0x140040b87  mov     rcx, rsi; CallbackData
0x140040b8a  call    cs:__imp_FltGetFileNameInformation
0x140040b91  nop     dword ptr [rax+rax+00h]
0x140040b96  mov     ecx, eax
0x140040b98  test    eax, eax
0x140040b9a  js      loc_1400417F2
0x140040ba0  mov     rax, [rbp+110h+FileNameInformation]
0x140040ba4  test    rax, rax
0x140040ba7  jz      short loc_140040BAC
0x140040ba9  mov     r13, rax
0x140040bac  test    ecx, ecx
0x140040bae  js      loc_14004200C
0x140040bb4  xor     edi, edi
0x140040bb6  mov     [rbp+110h+FileSystemType], edi
0x140040bb9  test    r14, r14
0x140040bbc  jz      loc_14004171B
0x140040bc2  mov     edx, [r14+0B8h]
0x140040bc9  mov     rax, cs:MpDlpData
0x140040bd0  lea     r8, cs:140000000h
0x140040bd7  movzx   ecx, byte ptr [rax+10Bh]
0x140040bde  test    cl, cl
0x140040be0  jz      loc_14004144A
0x140040be6  mov     r12d, [rsp+210h+EaLength]; jumptable 000000014004177F default case, cases 2-36,38-43,51
0x140040beb  mov     rax, cs:MpData
0x140040bf2  xor     dil, dil
0x140040bf5  mov     ecx, [rax+364h]
0x140040bfb  test    ecx, ecx
0x140040bfd  js      loc_14004203C
0x140040c03  cmp     edx, 24h ; '$'
0x140040c06  jz      short loc_140040C19; jumptable 0000000140041A4B cases 4-28,30-32
0x140040c08  add     edx, 0FFFFFFFEh; switch 42 cases
0x140040c0b  cmp     edx, 29h
0x140040c0e  jbe     loc_140041A34
0x140040c14  xor     dil, dil; jumptable 0000000140041A4B default case, cases 3,33-37
0x140040c17  jmp     short loc_140040C2C
0x140040c19  mov     rcx, r15; jumptable 0000000140041A4B cases 4-28,30-32
0x140040c1c  call    MpIsOfficeApplication
0x140040c21  test    al, al
0x140040c23  jz      loc_140041863
0x140040c29  mov     dil, 1
0x140040c2c  mov     [rsp+210h+var_1C0], dil
0x140040c31  test    r12d, r12d
0x140040c34  jz      loc_140041CD8
0x140040c3a  mov     rcx, qword ptr [rsp+210h+EaLength+8]; EaBuffer
0x140040c3f  xor     eax, eax
0x140040c41  mov     [rbp+110h+FileSystemType], eax
0x140040c44  test    rcx, rcx
0x140040c47  jz      short loc_140040CA9
0x140040c49  test    r12d, r12d
0x140040c4c  jz      short loc_140040CA9
0x140040c4e  lea     r8, [rbp+110h+FileSystemType]; ErrorOffset
0x140040c52  mov     edx, r12d; EaLength
0x140040c55  call    cs:__imp_IoCheckEaBufferValidity
0x140040c5c  nop     dword ptr [rax+rax+00h]
0x140040c61  test    eax, eax
0x140040c63  js      loc_140041BDF
0x140040c69  mov     rcx, qword ptr [rsp+210h+EaLength+8]
0x140040c6e  mov     [rsp+210h+var_198], rcx
0x140040c73  cmp     r12d, 0Ch
0x140040c77  jb      short loc_140040CA7
0x140040c79  add     rcx, 8; Str1
0x140040c7d  lea     rdx, aKernelSecEndpo; "$Kernel.SEC.EndpointDlp"
0x140040c84  call    cs:__imp__stricmp
0x140040c8b  nop     dword ptr [rax+rax+00h]
0x140040c90  test    eax, eax
0x140040c92  jz      loc_14004182B
0x140040c98  mov     rcx, [rsp+210h+var_198]
0x140040c9d  mov     eax, [rcx]
0x140040c9f  test    eax, eax
0x140040ca1  jnz     loc_1400417BF
0x140040ca7  xor     eax, eax
0x140040ca9  mov     [rsp+210h+var_198], rax
0x140040cae  xor     r12b, r12b
0x140040cb1  mov     [rsp+210h+var_1BC], r12b
0x140040cb6  mov     rax, cs:MpDlpData
0x140040cbd  mov     edx, [rsp+210h+EaLength]; EaLength
0x140040cc1  movzx   ecx, byte ptr [rax+10Ah]
0x140040cc8  test    cl, cl
0x140040cca  jnz     loc_1400415CA
0x140040cd0  test    r12b, r12b
0x140040cd3  jz      loc_14004151C
0x140040cd9  mov     rax, cs:MpData
0x140040ce0  cmp     [rax+1030h], ebx
0x140040ce6  jnz     loc_1400412A1
0x140040cec  test    r12b, r12b
0x140040cef  jz      loc_1400416E2
0x140040cf5  mov     rcx, [r15+80h]; FileName
0x140040cfc  lea     r9, [rbp+110h+FinalComponent]; FinalComponent
0x140040d00  xor     r8d, r8d; Stream
0x140040d03  xor     edx, edx; Extension
0x140040d05  call    cs:__imp_FltParseFileName
0x140040d0c  nop     dword ptr [rax+rax+00h]
0x140040d11  test    eax, eax
0x140040d13  js      loc_140042073
0x140040d19  movzx   ecx, word ptr [r13+8]
0x140040d1e  add     ecx, 0A6h
0x140040d24  cmp     ecx, 0A4h
0x140040d2a  jb      loc_1400424F8
0x140040d30  movzx   edi, [rbp+110h+FinalComponent.Length]
0x140040d34  add     edi, 2
0x140040d37  add     edi, ecx
0x140040d39  cmp     edi, ecx
0x140040d3b  jb      loc_1400424CF
0x140040d41  test    r12b, r12b
0x140040d44  jnz     loc_1400417CA
0x140040d4a  cmp     [rsp+210h+var_1BE], bl
0x140040d4e  jnz     loc_140042113
0x140040d54  cmp     [rsp+210h+var_1BF], bl
0x140040d58  jnz     loc_140042157
0x140040d5e  cmp     byte ptr [rsp+210h+var_1A0], bl
0x140040d62  jnz     loc_140042198
0x140040d68  mov     edx, edi
0x140040d6a  mov     ecx, 1
0x140040d6f  mov     r8d, 6C64504Dh
0x140040d75  call    MpAllocatePoolWithTag
0x140040d7a  mov     rbx, rax
0x140040d7d  test    rax, rax
0x140040d80  jz      loc_140042229
0x140040d86  mov     rdx, [rbp+110h+var_188]
0x140040d8a  lea     r9, [rbp+110h+PriorityInfo]; PriorityInfo
0x140040d8e  mov     [rax+4], edi
0x140040d91  xorps   xmm0, xmm0
0x140040d94  mov     dword ptr [rax], 401A5h
0x140040d9a  mov     rcx, rsi; Data
0x140040d9d  mov     [rbp+110h+PriorityInfo.Size], 10h
0x140040da4  xor     edi, edi
0x140040da6  mov     rdx, [rdx+20h]; FileObject
0x140040daa  movups  xmmword ptr [rax+8], xmm0
0x140040dae  mov     eax, 2
0x140040db3  mov     qword ptr [rbp+110h+PriorityInfo.ThreadPriority], 0FFFFh
0x140040dbb  mov     [rbp+110h+PriorityInfo.IoPriority], eax
0x140040dbe  mov     r8, gs:188h; Thread
0x140040dc7  call    cs:__imp_FltRetrieveIoPriorityInfo
0x140040dce  nop     dword ptr [rax+rax+00h]
0x140040dd3  test    eax, eax
0x140040dd5  js      loc_14004225D
  ... truncated ...
```
