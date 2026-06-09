# LaunchOrActivationAllowed(void *,HSTRING__ *,_SECURITY_DESCRIPTOR *,int,int,int,ulong,CToken *,ulong,CToken *,CClassData *)

- ea: `0x18005d8e0`
- end: `0x18005e4a9`
- name: `?LaunchOrActivationAllowed@@YAHPEAXPEAUHSTRING__@@PEAU_SECURITY_DESCRIPTOR@@HHHKPEAVCToken@@K3PEAVCClassData@@@Z`
- size: `3017`
- prototype: `__int64 __fastcall(void *, WCHAR *, struct _SECURITY_DESCRIPTOR *, int, int, int, unsigned int, struct CToken *, __int16, struct CToken *, struct CClassData *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000866c`
- `0x18005d7f4`

## callees

- `0x180018344`
- `0x18002575c`
- `0x180025884`
- `0x180045d94`
- `0x180048bf0`
- `0x18004fe30`
- `0x18005ba34`
- `0x18005d8e0`
- `0x18005f3a0`
- `0x1800665e4`
- `0x18006cb10`
- `0x180071294`
- `0x180076450`
- `0x1800b27e0`
- `0x1800b2bb0`
- `0x1800b3f7c`
- `0x1800e9904`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005df01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005df01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e480`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e0c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e137`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e1f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e262`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e0c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e137`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e1f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e262`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e030`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e0fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e163`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e030`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e0fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e163`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e08e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e1c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e08e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e1c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d9ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ddad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d9ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ddad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005da1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005da40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ddcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ddd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005da1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005da40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ddcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ddd7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005df52`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005df52`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18005db21`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18005dd04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18005de57`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18005db21`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18005dd04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18005de57`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005e323`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005e323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e341`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005e459`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005e459`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005db92`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005dd6c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005dd9b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005debd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005e469`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005db92`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005dd6c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005dd9b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005debd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005e469`
- `ext-ms-win-session-usertoken-l1-1-0!IsInteractiveUserSession` at `0x18005dc23`
- `ext-ms-win-session-usertoken-l1-1-0!IsInteractiveUserSession` at `0x18005dc23`

## string_xrefs

- `0x18005db5b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005dc80`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005dd3e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005de90`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005e155`: `Software\Microsoft\Ole\AppCompat\ActivationSecurityCheckExemptionList`
- `0x18005e114`: `AllowLocalActivationSecurityCheckExemptionList`
- `0x18005e01d`: `Software\Policies\Microsoft\Windows NT\DCOM\AppCompat\ActivationSecurityCheckExemptionList`
- `0x18005e0ec`: `Software\Policies\Microsoft\Windows NT\DCOM\AppCompat`
- `0x18005dc5d`: `GetUserSidForSession failed: %!HRESULT!`

## pseudocode

```c
__int64 __fastcall LaunchOrActivationAllowed(
        void *a1,
        WCHAR *a2,
        struct _SECURITY_DESCRIPTOR *a3,
        int a4,
        int a5,
        int a6,
        unsigned int a7,
        struct CToken *a8,
        __int16 a9,
        struct CToken *a10,
        struct CClassData *a11)
{
  struct CToken *v12; // rsi
  int v13; // eax
  int v14; // ebx
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  unsigned int SessionId2; // eax
  CSecDescriptor *v19; // rsi
  int v20; // edi
  __int64 v21; // rax
  __int64 v22; // r9
  PSECURITY_DESCRIPTOR v23; // rcx
  char v25; // r12
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rax
  int UserSidForSession; // eax
  struct _SECURITY_DESCRIPTOR *v30; // r14
  unsigned int v31; // r15d
  __int64 v32; // rsi
  CSecDescriptor *v33; // r12
  struct CSecDescriptor *v34; // r14
  void *v35; // rcx
  struct _SECURITY_DESCRIPTOR *v36; // rbx
  struct CToken *v37; // rbx
  HANDLE *v38; // r12
  __int64 v39; // rdx
  __int64 v40; // rax
  void *v41; // rcx
  __int64 v42; // rcx
  int v43; // ebx
  __int64 v44; // rcx
  int v45; // r14d
  const WCHAR *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  int v49; // r14d
  const WCHAR *v50; // rdx
  __int64 v51; // rax
  int v52; // eax
  int v53; // r14d
  int v54; // ecx
  __int64 v55; // rax
  __int64 v56; // r9
  LPWSTR v57; // r13
  void *UserSid; // rbx
  LPWSTR v59; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v61; // rcx
  bool v62; // zf
  int v63; // ecx
  int v64; // esi
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR v70; // [rsp+70h] [rbp-90h] BYREF
  int v71; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR v73; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type[2]; // [rsp+90h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v77; // [rsp+C0h] [rbp-40h]
  int v78; // [rsp+C8h] [rbp-38h]
  int v79; // [rsp+CCh] [rbp-34h]
  int *v80; // [rsp+D0h] [rbp-30h]
  __int64 v81; // [rsp+D8h] [rbp-28h]
  PCWSTR v82; // [rsp+E0h] [rbp-20h]
  int v83; // [rsp+E8h] [rbp-18h]
  int v84; // [rsp+ECh] [rbp-14h]
  LPWSTR v85; // [rsp+F0h] [rbp-10h]
  int v86; // [rsp+F8h] [rbp-8h]
  int v87; // [rsp+FCh] [rbp-4h]
  LPWSTR *v88; // [rsp+100h] [rbp+0h]
  __int64 v89; // [rsp+108h] [rbp+8h]

