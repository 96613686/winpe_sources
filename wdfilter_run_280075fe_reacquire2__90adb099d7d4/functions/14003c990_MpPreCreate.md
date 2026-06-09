# MpPreCreate

- ea: `0x14003c990`
- end: `0x14003dd3f`
- name: `MpPreCreate`
- size: `5039`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x140003d20`
- `0x14000505c`
- `0x1400051bc`
- `0x14000ae58`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003a2c0`
- `0x14003c3b0`
- `0x14003c7b0`
- `0x14003c990`
- `0x14003dd40`
- `0x14003e0d0`
- `0x14003e380`
- `0x1400444b0`
- `0x140066180`
- `0x14006e4f4`
- `0x1400733c8`
- `0x14007aadc`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14003cfde`
- `ntoskrnl!PsGetProcessId` at `0x14003cfde`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003d8bb`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003dbef`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003d8bb`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003dbef`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14003cfa5`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14003cfa5`
- `ntoskrnl!PsInitialSystemProcess` at `0x14003cf68`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003d3c1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003d3c1`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003cfcb`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003cfcb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d5d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d5d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003d5c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003d5c8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003d01c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003d01c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d00a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d00a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cc30`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d8d1`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cc30`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d8d1`
- `ntoskrnl!IoThreadToProcess` at `0x14003cf1e`
- `ntoskrnl!IoThreadToProcess` at `0x14003cf4a`
- `ntoskrnl!IoThreadToProcess` at `0x14003cf1e`
- `ntoskrnl!IoThreadToProcess` at `0x14003cf4a`
- `ntoskrnl!IoGetStackLimits` at `0x14003ca0e`
- `ntoskrnl!IoGetStackLimits` at `0x14003ca0e`
- `ntoskrnl!ExQueryDepthSList` at `0x14003d368`
- `ntoskrnl!ExQueryDepthSList` at `0x14003d368`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003d386`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003d386`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003cae0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003cae0`
- `FLTMGR!FltReleaseContext` at `0x14003cd52`
- `FLTMGR!FltReleaseContext` at `0x14003d132`
- `FLTMGR!FltReleaseContext` at `0x14003cd52`
- `FLTMGR!FltReleaseContext` at `0x14003d132`
- `FLTMGR!FltGetFileNameInformation` at `0x14003d98c`
- `FLTMGR!FltGetFileNameInformation` at `0x14003d98c`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003ce89`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d2f4`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d4d3`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d615`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d67f`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d72b`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d832`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003ce89`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d2f4`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d4d3`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d615`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d67f`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d72b`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14003d832`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003ca83`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003cb33`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003cba5`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003ce2f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003d237`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003d299`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003d478`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003ca83`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003cb33`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003cba5`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003ce2f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003d237`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003d299`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003d478`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003cab8`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003cb6f`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003cbda`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003ce6b`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003d26c`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003d2d6`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003d4b5`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003cab8`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003cb6f`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003cbda`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003ce6b`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003d26c`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003d2d6`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003d4b5`
- `FLTMGR!FltGetInstanceContext` at `0x14003cbf6`
- `FLTMGR!FltGetInstanceContext` at `0x14003d109`
- `FLTMGR!FltGetInstanceContext` at `0x14003cbf6`
- `FLTMGR!FltGetInstanceContext` at `0x14003d109`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003d9ce`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003d9ce`

## pseudocode

