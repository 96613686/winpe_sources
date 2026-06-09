# xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)

- ea: `0x1400ea7ac`
- end: `0x1400eb6ed`
- name: `?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z`
- size: `3905`
- prototype: ``
- caller_count: `10`
- callee_count: `27`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400dcbf0`
- `0x1400ea480`
- `0x1400eb740`
- `0x14012a40c`
- `0x14012a6a0`
- `0x14012a910`
- `0x14018f810`
- `0x1401ac3e4`
- `0x1402700a0`
- `0x14027b8f0`

## callees

- `0x14000a36c`
- `0x14000a408`
- `0x14001d1b4`
- `0x14001ea78`
- `0x14001eb04`
- `0x1400235ec`
- `0x1400241fc`
- `0x140033b58`
- `0x1400da990`
- `0x1400dbb50`
- `0x1400dc6cc`
- `0x1400dcb70`
- `0x1400dcda8`
- `0x1400dcfb0`
- `0x1400dd4c8`
- `0x1400e2cb0`
- `0x1400ea480`
- `0x1400ea7ac`
- `0x140144bf0`
- `0x140154e10`
- `0x140168e94`
- `0x14018935c`
- `0x14018bdb0`
- `0x14018f510`
- `0x1401ab494`
- `0x1402aae84`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationProcess` at `0x1400eae47`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400eae47`
- `ntoskrnl!PsGetProcessMachine` at `0x1400ea9c2`
- `ntoskrnl!PsGetProcessMachine` at `0x1400ea9db`
- `ntoskrnl!PsGetProcessMachine` at `0x1400eaa8c`
- `ntoskrnl!PsGetProcessMachine` at `0x1400eaaa5`
- `ntoskrnl!PsGetProcessMachine` at `0x1400ea9c2`
- `ntoskrnl!PsGetProcessMachine` at `0x1400ea9db`
- `ntoskrnl!PsGetProcessMachine` at `0x1400eaa8c`
- `ntoskrnl!PsGetProcessMachine` at `0x1400eaaa5`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400eae98`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400eae98`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400eaeac`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400eaeac`
- `ntoskrnl!PsGetThreadId` at `0x1400eaf72`
- `ntoskrnl!PsGetThreadId` at `0x1400eb574`
- `ntoskrnl!PsGetThreadId` at `0x1400eaf72`
- `ntoskrnl!PsGetThreadId` at `0x1400eb574`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400eae89`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400eae89`
- `win32kbase!IsKeyboardDelegationEnabledForThread` at `0x1400ea929`
- `win32kbase!IsKeyboardDelegationEnabledForThread` at `0x1400ea929`
- `win32kbase!IsRestricted` at `0x1400eaa56`
- `win32kbase!IsRestricted` at `0x1400eab9c`
- `win32kbase!IsRestricted` at `0x1400eaa56`
- `win32kbase!IsRestricted` at `0x1400eab9c`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1400ead34`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1400ead34`
- `win32kbase!EtwTraceUIPIHookError` at `0x1400eac35`
- `win32kbase!EtwTraceUIPIHookError` at `0x1400eac35`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x1400eb283`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x1400eb283`
- `win32kbase!IsImmersiveBroker` at `0x1400eadd4`
- `win32kbase!IsImmersiveBroker` at `0x1400eadd4`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x1400eab05`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x1400eab05`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400eb24d`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400eb261`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400eb24d`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400eb261`
- `win32kbase!IsProcessDwm` at `0x1400eaa27`
- `win32kbase!IsProcessDwm` at `0x1400eaaf1`
- `win32kbase!IsProcessDwm` at `0x1400eaa27`
- `win32kbase!IsProcessDwm` at `0x1400eaaf1`
- `win32kbase!luidSystem` at `0x1400eab69`
- `win32kbase!IsSpatialDelegationEnabledForThread` at `0x1400ea8fa`
- `win32kbase!IsSpatialDelegationEnabledForThread` at `0x1400ea8fa`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400eada6`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400eada6`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400eabe3`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400eac9f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400ead59`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400eabe3`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400eac9f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400ead59`
- `win32kbase!_HMPheFromObject` at `0x1400ea8ba`
- `win32kbase!_HMPheFromObject` at `0x1400eaf02`
- `win32kbase!_HMPheFromObject` at `0x1400eafe6`
- `win32kbase!_HMPheFromObject` at `0x1400ea8ba`
- `win32kbase!_HMPheFromObject` at `0x1400eaf02`
- `win32kbase!_HMPheFromObject` at `0x1400eafe6`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400eae0d`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400eae0d`
- `win32kbase!HMAssignmentLock` at `0x1400eb0f9`
- `win32kbase!HMAssignmentLock` at `0x1400eb13f`
- `win32kbase!HMAssignmentLock` at `0x1400eb2d3`
- `win32kbase!HMAssignmentLock` at `0x1400eb651`
- `win32kbase!HMAssignmentLock` at `0x1400eb0f9`
- `win32kbase!HMAssignmentLock` at `0x1400eb13f`
- `win32kbase!HMAssignmentLock` at `0x1400eb2d3`
- `win32kbase!HMAssignmentLock` at `0x1400eb651`
- `WIN32K!W32GetUserSessionState` at `0x1400ea7fc`
- `WIN32K!W32GetUserSessionState` at `0x1400ea833`
- `WIN32K!W32GetUserSessionState` at `0x1400eac59`
- `WIN32K!W32GetUserSessionState` at `0x1400eac73`
- `WIN32K!W32GetUserSessionState` at `0x1400eaccd`
- `WIN32K!W32GetUserSessionState` at `0x1400eacee`
- `WIN32K!W32GetUserSessionState` at `0x1400eb366`
- `WIN32K!W32GetUserSessionState` at `0x1400eb592`
- `WIN32K!W32GetUserSessionState` at `0x1400ea7fc`
- `WIN32K!W32GetUserSessionState` at `0x1400ea833`
- `WIN32K!W32GetUserSessionState` at `0x1400eac59`
- `WIN32K!W32GetUserSessionState` at `0x1400eac73`
- `WIN32K!W32GetUserSessionState` at `0x1400eaccd`
- `WIN32K!W32GetUserSessionState` at `0x1400eacee`
- `WIN32K!W32GetUserSessionState` at `0x1400eb366`
- `WIN32K!W32GetUserSessionState` at `0x1400eb592`

## pseudocode

```c
__int64 __fastcall xxxCallHook2(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  unsigned int v6; // r13d
  __int64 Valid; // r14
  unsigned int v8; // r12d
  struct tagTHREADINFO *v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // esi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v15; // rdx
  struct tagTHREADINFO *v16; // rcx
  int v17; // edi
  __int16 ProcessMachine; // bx
  __int16 v19; // bx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 UserSessionState; // rax
  const struct tagUIPI_INFO *v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // xmm6_8
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // r9
  __int64 v33; // rcx
  const struct tagUIPI_INFO *v34; // r8
  __int64 v35; // rax
  struct tagUIPI_INFO *v36; // rdx
  __int64 CurrentProcess; // rax
  unsigned int v38; // ebx
  __int64 HmodIndex; // rbx
  __int64 v40; // rdi
  __int64 *v41; // rax
  __int64 v42; // rsi
  __int64 v43; // rcx
  __int64 v44; // rax
  bool v45; // zf
  __int64 v46; // rbx
  int v48; // ebx
  struct tagUIPI_INFO *v49; // rdx
  char *v50; // rdi
  __int64 v51; // r12
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 *v54; // rax
  int v55; // esi
  char v56; // bl
  char v57; // r12
  bool v58; // r13
  int v59; // esi
  char ThreadId; // di
  __int64 v61; // rcx
  int v62; // ebx
  __int64 v63; // rdx
  __int64 v64; // rax
  int v65; // r8d
  int v66; // edx
  int ReturnLength; // [rsp+20h] [rbp-218h]
  int v68; // [rsp+28h] [rbp-210h]
  int v69; // [rsp+38h] [rbp-200h]
  char v70; // [rsp+60h] [rbp-1D8h]
  __int64 v71; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 ProcessInformation; // [rsp+70h] [rbp-1C8h] BYREF
  __int128 v73; // [rsp+78h] [rbp-1C0h]
  __int64 v74; // [rsp+88h] [rbp-1B0h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+90h] [rbp-1A8h] BYREF
  char *v76; // [rsp+A0h] [rbp-198h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-190h]
  __int64 v78; // [rsp+F0h] [rbp-148h] BYREF
  int v79; // [rsp+F8h] [rbp-140h]
  __int64 v80; // [rsp+100h] [rbp-138h] BYREF
  int v81; // [rsp+108h] [rbp-130h]
  ULONG_PTR v82[2]; // [rsp+110h] [rbp-128h] BYREF
  _QWORD v83[2]; // [rsp+120h] [rbp-118h] BYREF
  ULONG_PTR v84[2]; // [rsp+130h] [rbp-108h] BYREF
  _QWORD v85[2]; // [rsp+140h] [rbp-F8h] BYREF
  __m256i v86; // [rsp+150h] [rbp-E8h] BYREF
  __int64 v87; // [rsp+170h] [rbp-C8h]
  __int64 v88[4]; // [rsp+178h] [rbp-C0h] BYREF
  int v89; // [rsp+198h] [rbp-A0h]
  int v90; // [rsp+19Ch] [rbp-9Ch]
  __int64 *v91; // [rsp+1A0h] [rbp-98h]
  _BYTE v92[56]; // [rsp+1A8h] [rbp-90h] BYREF

  *(_QWORD *)&v73 = a4;
  *((_QWORD *)&v73 + 1) = a3;
  v6 = a2;
  Valid = a1;
  v74 = 0;
  v71 = 0;
  ProcessInformation = *(_QWORD *)(W32GetUserSessionState(a1, a2) + 42136);
  LockRefactorStagingAssertAny((const struct tagDomLock *)&ProcessInformation);
  if ( !Valid )
    return 0;
  v8 = *(_DWORD *)(Valid + 48);
  v9 = PtiCurrent();
  if ( v9 == *(struct tagTHREADINFO **)(W32GetUserSessionState(v11, v10) + 18752) && v8 != 13 && v8 != 14 )
    return 0;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x10000001) != 0
    || !*((_QWORD *)v9 + 61) && *(_DWORD *)(Valid + 48) != 14
    || (unsigned int)IsPointerInputHookCall(v8, a4) && v8 != 3 && v8 != 4 && v8 != 12 )
  {
    return 0;
  }
  while ( 1 )
  {
    SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v92);
    if ( (*(_BYTE *)(_HMPheFromObject(Valid) + 25) & 1) != 0 || (*(_DWORD *)(Valid + 64) & 0x1000) != 0 )
    {
      Valid = PhkNextValid(Valid);
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v92);
      goto LABEL_158;
    }
    SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v92);
    if ( (v8 != 14 || !*(_QWORD *)(Valid + 16) || !(unsigned __int8)IsSpatialDelegationEnabledForThread())
      && (v8 != 13 || !*(_QWORD *)(Valid + 16) || !(unsigned __int8)IsKeyboardDelegationEnabledForThread()) )
    {
      break;
    }
    Valid = PhkNextValid(Valid);