  v12 = a10;
  v13 = a5;
  StringSecurityDescriptor = a2;
  *(_QWORD *)&EventDescriptor.Id = a1;
  phkResult = (HKEY)a8;
  *(_QWORD *)Type = a10;
  v71 = a4;
  SecurityDescriptor = a3;
  if ( a4 )
  {
    if ( a5 )
    {
      v14 = 32;
      if ( !a6 )
        v14 = 64;
    }
    else
    {
      v14 = 16;
      if ( a6 )
        v14 = 4;
    }
  }
  else
  {
    v14 = 8;
    if ( a6 )
      v14 = 2;
  }
  if ( a11 )
  {
    if ( (unsigned int)CClassData::IsInteractiveUser(a11) )
    {
      v15 = *((_QWORD *)a11 + 11);
      if ( v15 )
      {
        v16 = *(_DWORD *)(v15 + 72);
LABEL_17:
        if ( (v16 & 0x20) != 0 )
        {
          if ( !a8 )
            return 0;
          SessionId2 = *((_DWORD *)a8 + 24);
          if ( SessionId2 == -1 )
          {
            SessionId2 = GetSessionId2(*((void **)a8 + 9));
            *((_DWORD *)a8 + 24) = SessionId2;
          }
          if ( a7 != SessionId2 )
            return 0;
        }
        goto LABEL_22;
      }
      v17 = *((_QWORD *)a11 + 12);
      if ( v17 )
      {
        v16 = *(_DWORD *)(v17 + 136);
        goto LABEL_17;
      }
    }
LABEL_22:
    v13 = a5;
  }
  if ( a6 && !v13 )
  {
    AcquireSRWLockShared(&gpClientLock);
    v19 = gpDefaultLaunchRestrictionsSD;
    if ( gpDefaultLaunchRestrictionsSD )
    {
      _InterlockedIncrement((volatile signed __int32 *)gpDefaultLaunchRestrictionsSD + 3);
      ReleaseSRWLockShared(&gpClientLock);
      v20 = CheckForAccess(*((HANDLE *)a8 + 9), *(PSECURITY_DESCRIPTOR *)v19, v14, 0);
      CSecDescriptor::DecRefCount(v19);
    }
    else
    {
      ReleaseSRWLockShared(&gpClientLock);
      v19 = gpNoRegLaunchRestrictionsSD;
      v20 = CheckForAccess(*((HANDLE *)a8 + 9), *(PSECURITY_DESCRIPTOR *)gpNoRegLaunchRestrictionsSD, v14, 0);
    }
    if ( !v20 )
    {
      if ( gdwActivationFailureLoggingLevel == 1 || !gdwActivationFailureLoggingLevel && (a9 & 0x4000) == 0 )
      {
        if ( a11 )
        {
          v21 = *((_QWORD *)a11 + 11);
          v22 = v21 + 196;
          if ( !v21 )
            v22 = 0;
        }
        else
        {
          v22 = 0;
        }
        LogAccessFailed(
          *(_QWORD *)&EventDescriptor.Id,
          a8,
          StringSecurityDescriptor,
          v22,
          0,
          18207,
          *((_QWORD *)a8 + 9),
          v71,
          0,
          7);
      }
      if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = *(PSECURITY_DESCRIPTOR *)v19;
        StringSecurityDescriptor = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v23, 1u, 0x1Fu, &StringSecurityDescriptor, 0)
          && (dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
        {
          ComTraceMessage(-1, "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx", "LaunchOrActivationAllowed", 3791);
        }
        if ( StringSecurityDescriptor )
        {
          LocalFree(StringSecurityDescriptor);
          return 0;
        }
      }
      return 0;
    }
    v12 = *(struct CToken **)Type;
  }
  *(_DWORD *)Data = 0;
  if ( a3 )
  {
    v25 = 0;
    hMem = 0;
    if ( !a11 || !(unsigned int)CClassData::IsInteractiveUser(a11) )
      goto LABEL_69;
    v26 = *((_QWORD *)a11 + 11);
    if ( v26 )
    {
      v27 = *(_DWORD *)(v26 + 72);
    }
    else
    {
      v28 = *((_QWORD *)a11 + 12);
      if ( !v28 )
        goto LABEL_69;
      v27 = *(_DWORD *)(v28 + 136);
    }
    if ( (v27 & 0x10) != 0 )
    {
      if ( v12 )
      {
        hMem = (char *)v12 + 156;
        goto LABEL_69;
      }
      if ( !a7 && (!(unsigned __int8)IsQueryActiveSessionPresent() || !(unsigned int)IsInteractiveUserSession(0)) )
        goto LABEL_69;
      UserSidForSession = GetUserSidForSession(a7, &hMem);
      if ( UserSidForSession < 0 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          ComTraceMessage(
            (unsigned int)UserSidForSession,
            "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            "LaunchOrActivationAllowed",
            3842);
        return 0;
      }
      v25 = 1;
    }
LABEL_69:
    v30 = (struct _SECURITY_DESCRIPTOR *)SecurityDescriptor;
    v31 = CheckForAccess(*((HANDLE *)a8 + 9), SecurityDescriptor, v14, hMem);
    v32 = -1;
    if ( !v31 && (dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
    {
      v70 = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v30, 1u, 0x1Fu, &v70, 0)
        && (dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
      {
        lpcbData = (LPDWORD)L"%ws";
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          "LaunchOrActivationAllowed",
          3862);
      }
      if ( v70 )
        LocalFree(v70);
    }
    LODWORD(v73) = 4;
    if ( !a6 )
      *(_DWORD *)Data = IsSACLPresentInSecurityDescriptor(v30);
    if ( v25 )
      LocalFree(hMem);
    goto LABEL_107;
  }
  AcquireSRWLockShared(&gpClientLock);
  v33 = gpDefaultLaunchPermissionsSD;
  if ( gpDefaultLaunchPermissionsSD )
  {
    _InterlockedIncrement((volatile signed __int32 *)gpDefaultLaunchPermissionsSD + 3);
    ReleaseSRWLockShared(&gpClientLock);
    v34 = v33;
  }
  else
  {
    ReleaseSRWLockShared(&gpClientLock);
    v34 = gpNoRegLaunchPermissionsSD;
  }
  v35 = (void *)*((_QWORD *)a8 + 9);
  hMem = *(HLOCAL *)v34;
  v31 = CheckForAccess(v35, hMem, v14, 0);
  v32 = -1;
  if ( !v31 && (dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
  {
    v36 = (struct _SECURITY_DESCRIPTOR *)hMem;
    v73 = 0;
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(hMem, 1u, 0x1Fu, &v73, 0)
      && (dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
    {
      lpcbData = (LPDWORD)L"%ws";
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        "LaunchOrActivationAllowed",
        3904);
    }
    if ( v73 )
      LocalFree(v73);
  }
  else
  {
    v36 = (struct _SECURITY_DESCRIPTOR *)hMem;
  }
  if ( !a6 )
    *(_DWORD *)Data = IsSACLPresentInSecurityDescriptor(v36);
  if ( v33 && _InterlockedExchangeAdd((volatile signed __int32 *)v34 + 3, 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v34 )
    {
      HeapFree(g_hHeap, 0, *(LPVOID *)v34);
      *(_QWORD *)v34 = 0;
    }
    operator delete(v34, 0x10u);
  }
  v30 = (struct _SECURITY_DESCRIPTOR *)SecurityDescriptor;
  LODWORD(v73) = 2;
LABEL_107:
  v37 = *(struct CToken **)Type;
  v38 = (HANDLE *)phkResult;
  if ( !*(_QWORD *)Type || *(_DWORD *)Data )
    goto LABEL_162;
  if ( !v31 )
  {
LABEL_115:
    if ( !a11 )
      goto LABEL_163;
    v39 = *((_QWORD *)a11 + 11);
    v40 = v39 + 118;
    if ( !v39 )
      v40 = 0;
    if ( !v40 )
      goto LABEL_119;
    if ( !v30 )
      goto LABEL_129;
    v41 = (void *)*((_QWORD *)a11 + 22);
    if ( v41 )
    {
LABEL_127:
      *(_DWORD *)Data = 1;
      IsValidCOMSecurityDescriptor(v41, (int *)Data);
      if ( *(_DWORD *)Data )
      {
        v31 = 0;
        goto LABEL_162;
      }
LABEL_129:
      hMem = 0;
      phkResult = 0;
      LODWORD(SecurityDescriptor) = 0;
      v43 = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows NT\\DCOM\\AppCompat\\ActivationSecurityCheckExemptionList",
             0,
             0x20019u,
             &phkResult) )
      {
        goto LABEL_147;
      }
      v44 = *((_QWORD *)a11 + 11);
      v45 = 0;
      v46 = (const WCHAR *)(v44 + 118);
      v47 = v44 + 118;
      if ( !v44 )
        v47 = 0;
      if ( v47 )
      {
        Type[0] = 0;
        if ( !v44 )
          v46 = 0;
        *(_DWORD *)Data = 0;
        LODWORD(v70) = 4;
        if ( !RegQueryValueExW(phkResult, v46, 0, Type, Data, (LPDWORD)&v70) && Type[0] == 1 )
        {
          v45 = 1;
          if ( *(_WORD *)Data == 49 && !*(_WORD *)&Data[2] )
            v43 = 1;
        }
      }
      v31 = 0;
      if ( v45 )
        v31 = v43;
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( !v45 )
      {
        v43 = v31;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Policies\\Microsoft\\Windows NT\\DCOM\\AppCompat",
                0,
                0x20019u,
                (PHKEY)&hMem) )
        {
          if ( ReadRegistryIntegerValue(
                 (HKEY)hMem,
                 L"AllowLocalActivationSecurityCheckExemptionList",
                 (unsigned int *)&SecurityDescriptor)
            && (_DWORD)SecurityDescriptor == 1 )
          {
            RegCloseKey((HKEY)hMem);
            hMem = 0;
LABEL_147:
            if ( !RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Ole\\AppCompat\\ActivationSecurityCheckExemptionList",
                    0,
                    0x20019u,
                    &phkResult) )
            {
              v48 = *((_QWORD *)a11 + 11);
              v49 = 0;
              v50 = (const WCHAR *)(v48 + 118);
              v51 = v48 + 118;
              if ( !v48 )
                v51 = 0;
              if ( v51 )
              {
                LODWORD(SecurityDescriptor) = 0;
                if ( !v48 )
                  v50 = 0;
                *(_DWORD *)Data = 0;
                LODWORD(v70) = 4;
                if ( !RegQueryValueExW(phkResult, v50, 0, (LPDWORD)&SecurityDescriptor, Data, (LPDWORD)&v70)
                  && (_DWORD)SecurityDescriptor == 1 )
                {
                  v49 = 1;
                  if ( *(_WORD *)Data != 49 || (v43 = 1, *(_WORD *)&Data[2]) )
                    v43 = 0;
                }
              }
              RegCloseKey(phkResult);
              phkResult = 0;
              v52 = 0;
              if ( v49 )
                v52 = v43;
              v43 = v52;
            }
            goto LABEL_161;
          }
          RegCloseKey((HKEY)hMem);
          hMem = 0;
        }
LABEL_161:
        v31 = v43;
      }