```c
__int64 __fastcall MpPreCreate(PFLT_CALLBACK_DATA Data, struct _FLT_FILTER **a2, PSLIST_ENTRY *a3)
{
  PSLIST_ENTRY v3; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  unsigned __int64 TargetFileObject; // r14
  UCHAR OperationFlags; // cl
  struct _FLT_FILTER *v10; // rbx
  ULONG_PTR v11; // rbx
  union _SLIST_HEADER *v12; // rcx
  struct _FLT_FILTER *v13; // rbx
  struct _FLT_FILTER *v14; // rbx
  NTSTATUS InstanceContext; // eax
  PFLT_CALLBACK_DATA v16; // r15
  struct _KPROCESS *CurrentProcess; // r12
  PFLT_CONTEXT v18; // r15
  bool v19; // zf
  unsigned __int16 v20; // r9
  unsigned int v21; // edi
  __int64 result; // rax
  unsigned __int16 v23; // ax
  __int64 v24; // rbx
  unsigned __int64 v25; // rcx
  struct _FLT_FILTER *v26; // rbx
  PDEVICE_OBJECT v27; // rcx
  int v28; // edx
  struct _KPROCESS *v29; // rbx
  struct _KPROCESS *v30; // rbx
  PACCESS_TOKEN v31; // rax
  void *v32; // rbx
  struct _KPROCESS *RequestorProcess; // rbx
  HANDLE ProcessId; // rax
  _QWORD *v35; // r15
  int ProcessContextFromTokenAttribute; // r13d
  unsigned __int64 v37; // r12
  char *v38; // rbx
  _QWORD *v39; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v41; // rcx
  int v42; // eax
  __int64 (__fastcall *v43)(_QWORD); // rax
  int v44; // eax
  NTSTATUS v45; // eax
  struct _SLIST_ENTRY *Next; // rcx
  __int64 v47; // r8
  int v48; // eax
  struct _FLT_FILTER *v49; // rbx
  struct _FLT_FILTER *v50; // rbx
  __int64 v51; // rcx
  struct _SLIST_ENTRY *v52; // rcx
  ULONG_PTR v53; // r14
  USHORT v54; // bx
  unsigned __int64 v55; // r14
  struct _FLT_FILTER *v56; // rbx
  int v57; // eax
  _DWORD *v58; // rcx
  int UserSid; // eax
  _DWORD *v60; // r12
  struct _KPROCESS *v61; // rax
  int ProcessContextByObject; // eax
  NTSTATUS FileNameInformation; // eax
  __int64 v64; // rdx
  PECP_LIST v65; // rcx
  int v66; // eax
  __int64 v67; // rcx
  ULONG Options; // [rsp+30h] [rbp-49h]
  ULONG v69; // [rsp+34h] [rbp-45h]
  int v70; // [rsp+38h] [rbp-41h]
  PECP_LIST EcpList; // [rsp+48h] [rbp-31h] BYREF
  PVOID EcpContext; // [rsp+50h] [rbp-29h] BYREF
  PFLT_CONTEXT v74; // [rsp+58h] [rbp-21h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-19h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int8 CopyOnOpen[2]; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int8 EffectiveOnly[2]; // [rsp+7Ah] [rbp+1h] BYREF
  ULONG EcpContextSize; // [rsp+7Ch] [rbp+3h] BYREF
  unsigned __int64 LowLimit; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 HighLimit; // [rsp+88h] [rbp+Fh] BYREF

  Context = 0;
  v3 = 0;
  LowLimit = 0;
  Iopb = Data->Iopb;
  HighLimit = 0;
  v74 = a2;
  TargetFileObject = (unsigned __int64)Iopb->TargetFileObject;
  Options = Iopb->Parameters.Create.Options;
  v69 = HIBYTE(Options);
  v70 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  if ( !TargetFileObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids, Data->Thread);
    return 1;
  }
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( TargetFileObject > LowLimit && TargetFileObject < HighLimit )
    return 1;
  OperationFlags = Data->Iopb->OperationFlags;
  if ( (OperationFlags & 2) != 0 )
  {
    if ( (unsigned int)MpHardenPageFileCreate(Data) != 1835009 )
      return 1;
    v21 = 4;
    goto LABEL_47;
  }
  if ( (OperationFlags & 4) != 0 )
    return 1;
  if ( (*(_DWORD *)(MpData + 864) & 4) != 0 )
  {
    v26 = a2[1];
    EcpList = 0;
    EcpContext = 0;
    EcpContextSize = 0;
    if ( FltGetEcpListFromCallbackData(v26, Data, &EcpList) >= 0 )
    {
      if ( EcpList )
      {
        _mm_lfence();
        if ( FltFindExtraCreateParameter(v26, EcpList, &GUID_ECP_CSV_DOWN_LEVEL_OPEN, &EcpContext, &EcpContextSize) >= 0 )
        {
          _mm_lfence();
          if ( !FltIsEcpFromUserMode(v26, EcpContext) )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
            {
              return 1;
            }
            v28 = 12;
LABEL_68:
            WPP_SF_qZ(
              v27->AttachedDevice,
              v28,
              (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              Data->Thread,
              TargetFileObject + 88);
            return 1;
          }
        }
      }
    }
  }
  if ( (*(_DWORD *)(MpData + 864) & 0x40) != 0 )
  {
    v49 = a2[1];
    EcpList = 0;
    EcpContext = 0;
    EcpContextSize = 0;
    if ( FltGetEcpListFromCallbackData(v49, Data, &EcpList) >= 0 )
    {
      if ( EcpList )
      {
        _mm_lfence();
        if ( FltFindExtraCreateParameter(v49, EcpList, &GUID_ECP_MSSECFLT_OPEN, &EcpContext, &EcpContextSize) >= 0 )
        {
          _mm_lfence();
          if ( !FltIsEcpFromUserMode(v49, EcpContext) )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
            {
              return 1;
            }
            v28 = 13;
            goto LABEL_68;
          }
        }
      }
    }
    v50 = a2[1];
    EcpList = 0;
    EcpContext = 0;
    EcpContextSize = 0;
    if ( FltGetEcpListFromCallbackData(v50, Data, &EcpList) >= 0 )
    {
      if ( EcpList )
      {
        _mm_lfence();
        if ( FltFindExtraCreateParameter(v50, EcpList, &GUID_WDD_ECP_WDDEVFLT_OPEN, &EcpContext, &EcpContextSize) >= 0 )
        {
          _mm_lfence();
          if ( !FltIsEcpFromUserMode(v50, EcpContext) )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
            {
              return 1;
            }
            v28 = 14;
            goto LABEL_68;
          }
        }
      }
    }
  }
  v10 = a2[1];
  EcpList = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  if ( FltGetEcpListFromCallbackData(v10, Data, &EcpList) >= 0 )
  {
    if ( EcpList )
    {
      _mm_lfence();
      if ( FltFindExtraCreateParameter(v10, EcpList, &GUID_MP_ECP_QUERY_EA, &EcpContext, &EcpContextSize) >= 0 )
      {
        _mm_lfence();
        if ( !FltIsEcpFromUserMode(v10, EcpContext) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_qZ(
              WPP_GLOBAL_Control->AttachedDevice,
              15,
              (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              Data->Thread,
              TargetFileObject + 88);
          }
          result = MpHandleQueryEaEcpPreCreate(Data, a2);
          *a3 = 0;
          return result;
        }
      }
    }
  }
  v11 = MpData + 896;
  v12 = (union _SLIST_HEADER *)(MpData + 896);
  ++*(_DWORD *)(MpData + 916);
  v3 = ExpInterlockedPopEntrySList(v12);
  if ( !v3 )
  {
    ++*(_DWORD *)(v11 + 24);
    v3 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v11 + 48))(
                         *(unsigned int *)(v11 + 36),
                         *(unsigned int *)(v11 + 44),
                         *(unsigned int *)(v11 + 40));
  }
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids, Data->Thread);
    return 1;
  }
  memset(v3, 0, 0xF8u);
  v13 = *(struct _FLT_FILTER **)(MpData + 16);
  EcpContext = 0;
  EcpList = 0;
  EcpContextSize = 0;
  if ( FltGetEcpListFromCallbackData(v13, Data, (PECP_LIST *)&EcpContext) >= 0 )
  {
    if ( EcpContext )
    {
      _mm_lfence();
      if ( FltFindExtraCreateParameter(
             v13,
             (PECP_LIST)EcpContext,
             &GUID_ECP_SRV_OPEN,
             (PVOID *)&EcpList,
             &EcpContextSize) >= 0 )
      {
        _mm_lfence();
        if ( !FltIsEcpFromUserMode(v13, EcpList) )
        {
          if ( (unsigned __int8)MpIsPotentialRemoteOpen(Data) )
          {
            if ( (*(_DWORD *)(MpData + 868) & 0x800) != 0 )
            {
              *((_BYTE *)&v3[1].Next + 8) = 1;
              UserSid = MpMjCreateGetUserSid(Data, (char *)&v3[10].Next + 2);
              if ( UserSid < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  _mm_lfence();
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
                    Data->Thread,
                    UserSid);
                }
              }
              else
              {
                *((_DWORD *)&v3[1].Next + 3) |= 2u;
              }
              CopyOnOpen[0] = 0;
              EffectiveOnly[0] = 0;
              if ( (int)MpIsSrvClientLocalhost(EcpList, EcpContextSize, CopyOnOpen, &v3[2], 65, EffectiveOnly) >= 0
                && CopyOnOpen[0] )
              {
                v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x2000);
              }
              if ( EffectiveOnly[0] )
                *((_DWORD *)&v3[1].Next + 3) |= 1u;
            }
            else
            {
              v64 = EcpContextSize;
              v65 = EcpList;
              EffectiveOnly[0] = 0;
              *((_BYTE *)&v3[1].Next + 8) = 0;
              if ( (int)MpIsSrvClientLocalhost(v65, v64, EffectiveOnly, 0, 0, 0) >= 0 && EffectiveOnly[0] )
                v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x2000);
            }
          }
        }
      }
    }
  }
  v14 = *(struct _FLT_FILTER **)(MpData + 16);
  EcpContext = 0;
  EcpList = 0;
  EcpContextSize = 0;
  if ( FltGetEcpListFromCallbackData(v14, Data, (PECP_LIST *)&EcpContext) >= 0 )
  {
    if ( EcpContext )
    {
      _mm_lfence();
      if ( FltFindExtraCreateParameter(
             v14,
             (PECP_LIST)EcpContext,
             &GUID_ECP_PREFETCH_OPEN,
             (PVOID *)&EcpList,
             &EcpContextSize) >= 0 )
      {
        _mm_lfence();
        if ( !FltIsEcpFromUserMode(v14, EcpList) )
        {
          v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x20);
          *a3 = v3;
          return 5;
        }
      }
    }
  }
  InstanceContext = FltGetInstanceContext(a2[3], &Context);
  if ( InstanceContext < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        Data->Thread,
        InstanceContext);
    }
    goto LABEL_46;
  }
  if ( (*(_DWORD *)(TargetFileObject + 80) & 0x400000) != 0 )
  {
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 1);
    if ( *(_WORD *)(TargetFileObject + 88) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          Data->Thread,
          TargetFileObject + 88);
    }
  }
  if ( (*(_DWORD *)(MpData + 864) & 0x10) != 0 )
  {
    v56 = *(struct _FLT_FILTER **)(MpData + 16);
    EcpContext = 0;
    EcpList = 0;
    EcpContextSize = 0;
    if ( FltGetEcpListFromCallbackData(v56, Data, (PECP_LIST *)&EcpContext) >= 0 )
    {
      if ( EcpContext )
      {
        _mm_lfence();
        if ( FltFindExtraCreateParameter(
               v56,
               (PECP_LIST)EcpContext,
               &GUID_ECP_CREATE_USER_PROCESS,
               (PVOID *)&EcpList,
               &EcpContextSize) >= 0 )
        {
          _mm_lfence();
          if ( !FltIsEcpFromUserMode(v56, EcpList) )
            v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x4000);
        }
      }
    }
  }
  v16 = Data;
  CurrentProcess = IoGetCurrentProcess();
  if ( !MpDlpData )
  {
    LOBYTE(CurrentProcess) = 0;
    goto LABEL_27;
  }
  if ( (unsigned __int64)(&Data[-1].RequestorMode + 7) <= 1 )
    v16 = 0;
  if ( !*((_BYTE *)MpDlpData + 32) )
  {
    LOBYTE(CurrentProcess) = 0;
    goto LABEL_27;
  }
  if ( (*(_DWORD *)(MpData + 864) & 0x400) == 0 )
  {
    LOBYTE(CurrentProcess) = 0;
    goto LABEL_27;
  }
  if ( !*(_QWORD *)(MpData + 320) && !*(_QWORD *)(MpData + 336) )
  {
    LOBYTE(CurrentProcess) = 0;
    goto LABEL_27;
  }
  v29 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v29
    || (v30 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v30) )
  {
    LOBYTE(CurrentProcess) = (unsigned __int64)(&Data[-1].RequestorMode + 7) <= 1;
    goto LABEL_27;
  }
  if ( !v16 || (CurrentProcess = (struct _KPROCESS *)MpGetRequestorProcess(v16)) != 0 )
  {
    if ( PsInitialSystemProcess == CurrentProcess
      && !(unsigned __int8)MpIsPotentialRemoteOpen(v16)
      && Data != (PFLT_CALLBACK_DATA)2 )
    {
      LOBYTE(CurrentProcess) = 0;
      goto LABEL_27;
    }
    EcpList = 0;
    if ( !v16 )
      goto LABEL_150;
    CopyOnOpen[0] = 0;
    EffectiveOnly[0] = 0;
    EcpContextSize = 0;
    v31 = PsReferenceImpersonationToken(
            KeGetCurrentThread(),
            CopyOnOpen,
            EffectiveOnly,
            (PSECURITY_IMPERSONATION_LEVEL)&EcpContextSize);
    v32 = v31;
    if ( v31 )
    {
      EcpContext = 0;
      ProcessContextFromTokenAttribute = MpDlpGetProcessContextFromTokenAttribute(v31, &EcpContext);
      if ( ProcessContextFromTokenAttribute < 0 )
      {
        PsDereferenceImpersonationToken(v32);
        EcpList = 0;
      }
      else
      {
        v60 = EcpContext;
        EcpList = (PECP_LIST)EcpContext;
        PsDereferenceImpersonationToken(v32);
        if ( v60 )
          goto LABEL_193;
      }
    }
    RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(v16);
    *(_QWORD *)&String1.Length = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    ProcessId = PsGetProcessId(RequestorProcess);
    v35 = 0;
    ProcessContextFromTokenAttribute = -1073741275;
    EcpContext = 0;
    v37 = (unsigned __int64)ProcessId;
    if ( ProcessId )
    {
      v38 = (char *)MpProcessTable;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)(v38 + 8), 1u);
      v39 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((v37 >> 2) & 0x7F));
      for ( i = (_QWORD *)*v39; i != v39; i = (_QWORD *)*i )
      {
        v41 = (volatile signed __int32 *)(i - 1);
        if ( v37 == i[2] && *(_QWORD *)&String1.Length == *((_QWORD *)v41 + 4) )
        {
          _InterlockedIncrement(v41 + 12);
          v35 = i - 1;
          EcpContext = i - 1;
          ProcessContextFromTokenAttribute = 0;
          break;
        }
      }
      ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
      KeLeaveCriticalRegion();
      if ( ProcessContextFromTokenAttribute >= 0 )
      {
        if ( v35 )
          goto LABEL_148;
      }
    }
    v61 = IoGetCurrentProcess();
    ProcessContextByObject = MpGetProcessContextByObject(v61);
    v35 = EcpContext;
    ProcessContextFromTokenAttribute = ProcessContextByObject;
    if ( EcpContext )
    {
LABEL_148:
      v58 = v35;
      if ( ProcessContextFromTokenAttribute < 0 )
        goto LABEL_149;
      v60 = v35;
LABEL_183:
      if ( !v60 )
        goto LABEL_150;
      if ( (v60[14] & 0x40000000) != 0 || v60[60] == 33 )
      {
        MpReleaseProcessContext(v58);
        LOBYTE(CurrentProcess) = 0;
        goto LABEL_27;
      }
LABEL_149:
      MpReleaseProcessContext(v58);
LABEL_150:
      LOBYTE(CurrentProcess) = 1;
      goto LABEL_27;
    }
    v60 = EcpList;
LABEL_193:
    v58 = v60;
    if ( ProcessContextFromTokenAttribute < 0 )
      goto LABEL_150;
    goto LABEL_183;
  }
LABEL_27:
  if ( (v70 & 0x20D0156) != 0 || v69 != 1 || (Options & 0x1000) != 0 )
  {
    v18 = v74;
    if ( ((__int64)v3->Next & 1) != 0 )
    {
      MpHardenSectorWrites(Data);
    }
    else
    {
      v57 = MpHardenPathOnPreCreate(Data, v74, Context, v3);
      if ( v57 == 1835009 )
      {
        v21 = 4;
        goto LABEL_47;
      }
      if ( v57 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          Data->Thread,
          v57);
      }
    }
  }
  else
  {
    v18 = v74;
  }
  if ( *((int *)Context + 20) < 0 )
  {
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 8);
    if ( !(_BYTE)CurrentProcess )
    {
      if ( ((__int64)v3->Next & 0x8010) == 0 )
      {
        v21 = 1;
        goto LABEL_47;
      }
      goto LABEL_103;
    }
  }
  else if ( !(_BYTE)CurrentProcess )
  {
    goto LABEL_33;
  }
  if ( (Options & 1) == 0 && ((__int64)v3->Next & 1) == 0 && v69 != 1 && (*((_DWORD *)Context + 21) & 0x810) != 0 )
  {
    if ( (unsigned int)MpDlpPreCreate(Data) == 2 )
    {
      if ( Data->IoStatus.Status >= 0 )
        Data->IoStatus.Status = dword_140026538;
      v21 = 4;
      goto LABEL_47;
    }
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x800);
  }
LABEL_33:
  v19 = *(_WORD *)(TargetFileObject + 88) == 0;
  if ( *(_WORD *)(TargetFileObject + 88) )
    goto LABEL_34;
  if ( !*(_QWORD *)(TargetFileObject + 64) )
  {
LABEL_196:
    v19 = *(_WORD *)(TargetFileObject + 88) == 0;
    goto LABEL_34;
  }
  v74 = 0;
  FileNameInformation = FltGetFileNameInformation(Data, 0x102u, (PFLT_FILE_NAME_INFORMATION *)&v74);
  if ( FileNameInformation == -1073741202 )
  {
    v67 = *(_QWORD *)(*(_QWORD *)(TargetFileObject + 64) + 16LL);
    String1 = 0;
    if ( v67 )
    {
      String1.MaximumLength = *(_WORD *)(v67 + 6);
      String1.Length = String1.MaximumLength;
      String1.Buffer = (PWSTR)(v67 + 32);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        Data->Thread,
        (__int64)&String1);
      v21 = 1;
      goto LABEL_47;
    }
    goto LABEL_46;
  }
  if ( FileNameInformation < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        Data->Thread,
        FileNameInformation);
    }
    goto LABEL_196;
  }
  String1 = *(UNICODE_STRING *)((char *)v74 + 8);
  if ( !(unsigned __int8)MpIsUnNamedDataAttribute(&String1) )
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 2);
  FltReleaseFileNameInformation((PFLT_FILE_NAME_INFORMATION)v74);
  v19 = *(_WORD *)(TargetFileObject + 88) == 0;
LABEL_34:
  if ( !v19 && (Options & 0x2000) == 0 )
  {
    v20 = _mm_cvtsi128_si32(*(__m128i *)(TargetFileObject + 88));
    String1 = *(UNICODE_STRING *)(TargetFileObject + 88);
    if ( v20 )
    {
      while ( String1.Buffer[((unsigned __int64)v20 >> 1) - 1] == 92 )
      {
        v20 -= 2;
        if ( !v20 )
          goto LABEL_39;
      }
      v23 = v20 >> 1;
      if ( v20 >> 1 )
      {
        do
        {
          if ( String1.Buffer[v23 - 1] == 92 )
            break;
          --v23;
        }
        while ( v23 );
      }
      while ( v23 < (unsigned __int16)(v20 >> 1) )
      {
        v24 = v23;
        v25 = 2LL * v23;
        if ( String1.Buffer[v25 / 2] == 58 )
        {
          v55 = v20;
          if ( v20 - v25 == 14 )
          {
            String1.Buffer = (PWSTR)((char *)String1.Buffer + v25);
            *(_QWORD *)&String1.Length = 917518;
            if ( RtlEqualUnicodeString(&String1, &_DATA, 1u) )
              break;
          }
          if ( v24 == (v55 >> 1) - 1 )
            break;
          goto LABEL_39;
        }
        ++v23;
      }
    }
    else
    {
LABEL_39:
      v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 2);
    }
  }
  if ( (v70 & 0x2000021) != 0 )
  {
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x40);
    goto LABEL_83;
  }
  if ( (v70 & 0x106) != 0 )
  {
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 4);
    goto LABEL_83;
  }
  if ( (v70 & 0x10000) != 0 )
  {
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x100);
LABEL_83:
    v74 = 0;
    if ( (*(_DWORD *)(MpData + 868) & 0x10) != 0 )
    {
      v42 = *(_DWORD *)(MpData + 864);
      if ( (v42 & 4) != 0 )
      {
        if ( (v42 & 0x10) != 0
          && (v43 = *(__int64 (__fastcall **)(_QWORD))(MpData + 192)) != 0
          && v43(*((_QWORD *)v18 + 4))
          || (*(_DWORD *)(MpData + 864) & 0x80u) != 0 )
        {
          v44 = MpAddECP(Data, &GUID_ECP_CREATE_REDIRECTION, *(unsigned int *)(MpData + 1920));
          if ( v44 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            _mm_lfence();
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids,
              (unsigned int)v44);
          }
        }
        v45 = FltGetInstanceContext(*((PFLT_INSTANCE *)v18 + 3), &v74);
        if ( v45 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids,
              (unsigned int)v45);
          }
        }
        else
        {
          if ( *((_DWORD *)v74 + 30) == 27 && dword_140026A00 == 1 )
          {
            v66 = MpAddECP(Data, &GUID_ECP_CSV_QUERY_FILE_REVISION, *(unsigned int *)(MpData + 1920));
            if ( v66 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              _mm_lfence();
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                23,
                WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids,
                (unsigned int)v66);
            }
          }
          FltReleaseContext(v74);
        }
      }
    }
    if ( *(_QWORD *)(MpData + 88) )
    {
      Next = v3->Next;
      if ( ((__int64)v3->Next & 1) == 0 )
      {
        v47 = 9;
        if ( (_BYTE)CurrentProcess && ((unsigned __int8)Next & 2) == 0 )
        {
          v47 = (*(_DWORD *)(MpData + 864) & 0x800 | 0x1200u) >> 9;
          v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)Next | 0x200);
        }
        v48 = (*(__int64 (__fastcall **)(_QWORD, PFLT_CALLBACK_DATA, __int64))(MpData + 88))(
                *(_QWORD *)(MpData + 16),
                Data,
                v47);
        if ( v48 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            Data->Thread,
            v48);
        }
      }
    }
LABEL_103:
    v21 = 5;
    *a3 = v3;
    v3 = 0;
    goto LABEL_47;
  }
  if ( (v70 & 0xC0000) != 0 )
  {
    v3->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v3->Next | 0x400);
    goto LABEL_83;
  }
LABEL_46:
  v21 = 1;
LABEL_47:
  if ( Context )
    FltReleaseContext(Context);
  if ( v3 )
  {
    v51 = *((_QWORD *)&v3->Next + 1);
    if ( v51 )
      MpFreeString(v51);
    v52 = v3[1].Next;
    if ( v52 )
      MpFreeString(v52);
    v53 = MpData + 896;
    ++*(_DWORD *)(MpData + 924);
    v54 = *(_WORD *)(v53 + 16);
    if ( ExQueryDepthSList((PSLIST_HEADER)v53) >= v54 )
    {
      ++*(_DWORD *)(v53 + 32);
      (*(void (__fastcall **)(PSLIST_ENTRY))(v53 + 56))(v3);
    }
    else
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v53, v3);
    }
  }
  return v21;
}

```