LABEL_158:
    if ( !Valid )
      return 0;
  }
  v12 = *(int *)(Valid + 48);
  v13 = dword_140356454[v12];
  if ( (_DWORD)v12 == 10
    && (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 8) != 0
    && ((v6 - 4) & 0xFFFFFFF3) == 0
    && v6 != 16 )
  {
    LOBYTE(v13) = v13 | 0x10;
  }
  if ( *(_DWORD *)(Valid + 48) == 10
    && (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 4) != 0
    && v6 == 11 )
  {
    LOBYTE(v13) = v13 | 0x10;
  }
  IsEnabledDeviceUsageNoInline = Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline();
  v16 = *(struct tagTHREADINFO **)(Valid + 16);
  if ( IsEnabledDeviceUsageNoInline )
  {
    v17 = 0;
    if ( v16 != v9 )
    {
      if ( (v13 & 0x20) != 0
        || (ProcessMachine = PsGetProcessMachine(**((_QWORD **)v16 + 57)),
            (unsigned __int16)PsGetProcessMachine(**((_QWORD **)v9 + 57)) != ProcessMachine)
        || (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0xC) != 0
        && (v16 = *(struct tagTHREADINFO **)(Valid + 16), *((_QWORD *)v16 + 57) != *((_QWORD *)v9 + 57))
        || (unsigned int)IsProcessDwm(**(_QWORD **)(*(_QWORD *)(Valid + 16) + 456LL))
        || (v16 = *(struct tagTHREADINFO **)(Valid + 16), *((_QWORD *)v16 + 57) != *((_QWORD *)v9 + 57))
        && (unsigned __int8)IsRestricted(*(_QWORD *)v16) )
      {
LABEL_55:
        v17 = 1;
      }
    }
  }
  else
  {
    if ( v16 != v9 )
    {
      if ( (v13 & 0x20) != 0 )
        goto LABEL_55;
      v19 = PsGetProcessMachine(**((_QWORD **)v16 + 57));
      if ( (unsigned __int16)PsGetProcessMachine(**((_QWORD **)v9 + 57)) != v19 )
        goto LABEL_55;
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0xC) != 0 )
      {
        v16 = *(struct tagTHREADINFO **)(Valid + 16);
        if ( *((_QWORD *)v16 + 57) != *((_QWORD *)v9 + 57) )
          goto LABEL_55;
      }
      if ( (unsigned int)IsProcessDwm(**(_QWORD **)(*(_QWORD *)(Valid + 16) + 456LL)) )
        goto LABEL_55;
      if ( !UIPrivilegeIsolation::Enforced(v16) && (*(_DWORD *)(Valid + 64) & 1) != 0 )
      {
        v20 = *((_QWORD *)v9 + 57);
        v15 = *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL);
        if ( (*(_DWORD *)(v15 + 764) != *(_DWORD *)(v20 + 764) || *(_DWORD *)(v15 + 768) != *(_DWORD *)(v20 + 768))
          && (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x400000) == 0 )
        {
          v15 = *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL);
          v16 = (struct tagTHREADINFO *)luidSystem[0];
          if ( *(_DWORD *)(v15 + 764) != luidSystem[0] )
            goto LABEL_55;
          v16 = (struct tagTHREADINFO *)luidSystem[1];
          if ( *(_DWORD *)(v15 + 768) != (_DWORD)v16 )
            goto LABEL_55;
        }
      }
      v16 = *(struct tagTHREADINFO **)(Valid + 16);
      if ( *((_QWORD *)v16 + 57) != *((_QWORD *)v9 + 57) )
      {
        if ( (unsigned __int8)IsRestricted(*(_QWORD *)v16) )
          goto LABEL_55;
      }
    }
    v17 = 0;
  }
  if ( (unsigned int)(*(_DWORD *)(Valid + 48) - 13) <= 1 )
  {
    if ( (a5 & 2) != 0
      || !*(_QWORD *)(W32GetUserSessionState(v16, v15) + 18968)
      || (UserSessionState = W32GetUserSessionState(v23, v15),
          UIPrivilegeIsolation::CheckAccess(
            (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) + 864LL),
            (const struct tagUIPI_INFO *)(*(_QWORD *)(UserSessionState + 18968) + 544LL),
            v25))
      || (unsigned int)IsForegroundShellFrameQueueAccessible(*(const struct tagTHREADINFO **)(Valid + 16))
      || (v26 = *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL), *(int *)(v26 + 12) < 0) )
    {
      if ( *(_DWORD *)(Valid + 48) != 14 )
        goto LABEL_74;
      if ( !UIPrivilegeIsolation::IsUIPIInfoValid(
              (struct tagTHREADINFO *)((char *)v9 + 1556),
              (const struct tagUIPI_INFO *)v15) )
        goto LABEL_74;
      if ( UIPrivilegeIsolation::CheckAccess(
             (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) + 864LL),
             (struct tagTHREADINFO *)((char *)v9 + 1556),
             v34) )
      {
        goto LABEL_74;
      }
      v33 = *(_QWORD *)(Valid + 16);
      if ( *(int *)(*(_QWORD *)(v33 + 456) + 12LL) < 0 )
        goto LABEL_74;
      v80 = *(_QWORD *)((char *)v9 + 1556);
      v81 = *((_DWORD *)v9 + 391);
      v32 = &v80;
      v31 = 0;
    }
    else
    {
      v27 = *(_QWORD *)(W32GetUserSessionState(v26, v15) + 18968);
      v28 = *(_QWORD *)(v27 + 544);
      v29 = *(_DWORD *)(v27 + 552);
      v31 = *(_QWORD *)(W32GetUserSessionState(v27, v30) + 18968);
      v78 = v28;
      v79 = v29;
      v32 = &v78;
      v33 = *(_QWORD *)(Valid + 16);
    }
    EtwTraceUIPIInputError(v33, 0, v31, v32, 6);
    LOBYTE(v13) = v13 & 0xEF;
    goto LABEL_74;
  }
  if ( !UIPrivilegeIsolation::CheckAccess(
          (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) + 864LL),
          (const struct tagUIPI_INFO *)(*((_QWORD *)v9 + 57) + 864LL),
          (const struct tagUIPI_INFO *)0x360) )
  {
    v22 = *(_QWORD *)(Valid + 16);
    if ( *(int *)(*(_QWORD *)(v22 + 456) + 12LL) >= 0 )
    {
      LOBYTE(v13) = v13 & 0xEF;
      LOBYTE(v21) = v13;
      EtwTraceUIPIHookError(Valid, v21, v22, v9, v8, v6, *((_QWORD *)&v73 + 1), v73);
    }
    v17 = 1;
  }
