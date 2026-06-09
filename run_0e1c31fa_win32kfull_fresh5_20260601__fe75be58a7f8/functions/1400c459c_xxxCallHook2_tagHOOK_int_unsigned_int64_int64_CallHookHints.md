# xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)

- ea: `0x1400c459c`
- end: `0x1400c53d6`
- name: `?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z`
- size: `3642`
- prototype: ``
- caller_count: `10`
- callee_count: `26`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b6960`
- `0x1400c4270`
- `0x1400c5428`
- `0x140123e7c`
- `0x140124110`
- `0x140124380`
- `0x140188ea0`
- `0x1401b1114`
- `0x14026cbb0`
- `0x140279640`

## callees

- `0x140004c3c`
- `0x140004cd8`
- `0x140022384`
- `0x140023be8`
- `0x140023c74`
- `0x1400286dc`
- `0x1400292ec`
- `0x1400381a8`
- `0x1400b4700`
- `0x1400b58c0`
- `0x1400b643c`
- `0x1400b68e0`
- `0x1400b6b18`
- `0x1400b6d20`
- `0x1400b7238`
- `0x1400bcaa0`
- `0x1400c4270`
- `0x1400c459c`
- `0x14014ec30`
- `0x140164320`
- `0x140172ff4`
- `0x14017c55c`
- `0x14017e910`
- `0x140183a90`
- `0x1401adf74`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationProcess` at `0x1400c4af6`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400c4af6`
- `ntoskrnl!PsGetProcessMachine` at `0x1400c47af`
- `ntoskrnl!PsGetProcessMachine` at `0x1400c47c8`
- `ntoskrnl!PsGetProcessMachine` at `0x1400c47af`
- `ntoskrnl!PsGetProcessMachine` at `0x1400c47c8`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400c4b48`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400c4b48`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400c4b5c`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400c4b5c`
- `ntoskrnl!PsGetThreadId` at `0x1400c4c22`
- `ntoskrnl!PsGetThreadId` at `0x1400c525e`
- `ntoskrnl!PsGetThreadId` at `0x1400c4c22`
- `ntoskrnl!PsGetThreadId` at `0x1400c525e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c4b39`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c4b39`
- `win32kbase!IsKeyboardDelegationEnabledForThread` at `0x1400c471a`
- `win32kbase!IsKeyboardDelegationEnabledForThread` at `0x1400c471a`
- `win32kbase!IsRestricted` at `0x1400c4841`
- `win32kbase!IsRestricted` at `0x1400c4841`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1400c49dc`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1400c49dc`
- `win32kbase!EtwTraceUIPIHookError` at `0x1400c48dd`
- `win32kbase!EtwTraceUIPIHookError` at `0x1400c48dd`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x1400c4f6e`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x1400c4f6e`
- `win32kbase!IsImmersiveBroker` at `0x1400c4a7f`
- `win32kbase!IsImmersiveBroker` at `0x1400c4a7f`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400c4f38`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400c4f4c`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400c4f38`
- `win32kbase!?ResetUIPIInfo@UIPrivilegeIsolation@@YAXPEAUtagUIPI_INFO@@@Z` at `0x1400c4f4c`
- `win32kbase!IsProcessDwm` at `0x1400c480c`
- `win32kbase!IsProcessDwm` at `0x1400c480c`
- `win32kbase!IsSpatialDelegationEnabledForThread` at `0x1400c46ec`
- `win32kbase!IsSpatialDelegationEnabledForThread` at `0x1400c46ec`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400c4a4e`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400c4a4e`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c4890`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c4947`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c4a01`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c4890`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c4947`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c4a01`
- `win32kbase!_HMPheFromObject` at `0x1400c46ad`
- `win32kbase!_HMPheFromObject` at `0x1400c4bb2`
- `win32kbase!_HMPheFromObject` at `0x1400c4c96`
- `win32kbase!_HMPheFromObject` at `0x1400c46ad`
- `win32kbase!_HMPheFromObject` at `0x1400c4bb2`
- `win32kbase!_HMPheFromObject` at `0x1400c4c96`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400c4abc`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400c4abc`
- `win32kbase!HMAssignmentLock` at `0x1400c4ddd`
- `win32kbase!HMAssignmentLock` at `0x1400c4e25`
- `win32kbase!HMAssignmentLock` at `0x1400c4fbe`
- `win32kbase!HMAssignmentLock` at `0x1400c533a`
- `win32kbase!HMAssignmentLock` at `0x1400c4ddd`
- `win32kbase!HMAssignmentLock` at `0x1400c4e25`
- `win32kbase!HMAssignmentLock` at `0x1400c4fbe`
- `win32kbase!HMAssignmentLock` at `0x1400c533a`
- `WIN32K!W32GetUserSessionState` at `0x1400c45ed`
- `WIN32K!W32GetUserSessionState` at `0x1400c4624`
- `WIN32K!W32GetUserSessionState` at `0x1400c4901`
- `WIN32K!W32GetUserSessionState` at `0x1400c491b`
- `WIN32K!W32GetUserSessionState` at `0x1400c4975`
- `WIN32K!W32GetUserSessionState` at `0x1400c4996`
- `WIN32K!W32GetUserSessionState` at `0x1400c504e`
- `WIN32K!W32GetUserSessionState` at `0x1400c527c`
- `WIN32K!W32GetUserSessionState` at `0x1400c45ed`
- `WIN32K!W32GetUserSessionState` at `0x1400c4624`
- `WIN32K!W32GetUserSessionState` at `0x1400c4901`
- `WIN32K!W32GetUserSessionState` at `0x1400c491b`
- `WIN32K!W32GetUserSessionState` at `0x1400c4975`
- `WIN32K!W32GetUserSessionState` at `0x1400c4996`
- `WIN32K!W32GetUserSessionState` at `0x1400c504e`
- `WIN32K!W32GetUserSessionState` at `0x1400c527c`

## pseudocode

```c
__int64 __fastcall xxxCallHook2(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rbx
  __int64 Valid; // r14
  unsigned int v8; // esi
  struct tagTHREADINFO *v9; // r15
  __int64 v10; // rcx
  const struct tagUIPI_INFO *v11; // rdx
  __int64 v12; // rcx
  int v13; // r12d
  int v14; // edi
  struct tagTHREADINFO *v15; // rcx
  __int16 ProcessMachine; // bx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 UserSessionState; // rax
  const struct tagUIPI_INFO *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // xmm6_8
  int v26; // ebx
  __int64 v27; // r8
  __int64 *v28; // r9
  __int64 v29; // rcx
  const struct tagUIPI_INFO *v30; // r8
  __int64 v31; // rax
  struct tagUIPI_INFO *v32; // rdx
  __int64 CurrentProcess; // rax
  unsigned int v34; // ebx
  __int64 HmodIndex; // rbx
  __int64 v36; // rdi
  __int64 *v37; // rax
  __int64 v38; // r12
  __int64 v39; // rcx
  __int64 v40; // rax
  struct tagHOOK *v41; // rax
  __int64 v42; // rbx
  int v44; // ebx
  struct tagUIPI_INFO *v45; // rdx
  char *v46; // rdi
  __int64 v47; // rsi
  __int64 v48; // rcx
  char v49; // r13
  __int64 *v50; // rax
  int v51; // r12d
  char v52; // bl
  int v53; // esi
  char ThreadId; // di
  __int64 v55; // rcx
  int v56; // ebx
  __int64 v57; // rax
  int v58; // r8d
  int v59; // edx
  int ReturnLength; // [rsp+20h] [rbp-218h]
  int v61; // [rsp+28h] [rbp-210h]
  int v62; // [rsp+38h] [rbp-200h]
  bool v63; // [rsp+60h] [rbp-1D8h]
  char v64; // [rsp+61h] [rbp-1D7h]
  __int64 v66; // [rsp+70h] [rbp-1C8h] BYREF
  __int64 ProcessInformation; // [rsp+78h] [rbp-1C0h] BYREF
  __int64 v68; // [rsp+80h] [rbp-1B8h]
  __int64 v69; // [rsp+88h] [rbp-1B0h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+90h] [rbp-1A8h] BYREF
  char *v71; // [rsp+A0h] [rbp-198h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-190h]
  __int64 v73; // [rsp+F0h] [rbp-148h] BYREF
  int v74; // [rsp+F8h] [rbp-140h]
  __int64 v75; // [rsp+100h] [rbp-138h] BYREF
  int v76; // [rsp+108h] [rbp-130h]
  ULONG_PTR v77[2]; // [rsp+110h] [rbp-128h] BYREF
  _QWORD v78[2]; // [rsp+120h] [rbp-118h] BYREF
  ULONG_PTR v79[2]; // [rsp+130h] [rbp-108h] BYREF
  _QWORD v80[2]; // [rsp+140h] [rbp-F8h] BYREF
  __m256i v81; // [rsp+150h] [rbp-E8h] BYREF
  __int64 v82; // [rsp+170h] [rbp-C8h]
  __int64 v83[4]; // [rsp+178h] [rbp-C0h] BYREF
  int v84; // [rsp+198h] [rbp-A0h]
  int v85; // [rsp+19Ch] [rbp-9Ch]
  __int64 *v86; // [rsp+1A0h] [rbp-98h]
  _BYTE v87[56]; // [rsp+1A8h] [rbp-90h] BYREF

  v5 = a4;
  v68 = a3;
  Valid = a1;
  v69 = 0;
  v66 = 0;
  ProcessInformation = *(_QWORD *)(W32GetUserSessionState(a1) + 42136);
  LockRefactorStagingAssertAny((const struct tagDomLock *)&ProcessInformation);
  if ( !Valid )
    return 0;
  v8 = *(_DWORD *)(Valid + 48);
  v9 = PtiCurrent();
  if ( v9 == *(struct tagTHREADINFO **)(W32GetUserSessionState(v10) + 18752) && v8 != 13 && v8 != 14 )
    return 0;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x10000001) != 0
    || !*((_QWORD *)v9 + 61) && *(_DWORD *)(Valid + 48) != 14
    || (unsigned int)IsPointerInputHookCall(v8, v5) && v8 != 3 && v8 != 4 && v8 != 12 )
  {
    return 0;
  }
  while ( 1 )
  {
    SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v87);
    if ( (*(_BYTE *)(_HMPheFromObject(Valid) + 25) & 1) != 0 || (*(_DWORD *)(Valid + 64) & 0x1000) != 0 )
    {
      Valid = PhkNextValid(Valid);
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v87);
      goto LABEL_148;
    }
    SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v87);
    if ( v8 == 14 && *(_QWORD *)(Valid + 16) && (unsigned __int8)IsSpatialDelegationEnabledForThread()
      || v8 == 13 && *(_QWORD *)(Valid + 16) && (unsigned __int8)IsKeyboardDelegationEnabledForThread() )
    {
      Valid = PhkNextValid(Valid);
      goto LABEL_148;
    }
    v12 = *(int *)(Valid + 48);
    v13 = dword_140355564[v12];
    if ( (_DWORD)v12 == 10
      && (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 8) != 0
      && ((a2 - 4) & 0xFFFFFFF3) == 0
      && a2 != 16 )
    {
      LOBYTE(v13) = v13 | 0x10;
    }
    if ( *(_DWORD *)(Valid + 48) == 10
      && (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 4) != 0
      && a2 == 11 )
    {
      LOBYTE(v13) = v13 | 0x10;
    }
    v14 = 0;
    v15 = *(struct tagTHREADINFO **)(Valid + 16);
    if ( v15 != v9 )
    {
      if ( (v13 & 0x20) != 0 )
      {
        v14 = 1;
        goto LABEL_44;
      }
      ProcessMachine = PsGetProcessMachine(**((_QWORD **)v15 + 57));
      if ( (unsigned __int16)PsGetProcessMachine(**((_QWORD **)v9 + 57)) != ProcessMachine
        || (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0xC) != 0
        && *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) != *((_QWORD *)v9 + 57)
        || (unsigned int)IsProcessDwm(**(_QWORD **)(*(_QWORD *)(Valid + 16) + 456LL)) )
      {
        v14 = 1;
LABEL_38:
        v5 = a4;
        goto LABEL_44;
      }
      v17 = *(_QWORD **)(Valid + 16);
      if ( v17[57] != *((_QWORD *)v9 + 57) )
      {
        if ( (unsigned __int8)IsRestricted(*v17) )
          v14 = 1;
        goto LABEL_38;
      }
      v5 = a4;
    }
