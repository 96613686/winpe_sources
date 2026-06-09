# LaunchOrActivationAllowed(void *,HSTRING__ *,_SECURITY_DESCRIPTOR *,int,int,int,ulong,CToken *,ulong,CToken *,CClassData *)

- ea: `0x180061fc0`
- end: `0x180062bfc`
- name: `?LaunchOrActivationAllowed@@YAHPEAXPEAUHSTRING__@@PEAU_SECURITY_DESCRIPTOR@@HHHKPEAVCToken@@K3PEAVCClassData@@@Z`
- size: `3132`
- prototype: `__int64 __fastcall(void *, HSTRING, struct _SECURITY_DESCRIPTOR *, int, int, int, unsigned int, struct CToken *, unsigned int, struct CToken *, struct CClassData *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009054`
- `0x180061ec0`

## callees

- `0x18001c624`
- `0x18002fad4`
- `0x18002fc10`
- `0x18003b69c`
- `0x180051954`
- `0x180053644`
- `0x180054bc0`
- `0x1800603ac`
- `0x1800618f8`
- `0x180061fc0`
- `0x180064614`
- `0x1800710a4`
- `0x180075b1c`
- `0x18007ab08`
- `0x1800b7ac0`
- `0x1800b7e90`
- `0x1800b927c`
- `0x1800f1174`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800625f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800625f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062bcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800627d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062850`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006291b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062997`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800627d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062850`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006291b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062997`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062731`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062810`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062882`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062731`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062810`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062882`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800628e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800628e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180062484`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180062484`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800624a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800624ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800624a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800624ba`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006264d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006264d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800621d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800623c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180062540`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800621d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800623c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180062540`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180062a5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180062a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a82`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180062b99`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180062b99`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006224b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180062437`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006246c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800625ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180062baf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006224b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180062437`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006246c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800625ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180062baf`
- `ext-ms-win-session-usertoken-l1-1-0!IsInteractiveUserSession` at `0x1800622e2`
- `ext-ms-win-session-usertoken-l1-1-0!IsInteractiveUserSession` at `0x1800622e2`

## string_xrefs

- `0x180062214`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180062345`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180062409`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006257f`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006282d`: `AllowLocalActivationSecurityCheckExemptionList`
- `0x18006271e`: `Software\Policies\Microsoft\Windows NT\DCOM\AppCompat\ActivationSecurityCheckExemptionList`
- `0x1800627ff`: `Software\Policies\Microsoft\Windows NT\DCOM\AppCompat`
- `0x180062874`: `Software\Microsoft\Ole\AppCompat\ActivationSecurityCheckExemptionList`
- `0x180062322`: `GetUserSidForSession failed: %!HRESULT!`

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
  unsigned int v14; // ebx
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  unsigned int SessionId2; // eax
  PSECURITY_DESCRIPTOR *DefaultLaunchRestrictions; // rax
  void *v20; // rcx
  CSecDescriptor *v21; // rsi
  int v22; // edi
  __int64 v23; // rax
  __int64 v24; // r9
  void *v25; // rcx
  char v27; // r12
  __int64 v28; // rax
  int v29; // ecx
  __int64 v30; // rax
  int UserSidForSession; // eax
  struct _SECURITY_DESCRIPTOR *v32; // r14
  unsigned int v33; // r15d
  __int64 v34; // rsi
  CSecDescriptor *v35; // r12
  struct CSecDescriptor *v36; // r14
  void *v37; // rcx
  struct _SECURITY_DESCRIPTOR *v38; // rbx
  struct CToken *v39; // rbx
  HANDLE *v40; // r12
  __int64 v41; // rdx
  __int64 v42; // rax
  void *v43; // rcx
  __int64 v44; // rcx
  int v45; // ebx
  __int64 v46; // rcx
  int v47; // r14d
  const WCHAR *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rcx
  int v51; // r14d
  const WCHAR *v52; // rdx
  __int64 v53; // rax
  int v54; // eax
  int v55; // r14d
  int v56; // ecx
  __int64 v57; // rax
  __int64 v58; // r9
  LPWSTR v59; // r13
  void *UserSid; // rbx
  LPWSTR v61; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v63; // rcx
  bool v64; // zf
  int v65; // ecx
  int v66; // esi
  PULONG StringSecurityDescriptorLen; // [rsp+20h] [rbp-E0h]
  PULONG StringSecurityDescriptorLena; // [rsp+20h] [rbp-E0h]
  PULONG StringSecurityDescriptorLenb; // [rsp+20h] [rbp-E0h]
  PULONG StringSecurityDescriptorLenc; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpcbData; // [rsp+70h] [rbp-90h] BYREF
  int v76; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR v78; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type[2]; // [rsp+90h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v82; // [rsp+C0h] [rbp-40h]
  int v83; // [rsp+C8h] [rbp-38h]
  int v84; // [rsp+CCh] [rbp-34h]
  int *v85; // [rsp+D0h] [rbp-30h]
  __int64 v86; // [rsp+D8h] [rbp-28h]
  PCWSTR v87; // [rsp+E0h] [rbp-20h]
  int v88; // [rsp+E8h] [rbp-18h]
  int v89; // [rsp+ECh] [rbp-14h]
  LPWSTR v90; // [rsp+F0h] [rbp-10h]
  int v91; // [rsp+F8h] [rbp-8h]
  int v92; // [rsp+FCh] [rbp-4h]
  LPWSTR *p_lpcbData; // [rsp+100h] [rbp+0h]
  __int64 v94; // [rsp+108h] [rbp+8h]

  v12 = a10;
  v13 = a5;
  StringSecurityDescriptor = a2;
  *(_QWORD *)&EventDescriptor.Id = a1;
  phkResult = (HKEY)a8;
  *(_QWORD *)Type = a10;
  v76 = a4;
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
    DefaultLaunchRestrictions = (PSECURITY_DESCRIPTOR *)GetDefaultLaunchRestrictions();
    v20 = (void *)*((_QWORD *)a8 + 9);
    v21 = (CSecDescriptor *)DefaultLaunchRestrictions;
    if ( DefaultLaunchRestrictions )
    {
      v22 = CheckForAccess(v20, *DefaultLaunchRestrictions, v14, 0);
      CSecDescriptor::DecRefCount(v21);
    }
    else
    {
      v21 = gpNoRegLaunchRestrictionsSD;
      v22 = CheckForAccess(v20, *(PSECURITY_DESCRIPTOR *)gpNoRegLaunchRestrictionsSD, v14, 0);
    }
    if ( !v22 )
    {
      if ( gdwActivationFailureLoggingLevel == 1 || !gdwActivationFailureLoggingLevel && (a9 & 0x4000) == 0 )
      {
        if ( a11 )
        {
          v23 = *((_QWORD *)a11 + 11);
          v24 = v23 + 196;
          if ( !v23 )
            v24 = 0;
        }
        else
        {
          v24 = 0;
        }
        LogAccessFailed(
          *(_QWORD *)&EventDescriptor.Id,
          a8,
          StringSecurityDescriptor,
          v24,
          0,
          18207,
          *((_QWORD *)a8 + 9),
          v76,
          0,
          7);
      }
      if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = *(void **)v21;
        StringSecurityDescriptor = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v25, 1u, 0x1Fu, &StringSecurityDescriptor, 0)
          && (dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
        {
          LODWORD(StringSecurityDescriptorLena) = 0;
          ComTraceMessage(
            -1,
            "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            "LaunchOrActivationAllowed",
            3791,
            StringSecurityDescriptorLena,
            L"%ws",
            StringSecurityDescriptor);
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
    v27 = 0;
    hMem = 0;
    if ( !a11 || !(unsigned int)CClassData::IsInteractiveUser(a11) )
      goto LABEL_69;
    v28 = *((_QWORD *)a11 + 11);
    if ( v28 )
    {
      v29 = *(_DWORD *)(v28 + 72);
    }
    else
    {
      v30 = *((_QWORD *)a11 + 12);
      if ( !v30 )
        goto LABEL_69;
      v29 = *(_DWORD *)(v30 + 136);
    }
    if ( (v29 & 0x10) != 0 )
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
        if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(StringSecurityDescriptorLen) = 0;
          ComTraceMessage(
            (unsigned int)UserSidForSession,
            "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            "LaunchOrActivationAllowed",
            3842,
            StringSecurityDescriptorLen,
            L"GetUserSidForSession failed: %!HRESULT!",
            UserSidForSession);
        }
        return 0;
      }
      v27 = 1;
    }
LABEL_69:
    v32 = (struct _SECURITY_DESCRIPTOR *)SecurityDescriptor;
    v33 = CheckForAccess(*((HANDLE *)a8 + 9), SecurityDescriptor, v14, hMem);
    v34 = -1;
    if ( !v33 && (dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
    {
      lpcbData = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v32, 1u, 0x1Fu, &lpcbData, 0)
        && (dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
      {
        LODWORD(StringSecurityDescriptorLenb) = 0;
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          "LaunchOrActivationAllowed",
          3862,
          StringSecurityDescriptorLenb,
          L"%ws",
          lpcbData);
      }
      if ( lpcbData )
        LocalFree(lpcbData);
    }
    LODWORD(v78) = 4;
    if ( !a6 )
      *(_DWORD *)Data = IsSACLPresentInSecurityDescriptor(v32);
    if ( v27 )
      LocalFree(hMem);
    goto LABEL_107;
  }
  AcquireSRWLockShared(&gpClientLock);
  v35 = gpDefaultLaunchPermissionsSD;
  if ( gpDefaultLaunchPermissionsSD )
  {
    _InterlockedIncrement((volatile signed __int32 *)gpDefaultLaunchPermissionsSD + 3);
    ReleaseSRWLockShared(&gpClientLock);
    v36 = v35;
  }
  else
  {
    ReleaseSRWLockShared(&gpClientLock);
    v36 = gpNoRegLaunchPermissionsSD;
  }
  v37 = (void *)*((_QWORD *)a8 + 9);
  hMem = *(HLOCAL *)v36;
  v33 = CheckForAccess(v37, hMem, v14, 0);
  v34 = -1;
  if ( !v33 && (dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
  {
    v38 = (struct _SECURITY_DESCRIPTOR *)hMem;
    v78 = 0;
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(hMem, 1u, 0x1Fu, &v78, 0)
      && (dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0) )
    {
      LODWORD(StringSecurityDescriptorLenc) = 0;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        "LaunchOrActivationAllowed",
        3904,
        StringSecurityDescriptorLenc,
        L"%ws",
        v78);
    }
    if ( v78 )
      LocalFree(v78);
  }
  else
  {
    v38 = (struct _SECURITY_DESCRIPTOR *)hMem;
  }
  if ( !a6 )
    *(_DWORD *)Data = IsSACLPresentInSecurityDescriptor(v38);
  if ( v35 && _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 3, 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v36 )
    {
      HeapFree(g_hHeap, 0, *(LPVOID *)v36);
      *(_QWORD *)v36 = 0;
    }
    operator delete(v36, 0x10u);
  }
  v32 = (struct _SECURITY_DESCRIPTOR *)SecurityDescriptor;
  LODWORD(v78) = 2;
LABEL_107:
  v39 = *(struct CToken **)Type;
  v40 = (HANDLE *)phkResult;
  if ( !*(_QWORD *)Type || *(_DWORD *)Data )
    goto LABEL_162;
  if ( !v33 )
  {
LABEL_115:
    if ( !a11 )
      goto LABEL_163;
    v41 = *((_QWORD *)a11 + 11);
    v42 = v41 + 118;
    if ( !v41 )
      v42 = 0;
    if ( !v42 )
      goto LABEL_119;
    if ( !v32 )
      goto LABEL_129;
    v43 = (void *)*((_QWORD *)a11 + 22);
    if ( v43 )
    {
LABEL_127:
      *(_DWORD *)Data = 1;
      IsValidCOMSecurityDescriptor(v43, (int *)Data);
      if ( *(_DWORD *)Data )
      {
        v33 = 0;
        goto LABEL_162;
      }
LABEL_129:
      hMem = 0;
      phkResult = 0;
      LODWORD(SecurityDescriptor) = 0;
      v45 = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows NT\\DCOM\\AppCompat\\ActivationSecurityCheckExemptionList",
             0,
             0x20019u,
             &phkResult) )
      {
        goto LABEL_147;
      }
      v46 = *((_QWORD *)a11 + 11);
      v47 = 0;
      v48 = (const WCHAR *)(v46 + 118);
      v49 = v46 + 118;
      if ( !v46 )
        v49 = 0;
      if ( v49 )
      {
        Type[0] = 0;
        if ( !v46 )
          v48 = 0;
        *(_DWORD *)Data = 0;
        LODWORD(lpcbData) = 4;
        if ( !RegQueryValueExW(phkResult, v48, 0, Type, Data, (LPDWORD)&lpcbData) && Type[0] == 1 )
        {
          v47 = 1;
          if ( *(_WORD *)Data == 49 && !*(_WORD *)&Data[2] )
            v45 = 1;
        }
      }
      v33 = 0;
      if ( v47 )
        v33 = v45;
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( !v47 )
      {
        v45 = v33;
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
              v50 = *((_QWORD *)a11 + 11);
              v51 = 0;
              v52 = (const WCHAR *)(v50 + 118);
              v53 = v50 + 118;
              if ( !v50 )
                v53 = 0;
              if ( v53 )
              {
                LODWORD(SecurityDescriptor) = 0;
                if ( !v50 )
                  v52 = 0;
                *(_DWORD *)Data = 0;
                LODWORD(lpcbData) = 4;
                if ( !RegQueryValueExW(phkResult, v52, 0, (LPDWORD)&SecurityDescriptor, Data, (LPDWORD)&lpcbData)
                  && (_DWORD)SecurityDescriptor == 1 )
                {
                  v51 = 1;
                  if ( *(_WORD *)Data != 49 || (v45 = 1, *(_WORD *)&Data[2]) )
                    v45 = 0;
                }
              }
              RegCloseKey(phkResult);
              phkResult = 0;
              v54 = 0;
              if ( v51 )
                v54 = v45;
              v45 = v54;
            }
            goto LABEL_161;
          }
          RegCloseKey((HKEY)hMem);
          hMem = 0;
        }
LABEL_161:
        v33 = v45;
      }
LABEL_162:
      if ( v33 )
        return v33;
LABEL_163:
      if ( gdwActivationFailureLoggingLevel != 1 && (gdwActivationFailureLoggingLevel || (a9 & 0x4000) != 0) )
      {
        v59 = StringSecurityDescriptor;
        v55 = a6;
      }
      else
      {
        v55 = a6;
        v56 = 0;
        if ( a11 )
        {
          v57 = *((_QWORD *)a11 + 11);
          v58 = v57 + 196;
          if ( !v57 )
            v58 = 0;
        }
        else
        {
          v58 = 0;
        }
        v59 = StringSecurityDescriptor;
        LOBYTE(v56) = a6 == 0;
        LogAccessFailed(
          *(_QWORD *)&EventDescriptor.Id,
          v40,
          StringSecurityDescriptor,
          v58,
          0,
          18208,
          v40[9],
          v76,
          v56,
          (_DWORD)v78);
      }
      if ( a5 )
      {
        UserSid = GetUserSid(v40[9]);
        if ( (unsigned int)dword_1801574B8 > 2
          && (qword_1801574C8 & 0x400000000000LL) != 0
          && (qword_1801574D0 & 0x400000000000LL) == qword_1801574D0 )
        {
          LODWORD(lpcbData) = v55;
          StringSecurityDescriptor = 0;
          ConvertSidToStringSidW(UserSid, &StringSecurityDescriptor);
          v61 = (LPWSTR)&Class;
          if ( StringSecurityDescriptor )
            v61 = StringSecurityDescriptor;
          StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v59, 0);
          v76 = -2147024891;
          p_lpcbData = &lpcbData;
          v94 = 4;
          if ( v61 )
          {
            v63 = -1;
            do
              v64 = v61[++v63] == 0;
            while ( !v64 );
            v65 = 2 * v63 + 2;
          }
          else
          {
            v61 = (LPWSTR)&Class;
            v65 = 2;
          }
          v90 = v61;
          v91 = v65;
          v92 = 0;
          if ( StringRawBuffer )
          {
            do
              v64 = StringRawBuffer[++v34] == 0;
            while ( !v64 );
            v66 = 2 * v34 + 2;
          }
          else
          {
            StringRawBuffer = &Class;
            v66 = 2;
          }
          v87 = StringRawBuffer;
          v88 = v66;
          v85 = &v76;
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_1801574C0;
          v89 = 0;
          v86 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_1801574C0;
          v82 = byte_180148A3B;
          UserData.Reserved = 2;
          v83 = 89;
          v84 = 1;
          LODWORD(v78) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
          if ( StringSecurityDescriptor )
            LocalFree(StringSecurityDescriptor);
        }
        if ( UserSid )
          HeapFree(g_hHeap, 0, UserSid);
      }
      return v33;
    }
    if ( v41 )
    {
      v43 = *(void **)(v41 + 48);
    }
    else
    {
      v44 = *((_QWORD *)a11 + 12);
      if ( !v44 )
        goto LABEL_119;
      v43 = *(void **)(v44 + 104);
    }
    if ( v43 )
      goto LABEL_127;
LABEL_119:
    v33 = 0;
    goto LABEL_162;
  }
  if ( EqualSid(phkResult + 39, gSidAnonymous) || !(unsigned int)CToken::IsTokenILLower((CToken *)v40, v39) )
    return v33;
  if ( (unsigned int)CToken::IsTokenILLowerThanDefaultLabel((CToken *)v40) )
  {
    v33 = 0;
    goto LABEL_115;
  }
  return 1;
}

```