LABEL_74:
  if ( !v17
    && (*(_DWORD *)(Valid + 64) & 1) != 0
    && !(unsigned int)IsImmersiveBroker(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL)) )
  {
    v35 = *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL);
    if ( *(int *)(v35 + 12) >= 0 && v35 != *((_QWORD *)v9 + 57) && (*(_DWORD *)(v35 + 808) & 0x100LL) == 0 )
    {
      if ( (unsigned int)IsImmersiveAppRestricted()
        || (ProcessInformation = 6,
            ZwQueryInformationProcess(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              ProcessCookie|ProcessUserModeIOPL,
              &ProcessInformation,
              8u,
              0) < 0)
        || (ProcessInformation & 0x100000000LL) != 0 )
      {
        v17 = 1;
      }
    }
  }
  Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, v9, Valid);
  if ( !v17 )
  {
    if ( *(_DWORD *)(Valid + 68) != -1 )
    {
      CurrentProcess = PsGetCurrentProcess();
      if ( (unsigned int)PsIsProtectedProcess(CurrentProcess) )
        goto LABEL_102;
      if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
        goto LABEL_102;
      v38 = *(_DWORD *)(Valid + 68);
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v85);
      HmodIndex = xxxLoadHmodIndex(v38);
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v85);
      if ( !HmodIndex )
        goto LABEL_102;
      SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v85);
      if ( (*(_BYTE *)(_HMPheFromObject(Valid) + 25) & 1) != 0 || (*(_DWORD *)(Valid + 64) & 0x1000) != 0 )
        goto LABEL_101;
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v85);
    }
    if ( ((*((_DWORD *)v9 + 178) | *(_DWORD *)(**((_QWORD **)v9 + 62) + 16LL)) & 0x400) == 0
      || *(_DWORD *)(Valid + 48) == 9 )
    {
      goto LABEL_98;
    }
    memset(v88, 0, sizeof(v88));
    v88[0] = (unsigned int)PsGetThreadId(*(PETHREAD *)v9);
    LODWORD(v88[3]) = v6;
    *(_OWORD *)&v88[1] = v73;
    if ( (unsigned int)xxxCallHook(0, *(int *)(Valid + 48), (__int64)v88, 9) )
    {
LABEL_102:
      Valid = PhkNextValid(Valid);
      v44 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
      if ( !v44 )
      {
LABEL_113:
        Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
        goto LABEL_158;
      }
      v45 = (*(_DWORD *)(v44 + 64) & 0x10) == 0;
LABEL_111:
      if ( !v45 )
        FreeHook((struct tagHOOK *)v44);
      goto LABEL_113;
    }
    SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v85);
    if ( (*(_BYTE *)(_HMPheFromObject(Valid) + 25) & 1) == 0 && (*(_DWORD *)(Valid + 64) & 0x1000) == 0 )
    {
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v85);
LABEL_98:
      v40 = *((_QWORD *)v9 + 90);
      Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v82, v9, v40);
      if ( *((_QWORD *)v9 + 64) )
      {
        v41 = (__int64 *)PhkNextValid(Valid);
        v42 = *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL);
        v74 = v42;
        if ( v41 )
          v43 = *v41;
        else
          v43 = 0;
        *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v43;
      }
      else
      {
        v42 = v74;
      }
      v83[0] = (char *)v9 + 720;
      v83[1] = Valid;
      HMAssignmentLock(v83, 1);
      v71 = xxxHkCallHook(Valid, v6, *((_QWORD *)&v73 + 1), v73);
      v76 = (char *)v9 + 720;
      v77 = v40;
      HMAssignmentLock(&v76, 1);
      if ( *((_QWORD *)v9 + 64) )
        *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v42;
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v82);
      if ( (*(_DWORD *)(Valid + 64) & 0x10) == 0 )
      {
        v46 = v71;
        goto LABEL_115;
      }
      Valid = PhkNextValid(Valid);
      v44 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
      v45 = v44 == 0;
      goto LABEL_111;
    }