LABEL_44:
    if ( (unsigned int)(*(_DWORD *)(Valid + 48) - 13) <= 1 )
    {
      if ( (a5 & 2) != 0
        || !*(_QWORD *)(W32GetUserSessionState(1) + 18968)
        || (UserSessionState = W32GetUserSessionState(v20),
            UIPrivilegeIsolation::CheckAccess(
              (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) + 864LL),
              (const struct tagUIPI_INFO *)(*(_QWORD *)(UserSessionState + 18968) + 544LL),
              v22))
        || (unsigned int)IsForegroundShellFrameQueueAccessible(*(const struct tagTHREADINFO **)(Valid + 16))
        || (v23 = *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL), *(int *)(v23 + 12) < 0) )
      {
        if ( *(_DWORD *)(Valid + 48) != 14 )
          goto LABEL_61;
        if ( !UIPrivilegeIsolation::IsUIPIInfoValid((struct tagTHREADINFO *)((char *)v9 + 1556), v11) )
          goto LABEL_61;
        if ( UIPrivilegeIsolation::CheckAccess(
               (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) + 864LL),
               (struct tagTHREADINFO *)((char *)v9 + 1556),
               v30) )
        {
          goto LABEL_61;
        }
        v29 = *(_QWORD *)(Valid + 16);
        if ( *(int *)(*(_QWORD *)(v29 + 456) + 12LL) < 0 )
          goto LABEL_61;
        v75 = *(_QWORD *)((char *)v9 + 1556);
        v76 = *((_DWORD *)v9 + 391);
        v28 = &v75;
        v27 = 0;
      }
      else
      {
        v24 = *(_QWORD *)(W32GetUserSessionState(v23) + 18968);
        v25 = *(_QWORD *)(v24 + 544);
        v26 = *(_DWORD *)(v24 + 552);
        v27 = *(_QWORD *)(W32GetUserSessionState(v24) + 18968);
        v73 = v25;
        v74 = v26;
        v28 = &v73;
        v29 = *(_QWORD *)(Valid + 16);
      }
      EtwTraceUIPIInputError(v29, 0, v27, v28, 6);
      LOBYTE(v13) = v13 & 0xEF;
      goto LABEL_61;
    }
    if ( !UIPrivilegeIsolation::CheckAccess(
            (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL) + 864LL),
            (const struct tagUIPI_INFO *)(*((_QWORD *)v9 + 57) + 864LL),
            (const struct tagUIPI_INFO *)0x360) )
    {
      v19 = *(_QWORD *)(Valid + 16);
      if ( *(int *)(*(_QWORD *)(v19 + 456) + 12LL) >= 0 )
      {
        LOBYTE(v13) = v13 & 0xEF;
        LOBYTE(v18) = v13;
        EtwTraceUIPIHookError(Valid, v18, v19, v9, v8, a2, v68, v5);
      }
      v14 = 1;
    }