## disassembly

```asm
0x14003c990  mov     [rsp-8+arg_18], rbx
0x14003c995  push    rbp
0x14003c996  push    rsi
0x14003c997  push    rdi
0x14003c998  push    r12
0x14003c99a  push    r13
0x14003c99c  push    r14
0x14003c99e  push    r15
0x14003c9a0  lea     rbp, [rsp-27h]
0x14003c9a5  sub     rsp, 0A0h
0x14003c9ac  mov     rax, cs:__security_cookie
0x14003c9b3  xor     rax, rsp
0x14003c9b6  mov     [rbp+57h+var_40], rax
0x14003c9ba  xor     eax, eax
0x14003c9bc  mov     [rbp+57h+var_90], r8
0x14003c9c0  mov     [rbp+57h+Context], rax
0x14003c9c4  mov     esi, eax
0x14003c9c6  mov     [rbp+57h+LowLimit], rax
0x14003c9ca  mov     rdi, rcx
0x14003c9cd  mov     rcx, [rcx+10h]
0x14003c9d1  mov     r13, r8
0x14003c9d4  mov     [rbp+57h+HighLimit], rax
0x14003c9d8  mov     r15, rdx
0x14003c9db  mov     [rbp+57h+var_78], rdx
0x14003c9df  mov     eax, [rcx+20h]
0x14003c9e2  mov     r14, [rcx+8]
0x14003c9e6  mov     [rbp+57h+var_A0], eax
0x14003c9e9  shr     eax, 18h
0x14003c9ec  mov     [rbp+57h+var_9C], eax
0x14003c9ef  mov     rax, [rcx+18h]
0x14003c9f3  mov     eax, [rax+10h]
0x14003c9f6  mov     [rbp+57h+var_98], eax
0x14003c9f9  test    r14, r14
0x14003c9fc  jz      loc_14003DAFF
0x14003ca02  lea     rdx, [rbp+57h+HighLimit]; HighLimit
0x14003ca06  lea     rcx, [rbp+57h+LowLimit]; LowLimit
0x14003ca0a  lea     r12, [r14+58h]
0x14003ca0e  call    cs:__imp_IoGetStackLimits
0x14003ca15  nop     dword ptr [rax+rax+00h]
0x14003ca1a  cmp     r14, [rbp+57h+LowLimit]
0x14003ca1e  ja      loc_14003CDAE
0x14003ca24  mov     rax, [rdi+10h]
0x14003ca28  movzx   ecx, byte ptr [rax+6]
0x14003ca2c  test    cl, 2
0x14003ca2f  jnz     loc_14003CD91
0x14003ca35  test    cl, 4
0x14003ca38  jnz     loc_14003D812
0x14003ca3e  mov     rax, cs:MpData
0x14003ca45  mov     ecx, [rax+360h]
0x14003ca4b  test    cl, 4
0x14003ca4e  jnz     loc_14003CE16
0x14003ca54  mov     rax, cs:MpData
0x14003ca5b  mov     ecx, [rax+360h]
0x14003ca61  test    cl, 40h
0x14003ca64  jnz     loc_14003D21E
0x14003ca6a  mov     rbx, [r15+8]
0x14003ca6e  lea     r8, [rbp+57h+EcpList]; EcpList
0x14003ca72  mov     rcx, rbx; Filter
0x14003ca75  mov     [rbp+57h+EcpList], rsi
0x14003ca79  mov     rdx, rdi; CallbackData
0x14003ca7c  mov     [rbp+57h+EcpContext], rsi
0x14003ca80  mov     [rbp+57h+var_54], esi
0x14003ca83  call    cs:__imp_FltGetEcpListFromCallbackData
0x14003ca8a  nop     dword ptr [rax+rax+00h]
0x14003ca8f  test    eax, eax
0x14003ca91  js      short loc_14003CACC
0x14003ca93  cmp     [rbp+57h+EcpList], 0
0x14003ca98  jz      short loc_14003CACC
0x14003ca9a  lfence
0x14003ca9d  mov     rdx, [rbp+57h+EcpList]; EcpList
0x14003caa1  lea     rax, [rbp+57h+var_54]
0x14003caa5  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x14003caa9  mov     [rsp+0D0h+EcpContextSize], rax; EcpContextSize
0x14003caae  lea     r8, GUID_MP_ECP_QUERY_EA; EcpType
0x14003cab5  mov     rcx, rbx; Filter
0x14003cab8  call    cs:__imp_FltFindExtraCreateParameter
0x14003cabf  nop     dword ptr [rax+rax+00h]
0x14003cac4  test    eax, eax
0x14003cac6  jns     loc_14003D60B
0x14003cacc  mov     rbx, cs:MpData
0x14003cad3  add     rbx, 380h
0x14003cada  mov     rcx, rbx; ListHead
0x14003cadd  inc     dword ptr [rbx+14h]
0x14003cae0  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003cae7  nop     dword ptr [rax+rax+00h]
0x14003caec  mov     rsi, rax
0x14003caef  test    rax, rax
0x14003caf2  jz      loc_14003D504
0x14003caf8  test    rsi, rsi
0x14003cafb  jz      loc_14003D7BF
0x14003cb01  xor     edx, edx; Val
0x14003cb03  mov     r8d, 0F8h; Size
0x14003cb09  mov     rcx, rsi; void *
0x14003cb0c  call    memset
0x14003cb11  mov     rax, cs:MpData
0x14003cb18  lea     r8, [rbp+57h+EcpContext]; EcpList
0x14003cb1c  mov     rdx, rdi; CallbackData
0x14003cb1f  mov     rbx, [rax+10h]
0x14003cb23  xor     eax, eax
0x14003cb25  mov     rcx, rbx; Filter
0x14003cb28  mov     [rbp+57h+EcpContext], rax
0x14003cb2c  mov     [rbp+57h+EcpList], rax
0x14003cb30  mov     [rbp+57h+var_54], eax
0x14003cb33  call    cs:__imp_FltGetEcpListFromCallbackData
0x14003cb3a  nop     dword ptr [rax+rax+00h]
0x14003cb3f  lea     r13, WPP_GLOBAL_Control
0x14003cb46  test    eax, eax
0x14003cb48  js      short loc_14003CB83
0x14003cb4a  cmp     [rbp+57h+EcpContext], 0
0x14003cb4f  jz      short loc_14003CB83
0x14003cb51  lfence
0x14003cb54  mov     rdx, [rbp+57h+EcpContext]; EcpList
0x14003cb58  lea     rax, [rbp+57h+var_54]
0x14003cb5c  lea     r9, [rbp+57h+EcpList]; EcpContext
0x14003cb60  mov     [rsp+0D0h+EcpContextSize], rax; EcpContextSize
0x14003cb65  lea     r8, GUID_ECP_SRV_OPEN; EcpType
0x14003cb6c  mov     rcx, rbx; Filter
0x14003cb6f  call    cs:__imp_FltFindExtraCreateParameter
0x14003cb76  nop     dword ptr [rax+rax+00h]
0x14003cb7b  test    eax, eax
0x14003cb7d  jns     loc_14003D675
0x14003cb83  mov     rax, cs:MpData
0x14003cb8a  lea     r8, [rbp+57h+EcpContext]; EcpList
0x14003cb8e  mov     rdx, rdi; CallbackData
0x14003cb91  mov     rbx, [rax+10h]
0x14003cb95  xor     eax, eax
0x14003cb97  mov     rcx, rbx; Filter
0x14003cb9a  mov     [rbp+57h+EcpContext], rax
0x14003cb9e  mov     [rbp+57h+EcpList], rax
0x14003cba2  mov     [rbp+57h+var_54], eax
0x14003cba5  call    cs:__imp_FltGetEcpListFromCallbackData
0x14003cbac  nop     dword ptr [rax+rax+00h]
0x14003cbb1  test    eax, eax
0x14003cbb3  js      short loc_14003CBEE
0x14003cbb5  cmp     [rbp+57h+EcpContext], 0
0x14003cbba  jz      short loc_14003CBEE
0x14003cbbc  lfence
0x14003cbbf  mov     rdx, [rbp+57h+EcpContext]; EcpList
0x14003cbc3  lea     rax, [rbp+57h+var_54]
0x14003cbc7  lea     r9, [rbp+57h+EcpList]; EcpContext
0x14003cbcb  mov     [rsp+0D0h+EcpContextSize], rax; EcpContextSize
0x14003cbd0  lea     r8, GUID_ECP_PREFETCH_OPEN; EcpType
0x14003cbd7  mov     rcx, rbx; Filter
0x14003cbda  call    cs:__imp_FltFindExtraCreateParameter
0x14003cbe1  nop     dword ptr [rax+rax+00h]
0x14003cbe6  test    eax, eax
0x14003cbe8  jns     loc_14003D721
0x14003cbee  mov     rcx, [r15+18h]; Instance
0x14003cbf2  lea     rdx, [rbp+57h+Context]; Context
0x14003cbf6  call    cs:__imp_FltGetInstanceContext
0x14003cbfd  nop     dword ptr [rax+rax+00h]
0x14003cc02  test    eax, eax
0x14003cc04  js      loc_14003CD34
0x14003cc0a  test    dword ptr [r14+50h], 400000h
0x14003cc12  jnz     loc_14003D920
0x14003cc18  mov     rcx, cs:MpData
0x14003cc1f  mov     eax, [rcx+360h]
0x14003cc25  test    al, 10h
0x14003cc27  jnz     loc_14003D453
0x14003cc2d  mov     r15, rdi
0x14003cc30  call    cs:__imp_IoGetCurrentProcess
0x14003cc37  nop     dword ptr [rax+rax+00h]
0x14003cc3c  mov     rcx, cs:MpDlpData
0x14003cc43  mov     r12, rax
0x14003cc46  test    rcx, rcx
0x14003cc49  jz      loc_14003DBDF
0x14003cc4f  lea     rax, [rdi-1]
0x14003cc53  cmp     rax, 1
0x14003cc57  jbe     loc_14003DA3B
0x14003cc5d  movzx   eax, byte ptr [rcx+20h]
0x14003cc61  test    al, al
0x14003cc63  jnz     loc_14003CEE2
0x14003cc69  xor     r12b, r12b
0x14003cc6c  test    [rbp+57h+var_98], 20D0156h
0x14003cc73  mov     ebx, [rbp+57h+var_9C]
0x14003cc76  mov     r13d, [rbp+57h+var_A0]
0x14003cc7a  jnz     loc_14003D523
0x14003cc80  cmp     ebx, 1
0x14003cc83  jnz     loc_14003D523
0x14003cc89  bt      r13d, 0Ch
0x14003cc8e  jb      loc_14003D523
0x14003cc94  mov     r15, [rbp+57h+var_78]
0x14003cc98  mov     rax, [rbp+57h+Context]
0x14003cc9c  cmp     dword ptr [rax+50h], 0
0x14003cca0  jl      loc_14003D1ED
0x14003cca6  test    r12b, r12b
0x14003cca9  jnz     loc_14003D403
0x14003ccaf  cmp     word ptr [r14+58h], 0
0x14003ccb5  jz      loc_14003D90E
0x14003ccbb  jbe     short loc_14003CCFE
0x14003ccbd  bt      r13d, 0Dh
0x14003ccc2  jb      short loc_14003CCFE
0x14003ccc4  movups  xmm0, xmmword ptr [r14+58h]
0x14003ccc9  movd    r9d, xmm0
0x14003ccce  movaps  xmmword ptr [rbp+57h+String1.Length], xmm0
0x14003ccd2  test    r9w, r9w
0x14003ccd6  jz      short loc_14003CCFA
0x14003ccd8  mov     rdx, [rbp+57h+String1.Buffer]
0x14003ccdc  mov     ecx, 0FFFEh
0x14003cce1  movzx   eax, r9w
0x14003cce5  shr     rax, 1
0x14003cce8  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x14003ccee  jnz     loc_14003CDBD
0x14003ccf4  add     r9w, cx
0x14003ccf8  jnz     short loc_14003CCE1
0x14003ccfa  or      qword ptr [rsi], 2
0x14003ccfe  mov     eax, [rbp+57h+var_98]
0x14003cd01  test    eax, 2000021h
0x14003cd06  jnz     loc_14003D06C
0x14003cd0c  test    eax, 106h
0x14003cd11  jnz     loc_14003D79D
0x14003cd17  bt      eax, 10h
0x14003cd1b  jb      loc_14003D81C
0x14003cd21  test    eax, 0C0000h
0x14003cd26  jz      short loc_14003CD44
0x14003cd28  or      qword ptr [rsi], 400h
0x14003cd2f  jmp     loc_14003D070
0x14003cd34  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd3b  cmp     rcx, r13
0x14003cd3e  jnz     loc_14003DBA7
0x14003cd44  mov     edi, 1
0x14003cd49  mov     rcx, [rbp+57h+Context]; Context
0x14003cd4d  test    rcx, rcx
0x14003cd50  jz      short loc_14003CD5E
0x14003cd52  call    cs:__imp_FltReleaseContext
0x14003cd59  nop     dword ptr [rax+rax+00h]
0x14003cd5e  test    rsi, rsi
0x14003cd61  jnz     loc_14003D334
0x14003cd67  mov     eax, edi
0x14003cd69  mov     rcx, [rbp+57h+var_40]
0x14003cd6d  xor     rcx, rsp; StackCookie
0x14003cd70  call    __security_check_cookie
0x14003cd75  mov     rbx, [rsp+0D0h+arg_18]
0x14003cd7d  add     rsp, 0A0h
0x14003cd84  pop     r15
0x14003cd86  pop     r14
0x14003cd88  pop     r13
0x14003cd8a  pop     r12
0x14003cd8c  pop     rdi
0x14003cd8d  pop     rsi
0x14003cd8e  pop     rbp
0x14003cd8f  retn
0x14003cd91  mov     rdx, r15
0x14003cd94  mov     rcx, rdi; CallbackData
0x14003cd97  call    MpHardenPageFileCreate
0x14003cd9c  cmp     eax, 1C0001h
0x14003cda1  jnz     loc_14003D812
0x14003cda7  mov     edi, 4
0x14003cdac  jmp     short loc_14003CD49
0x14003cdae  cmp     r14, [rbp+57h+HighLimit]
0x14003cdb2  jnb     loc_14003CA24
0x14003cdb8  jmp     loc_14003D812
0x14003cdbd  test    r9w, r9w
0x14003cdc1  jz      loc_14003CCFA
0x14003cdc7  movzx   r10d, r9w
0x14003cdcb  shr     r10w, 1
0x14003cdcf  movzx   eax, r10w
0x14003cdd3  jz      short loc_14003CDF1
0x14003cdd5  mov     r8d, 0FFFFh
0x14003cddb  nop     dword ptr [rax+rax+00h]
0x14003cde0  movzx   ecx, ax
0x14003cde3  cmp     word ptr [rdx+rcx*2-2], 5Ch ; '\'
0x14003cde9  jz      short loc_14003CDF1
0x14003cdeb  add     ax, r8w
0x14003cdef  jnz     short loc_14003CDE0
0x14003cdf1  cmp     ax, r10w
0x14003cdf5  jnb     loc_14003CCFE
0x14003cdfb  movzx   ebx, ax
0x14003cdfe  lea     rcx, [rbx+rbx]
0x14003ce02  cmp     word ptr [rdx+rcx], 3Ah ; ':'
0x14003ce07  lea     r8, [rdx+rcx]
0x14003ce0b  jz      loc_14003D397
0x14003ce11  inc     ax
0x14003ce14  jmp     short loc_14003CDF1
0x14003ce16  mov     rbx, [r15+8]
0x14003ce1a  lea     r8, [rbp+57h+EcpList]; EcpList
0x14003ce1e  mov     rcx, rbx; Filter
0x14003ce21  mov     [rbp+57h+EcpList], rsi
0x14003ce25  mov     rdx, rdi; CallbackData
0x14003ce28  mov     [rbp+57h+EcpContext], rsi
0x14003ce2c  mov     [rbp+57h+var_54], esi
0x14003ce2f  call    cs:__imp_FltGetEcpListFromCallbackData
0x14003ce36  nop     dword ptr [rax+rax+00h]
0x14003ce3b  test    eax, eax
0x14003ce3d  js      loc_14003CA54
0x14003ce43  cmp     [rbp+57h+EcpList], rsi
0x14003ce47  jz      loc_14003CA54
0x14003ce4d  lfence
0x14003ce50  mov     rdx, [rbp+57h+EcpList]; EcpList
0x14003ce54  lea     rax, [rbp+57h+var_54]
0x14003ce58  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x14003ce5c  mov     [rsp+0D0h+EcpContextSize], rax; EcpContextSize
0x14003ce61  lea     r8, GUID_ECP_CSV_DOWN_LEVEL_OPEN; EcpType
0x14003ce68  mov     rcx, rbx; Filter
0x14003ce6b  call    cs:__imp_FltFindExtraCreateParameter
0x14003ce72  nop     dword ptr [rax+rax+00h]
0x14003ce77  test    eax, eax
0x14003ce79  js      loc_14003CA54
0x14003ce7f  lfence
0x14003ce82  mov     rdx, [rbp+57h+EcpContext]; EcpContext
  ... truncated ...
```