LABEL_101:
    SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v85);
    goto LABEL_102;
  }
  if ( (v13 & 0x10) == 0 )
    goto LABEL_102;
  *(_OWORD *)&v86.m256i_u64[2] = 0;
  v87 = 0;
  v48 = 200;
  *(_OWORD *)v86.m256i_i8 = (unsigned __int64)v73;
  v85[0] = Valid;
  v85[1] = v6;
  UIPrivilegeIsolation::ResetUIPIInfo((UIPrivilegeIsolation *)((char *)&v86.m256i_u64[1] + 4), v36);
  UIPrivilegeIsolation::ResetUIPIInfo((UIPrivilegeIsolation *)&v86.m256i_u64[3], v49);
  v86.m256i_i32[2] = 0;
  if ( tagPROCESSINFO::SyncAndTestFreeze(*(tagPROCESSINFO **)(*(_QWORD *)(Valid + 16) + 456LL)) )
    goto LABEL_102;
  v50 = (char *)v9 + 720;
  v51 = *((_QWORD *)v9 + 90);
  ProcessInformation = v51;
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v84, v9, v51);
  v76 = (char *)v9 + 720;
  v77 = Valid;
  HMAssignmentLock(&v76, 0);
  if ( *((_QWORD *)v9 + 64) )
  {
    v54 = (__int64 *)PhkNextValid(Valid);
    v74 = *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL);
    if ( v54 )
      v53 = *v54;
    else
      v53 = 0;
    *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v53;
  }
  v55 = v13 & 0x20;
  LODWORD(v73) = v55;
  if ( v55 )
  {
    v48 = (*(_DWORD *)(Valid + 64) & 0x40) != 0 ? 30000 : *(_DWORD *)(W32GetUserSessionState(v53, v52) + 63968);
    if ( (*(_DWORD *)(Valid + 64) & 0x4000) != 0 )
      v48 = 20;
  }
  if ( v55 || (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0xC) != 0 )
  {
    memset((char *)v88 + 4, 0, 28);
    LODWORD(v88[0]) = 2;
    v89 = 2;
    v90 = v48;
    v91 = &v71;
    if ( v55 )
    {
      *(__int64 *)((char *)&v86.m256i_i64[1] + 4) = *((_QWORD *)v9 + 193);
      v86.m256i_i32[5] = *((_DWORD *)v9 + 388);
      v86.m256i_i64[3] = *(_QWORD *)((char *)v9 + 1556);
      LODWORD(v87) = *((_DWORD *)v9 + 391);
      v86.m256i_i64[0] = *((_QWORD *)v9 + 196);
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x20000) != 0
      || IsThreadHung(*(const struct tagTHREADINFO **)(Valid + 16)) )
    {
      v71 = 0;
    }
    else
    {
      v56 = BoostHook(v9, Valid, a5);
      v70 = v56;
      if ( v56 )
        v86.m256i_i32[2] |= 1u;
      if ( !xxxInterSendMsgEx(
              0,
              0x314u,
              *((__int64 *)&v73 + 1),
              (ULONG_PTR)v85,
              1,
              *(_QWORD *)(Valid + 16),
              (__int64)v88,
              1,
              0) )
      {
        v71 = 0;
        if ( (*(_DWORD *)(Valid + 64) & 0x80u) == 0 )
        {
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
            || (v57 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
          {
            v57 = 0;
          }
          v58 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v57 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v59 = *(_DWORD *)(Valid + 48);
            ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(Valid + 16));
            v61 = *(_QWORD *)(Valid + 16);
            v62 = *(_DWORD *)(*(_QWORD *)(v61 + 456) + 56LL);
            v64 = W32GetUserSessionState(v61, v63);
            LOBYTE(v65) = v58;
            LOBYTE(v66) = v57;
            WPP_RECORDER_AND_TRACE_SF_DDd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v66,
              v65,
              *(_QWORD *)(v64 + 69152),
              ReturnLength,
              v68,
              47,
              v69,
              v62,
              ThreadId,
              v59);
            v55 = v73;
            v56 = v70;
            v50 = (char *)v9 + 720;
          }
          v51 = ProcessInformation;
        }
      }
      if ( v56 )
        DeBoostHook((struct tagHOOK *)Valid);
    }
    if ( v55 && v71 )
      _InterlockedExchange(
        (volatile __int32 *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 480LL) + 20LL),
        (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  }
  else
  {
    v71 = xxxInterSendMsgEx(0, 0x314u, *((__int64 *)&v73 + 1), (ULONG_PTR)v85, 1, *(_QWORD *)(Valid + 16), 0, 1, 0);
  }
  v76 = v50;
  v77 = v51;
  HMAssignmentLock(&v76, 1);
  if ( *((_QWORD *)v9 + 64) )
    *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v74;
  v46 = v71;
  Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v84);