LABEL_61:
    if ( !v14
      && (*(_DWORD *)(Valid + 64) & 1) != 0
      && !(unsigned int)IsImmersiveBroker(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL)) )
    {
      v31 = *(_QWORD *)(*(_QWORD *)(Valid + 16) + 456LL);
      if ( *(int *)(v31 + 12) >= 0 && v31 != *((_QWORD *)v9 + 57) && (*(_DWORD *)(v31 + 808) & 0x100LL) == 0 )
      {
        if ( (unsigned int)IsImmersiveAppRestricted() )
        {
          v14 = 1;
        }
        else
        {
          ProcessInformation = 6;
          if ( ZwQueryInformationProcess(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 ProcessCookie|ProcessUserModeIOPL,
                 &ProcessInformation,
                 8u,
                 0) < 0
            || (ProcessInformation & 0x100000000LL) != 0 )
          {
            v14 = 1;
          }
        }
      }
    }
    Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, v9, Valid);
    if ( v14 )
      break;
    if ( *(_DWORD *)(Valid + 68) != -1 )
    {
      CurrentProcess = PsGetCurrentProcess();
      if ( (unsigned int)PsIsProtectedProcess(CurrentProcess) )
        goto LABEL_90;
      if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
        goto LABEL_90;
      v34 = *(_DWORD *)(Valid + 68);
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v80);
      HmodIndex = xxxLoadHmodIndex(v34);
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v80);
      if ( !HmodIndex )
        goto LABEL_90;
      SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v80);
      if ( (*(_BYTE *)(_HMPheFromObject(Valid) + 25) & 1) != 0 || (*(_DWORD *)(Valid + 64) & 0x1000) != 0 )
      {
        SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v80);
        goto LABEL_90;
      }
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v80);
    }
    if ( ((*((_DWORD *)v9 + 178) | *(_DWORD *)(**((_QWORD **)v9 + 62) + 16LL)) & 0x400) != 0
      && *(_DWORD *)(Valid + 48) != 9 )
    {
      memset(v83, 0, sizeof(v83));
      v83[0] = (unsigned int)PsGetThreadId(*(PETHREAD *)v9);
      LODWORD(v83[3]) = a2;
      v83[2] = v68;
      v5 = a4;
      v83[1] = a4;
      if ( (unsigned int)xxxCallHook(0, *(int *)(Valid + 48), (__int64)v83, 9) )
        goto LABEL_91;
      SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v80);
      if ( (*(_BYTE *)(_HMPheFromObject(Valid) + 25) & 1) != 0 || (*(_DWORD *)(Valid + 64) & 0x1000) != 0 )
      {
        SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v80);