LABEL_162:
      if ( v31 )
        return v31;
LABEL_163:
      if ( gdwActivationFailureLoggingLevel != 1 && (gdwActivationFailureLoggingLevel || (a9 & 0x4000) != 0) )
      {
        v57 = StringSecurityDescriptor;
        v53 = a6;
      }
      else
      {
        v53 = a6;
        v54 = 0;
        if ( a11 )
        {
          v55 = *((_QWORD *)a11 + 11);
          v56 = v55 + 196;
          if ( !v55 )
            v56 = 0;
        }
        else
        {
          v56 = 0;
        }
        v57 = StringSecurityDescriptor;
        LOBYTE(v54) = a6 == 0;
        LODWORD(lpcbData) = 18208;
        LogAccessFailed(
          *(_QWORD *)&EventDescriptor.Id,
          v38,
          StringSecurityDescriptor,
          v56,
          0,
          lpcbData,
          v38[9],
          v71,
          v54,
          (_DWORD)v73);
      }
      if ( a5 )
      {
        UserSid = GetUserSid(v38[9]);
        if ( (unsigned int)dword_18014E4B8 > 2
          && (qword_18014E4C8 & 0x400000000000LL) != 0
          && (qword_18014E4D0 & 0x400000000000LL) == qword_18014E4D0 )
        {
          LODWORD(v70) = v53;
          StringSecurityDescriptor = 0;
          ConvertSidToStringSidW(UserSid, &StringSecurityDescriptor);
          v59 = (LPWSTR)&Class;
          if ( StringSecurityDescriptor )
            v59 = StringSecurityDescriptor;
          StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v57, 0);
          v71 = -2147024891;
          v88 = &v70;
          v89 = 4;
          if ( v59 )
          {
            v61 = -1;
            do
              v62 = v59[++v61] == 0;
            while ( !v62 );
            v63 = 2 * v61 + 2;
          }
          else
          {
            v59 = (LPWSTR)&Class;
            v63 = 2;
          }
          v85 = v59;
          v86 = v63;
          v87 = 0;
          if ( StringRawBuffer )
          {
            do
              v62 = StringRawBuffer[++v32] == 0;
            while ( !v62 );
            v64 = 2 * v32 + 2;
          }
          else
          {
            StringRawBuffer = &Class;
            v64 = 2;
          }
          v82 = StringRawBuffer;
          v83 = v64;
          v80 = &v71;
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_18014E4C0;
          v84 = 0;
          v81 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18014E4C0;
          v77 = byte_18013FA9B;
          UserData.Reserved = 2;
          v78 = 89;
          v79 = 1;
          LODWORD(v73) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
          if ( StringSecurityDescriptor )
            LocalFree(StringSecurityDescriptor);
        }
        if ( UserSid )
          HeapFree(g_hHeap, 0, UserSid);
      }
      return v31;
    }
    if ( v39 )
    {
      v41 = *(void **)(v39 + 48);
    }
    else
    {
      v42 = *((_QWORD *)a11 + 12);
      if ( !v42 )
        goto LABEL_119;
      v41 = *(void **)(v42 + 104);
    }
    if ( v41 )
      goto LABEL_127;