LABEL_115:
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  return v46;
}

```

## disassembly

```asm
0x1400ea7ac  mov     rax, rsp
0x1400ea7af  push    rbx
0x1400ea7b0  push    rsi
0x1400ea7b1  push    rdi
0x1400ea7b2  push    r12
0x1400ea7b4  push    r13
0x1400ea7b6  push    r14
0x1400ea7b8  push    r15
0x1400ea7ba  sub     rsp, 200h
0x1400ea7c1  movaps  xmmword ptr [rax-48h], xmm6
0x1400ea7c5  mov     rax, cs:__security_cookie
0x1400ea7cc  xor     rax, rsp
0x1400ea7cf  mov     [rsp+238h+var_58], rax
0x1400ea7d7  mov     rbx, r9
0x1400ea7da  mov     [rsp+238h+var_1C0], rbx
0x1400ea7df  mov     [rsp+238h+var_1B8], r8
0x1400ea7e7  mov     r13d, edx
0x1400ea7ea  mov     r14, rcx
0x1400ea7ed  xor     esi, esi
0x1400ea7ef  mov     [rsp+238h+var_1B0], rsi
0x1400ea7f7  mov     [rsp+238h+var_1D0], rsi
0x1400ea7fc  call    cs:__imp_W32GetUserSessionState
0x1400ea803  nop     dword ptr [rax+rax+00h]
0x1400ea808  mov     rcx, [rax+0A498h]
0x1400ea80f  mov     [rsp+238h+ProcessInformation], rcx
0x1400ea814  lea     rcx, [rsp+238h+ProcessInformation]; struct tagDomLock *
0x1400ea819  call    ?LockRefactorStagingAssertAny@@YAXAEBUtagDomLock@@@Z; LockRefactorStagingAssertAny(tagDomLock const &)
0x1400ea81e  test    r14, r14
0x1400ea821  jz      loc_1400EB6BF
0x1400ea827  mov     r12d, [r14+30h]
0x1400ea82b  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400ea830  mov     r15, rax
0x1400ea833  call    cs:__imp_W32GetUserSessionState
0x1400ea83a  nop     dword ptr [rax+rax+00h]
0x1400ea83f  cmp     r15, [rax+4940h]
0x1400ea846  jnz     short loc_1400EA859
0x1400ea848  mov     eax, r12d
0x1400ea84b  sub     eax, 0Dh
0x1400ea84e  jz      short loc_1400EA859
0x1400ea850  cmp     eax, 1
0x1400ea853  jnz     loc_1400EB6BF
0x1400ea859  xor     ecx, ecx
0x1400ea85b  xor     eax, eax
0x1400ea85d  lock cmpxchg [r15+208h], ecx
0x1400ea866  test    eax, 10000001h
0x1400ea86b  jnz     loc_1400EB6BF
0x1400ea871  cmp     [r15+1E8h], rcx
0x1400ea878  jnz     short loc_1400EA885
0x1400ea87a  cmp     dword ptr [r14+30h], 0Eh
0x1400ea87f  jnz     loc_1400EB6BF
0x1400ea885  mov     rdx, rbx
0x1400ea888  mov     ecx, r12d
0x1400ea88b  call    IsPointerInputHookCall
0x1400ea890  test    eax, eax
0x1400ea892  jz      short loc_1400EA8AA
0x1400ea894  mov     eax, r12d
0x1400ea897  sub     eax, 3
0x1400ea89a  jz      short loc_1400EA8AA
0x1400ea89c  sub     eax, 1
0x1400ea89f  jz      short loc_1400EA8AA
0x1400ea8a1  cmp     eax, 8
0x1400ea8a4  jnz     loc_1400EB6BF
0x1400ea8aa  lea     rcx, [rsp+238h+var_90]
0x1400ea8b2  call    ??0?$ObjectLock@$$V@?$DomainExclusive@$$V@?$DomainShared@VDLT_HANDLEMANAGER@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(void)
0x1400ea8b7  mov     rcx, r14
0x1400ea8ba  call    cs:__imp__HMPheFromObject
0x1400ea8c1  nop     dword ptr [rax+rax+00h]
0x1400ea8c6  test    byte ptr [rax+19h], 1
0x1400ea8ca  jnz     loc_1400EB69E
0x1400ea8d0  test    dword ptr [r14+40h], 1000h
0x1400ea8d8  jnz     loc_1400EB69E
0x1400ea8de  lea     rcx, [rsp+238h+var_90]
0x1400ea8e6  call    ??1?$ObjectLock@$$V@?$DomainExclusive@VDLT_HANDLEMANAGER@@@?$DomainShared@$$V@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(void)
0x1400ea8eb  cmp     r12d, 0Eh
0x1400ea8ef  jnz     short loc_1400EA91A
0x1400ea8f1  mov     rcx, [r14+10h]
0x1400ea8f5  test    rcx, rcx
0x1400ea8f8  jz      short loc_1400EA91A
0x1400ea8fa  call    cs:__imp_IsSpatialDelegationEnabledForThread
0x1400ea901  nop     dword ptr [rax+rax+00h]
0x1400ea906  test    al, al
0x1400ea908  jz      short loc_1400EA91A
0x1400ea90a  mov     rcx, r14
0x1400ea90d  call    PhkNextValid
0x1400ea912  mov     r14, rax
0x1400ea915  jmp     loc_1400EB6B6
0x1400ea91a  cmp     r12d, 0Dh
0x1400ea91e  jnz     short loc_1400EA939
0x1400ea920  mov     rcx, [r14+10h]
0x1400ea924  test    rcx, rcx
0x1400ea927  jz      short loc_1400EA939
0x1400ea929  call    cs:__imp_IsKeyboardDelegationEnabledForThread
0x1400ea930  nop     dword ptr [rax+rax+00h]
0x1400ea935  test    al, al
0x1400ea937  jnz     short loc_1400EA90A
0x1400ea939  movsxd  rcx, dword ptr [r14+30h]
0x1400ea93d  lea     rsi, dword_140356454
0x1400ea944  mov     esi, [rsi+rcx*4]
0x1400ea947  cmp     ecx, 0Ah
0x1400ea94a  jnz     short loc_1400EA971
0x1400ea94c  xor     ecx, ecx
0x1400ea94e  xor     eax, eax
0x1400ea950  lock cmpxchg [r15+208h], ecx
0x1400ea959  test    al, 8
0x1400ea95b  jz      short loc_1400EA971
0x1400ea95d  lea     eax, [r13-4]
0x1400ea961  test    eax, 0FFFFFFF3h
0x1400ea966  jnz     short loc_1400EA971
0x1400ea968  cmp     r13d, 10h
0x1400ea96c  jz      short loc_1400EA971
0x1400ea96e  or      esi, 10h
0x1400ea971  cmp     dword ptr [r14+30h], 0Ah
0x1400ea976  jnz     short loc_1400EA992
0x1400ea978  xor     ecx, ecx
0x1400ea97a  xor     eax, eax
0x1400ea97c  lock cmpxchg [r15+208h], ecx
0x1400ea985  test    al, 4
0x1400ea987  jz      short loc_1400EA992
0x1400ea989  cmp     r13d, 0Bh
0x1400ea98d  jnz     short loc_1400EA992
0x1400ea98f  or      esi, 10h
0x1400ea992  call    Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline
0x1400ea997  mov     rcx, [r14+10h]
0x1400ea99b  test    eax, eax
0x1400ea99d  jz      loc_1400EAA6F
0x1400ea9a3  xor     edi, edi
0x1400ea9a5  cmp     rcx, r15
0x1400ea9a8  jz      loc_1400EABB5
0x1400ea9ae  test    sil, 20h
0x1400ea9b2  jnz     loc_1400EABAC
0x1400ea9b8  mov     rcx, [rcx+1C8h]
0x1400ea9bf  mov     rcx, [rcx]
0x1400ea9c2  call    cs:__imp_PsGetProcessMachine
0x1400ea9c9  nop     dword ptr [rax+rax+00h]
0x1400ea9ce  movzx   ebx, ax
0x1400ea9d1  mov     rcx, [r15+1C8h]
0x1400ea9d8  mov     rcx, [rcx]
0x1400ea9db  call    cs:__imp_PsGetProcessMachine
0x1400ea9e2  nop     dword ptr [rax+rax+00h]
0x1400ea9e7  cmp     ax, bx
0x1400ea9ea  jnz     loc_1400EABAC
0x1400ea9f0  xor     ecx, ecx
0x1400ea9f2  xor     eax, eax
0x1400ea9f4  lock cmpxchg [r15+208h], ecx
0x1400ea9fd  test    al, 0Ch
0x1400ea9ff  jz      short loc_1400EAA19
0x1400eaa01  mov     rcx, [r14+10h]
0x1400eaa05  mov     rax, [r15+1C8h]
0x1400eaa0c  cmp     [rcx+1C8h], rax
0x1400eaa13  jnz     loc_1400EABAC
0x1400eaa19  mov     rax, [r14+10h]
0x1400eaa1d  mov     rcx, [rax+1C8h]
0x1400eaa24  mov     rcx, [rcx]
0x1400eaa27  call    cs:__imp_IsProcessDwm
0x1400eaa2e  nop     dword ptr [rax+rax+00h]
0x1400eaa33  test    eax, eax
0x1400eaa35  jnz     loc_1400EABAC
0x1400eaa3b  mov     rcx, [r14+10h]
0x1400eaa3f  mov     rax, [r15+1C8h]
0x1400eaa46  cmp     [rcx+1C8h], rax
0x1400eaa4d  jz      loc_1400EABB5
0x1400eaa53  mov     rcx, [rcx]
0x1400eaa56  call    cs:__imp_IsRestricted
0x1400eaa5d  nop     dword ptr [rax+rax+00h]
0x1400eaa62  test    al, al
0x1400eaa64  jz      loc_1400EABB5
0x1400eaa6a  jmp     loc_1400EABAC
0x1400eaa6f  cmp     rcx, r15
0x1400eaa72  jz      loc_1400EABB3
0x1400eaa78  test    sil, 20h
0x1400eaa7c  jnz     loc_1400EABAC
0x1400eaa82  mov     rcx, [rcx+1C8h]
0x1400eaa89  mov     rcx, [rcx]
0x1400eaa8c  call    cs:__imp_PsGetProcessMachine
0x1400eaa93  nop     dword ptr [rax+rax+00h]
0x1400eaa98  movzx   ebx, ax
0x1400eaa9b  mov     rcx, [r15+1C8h]
0x1400eaaa2  mov     rcx, [rcx]
0x1400eaaa5  call    cs:__imp_PsGetProcessMachine
0x1400eaaac  nop     dword ptr [rax+rax+00h]
0x1400eaab1  cmp     ax, bx
0x1400eaab4  jnz     loc_1400EABAC
0x1400eaaba  xor     ecx, ecx
0x1400eaabc  xor     eax, eax
0x1400eaabe  lock cmpxchg [r15+208h], ecx
0x1400eaac7  test    al, 0Ch
0x1400eaac9  jz      short loc_1400EAAE3
0x1400eaacb  mov     rcx, [r14+10h]
0x1400eaacf  mov     rax, [r15+1C8h]
0x1400eaad6  cmp     [rcx+1C8h], rax
0x1400eaadd  jnz     loc_1400EABAC
0x1400eaae3  mov     rax, [r14+10h]
0x1400eaae7  mov     rcx, [rax+1C8h]
0x1400eaaee  mov     rcx, [rcx]
0x1400eaaf1  call    cs:__imp_IsProcessDwm
0x1400eaaf8  nop     dword ptr [rax+rax+00h]
0x1400eaafd  test    eax, eax
0x1400eaaff  jnz     loc_1400EABAC
0x1400eab05  call    cs:__imp_?Enforced@UIPrivilegeIsolation@@YA_NXZ; UIPrivilegeIsolation::Enforced(void)
0x1400eab0c  nop     dword ptr [rax+rax+00h]
0x1400eab11  test    al, al
0x1400eab13  jnz     short loc_1400EAB85
0x1400eab15  mov     eax, [r14+40h]
0x1400eab19  test    al, 1
0x1400eab1b  jz      short loc_1400EAB85
0x1400eab1d  mov     rcx, [r15+1C8h]
0x1400eab24  mov     rax, [r14+10h]
0x1400eab28  mov     rdx, [rax+1C8h]
0x1400eab2f  mov     eax, [rcx+2FCh]
0x1400eab35  cmp     [rdx+2FCh], eax
0x1400eab3b  jnz     short loc_1400EAB4B
0x1400eab3d  mov     eax, [rcx+300h]
0x1400eab43  cmp     [rdx+300h], eax
0x1400eab49  jz      short loc_1400EAB85
0x1400eab4b  xor     ecx, ecx
0x1400eab4d  xor     eax, eax
0x1400eab4f  lock cmpxchg [r15+208h], ecx
0x1400eab58  bt      eax, 16h
0x1400eab5c  jb      short loc_1400EAB85
0x1400eab5e  mov     rax, [r14+10h]
0x1400eab62  mov     rdx, [rax+1C8h]
0x1400eab69  mov     rax, cs:__imp_luidSystem
0x1400eab70  mov     ecx, [rax]
0x1400eab72  cmp     [rdx+2FCh], ecx
0x1400eab78  jnz     short loc_1400EABAC
0x1400eab7a  mov     ecx, [rax+4]
0x1400eab7d  cmp     [rdx+300h], ecx
0x1400eab83  jnz     short loc_1400EABAC
0x1400eab85  mov     rcx, [r14+10h]
0x1400eab89  mov     rax, [r15+1C8h]
0x1400eab90  cmp     [rcx+1C8h], rax
0x1400eab97  jz      short loc_1400EABB3
0x1400eab99  mov     rcx, [rcx]
0x1400eab9c  call    cs:__imp_IsRestricted
0x1400eaba3  nop     dword ptr [rax+rax+00h]
0x1400eaba8  test    al, al
0x1400eabaa  jz      short loc_1400EABB3
0x1400eabac  mov     edi, 1
0x1400eabb1  jmp     short loc_1400EABB5
0x1400eabb3  xor     edi, edi
0x1400eabb5  mov     eax, [r14+30h]
0x1400eabb9  sub     eax, 0Dh
0x1400eabbc  cmp     eax, 1
0x1400eabbf  jbe     loc_1400EAC4B
0x1400eabc5  mov     rdx, [r15+1C8h]
0x1400eabcc  mov     r8d, 360h
0x1400eabd2  add     rdx, r8
0x1400eabd5  mov     rax, [r14+10h]
0x1400eabd9  mov     rcx, [rax+1C8h]
0x1400eabe0  add     rcx, r8
0x1400eabe3  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400eabea  nop     dword ptr [rax+rax+00h]
0x1400eabef  test    al, al
0x1400eabf1  jnz     loc_1400EADB5
0x1400eabf7  mov     r8, [r14+10h]
0x1400eabfb  mov     rax, [r8+1C8h]
0x1400eac02  cmp     dword ptr [rax+0Ch], 0
0x1400eac06  jl      short loc_1400EAC41
0x1400eac08  and     esi, 0FFFFFFEFh
0x1400eac0b  mov     dl, sil
0x1400eac0e  mov     rax, [rsp+238h+var_1C0]
0x1400eac13  mov     [rsp+238h+var_200], rax
0x1400eac18  mov     rax, [rsp+238h+var_1B8]
0x1400eac20  mov     [rsp+238h+var_208], rax
0x1400eac25  mov     dword ptr [rsp+238h+var_210], r13d
0x1400eac2a  mov     dword ptr [rsp+238h+ReturnLength], r12d
0x1400eac2f  mov     r9, r15
0x1400eac32  mov     rcx, r14
0x1400eac35  call    cs:__imp_EtwTraceUIPIHookError
0x1400eac3c  nop     dword ptr [rax+rax+00h]
0x1400eac41  mov     edi, 1
0x1400eac46  jmp     loc_1400EADB5
0x1400eac4b  test    byte ptr [rsp+238h+arg_20], 2
0x1400eac53  jnz     loc_1400EAD1F
0x1400eac59  call    cs:__imp_W32GetUserSessionState
0x1400eac60  nop     dword ptr [rax+rax+00h]
0x1400eac65  cmp     qword ptr [rax+4A18h], 0
0x1400eac6d  jz      loc_1400EAD1F
0x1400eac73  call    cs:__imp_W32GetUserSessionState
0x1400eac7a  nop     dword ptr [rax+rax+00h]
0x1400eac7f  mov     rdx, [rax+4A18h]
0x1400eac86  add     rdx, 220h
0x1400eac8d  mov     rax, [r14+10h]
0x1400eac91  mov     rcx, [rax+1C8h]
0x1400eac98  add     rcx, 360h
0x1400eac9f  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400eaca6  nop     dword ptr [rax+rax+00h]
0x1400eacab  test    al, al
0x1400eacad  jnz     short loc_1400EAD1F
0x1400eacaf  mov     rcx, [r14+10h]; struct tagTHREADINFO *
0x1400eacb3  call    ?IsForegroundShellFrameQueueAccessible@@YAHPEBUtagTHREADINFO@@@Z; IsForegroundShellFrameQueueAccessible(tagTHREADINFO const *)
0x1400eacb8  test    eax, eax
0x1400eacba  jnz     short loc_1400EAD1F
0x1400eacbc  mov     rax, [r14+10h]
0x1400eacc0  mov     rcx, [rax+1C8h]
0x1400eacc7  cmp     dword ptr [rcx+0Ch], 0
0x1400eaccb  jl      short loc_1400EAD1F
0x1400eaccd  call    cs:__imp_W32GetUserSessionState
0x1400eacd4  nop     dword ptr [rax+rax+00h]
0x1400eacd9  mov     rcx, [rax+4A18h]
  ... truncated ...
```