LABEL_91:
        Valid = PhkNextValid(Valid);
        v40 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
        if ( v40 && (*(_DWORD *)(v40 + 64) & 0x10) != 0 )
          FreeHook((struct tagHOOK *)v40);
        Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
        goto LABEL_148;
      }
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v80);
    }
    v36 = *((_QWORD *)v9 + 90);
    Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v77, v9, v36);
    if ( *((_QWORD *)v9 + 64) )
    {
      v37 = (__int64 *)PhkNextValid(Valid);
      v38 = *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL);
      v69 = v38;
      if ( v37 )
        v39 = *v37;
      else
        v39 = 0;
      *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v39;
    }
    else
    {
      v38 = v69;
    }
    v78[0] = (char *)v9 + 720;
    v78[1] = Valid;
    HMAssignmentLock(v78, 1);
    v66 = xxxHkCallHook(Valid, a2, v68, a4);
    v71 = (char *)v9 + 720;
    v72 = v36;
    HMAssignmentLock(&v71, 1);
    if ( *((_QWORD *)v9 + 64) )
      *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v38;
    Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v77);
    if ( (*(_DWORD *)(Valid + 64) & 0x10) == 0 )
    {
      v42 = v66;
      goto LABEL_106;
    }
    Valid = PhkNextValid(Valid);
    v41 = (struct tagHOOK *)Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
    if ( v41 )
      FreeHook(v41);
    Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
    v5 = a4;