LABEL_119:
    v31 = 0;
    goto LABEL_162;
  }
  if ( EqualSid(phkResult + 39, gSidAnonymous) || !(unsigned int)CToken::IsTokenILLower((CToken *)v38, v37) )
    return v31;
  if ( (unsigned int)CToken::IsTokenILLowerThanDefaultLabel((CToken *)v38) )
  {
    v31 = 0;
    goto LABEL_115;
  }
  return 1;
}

```

## disassembly

```asm
0x18005d8e0  push    rbp
0x18005d8e2  push    rbx
0x18005d8e3  push    rsi
0x18005d8e4  push    rdi
0x18005d8e5  push    r12
0x18005d8e7  push    r13
0x18005d8e9  push    r14
0x18005d8eb  push    r15
0x18005d8ed  lea     rbp, [rsp-28h]
0x18005d8f2  sub     rsp, 128h
0x18005d8f9  mov     rax, cs:__security_cookie
0x18005d900  xor     rax, rsp
0x18005d903  mov     [rbp+60h+var_50], rax
0x18005d907  mov     r15, [rbp+60h+arg_38]
0x18005d90e  mov     r12, r8
0x18005d911  mov     rsi, [rbp+60h+arg_48]
0x18005d918  mov     r13, [rbp+60h+arg_50]
0x18005d91f  mov     eax, [rbp+60h+arg_20]
0x18005d925  mov     edi, [rbp+60h+arg_28]
0x18005d92b  mov     [rsp+160h+StringSecurityDescriptor], rdx
0x18005d930  mov     edx, 4
0x18005d935  mov     qword ptr [rbp+60h+EventDescriptor.Id], rcx
0x18005d939  mov     ecx, 2
0x18005d93e  mov     [rsp+160h+phkResult], r15
0x18005d943  mov     qword ptr [rbp+60h+Type], rsi
0x18005d947  mov     [rsp+160h+var_E8], r9d
0x18005d94c  mov     [rbp+60h+SecurityDescriptor], r8
0x18005d950  test    r9d, r9d
0x18005d953  jz      short loc_18005D976
0x18005d955  test    eax, eax
0x18005d957  jz      short loc_18005D96A
0x18005d959  test    edi, edi
0x18005d95b  mov     ebx, 20h ; ' '
0x18005d960  mov     ecx, 40h ; '@'
0x18005d965  cmovz   ebx, ecx
0x18005d968  jmp     short loc_18005D980
0x18005d96a  test    edi, edi
0x18005d96c  mov     ebx, 10h
0x18005d971  cmovnz  ebx, edx
0x18005d974  jmp     short loc_18005D980
0x18005d976  test    edi, edi
0x18005d978  mov     ebx, 8
0x18005d97d  cmovnz  ebx, ecx
0x18005d980  mov     r14d, [rbp+60h+arg_30]
0x18005d987  test    r13, r13
0x18005d98a  jz      short loc_18005D9E8
0x18005d98c  mov     rcx, r13; this
0x18005d98f  call    ?IsInteractiveUser@CClassData@@QEAAHXZ; CClassData::IsInteractiveUser(void)
0x18005d994  test    eax, eax
0x18005d996  jz      short loc_18005D9E2
0x18005d998  mov     rax, [r13+58h]
0x18005d99c  test    rax, rax
0x18005d99f  jz      short loc_18005D9A6
0x18005d9a1  mov     ecx, [rax+48h]
0x18005d9a4  jmp     short loc_18005D9B5
0x18005d9a6  mov     rax, [r13+60h]
0x18005d9aa  test    rax, rax
0x18005d9ad  jz      short loc_18005D9E2
0x18005d9af  mov     ecx, [rax+88h]
0x18005d9b5  test    cl, 20h
0x18005d9b8  jz      short loc_18005D9E2
0x18005d9ba  test    r15, r15
0x18005d9bd  jz      loc_18005DC8C
0x18005d9c3  mov     eax, [r15+60h]
0x18005d9c7  cmp     eax, 0FFFFFFFFh
0x18005d9ca  jnz     short loc_18005D9D9
0x18005d9cc  mov     rcx, [r15+48h]; void *
0x18005d9d0  call    ?GetSessionId2@@YAKPEAX@Z; GetSessionId2(void *)
0x18005d9d5  mov     [r15+60h], eax
0x18005d9d9  cmp     r14d, eax
0x18005d9dc  jnz     loc_18005DC8C
0x18005d9e2  mov     eax, [rbp+60h+arg_20]
0x18005d9e8  test    edi, edi
0x18005d9ea  jz      loc_18005DBA3
0x18005d9f0  test    eax, eax
0x18005d9f2  jnz     loc_18005DBA3
0x18005d9f8  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005d9ff  call    cs:__imp_AcquireSRWLockShared
0x18005da05  mov     rsi, cs:?gpDefaultLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultLaunchRestrictionsSD
0x18005da0c  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005da13  test    rsi, rsi
0x18005da16  jz      short loc_18005DA40
0x18005da18  lock inc dword ptr [rsi+0Ch]
0x18005da1c  call    cs:__imp_ReleaseSRWLockShared
0x18005da22  mov     rdx, [rsi]; pSecurityDescriptor
0x18005da25  xor     r9d, r9d; void *
0x18005da28  mov     rcx, [r15+48h]; ClientToken
0x18005da2c  mov     r8d, ebx; unsigned int
0x18005da2f  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x18005da34  mov     rcx, rsi; this
0x18005da37  mov     edi, eax
0x18005da39  call    ?DecRefCount@CSecDescriptor@@QEAAXXZ; CSecDescriptor::DecRefCount(void)
0x18005da3e  jmp     short loc_18005DA61
0x18005da40  call    cs:__imp_ReleaseSRWLockShared
0x18005da46  mov     rsi, cs:?gpNoRegLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpNoRegLaunchRestrictionsSD
0x18005da4d  xor     r9d, r9d; void *
0x18005da50  mov     rcx, [r15+48h]; ClientToken
0x18005da54  mov     r8d, ebx; unsigned int
0x18005da57  mov     rdx, [rsi]; pSecurityDescriptor
0x18005da5a  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x18005da5f  mov     edi, eax
0x18005da61  test    edi, edi
0x18005da63  jnz     loc_18005DB9F
0x18005da69  mov     eax, cs:?gdwActivationFailureLoggingLevel@@3KA; ulong gdwActivationFailureLoggingLevel
0x18005da6f  xor     edi, edi
0x18005da71  cmp     eax, 1
0x18005da74  jz      short loc_18005DA86
0x18005da76  test    eax, eax
0x18005da78  jnz     short loc_18005DADD
0x18005da7a  test    dword ptr [rbp+60h+arg_40], 4000h
0x18005da84  jnz     short loc_18005DADD
0x18005da86  mov     rcx, [r15+48h]
0x18005da8a  test    r13, r13
0x18005da8d  jz      short loc_18005DAA3
0x18005da8f  mov     rax, [r13+58h]
0x18005da93  test    rax, rax
0x18005da96  lea     r9, [rax+0C4h]
0x18005da9d  cmovz   r9, rdi
0x18005daa1  jmp     short loc_18005DAA6
0x18005daa3  mov     r9, rdi
0x18005daa6  mov     eax, [rsp+160h+var_E8]
0x18005daaa  mov     rdx, r15
0x18005daad  mov     r8, [rsp+160h+StringSecurityDescriptor]
0x18005dab2  mov     [rsp+160h+var_118], 7
0x18005daba  mov     [rsp+160h+var_120], edi
0x18005dabe  mov     [rsp+160h+var_128], eax
0x18005dac2  mov     [rsp+160h+var_130], rcx
0x18005dac7  mov     rcx, qword ptr [rbp+60h+EventDescriptor.Id]
0x18005dacb  mov     dword ptr [rsp+160h+lpcbData], 471Fh
0x18005dad3  mov     [rsp+160h+StringSecurityDescriptorLen], rdi
0x18005dad8  call    ?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z; LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)
0x18005dadd  mov     eax, cs:dword_18014E4B8
0x18005dae3  test    eax, eax
0x18005dae5  jnz     short loc_18005DB04
0x18005dae7  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18005daed  jz      loc_18005DC8C
0x18005daf3  mov     rax, cs:WPP_GLOBAL_Control
0x18005dafa  test    byte ptr [rax+1Ch], 1
0x18005dafe  jz      loc_18005DC8C
0x18005db04  mov     rcx, [rsi]; SecurityDescriptor
0x18005db07  lea     r9, [rsp+160h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18005db0c  mov     edx, 1; RequestedStringSDRevision
0x18005db11  mov     [rsp+160h+StringSecurityDescriptor], rdi
0x18005db16  mov     r8d, 1Fh; SecurityInformation
0x18005db1c  mov     [rsp+160h+StringSecurityDescriptorLen], rdi; StringSecurityDescriptorLen
0x18005db21  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18005db27  test    eax, eax
0x18005db29  jz      short loc_18005DB84
0x18005db2b  mov     eax, cs:dword_18014E4B8
0x18005db31  test    eax, eax
0x18005db33  jnz     short loc_18005DB4A
0x18005db35  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18005db3b  jz      short loc_18005DB84
0x18005db3d  mov     rax, cs:WPP_GLOBAL_Control
0x18005db44  test    byte ptr [rax+1Ch], 1
0x18005db48  jz      short loc_18005DB84
0x18005db4a  mov     rax, [rsp+160h+StringSecurityDescriptor]
0x18005db4f  lea     r8, aLaunchoractiva; "LaunchOrActivationAllowed"
0x18005db56  mov     [rsp+160h+var_130], rax
0x18005db5b  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005db62  lea     rax, aWs; "%ws"
0x18005db69  mov     r9d, 0ECFh
0x18005db6f  mov     [rsp+160h+lpcbData], rax
0x18005db74  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005db7b  mov     dword ptr [rsp+160h+StringSecurityDescriptorLen], edi
0x18005db7f  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005db84  mov     rcx, [rsp+160h+StringSecurityDescriptor]; hMem
0x18005db89  test    rcx, rcx
0x18005db8c  jz      loc_18005DC8C
0x18005db92  call    cs:__imp_LocalFree
0x18005db98  xor     eax, eax
0x18005db9a  jmp     loc_18005E489
0x18005db9f  mov     rsi, qword ptr [rbp+60h+Type]
0x18005dba3  xor     edi, edi
0x18005dba5  mov     dword ptr [rsp+160h+Data], edi
0x18005dba9  test    r12, r12
0x18005dbac  jz      loc_18005DDA6
0x18005dbb2  xor     r12b, r12b
0x18005dbb5  mov     [rsp+160h+hMem], rdi
0x18005dbba  test    r13, r13
0x18005dbbd  jz      loc_18005DC96
0x18005dbc3  mov     rcx, r13; this
0x18005dbc6  call    ?IsInteractiveUser@CClassData@@QEAAHXZ; CClassData::IsInteractiveUser(void)
0x18005dbcb  test    eax, eax
0x18005dbcd  jz      loc_18005DC96
0x18005dbd3  mov     rax, [r13+58h]
0x18005dbd7  test    rax, rax
0x18005dbda  jz      short loc_18005DBE1
0x18005dbdc  mov     ecx, [rax+48h]
0x18005dbdf  jmp     short loc_18005DBF4
0x18005dbe1  mov     rax, [r13+60h]
0x18005dbe5  test    rax, rax
0x18005dbe8  jz      loc_18005DC96
0x18005dbee  mov     ecx, [rax+88h]
0x18005dbf4  test    cl, 10h
0x18005dbf7  jz      loc_18005DC96
0x18005dbfd  test    rsi, rsi
0x18005dc00  jz      short loc_18005DC13
0x18005dc02  lea     rax, [rsi+9Ch]
0x18005dc09  mov     [rsp+160h+hMem], rax
0x18005dc0e  jmp     loc_18005DC96
0x18005dc13  test    r14d, r14d
0x18005dc16  jnz     short loc_18005DC2D
0x18005dc18  call    IsQueryActiveSessionPresent
0x18005dc1d  test    al, al
0x18005dc1f  jz      short loc_18005DC96
0x18005dc21  xor     ecx, ecx
0x18005dc23  call    cs:__imp_IsInteractiveUserSession
0x18005dc29  test    eax, eax
0x18005dc2b  jz      short loc_18005DC96
0x18005dc2d  lea     rdx, [rsp+160h+hMem]; void **
0x18005dc32  mov     ecx, r14d; unsigned int
0x18005dc35  call    ?GetUserSidForSession@@YAJKPEAPEAX@Z; GetUserSidForSession(ulong,void * *)
0x18005dc3a  test    eax, eax
0x18005dc3c  jns     short loc_18005DC93
0x18005dc3e  mov     ecx, cs:dword_18014E4B8
0x18005dc44  test    ecx, ecx
0x18005dc46  jnz     short loc_18005DC5D
0x18005dc48  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18005dc4e  jz      short loc_18005DC8C
0x18005dc50  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dc57  test    byte ptr [rcx+1Ch], 1
0x18005dc5b  jz      short loc_18005DC8C
0x18005dc5d  lea     rcx, aGetusersidfors; "GetUserSidForSession failed: %!HRESULT!"
0x18005dc64  mov     dword ptr [rsp+160h+var_130], eax
0x18005dc68  mov     [rsp+160h+lpcbData], rcx
0x18005dc6d  lea     r8, aLaunchoractiva; "LaunchOrActivationAllowed"
0x18005dc74  mov     ecx, eax
0x18005dc76  mov     dword ptr [rsp+160h+StringSecurityDescriptorLen], edi
0x18005dc7a  mov     r9d, 0F02h
0x18005dc80  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005dc87  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005dc8c  xor     eax, eax
0x18005dc8e  jmp     loc_18005E489
0x18005dc93  mov     r12b, 1
0x18005dc96  mov     r14, [rbp+60h+SecurityDescriptor]
0x18005dc9a  mov     r8d, ebx; unsigned int
0x18005dc9d  mov     r9, [rsp+160h+hMem]; void *
0x18005dca2  mov     rdx, r14; pSecurityDescriptor
0x18005dca5  mov     rcx, [r15+48h]; ClientToken
0x18005dca9  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x18005dcae  mov     r15d, eax
0x18005dcb1  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18005dcb8  test    eax, eax
0x18005dcba  jnz     loc_18005DD72
0x18005dcc0  mov     ecx, cs:dword_18014E4B8
0x18005dcc6  test    ecx, ecx
0x18005dcc8  jnz     short loc_18005DCE7
0x18005dcca  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18005dcd0  jz      loc_18005DD72
0x18005dcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dcdd  test    byte ptr [rcx+1Ch], 1
0x18005dce1  jz      loc_18005DD72
0x18005dce7  lea     r9, [rsp+160h+var_F0]; StringSecurityDescriptor
0x18005dcec  mov     [rsp+160h+var_F0], rdi
0x18005dcf1  mov     edx, 1; RequestedStringSDRevision
0x18005dcf6  mov     [rsp+160h+StringSecurityDescriptorLen], rdi; StringSecurityDescriptorLen
0x18005dcfb  mov     r8d, 1Fh; SecurityInformation
0x18005dd01  mov     rcx, r14; SecurityDescriptor
0x18005dd04  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18005dd0a  test    eax, eax
0x18005dd0c  jz      short loc_18005DD62
0x18005dd0e  mov     eax, cs:dword_18014E4B8
0x18005dd14  test    eax, eax
0x18005dd16  jnz     short loc_18005DD2D
0x18005dd18  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18005dd1e  jz      short loc_18005DD62
0x18005dd20  mov     rax, cs:WPP_GLOBAL_Control
0x18005dd27  test    byte ptr [rax+1Ch], 1
0x18005dd2b  jz      short loc_18005DD62
0x18005dd2d  mov     rax, [rsp+160h+var_F0]
0x18005dd32  lea     r8, aLaunchoractiva; "LaunchOrActivationAllowed"
0x18005dd39  mov     [rsp+160h+var_130], rax
0x18005dd3e  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005dd45  lea     rax, aWs; "%ws"
0x18005dd4c  mov     r9d, 0F16h
0x18005dd52  mov     [rsp+160h+lpcbData], rax
0x18005dd57  mov     ecx, esi
0x18005dd59  mov     dword ptr [rsp+160h+StringSecurityDescriptorLen], edi
0x18005dd5d  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005dd62  mov     rcx, [rsp+160h+var_F0]; hMem
0x18005dd67  test    rcx, rcx
0x18005dd6a  jz      short loc_18005DD72
0x18005dd6c  call    cs:__imp_LocalFree
0x18005dd72  mov     dword ptr [rbp+60h+var_D8], 4
0x18005dd79  cmp     [rbp+60h+arg_28], edi
0x18005dd7f  jnz     short loc_18005DD8D
0x18005dd81  mov     rcx, r14; struct _SECURITY_DESCRIPTOR *
0x18005dd84  call    ?IsSACLPresentInSecurityDescriptor@@YAHPEAU_SECURITY_DESCRIPTOR@@@Z; IsSACLPresentInSecurityDescriptor(_SECURITY_DESCRIPTOR *)
0x18005dd89  mov     dword ptr [rsp+160h+Data], eax
0x18005dd8d  test    r12b, r12b
0x18005dd90  jz      loc_18005DF22
0x18005dd96  mov     rcx, [rsp+160h+hMem]; hMem
0x18005dd9b  call    cs:__imp_LocalFree
0x18005dda1  jmp     loc_18005DF22
0x18005dda6  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005ddad  call    cs:__imp_AcquireSRWLockShared
0x18005ddb3  mov     r12, cs:?gpDefaultLaunchPermissionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultLaunchPermissionsSD
0x18005ddba  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005ddc1  test    r12, r12
  ... truncated ...
```