## disassembly

```asm
0x180061fc0  push    rbp
0x180061fc2  push    rbx
0x180061fc3  push    rsi
0x180061fc4  push    rdi
0x180061fc5  push    r12
0x180061fc7  push    r13
0x180061fc9  push    r14
0x180061fcb  push    r15
0x180061fcd  lea     rbp, [rsp-28h]
0x180061fd2  sub     rsp, 128h
0x180061fd9  mov     rax, cs:__security_cookie
0x180061fe0  xor     rax, rsp
0x180061fe3  mov     [rbp+60h+var_50], rax
0x180061fe7  mov     r15, [rbp+60h+arg_38]
0x180061fee  mov     r12, r8
0x180061ff1  mov     rsi, [rbp+60h+arg_48]
0x180061ff8  mov     r13, [rbp+60h+arg_50]
0x180061fff  mov     eax, [rbp+60h+arg_20]
0x180062005  mov     edi, [rbp+60h+arg_28]
0x18006200b  mov     [rsp+160h+StringSecurityDescriptor], rdx
0x180062010  mov     edx, 4
0x180062015  mov     qword ptr [rbp+60h+EventDescriptor.Id], rcx
0x180062019  mov     ecx, 2
0x18006201e  mov     [rsp+160h+phkResult], r15
0x180062023  mov     qword ptr [rbp+60h+Type], rsi
0x180062027  mov     [rsp+160h+var_E8], r9d
0x18006202c  mov     [rbp+60h+SecurityDescriptor], r8
0x180062030  test    r9d, r9d
0x180062033  jz      short loc_180062056
0x180062035  test    eax, eax
0x180062037  jz      short loc_18006204A
0x180062039  test    edi, edi
0x18006203b  mov     ebx, 20h ; ' '
0x180062040  mov     ecx, 40h ; '@'
0x180062045  cmovz   ebx, ecx
0x180062048  jmp     short loc_180062060
0x18006204a  test    edi, edi
0x18006204c  mov     ebx, 10h
0x180062051  cmovnz  ebx, edx
0x180062054  jmp     short loc_180062060
0x180062056  test    edi, edi
0x180062058  mov     ebx, 8
0x18006205d  cmovnz  ebx, ecx
0x180062060  mov     r14d, [rbp+60h+arg_30]
0x180062067  test    r13, r13
0x18006206a  jz      short loc_1800620C8
0x18006206c  mov     rcx, r13; this
0x18006206f  call    ?IsInteractiveUser@CClassData@@QEAAHXZ; CClassData::IsInteractiveUser(void)
0x180062074  test    eax, eax
0x180062076  jz      short loc_1800620C2
0x180062078  mov     rax, [r13+58h]
0x18006207c  test    rax, rax
0x18006207f  jz      short loc_180062086
0x180062081  mov     ecx, [rax+48h]
0x180062084  jmp     short loc_180062095
0x180062086  mov     rax, [r13+60h]
0x18006208a  test    rax, rax
0x18006208d  jz      short loc_1800620C2
0x18006208f  mov     ecx, [rax+88h]
0x180062095  test    cl, 20h
0x180062098  jz      short loc_1800620C2
0x18006209a  test    r15, r15
0x18006209d  jz      loc_180062351
0x1800620a3  mov     eax, [r15+60h]
0x1800620a7  cmp     eax, 0FFFFFFFFh
0x1800620aa  jnz     short loc_1800620B9
0x1800620ac  mov     rcx, [r15+48h]; void *
0x1800620b0  call    ?GetSessionId2@@YAKPEAX@Z; GetSessionId2(void *)
0x1800620b5  mov     [r15+60h], eax
0x1800620b9  cmp     r14d, eax
0x1800620bc  jnz     loc_180062351
0x1800620c2  mov     eax, [rbp+60h+arg_20]
0x1800620c8  test    edi, edi
0x1800620ca  jz      loc_180062262
0x1800620d0  test    eax, eax
0x1800620d2  jnz     loc_180062262
0x1800620d8  call    ?GetDefaultLaunchRestrictions@@YAPEAVCSecDescriptor@@XZ; GetDefaultLaunchRestrictions(void)
0x1800620dd  mov     rcx, [r15+48h]; ClientToken
0x1800620e1  xor     r9d, r9d; void *
0x1800620e4  mov     rsi, rax
0x1800620e7  mov     r8d, ebx; unsigned int
0x1800620ea  test    rax, rax
0x1800620ed  jnz     short loc_180062102
0x1800620ef  mov     rsi, cs:?gpNoRegLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpNoRegLaunchRestrictionsSD
0x1800620f6  mov     rdx, [rsi]; pSecurityDescriptor
0x1800620f9  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x1800620fe  mov     edi, eax
0x180062100  jmp     short loc_180062114
0x180062102  mov     rdx, [rax]; pSecurityDescriptor
0x180062105  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x18006210a  mov     rcx, rsi; this
0x18006210d  mov     edi, eax
0x18006210f  call    ?DecRefCount@CSecDescriptor@@QEAAXXZ; CSecDescriptor::DecRefCount(void)
0x180062114  test    edi, edi
0x180062116  jnz     loc_18006225E
0x18006211c  mov     eax, cs:?gdwActivationFailureLoggingLevel@@3KA; ulong gdwActivationFailureLoggingLevel
0x180062122  xor     edi, edi
0x180062124  cmp     eax, 1
0x180062127  jz      short loc_180062139
0x180062129  test    eax, eax
0x18006212b  jnz     short loc_180062190
0x18006212d  test    dword ptr [rbp+60h+arg_40], 4000h
0x180062137  jnz     short loc_180062190
0x180062139  mov     rcx, [r15+48h]
0x18006213d  test    r13, r13
0x180062140  jz      short loc_180062156
0x180062142  mov     rax, [r13+58h]
0x180062146  test    rax, rax
0x180062149  lea     r9, [rax+0C4h]
0x180062150  cmovz   r9, rdi
0x180062154  jmp     short loc_180062159
0x180062156  mov     r9, rdi
0x180062159  mov     eax, [rsp+160h+var_E8]
0x18006215d  mov     rdx, r15
0x180062160  mov     r8, [rsp+160h+StringSecurityDescriptor]
0x180062165  mov     [rsp+160h+var_118], 7
0x18006216d  mov     [rsp+160h+var_120], edi
0x180062171  mov     [rsp+160h+var_128], eax
0x180062175  mov     [rsp+160h+var_130], rcx
0x18006217a  mov     rcx, qword ptr [rbp+60h+EventDescriptor.Id]
0x18006217e  mov     dword ptr [rsp+160h+lpcbData], 471Fh
0x180062186  mov     [rsp+160h+StringSecurityDescriptorLen], rdi
0x18006218b  call    ?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z; LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)
0x180062190  mov     eax, cs:dword_1801574B8
0x180062196  test    eax, eax
0x180062198  jnz     short loc_1800621B7
0x18006219a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800621a0  jz      loc_180062351
0x1800621a6  mov     rax, cs:WPP_GLOBAL_Control
0x1800621ad  test    byte ptr [rax+1Ch], 1
0x1800621b1  jz      loc_180062351
0x1800621b7  mov     rcx, [rsi]; SecurityDescriptor
0x1800621ba  lea     r9, [rsp+160h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800621bf  mov     edx, 1; RequestedStringSDRevision
0x1800621c4  mov     [rsp+160h+StringSecurityDescriptor], rdi
0x1800621c9  mov     r8d, 1Fh; SecurityInformation
0x1800621cf  mov     [rsp+160h+StringSecurityDescriptorLen], rdi; StringSecurityDescriptorLen
0x1800621d4  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800621db  nop     dword ptr [rax+rax+00h]
0x1800621e0  test    eax, eax
0x1800621e2  jz      short loc_18006223D
0x1800621e4  mov     eax, cs:dword_1801574B8
0x1800621ea  test    eax, eax
0x1800621ec  jnz     short loc_180062203
0x1800621ee  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800621f4  jz      short loc_18006223D
0x1800621f6  mov     rax, cs:WPP_GLOBAL_Control
0x1800621fd  test    byte ptr [rax+1Ch], 1
0x180062201  jz      short loc_18006223D
0x180062203  mov     rax, [rsp+160h+StringSecurityDescriptor]
0x180062208  lea     r8, aLaunchoractiva; "LaunchOrActivationAllowed"
0x18006220f  mov     [rsp+160h+var_130], rax
0x180062214  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006221b  lea     rax, aWs; "%ws"
0x180062222  mov     r9d, 0ECFh
0x180062228  mov     [rsp+160h+lpcbData], rax
0x18006222d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180062234  mov     dword ptr [rsp+160h+StringSecurityDescriptorLen], edi
0x180062238  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18006223d  mov     rcx, [rsp+160h+StringSecurityDescriptor]; hMem
0x180062242  test    rcx, rcx
0x180062245  jz      loc_180062351
0x18006224b  call    cs:__imp_LocalFree
0x180062252  nop     dword ptr [rax+rax+00h]
0x180062257  xor     eax, eax
0x180062259  jmp     loc_180062BDB
0x18006225e  mov     rsi, qword ptr [rbp+60h+Type]
0x180062262  xor     edi, edi
0x180062264  mov     dword ptr [rsp+160h+Data], edi
0x180062268  test    r12, r12
0x18006226b  jz      loc_18006247D
0x180062271  xor     r12b, r12b
0x180062274  mov     [rsp+160h+hMem], rdi
0x180062279  test    r13, r13
0x18006227c  jz      loc_18006235B
0x180062282  mov     rcx, r13; this
0x180062285  call    ?IsInteractiveUser@CClassData@@QEAAHXZ; CClassData::IsInteractiveUser(void)
0x18006228a  test    eax, eax
0x18006228c  jz      loc_18006235B
0x180062292  mov     rax, [r13+58h]
0x180062296  test    rax, rax
0x180062299  jz      short loc_1800622A0
0x18006229b  mov     ecx, [rax+48h]
0x18006229e  jmp     short loc_1800622B3
0x1800622a0  mov     rax, [r13+60h]
0x1800622a4  test    rax, rax
0x1800622a7  jz      loc_18006235B
0x1800622ad  mov     ecx, [rax+88h]
0x1800622b3  test    cl, 10h
0x1800622b6  jz      loc_18006235B
0x1800622bc  test    rsi, rsi
0x1800622bf  jz      short loc_1800622D2
0x1800622c1  lea     rax, [rsi+9Ch]
0x1800622c8  mov     [rsp+160h+hMem], rax
0x1800622cd  jmp     loc_18006235B
0x1800622d2  test    r14d, r14d
0x1800622d5  jnz     short loc_1800622F2
0x1800622d7  call    IsQueryActiveSessionPresent
0x1800622dc  test    al, al
0x1800622de  jz      short loc_18006235B
0x1800622e0  xor     ecx, ecx
0x1800622e2  call    cs:__imp_IsInteractiveUserSession
0x1800622e9  nop     dword ptr [rax+rax+00h]
0x1800622ee  test    eax, eax
0x1800622f0  jz      short loc_18006235B
0x1800622f2  lea     rdx, [rsp+160h+hMem]; void **
0x1800622f7  mov     ecx, r14d; unsigned int
0x1800622fa  call    ?GetUserSidForSession@@YAJKPEAPEAX@Z; GetUserSidForSession(ulong,void * *)
0x1800622ff  test    eax, eax
0x180062301  jns     short loc_180062358
0x180062303  mov     ecx, cs:dword_1801574B8
0x180062309  test    ecx, ecx
0x18006230b  jnz     short loc_180062322
0x18006230d  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180062313  jz      short loc_180062351
0x180062315  mov     rcx, cs:WPP_GLOBAL_Control
0x18006231c  test    byte ptr [rcx+1Ch], 1
0x180062320  jz      short loc_180062351
0x180062322  lea     rcx, aGetusersidfors; "GetUserSidForSession failed: %!HRESULT!"
0x180062329  mov     dword ptr [rsp+160h+var_130], eax
0x18006232d  mov     [rsp+160h+lpcbData], rcx
0x180062332  lea     r8, aLaunchoractiva; "LaunchOrActivationAllowed"
0x180062339  mov     ecx, eax
0x18006233b  mov     dword ptr [rsp+160h+StringSecurityDescriptorLen], edi
0x18006233f  mov     r9d, 0F02h
0x180062345  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006234c  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180062351  xor     eax, eax
0x180062353  jmp     loc_180062BDB
0x180062358  mov     r12b, 1
0x18006235b  mov     r14, [rbp+60h+SecurityDescriptor]
0x18006235f  mov     r8d, ebx; unsigned int
0x180062362  mov     r9, [rsp+160h+hMem]; void *
0x180062367  mov     rdx, r14; pSecurityDescriptor
0x18006236a  mov     rcx, [r15+48h]; ClientToken
0x18006236e  call    ?CheckForAccess@@YAHPEAXPEAU_SECURITY_DESCRIPTOR@@K0@Z; CheckForAccess(void *,_SECURITY_DESCRIPTOR *,ulong,void *)
0x180062373  mov     r15d, eax
0x180062376  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18006237d  test    eax, eax
0x18006237f  jnz     loc_180062443
0x180062385  mov     ecx, cs:dword_1801574B8
0x18006238b  test    ecx, ecx
0x18006238d  jnz     short loc_1800623AC
0x18006238f  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180062395  jz      loc_180062443
0x18006239b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623a2  test    byte ptr [rcx+1Ch], 1
0x1800623a6  jz      loc_180062443
0x1800623ac  lea     r9, [rsp+160h+var_F0]; StringSecurityDescriptor
0x1800623b1  mov     [rsp+160h+var_F0], rdi
0x1800623b6  mov     edx, 1; RequestedStringSDRevision
0x1800623bb  mov     [rsp+160h+StringSecurityDescriptorLen], rdi; StringSecurityDescriptorLen
0x1800623c0  mov     r8d, 1Fh; SecurityInformation
0x1800623c6  mov     rcx, r14; SecurityDescriptor
0x1800623c9  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800623d0  nop     dword ptr [rax+rax+00h]
0x1800623d5  test    eax, eax
0x1800623d7  jz      short loc_18006242D
0x1800623d9  mov     eax, cs:dword_1801574B8
0x1800623df  test    eax, eax
0x1800623e1  jnz     short loc_1800623F8
0x1800623e3  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800623e9  jz      short loc_18006242D
0x1800623eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800623f2  test    byte ptr [rax+1Ch], 1
0x1800623f6  jz      short loc_18006242D
0x1800623f8  mov     rax, [rsp+160h+var_F0]
0x1800623fd  lea     r8, aLaunchoractiva; "LaunchOrActivationAllowed"
0x180062404  mov     [rsp+160h+var_130], rax
0x180062409  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180062410  lea     rax, aWs; "%ws"
0x180062417  mov     r9d, 0F16h
0x18006241d  mov     [rsp+160h+lpcbData], rax
0x180062422  mov     ecx, esi
0x180062424  mov     dword ptr [rsp+160h+StringSecurityDescriptorLen], edi
0x180062428  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18006242d  mov     rcx, [rsp+160h+var_F0]; hMem
0x180062432  test    rcx, rcx
0x180062435  jz      short loc_180062443
0x180062437  call    cs:__imp_LocalFree
0x18006243e  nop     dword ptr [rax+rax+00h]
0x180062443  mov     dword ptr [rbp+60h+var_D8], 4
0x18006244a  cmp     [rbp+60h+arg_28], edi
0x180062450  jnz     short loc_18006245E
0x180062452  mov     rcx, r14; struct _SECURITY_DESCRIPTOR *
0x180062455  call    ?IsSACLPresentInSecurityDescriptor@@YAHPEAU_SECURITY_DESCRIPTOR@@@Z; IsSACLPresentInSecurityDescriptor(_SECURITY_DESCRIPTOR *)
0x18006245a  mov     dword ptr [rsp+160h+Data], eax
0x18006245e  test    r12b, r12b
0x180062461  jz      loc_18006261D
0x180062467  mov     rcx, [rsp+160h+hMem]; hMem
0x18006246c  call    cs:__imp_LocalFree
0x180062473  nop     dword ptr [rax+rax+00h]
0x180062478  jmp     loc_18006261D
0x18006247d  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180062484  call    cs:__imp_AcquireSRWLockShared
0x18006248b  nop     dword ptr [rax+rax+00h]
0x180062490  mov     r12, cs:?gpDefaultLaunchPermissionsSD@@3PEAVCSecDescriptor@@EA; CSecDescriptor * gpDefaultLaunchPermissionsSD
0x180062497  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18006249e  test    r12, r12
0x1800624a1  jz      short loc_1800624BA
  ... truncated ...
```