LABEL_148:
    if ( !Valid )
      return 0;
  }
  if ( (v13 & 0x10) == 0 )
    goto LABEL_90;
  *(_OWORD *)&v81.m256i_u64[2] = 0;
  v82 = 0;
  v44 = 200;
  *(_OWORD *)v81.m256i_i8 = (unsigned __int64)a4;
  v80[0] = Valid;
  v80[1] = a2;
  UIPrivilegeIsolation::ResetUIPIInfo((UIPrivilegeIsolation *)((char *)&v81.m256i_u64[1] + 4), v32);
  UIPrivilegeIsolation::ResetUIPIInfo((UIPrivilegeIsolation *)&v81.m256i_u64[3], v45);
  v81.m256i_i32[2] = 0;
  if ( tagPROCESSINFO::SyncAndTestFreeze(*(tagPROCESSINFO **)(*(_QWORD *)(Valid + 16) + 456LL)) )
  {
LABEL_90:
    v5 = a4;
    goto LABEL_91;
  }
  v46 = (char *)v9 + 720;
  v47 = *((_QWORD *)v9 + 90);
  ProcessInformation = v47;
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v79, v9, v47);
  v71 = (char *)v9 + 720;
  v72 = Valid;
  HMAssignmentLock(&v71, 0);
  v49 = 0;
  if ( *((_QWORD *)v9 + 64) )
  {
    v50 = (__int64 *)PhkNextValid(Valid);
    v69 = *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL);
    if ( v50 )
      v48 = *v50;
    else
      v48 = 0;
    *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v48;
  }
  v51 = v13 & 0x20;
  if ( v51 )
  {
    v44 = (*(_DWORD *)(Valid + 64) & 0x40) != 0 ? 30000 : *(_DWORD *)(W32GetUserSessionState(v48) + 63968);
    if ( (*(_DWORD *)(Valid + 64) & 0x4000) != 0 )
      v44 = 20;
  }
  if ( v51 || (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0xC) != 0 )
  {
    memset((char *)v83 + 4, 0, 28);
    LODWORD(v83[0]) = 2;
    v84 = 2;
    v85 = v44;
    v86 = &v66;
    if ( v51 )
    {
      *(__int64 *)((char *)&v81.m256i_i64[1] + 4) = *((_QWORD *)v9 + 193);
      v81.m256i_i32[5] = *((_DWORD *)v9 + 388);
      v81.m256i_i64[3] = *(_QWORD *)((char *)v9 + 1556);
      LODWORD(v82) = *((_DWORD *)v9 + 391);
      v81.m256i_i64[0] = *((_QWORD *)v9 + 196);
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x20000) != 0
      || IsThreadHung(*(const struct tagTHREADINFO **)(Valid + 16)) )
    {
      v66 = 0;
    }
    else
    {
      v52 = BoostHook(v9, Valid, a5);
      v64 = v52;
      if ( v52 )
        v81.m256i_i32[2] |= 1u;
      if ( !xxxInterSendMsgEx(0, 0x314u, 1, *(_QWORD *)(Valid + 16), (__int64)v83, 1, 0) )
      {
        v66 = 0;
        if ( (*(_DWORD *)(Valid + 64) & 0x80u) == 0 )
        {
          if ( WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
          {
            v49 = 1;
          }
          v63 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v49 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v53 = *(_DWORD *)(Valid + 48);
            ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(Valid + 16));
            v55 = *(_QWORD *)(Valid + 16);
            v56 = *(_DWORD *)(*(_QWORD *)(v55 + 456) + 56LL);
            v57 = W32GetUserSessionState(v55);
            LOBYTE(v58) = v63;
            LOBYTE(v59) = v49;
            WPP_RECORDER_AND_TRACE_SF_DDd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v59,
              v58,
              *(_QWORD *)(v57 + 69152),
              ReturnLength,
              v61,
              45,
              v62,
              v56,
              ThreadId,
              v53);
            v52 = v64;
            v46 = (char *)v9 + 720;
            v47 = ProcessInformation;
          }
        }
      }
      if ( v52 )
        DeBoostHook((struct tagHOOK *)Valid);
    }
    if ( v51 && v66 )
      _InterlockedExchange(
        (volatile __int32 *)(*(_QWORD *)(*(_QWORD *)(Valid + 16) + 480LL) + 20LL),
        (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  }
  else
  {
    v66 = xxxInterSendMsgEx(0, 0x314u, 1, *(_QWORD *)(Valid + 16), 0, 1, 0);
  }
  v71 = v46;
  v72 = v47;
  HMAssignmentLock(&v71, 1);
  if ( *((_QWORD *)v9 + 64) )
    *(_QWORD *)(*((_QWORD *)v9 + 64) + 48LL) = v69;
  v42 = v66;
  Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v79);
LABEL_106:
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  return v42;
}

```

## disassembly

```asm
0x1400c459c  mov     rax, rsp
0x1400c459f  push    rbx
0x1400c45a0  push    rsi
0x1400c45a1  push    rdi
0x1400c45a2  push    r12
0x1400c45a4  push    r13
0x1400c45a6  push    r14
0x1400c45a8  push    r15
0x1400c45aa  sub     rsp, 200h
0x1400c45b1  movaps  xmmword ptr [rax-48h], xmm6
0x1400c45b5  mov     rax, cs:__security_cookie
0x1400c45bc  xor     rax, rsp
0x1400c45bf  mov     [rsp+238h+var_58], rax
0x1400c45c7  mov     rbx, r9
0x1400c45ca  mov     [rsp+238h+var_1D0], rbx
0x1400c45cf  mov     [rsp+238h+var_1B8], r8
0x1400c45d7  mov     r13d, edx
0x1400c45da  mov     r14, rcx
0x1400c45dd  xor     r12d, r12d
0x1400c45e0  mov     [rsp+238h+var_1B0], r12
0x1400c45e8  mov     [rsp+238h+var_1C8], r12
0x1400c45ed  call    cs:__imp_W32GetUserSessionState
0x1400c45f4  nop     dword ptr [rax+rax+00h]
0x1400c45f9  mov     rcx, [rax+0A498h]
0x1400c4600  mov     [rsp+238h+ProcessInformation], rcx
0x1400c4605  lea     rcx, [rsp+238h+ProcessInformation]; struct tagDomLock *
0x1400c460a  call    ?LockRefactorStagingAssertAny@@YAXAEBUtagDomLock@@@Z; LockRefactorStagingAssertAny(tagDomLock const &)
0x1400c460f  test    r14, r14
0x1400c4612  jz      loc_1400C53A8
0x1400c4618  mov     esi, [r14+30h]
0x1400c461c  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400c4621  mov     r15, rax
0x1400c4624  call    cs:__imp_W32GetUserSessionState
0x1400c462b  nop     dword ptr [rax+rax+00h]
0x1400c4630  cmp     r15, [rax+4940h]
0x1400c4637  jnz     short loc_1400C4649
0x1400c4639  mov     eax, esi
0x1400c463b  sub     eax, 0Dh
0x1400c463e  jz      short loc_1400C4649
0x1400c4640  cmp     eax, 1
0x1400c4643  jnz     loc_1400C53A8
0x1400c4649  xor     ecx, ecx
0x1400c464b  xor     eax, eax
0x1400c464d  lock cmpxchg [r15+208h], ecx
0x1400c4656  test    eax, 10000001h
0x1400c465b  jnz     loc_1400C53A8
0x1400c4661  cmp     [r15+1E8h], rcx
0x1400c4668  jnz     short loc_1400C4675
0x1400c466a  cmp     dword ptr [r14+30h], 0Eh
0x1400c466f  jnz     loc_1400C53A8
0x1400c4675  mov     rdx, rbx
0x1400c4678  mov     ecx, esi
0x1400c467a  call    IsPointerInputHookCall
0x1400c467f  test    eax, eax
0x1400c4681  jz      short loc_1400C4698
0x1400c4683  mov     eax, esi
0x1400c4685  sub     eax, 3
0x1400c4688  jz      short loc_1400C4698
0x1400c468a  sub     eax, 1
0x1400c468d  jz      short loc_1400C4698
0x1400c468f  cmp     eax, 8
0x1400c4692  jnz     loc_1400C53A8
0x1400c4698  mov     edi, 1
0x1400c469d  lea     rcx, [rsp+238h+var_90]
0x1400c46a5  call    ??0?$ObjectLock@$$V@?$DomainExclusive@$$V@?$DomainShared@VDLT_HANDLEMANAGER@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::DomainShared<DLT_HANDLEMANAGER>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(void)
0x1400c46aa  mov     rcx, r14
0x1400c46ad  call    cs:__imp__HMPheFromObject
0x1400c46b4  nop     dword ptr [rax+rax+00h]
0x1400c46b9  test    [rax+19h], dil
0x1400c46bd  jnz     loc_1400C5387
0x1400c46c3  test    dword ptr [r14+40h], 1000h
0x1400c46cb  jnz     loc_1400C5387
0x1400c46d1  lea     rcx, [rsp+238h+var_90]
0x1400c46d9  call    ??1?$ObjectLock@$$V@?$DomainExclusive@VDLT_HANDLEMANAGER@@@?$DomainShared@$$V@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(void)
0x1400c46de  cmp     esi, 0Eh
0x1400c46e1  jnz     short loc_1400C470C
0x1400c46e3  mov     rcx, [r14+10h]
0x1400c46e7  test    rcx, rcx
0x1400c46ea  jz      short loc_1400C470C
0x1400c46ec  call    cs:__imp_IsSpatialDelegationEnabledForThread
0x1400c46f3  nop     dword ptr [rax+rax+00h]
0x1400c46f8  test    al, al
0x1400c46fa  jz      short loc_1400C470C
0x1400c46fc  mov     rcx, r14
0x1400c46ff  call    PhkNextValid
0x1400c4704  mov     r14, rax
0x1400c4707  jmp     loc_1400C539F
0x1400c470c  cmp     esi, 0Dh
0x1400c470f  jnz     short loc_1400C472A
0x1400c4711  mov     rcx, [r14+10h]
0x1400c4715  test    rcx, rcx
0x1400c4718  jz      short loc_1400C472A
0x1400c471a  call    cs:__imp_IsKeyboardDelegationEnabledForThread
0x1400c4721  nop     dword ptr [rax+rax+00h]
0x1400c4726  test    al, al
0x1400c4728  jnz     short loc_1400C46FC
0x1400c472a  movsxd  rcx, dword ptr [r14+30h]
0x1400c472e  lea     r12, dword_140355564
0x1400c4735  mov     r12d, [r12+rcx*4]
0x1400c4739  cmp     ecx, 0Ah
0x1400c473c  jnz     short loc_1400C4764
0x1400c473e  xor     ecx, ecx
0x1400c4740  xor     eax, eax
0x1400c4742  lock cmpxchg [r15+208h], ecx
0x1400c474b  test    al, 8
0x1400c474d  jz      short loc_1400C4764
0x1400c474f  lea     eax, [r13-4]
0x1400c4753  test    eax, 0FFFFFFF3h
0x1400c4758  jnz     short loc_1400C4764
0x1400c475a  cmp     r13d, 10h
0x1400c475e  jz      short loc_1400C4764
0x1400c4760  or      r12d, 10h
0x1400c4764  cmp     dword ptr [r14+30h], 0Ah
0x1400c4769  jnz     short loc_1400C4786
0x1400c476b  xor     ecx, ecx
0x1400c476d  xor     eax, eax
0x1400c476f  lock cmpxchg [r15+208h], ecx
0x1400c4778  test    al, 4
0x1400c477a  jz      short loc_1400C4786
0x1400c477c  cmp     r13d, 0Bh
0x1400c4780  jnz     short loc_1400C4786
0x1400c4782  or      r12d, 10h
0x1400c4786  xor     edi, edi
0x1400c4788  mov     rcx, [r14+10h]
0x1400c478c  cmp     rcx, r15
0x1400c478f  jz      loc_1400C485E
0x1400c4795  test    r12b, 20h
0x1400c4799  jz      short loc_1400C47A5
0x1400c479b  lea     ecx, [rdi+1]
0x1400c479e  mov     edi, ecx
0x1400c47a0  jmp     loc_1400C4863
0x1400c47a5  mov     rcx, [rcx+1C8h]
0x1400c47ac  mov     rcx, [rcx]
0x1400c47af  call    cs:__imp_PsGetProcessMachine
0x1400c47b6  nop     dword ptr [rax+rax+00h]
0x1400c47bb  movzx   ebx, ax
0x1400c47be  mov     rcx, [r15+1C8h]
0x1400c47c5  mov     rcx, [rcx]
0x1400c47c8  call    cs:__imp_PsGetProcessMachine
0x1400c47cf  nop     dword ptr [rax+rax+00h]
0x1400c47d4  cmp     ax, bx
0x1400c47d7  jnz     short loc_1400C481C
0x1400c47d9  xor     ecx, ecx
0x1400c47db  xor     eax, eax
0x1400c47dd  lock cmpxchg [r15+208h], ecx
0x1400c47e6  test    al, 0Ch
0x1400c47e8  jz      short loc_1400C47FE
0x1400c47ea  mov     rcx, [r14+10h]
0x1400c47ee  mov     rax, [r15+1C8h]
0x1400c47f5  cmp     [rcx+1C8h], rax
0x1400c47fc  jnz     short loc_1400C481C
0x1400c47fe  mov     rax, [r14+10h]
0x1400c4802  mov     rcx, [rax+1C8h]
0x1400c4809  mov     rcx, [rcx]
0x1400c480c  call    cs:__imp_IsProcessDwm
0x1400c4813  nop     dword ptr [rax+rax+00h]
0x1400c4818  test    eax, eax
0x1400c481a  jz      short loc_1400C482A
0x1400c481c  mov     ecx, 1
0x1400c4821  mov     edi, ecx
0x1400c4823  mov     rbx, [rsp+238h+var_1D0]
0x1400c4828  jmp     short loc_1400C4863
0x1400c482a  mov     rcx, [r14+10h]
0x1400c482e  mov     rax, [r15+1C8h]
0x1400c4835  cmp     [rcx+1C8h], rax
0x1400c483c  jz      short loc_1400C4859
0x1400c483e  mov     rcx, [rcx]
0x1400c4841  call    cs:__imp_IsRestricted
0x1400c4848  nop     dword ptr [rax+rax+00h]
0x1400c484d  test    al, al
0x1400c484f  mov     ecx, 1
0x1400c4854  cmovnz  edi, ecx
0x1400c4857  jmp     short loc_1400C4823
0x1400c4859  mov     rbx, [rsp+238h+var_1D0]
0x1400c485e  mov     ecx, 1
0x1400c4863  mov     eax, [r14+30h]
0x1400c4867  sub     eax, 0Dh
0x1400c486a  cmp     eax, ecx
0x1400c486c  jbe     loc_1400C48F3
0x1400c4872  mov     rdx, [r15+1C8h]
0x1400c4879  mov     r8d, 360h
0x1400c487f  add     rdx, r8
0x1400c4882  mov     rax, [r14+10h]
0x1400c4886  mov     rcx, [rax+1C8h]
0x1400c488d  add     rcx, r8
0x1400c4890  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400c4897  nop     dword ptr [rax+rax+00h]
0x1400c489c  test    al, al
0x1400c489e  jnz     loc_1400C4A5E
0x1400c48a4  mov     r8, [r14+10h]
0x1400c48a8  mov     rax, [r8+1C8h]
0x1400c48af  cmp     dword ptr [rax+0Ch], 0
0x1400c48b3  jl      short loc_1400C48E9
0x1400c48b5  and     r12d, 0FFFFFFEFh
0x1400c48b9  mov     dl, r12b
0x1400c48bc  mov     qword ptr [rsp+238h+var_200], rbx
0x1400c48c1  mov     rax, [rsp+238h+var_1B8]
0x1400c48c9  mov     [rsp+238h+var_208], rax
0x1400c48ce  mov     dword ptr [rsp+238h+var_210], r13d
0x1400c48d3  mov     dword ptr [rsp+238h+ReturnLength], esi
0x1400c48d7  mov     r9, r15
0x1400c48da  mov     rcx, r14
0x1400c48dd  call    cs:__imp_EtwTraceUIPIHookError
0x1400c48e4  nop     dword ptr [rax+rax+00h]
0x1400c48e9  mov     edi, 1
0x1400c48ee  jmp     loc_1400C4A5E
0x1400c48f3  test    byte ptr [rsp+238h+arg_20], 2
0x1400c48fb  jnz     loc_1400C49C7
0x1400c4901  call    cs:__imp_W32GetUserSessionState
0x1400c4908  nop     dword ptr [rax+rax+00h]
0x1400c490d  cmp     qword ptr [rax+4A18h], 0
0x1400c4915  jz      loc_1400C49C7
0x1400c491b  call    cs:__imp_W32GetUserSessionState
0x1400c4922  nop     dword ptr [rax+rax+00h]
0x1400c4927  mov     rdx, [rax+4A18h]
0x1400c492e  add     rdx, 220h
0x1400c4935  mov     rax, [r14+10h]
0x1400c4939  mov     rcx, [rax+1C8h]
0x1400c4940  add     rcx, 360h
0x1400c4947  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400c494e  nop     dword ptr [rax+rax+00h]
0x1400c4953  test    al, al
0x1400c4955  jnz     short loc_1400C49C7
0x1400c4957  mov     rcx, [r14+10h]; struct tagTHREADINFO *
0x1400c495b  call    ?IsForegroundShellFrameQueueAccessible@@YAHPEBUtagTHREADINFO@@@Z; IsForegroundShellFrameQueueAccessible(tagTHREADINFO const *)
0x1400c4960  test    eax, eax
0x1400c4962  jnz     short loc_1400C49C7
0x1400c4964  mov     rax, [r14+10h]
0x1400c4968  mov     rcx, [rax+1C8h]
0x1400c496f  cmp     dword ptr [rcx+0Ch], 0
0x1400c4973  jl      short loc_1400C49C7
0x1400c4975  call    cs:__imp_W32GetUserSessionState
0x1400c497c  nop     dword ptr [rax+rax+00h]
0x1400c4981  mov     rcx, [rax+4A18h]
0x1400c4988  movsd   xmm6, qword ptr [rcx+220h]
0x1400c4990  mov     ebx, [rcx+228h]
0x1400c4996  call    cs:__imp_W32GetUserSessionState
0x1400c499d  nop     dword ptr [rax+rax+00h]
0x1400c49a2  mov     r8, [rax+4A18h]
0x1400c49a9  movsd   [rsp+238h+var_148], xmm6
0x1400c49b2  mov     [rsp+238h+var_140], ebx
0x1400c49b9  lea     r9, [rsp+238h+var_148]
0x1400c49c1  mov     rcx, [r14+10h]
0x1400c49c5  jmp     short loc_1400C4A44
0x1400c49c7  cmp     dword ptr [r14+30h], 0Eh
0x1400c49cc  jnz     loc_1400C4A5E
0x1400c49d2  lea     rbx, [r15+614h]
0x1400c49d9  mov     rcx, rbx
0x1400c49dc  call    cs:__imp_?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z; UIPrivilegeIsolation::IsUIPIInfoValid(tagUIPI_INFO const &)
0x1400c49e3  nop     dword ptr [rax+rax+00h]
0x1400c49e8  test    al, al
0x1400c49ea  jz      short loc_1400C4A5E
0x1400c49ec  mov     rax, [r14+10h]
0x1400c49f0  mov     rcx, [rax+1C8h]
0x1400c49f7  add     rcx, 360h
0x1400c49fe  mov     rdx, rbx
0x1400c4a01  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400c4a08  nop     dword ptr [rax+rax+00h]
0x1400c4a0d  test    al, al
0x1400c4a0f  jnz     short loc_1400C4A5E
0x1400c4a11  mov     rcx, [r14+10h]
0x1400c4a15  mov     rax, [rcx+1C8h]
0x1400c4a1c  cmp     dword ptr [rax+0Ch], 0
0x1400c4a20  jl      short loc_1400C4A5E
0x1400c4a22  movsd   xmm0, qword ptr [rbx]
0x1400c4a26  movsd   [rsp+238h+var_138], xmm0
0x1400c4a2f  mov     eax, [rbx+8]
0x1400c4a32  mov     [rsp+238h+var_130], eax
0x1400c4a39  lea     r9, [rsp+238h+var_138]
0x1400c4a41  xor     r8d, r8d
0x1400c4a44  mov     dword ptr [rsp+238h+ReturnLength], 6
0x1400c4a4c  xor     edx, edx
0x1400c4a4e  call    cs:__imp_EtwTraceUIPIInputError
0x1400c4a55  nop     dword ptr [rax+rax+00h]
0x1400c4a5a  and     r12d, 0FFFFFFEFh
0x1400c4a5e  xor     ebx, ebx
0x1400c4a60  test    edi, edi
0x1400c4a62  jnz     loc_1400C4B13
0x1400c4a68  mov     eax, [r14+40h]
0x1400c4a6c  test    al, 1
0x1400c4a6e  jz      loc_1400C4B13
0x1400c4a74  mov     rcx, [r14+10h]
0x1400c4a78  mov     rcx, [rcx+1C8h]
0x1400c4a7f  call    cs:__imp_IsImmersiveBroker
0x1400c4a86  nop     dword ptr [rax+rax+00h]
0x1400c4a8b  test    eax, eax
0x1400c4a8d  jnz     loc_1400C4B13
0x1400c4a93  mov     rax, [r14+10h]
0x1400c4a97  mov     rax, [rax+1C8h]
0x1400c4a9e  cmp     [rax+0Ch], ebx
0x1400c4aa1  jl      short loc_1400C4B13
0x1400c4aa3  mov     rcx, [r15+1C8h]
0x1400c4aaa  cmp     rax, rcx
0x1400c4aad  jz      short loc_1400C4B13
0x1400c4aaf  mov     eax, [rax+328h]
0x1400c4ab5  bt      rax, 8
0x1400c4aba  jb      short loc_1400C4B13
0x1400c4abc  call    cs:__imp_IsImmersiveAppRestricted
0x1400c4ac3  nop     dword ptr [rax+rax+00h]
0x1400c4ac8  test    eax, eax
  ... truncated ...
```
