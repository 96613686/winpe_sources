# EvaluateExtensionActivationContextProperties(IExtensionActivationContextProperties *,ActivationPropertiesIn *,ACTIVATION_PARAMS *)

- ea: `0x1800221a0`
- end: `0x180022d82`
- name: `?EvaluateExtensionActivationContextProperties@@YAJPEAUIExtensionActivationContextProperties@@PEAVActivationPropertiesIn@@PEAUACTIVATION_PARAMS@@@Z`
- size: `3042`
- prototype: `int(struct IExtensionActivationContextProperties *, struct ActivationPropertiesIn *, struct ACTIVATION_PARAMS *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008e54c`

## callees

- `0x180005b40`
- `0x18000b0c4`
- `0x18000b100`
- `0x18000ce5c`
- `0x1800210f8`
- `0x1800221a0`
- `0x180023cfc`
- `0x180024590`
- `0x180025950`
- `0x18002aa10`
- `0x180093f20`
- `0x180095c0c`
- `0x1800961a4`
- `0x1800b7ac0`
- `0x1800b9b90`
- `0x1800c31fc`
- `0x1800c3b84`
- `0x1800cc71c`
- `0x180110df8`
- `0x180114010`

## import_xrefs

- `ntdll!RtlQueryPackageClaims` at `0x180022a55`
- `ntdll!RtlQueryPackageClaims` at `0x180022a55`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800226e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800226e7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022b94`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022b94`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022786`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022b40`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022bd2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022c35`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022786`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022b40`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022bd2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022c35`
- `KERNELBASE!GetApplicationUserModelIdFromToken` at `0x1800229fa`
- `KERNELBASE!GetApplicationUserModelIdFromToken` at `0x1800229fa`
- `KERNELBASE!GetPackageFullNameFromToken` at `0x1800229bd`
- `KERNELBASE!GetPackageFullNameFromToken` at `0x1800229bd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002274c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002274c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180022948`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180022948`

## string_xrefs

- `0x180022492`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800224ea`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022509`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002252e`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002255a`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002257c`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002259e`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800225ca`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800225ec`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022625`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022647`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002266a`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800226b6`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022702`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002276f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800227ca`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800227fc`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022839`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002285b`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002287d`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800228ac`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800228e1`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022916`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002298a`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800229d8`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022a11`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022a6c`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022af6`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022b22`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022bab`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022c60`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022ca8`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022ceb`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022d16`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180022d67`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`

## pseudocode

```c
__int64 __fastcall EvaluateExtensionActivationContextProperties(
        struct IExtensionActivationContextProperties *a1,
        struct ActivationPropertiesIn *a2,
        struct ACTIVATION_PARAMS *a3)
{
  int v6; // eax
  unsigned int v7; // r14d
  int v8; // eax
  unsigned int v9; // r14d
  unsigned int i; // eax
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  char v13; // r14
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // edi
  unsigned __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  _QWORD *v22; // r14
  int v23; // eax
  unsigned int v24; // edi
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // edi
  int v30; // eax
  unsigned int v31; // edi
  int v32; // eax
  unsigned int v33; // r14d
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // edi
  int v37; // eax
  unsigned int v38; // edi
  int v39; // eax
  unsigned int v40; // edi
  int v41; // eax
  unsigned int v42; // ebx
  __int64 v44; // rdx
  int v45; // eax
  unsigned int v46; // edi
  __int64 v47; // rax
  const char *v48; // r9
  unsigned int LastError; // ebx
  __int64 v50; // rax
  WCHAR *v51; // r8
  HANDLE v52; // rdi
  __int64 v53; // rcx
  int v54; // r15d
  __int64 v55; // rdx
  unsigned int PackageFullNameFromToken; // eax
  unsigned int ApplicationUserModelIdFromToken; // eax
  int PackageClaims; // eax
  int v59; // r8d
  unsigned int PsmTokenWithDynamicId; // eax
  unsigned int v61; // r14d
  const char *v62; // r9
  unsigned int TokenFromHandle; // eax
  unsigned int v64; // ebx
  int v65; // eax
  unsigned int v66; // edi
  __int64 v67; // rcx
  int ConsoleHandles; // eax
  unsigned int v69; // edi
  unsigned int TokenType; // [rsp+20h] [rbp-E0h]
  int TokenTypea; // [rsp+20h] [rbp-E0h]
  unsigned int TokenTypeb; // [rsp+20h] [rbp-E0h]
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hExistingToken; // [rsp+58h] [rbp-A8h] BYREF
  void *phNewToken; // [rsp+60h] [rbp-A0h] BYREF
  char *v76; // [rsp+68h] [rbp-98h] BYREF
  __int64 v77; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  UINT32 packageFullNameLength; // [rsp+80h] [rbp-80h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v81; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v82; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h] BYREF
  WCHAR packageFullName[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v6 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, char *))(*(_QWORD *)a1 + 32LL))(
         a1,
         (char *)a3 + 504);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v6,
      TokenType);
    return v7;
  }
  v8 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v8,
      TokenType);
    return v9;
  }
  if ( !*((_QWORD *)a3 + 63) && *((_DWORD *)a2 + 11) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)a2 + 34) )
        goto LABEL_17;
      v11 = (_QWORD *)(*((_QWORD *)a2 + 20) + 16LL * i);
      v12 = *v11 - *(_QWORD *)&GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1;
      if ( *v11 == *(_QWORD *)&GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1 )
        v12 = v11[1] - *(_QWORD *)GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4;
      if ( !v12 )
        break;
    }
    v13 = *((_BYTE *)a3 + 188);
    hToken = 0;
    v14 = ActivationPropertiesIn::QueryInterface(a2, &GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a, &hToken);
    v16 = v14;
    if ( v14 < 0 )
    {
      if ( v14 == -2147467262 && v13 )
      {
LABEL_15:
        if ( hToken )
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hToken + 16LL))(hToken);
        goto LABEL_17;
      }
      v44 = 328;
    }
    else
    {
      if ( v13 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v15);
      v14 = (*(__int64 (__fastcall **)(HANDLE, char *))(*(_QWORD *)hToken + 32LL))(hToken, (char *)a3 + 504);
      v16 = v14;
      if ( v14 < 0 )
      {
        v44 = 333;
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)hToken + 24LL))(hToken, 0);
        v16 = v14;
        if ( v14 >= 0 )
          goto LABEL_15;
        v44 = 335;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v14,
      TokenType);
    if ( hToken )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hToken + 16LL))(hToken);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)v16,
      TokenTypea);
    return v16;
  }
LABEL_17:
  v17 = *((_QWORD *)a3 + 63);
  if ( v17 )
  {
    v45 = IsAllowedToActivateAsUser(*(void **)(*((_QWORD *)a3 + 2) + 72LL), v17);
    v46 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x296,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v45,
        TokenType);
      return v46;
    }
  }
  v18 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, char *))(*(_QWORD *)a1 + 48LL))(
          a1,
          (char *)a3 + 496);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v18,
      TokenType);
    return v19;
  }
  v20 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, _QWORD))(*(_QWORD *)a1 + 40LL))(
          a1,
          0);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v20,
      TokenType);
    return v21;
  }
  v22 = (_QWORD *)((char *)a3 + 520);
  v23 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, char *))(*(_QWORD *)a1 + 64LL))(
          a1,
          (char *)a3 + 520);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v23,
      TokenType);
    return v24;
  }
  v25 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, GUID *))(*(_QWORD *)a1 + 56LL))(
          a1,
          &GUID_NULL);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29F,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v25,
      TokenType);
    return v26;
  }
  v27 = *(_QWORD *)a1;
  v81 = 0;
  v28 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, __int64 *))(v27 + 80))(a1, &v81);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A2,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v28,
      TokenType);
    return v29;
  }
  v30 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, _QWORD))(*(_QWORD *)a1 + 72LL))(
          a1,
          0);
  v31 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v30,
      TokenType);
    return v31;
  }
  if ( v81 )
  {
    v53 = *((_QWORD *)a3 + 1);
    if ( !v53 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A9,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        TokenType);
      return 2147942487LL;
    }
    v47 = *v22 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *v22 == *(_QWORD *)&GUID_NULL.Data1 )
      v47 = *((_QWORD *)a3 + 66) - *(_QWORD *)GUID_NULL.Data4;
    if ( !v47 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AD,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        TokenType);
      return 2147942487LL;
    }
    if ( *((_QWORD *)a3 + 63) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B0,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        TokenType);
      return 2147942487LL;
    }
    CProcess::GetRacActivationToken(v53, &hToken);
    v52 = hToken;
    if ( (char *)hToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        TokenType);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      return 2147942487LL;
    }
    v82 = 0;
    if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070005LL,
        TokenType);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      return 2147942405LL;
    }
    v54 = UMgrQueryUserContext(v52, &v82);
    if ( v54 < 0 )
    {
      v55 = 697;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v55,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v54,
        TokenType);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      return (unsigned int)v54;
    }
    v54 = IsAllowedToActivateAsUser(*(void **)(*((_QWORD *)a3 + 2) + 72LL), v82);
    if ( v54 < 0 )
    {
      v55 = 698;
      goto LABEL_80;
    }
    if ( !*((_QWORD *)a3 + 56) )
    {
      if ( !ImpersonateLoggedOnUser(v52) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2BF,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                      v48);
LABEL_95:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        return LastError;
      }
      packageFullNameLength = 128;
      PackageFullNameFromToken = GetPackageFullNameFromToken(v52, &packageFullNameLength, packageFullName);
      if ( PackageFullNameFromToken )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x2C4,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                      (const char *)PackageFullNameFromToken,
                      TokenType);
LABEL_94:
        RevertToSelf();
        goto LABEL_95;
      }
      applicationUserModelIdLength = 130;
      v50 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &hMem,
              0,
              130);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)a3 + 576,
        v50);
      if ( hMem )
        LocalFree(hMem);
      v51 = (WCHAR *)*((_QWORD *)a3 + 72);
      if ( !v51 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C9,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)0x8007000ELL,
          TokenType);
        RevertToSelf();
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        return 2147942414LL;
      }
      ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(v52, &applicationUserModelIdLength, v51);
      if ( ApplicationUserModelIdFromToken )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x2CA,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                      (const char *)ApplicationUserModelIdFromToken,
                      TokenType);
        goto LABEL_94;
      }
      v77 = 0;
      PackageClaims = RtlQueryPackageClaims(v52, 0, 0, 0);
      if ( PackageClaims < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x2CD,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                      (const char *)(unsigned int)PackageClaims,
                      0);
        goto LABEL_94;
      }
      LODWORD(v77) = v77 & 0xFFFFFFEF;
      hExistingToken = 0;
      LODWORD(v76) = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hExistingToken,
        0);
      PsmTokenWithDynamicId = PrivGetPsmTokenWithDynamicId(
                                (_DWORD)g_hRpcActKernel,
                                (unsigned int)v77 | 0x40000000,
                                v59,
                                (unsigned int)packageFullName,
                                *((_QWORD *)a3 + 72),
                                (__int64)a3 + 520,
                                *((_QWORD *)a3 + 62),
                                (__int64)&hExistingToken,
                                (__int64)&v76);
      if ( PsmTokenWithDynamicId )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x2D7,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                      (const char *)PsmTokenWithDynamicId,
                      TokenTypeb);
LABEL_93:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
        goto LABEL_94;
      }
      v61 = (unsigned int)v76;
      if ( (int)v76 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D8,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)v76,
          TokenTypeb);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
        RevertToSelf();
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        return v61;
      }
      phNewToken = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &phNewToken,
        0);
      if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2DA,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                      v62);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        goto LABEL_93;
      }
      hMem = v52;
      hToken = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &hToken,
        &phNewToken);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &phNewToken,
        &hMem);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hMem);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
      RevertToSelf();
      v52 = hToken;
    }
    TokenFromHandle = LookupOrCreateTokenFromHandle(v52, (struct CToken **)a3 + 67);
    if ( TokenFromHandle )
    {
      v64 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2DE,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
              (const char *)TokenFromHandle,
              TokenType);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      return v64;
    }
    hToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  }
  v32 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, char *))(*(_QWORD *)a1 + 96LL))(
          a1,
          (char *)a3 + 544);
  v33 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v32,
      TokenType);
    return v33;
  }
  if ( *((_QWORD *)a3 + 68) )
  {
    if ( !v81 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        TokenType);
      return 2147942487LL;
    }
    v65 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, _QWORD))(*(_QWORD *)a1 + 88LL))(
            a1,
            0);
    v66 = v65;
    if ( v65 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v65,
        TokenType);
      return v66;
    }
  }
  v34 = *(_QWORD *)a1;
  v83 = 0;
  v35 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, __int64 *))(v34 + 112))(a1, &v83);
  v36 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v35,
      TokenType);
    return v36;
  }
  v37 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, _QWORD))(*(_QWORD *)a1 + 104LL))(
          a1,
          0);
  v38 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v37,
      TokenType);
    return v38;
  }
  if ( !v83 )
    goto LABEL_30;
  v67 = *((_QWORD *)a3 + 1);
  if ( !v67 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)0x80070057LL,
      TokenType);
    return 2147942487LL;
  }
  ConsoleHandles = CProcess::GetConsoleHandles(v67, v83, (int)a3 + 584, (int)a3 + 592, (__int64)a3 + 600);
  v69 = ConsoleHandles;
  if ( ConsoleHandles < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)ConsoleHandles,
      TokenType);
    return v69;
  }
  else
  {
LABEL_30:
    v39 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, char *))(*(_QWORD *)a1 + 128LL))(
            a1,
            (char *)a3 + 552);
    v40 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v39,
        TokenType);
      return v40;
    }
    else
    {
      v41 = (*(__int64 (__fastcall **)(struct IExtensionActivationContextProperties *, _QWORD))(*(_QWORD *)a1 + 120LL))(
              a1,
              0);
      v42 = v41;
      if ( v41 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FE,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)v41,
          TokenType);
        return v42;
      }
    }
  }
}

```

## disassembly

```asm
0x1800221a0  push    rbp
0x1800221a2  push    rbx
0x1800221a3  push    rsi
0x1800221a4  push    rdi
0x1800221a5  push    r14
0x1800221a7  push    r15
0x1800221a9  lea     rbp, [rsp-0B8h]
0x1800221b1  sub     rsp, 1B8h
0x1800221b8  mov     rax, cs:__security_cookie
0x1800221bf  xor     rax, rsp
0x1800221c2  mov     [rbp+0E0h+var_40], rax
0x1800221c9  mov     rax, [rcx]
0x1800221cc  mov     rdi, rdx
0x1800221cf  lea     rdx, [r8+1F8h]
0x1800221d6  mov     rsi, r8
0x1800221d9  mov     rbx, rcx
0x1800221dc  mov     rax, [rax+20h]
0x1800221e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221e5  mov     r14d, eax
0x1800221e8  test    eax, eax
0x1800221ea  js      loc_180022640
0x1800221f0  mov     rax, [rbx]
0x1800221f3  xor     edx, edx
0x1800221f5  mov     rcx, rbx
0x1800221f8  mov     rax, [rax+18h]
0x1800221fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022201  mov     r14d, eax
0x180022204  test    eax, eax
0x180022206  js      loc_1800227F5
0x18002220c  mov     [rsp+1E0h+var_30], r13
0x180022214  xor     r13d, r13d
0x180022217  cmp     [rsi+1F8h], r13
0x18002221e  jnz     loc_1800222FF
0x180022224  cmp     [rdi+2Ch], r13d
0x180022228  jz      loc_1800222FF
0x18002222e  mov     r8d, [rdi+88h]
0x180022235  mov     eax, r13d
0x180022238  nop     dword ptr [rax+rax+00000000h]
0x180022240  cmp     eax, r8d
0x180022243  jnb     loc_1800222FF
0x180022249  mov     edx, eax
0x18002224b  shl     rdx, 4
0x18002224f  add     rdx, [rdi+0A0h]
0x180022256  mov     rcx, [rdx]
0x180022259  sub     rcx, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1
0x180022260  jnz     short loc_18002226D
0x180022262  mov     rcx, [rdx+8]
0x180022266  sub     rcx, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4
0x18002226d  test    rcx, rcx
0x180022270  jnz     loc_1800224D8
0x180022276  movzx   r14d, byte ptr [rsi+0BCh]
0x18002227e  lea     r8, [rsp+1E0h+hToken]; void **
0x180022283  lea     rdx, _GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a; struct _GUID *
0x18002228a  mov     [rsp+1E0h+hToken], r13
0x18002228f  mov     rcx, rdi; this
0x180022292  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x180022297  mov     edi, eax
0x180022299  test    eax, eax
0x18002229b  js      loc_180022818
0x1800222a1  test    r14b, r14b
0x1800222a4  jnz     loc_180022685
0x1800222aa  mov     rcx, [rsp+1E0h+hToken]
0x1800222af  lea     rdx, [rsi+1F8h]
0x1800222b6  mov     rax, [rcx]
0x1800222b9  mov     rax, [rax+20h]
0x1800222bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222c2  mov     edi, eax
0x1800222c4  test    eax, eax
0x1800222c6  js      loc_1800225B9
0x1800222cc  mov     rcx, [rsp+1E0h+hToken]
0x1800222d1  xor     edx, edx
0x1800222d3  mov     rax, [rcx]
0x1800222d6  mov     rax, [rax+18h]
0x1800222da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222df  mov     edi, eax
0x1800222e1  test    eax, eax
0x1800222e3  js      loc_180022522
0x1800222e9  mov     rcx, [rsp+1E0h+hToken]
0x1800222ee  test    rcx, rcx
0x1800222f1  jz      short loc_1800222FF
0x1800222f3  mov     rax, [rcx]
0x1800222f6  mov     rax, [rax+10h]
0x1800222fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ff  mov     rdx, [rsi+1F8h]; unsigned __int64
0x180022306  test    rdx, rdx
0x180022309  jnz     loc_180022607
0x18002230f  mov     rax, [rbx]
0x180022312  lea     rdx, [rsi+1F0h]
0x180022319  mov     rcx, rbx
0x18002231c  mov     [rsp+1E0h+arg_18], r12
0x180022324  mov     rax, [rax+30h]
0x180022328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002232d  mov     edi, eax
0x18002232f  test    eax, eax
0x180022331  js      loc_180022597
0x180022337  mov     rax, [rbx]
0x18002233a  xor     edx, edx
0x18002233c  mov     rcx, rbx
0x18002233f  mov     rax, [rax+28h]
0x180022343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022348  mov     edi, eax
0x18002234a  test    eax, eax
0x18002234c  js      loc_180022832
0x180022352  mov     rax, [rbx]
0x180022355  lea     r14, [rsi+208h]
0x18002235c  mov     rdx, r14
0x18002235f  mov     rcx, rbx
0x180022362  mov     rax, [rax+40h]
0x180022366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002236b  mov     edi, eax
0x18002236d  test    eax, eax
0x18002236f  js      loc_180022575
0x180022375  mov     rax, [rbx]
0x180022378  lea     rdx, GUID_NULL
0x18002237f  mov     rcx, rbx
0x180022382  mov     rax, [rax+38h]
0x180022386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002238b  mov     edi, eax
0x18002238d  test    eax, eax
0x18002238f  js      loc_1800225C3
0x180022395  mov     rax, [rbx]
0x180022398  lea     rdx, [rbp+0E0h+var_158]
0x18002239c  mov     rcx, rbx
0x18002239f  mov     [rbp+0E0h+var_158], r13
0x1800223a3  mov     rax, [rax+50h]
0x1800223a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223ac  mov     edi, eax
0x1800223ae  test    eax, eax
0x1800223b0  js      loc_180022854
0x1800223b6  mov     rax, [rbx]
0x1800223b9  xor     edx, edx
0x1800223bb  mov     rcx, rbx
0x1800223be  mov     rax, [rax+48h]
0x1800223c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223c7  mov     edi, eax
0x1800223c9  test    eax, eax
0x1800223cb  js      loc_180022876
0x1800223d1  mov     r8, [rbp+0E0h+var_158]
0x1800223d5  test    r8, r8
0x1800223d8  jnz     loc_180022898
0x1800223de  mov     rax, [rbx]
0x1800223e1  lea     rdx, [rsi+220h]
0x1800223e8  mov     rcx, rbx
0x1800223eb  mov     rax, [rax+60h]
0x1800223ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223f4  mov     r14d, eax
0x1800223f7  test    eax, eax
0x1800223f9  js      loc_180022502
0x1800223ff  cmp     [rsi+220h], r13
0x180022406  jnz     loc_180022C9B
0x18002240c  mov     rax, [rbx]
0x18002240f  lea     rdx, [rbp+0E0h+var_148]
0x180022413  mov     rcx, rbx
0x180022416  mov     [rbp+0E0h+var_148], r13
0x18002241a  mov     rax, [rax+70h]
0x18002241e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022423  mov     edi, eax
0x180022425  test    eax, eax
0x180022427  js      loc_1800225E5
0x18002242d  mov     rax, [rbx]
0x180022430  xor     edx, edx
0x180022432  mov     rcx, rbx
0x180022435  mov     rax, [rax+68h]
0x180022439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002243e  mov     edi, eax
0x180022440  test    eax, eax
0x180022442  js      loc_180022663
0x180022448  mov     rdx, [rbp+0E0h+var_148]
0x18002244c  test    rdx, rdx
0x18002244f  jnz     loc_180022D06
0x180022455  mov     rax, [rbx]
0x180022458  lea     rdx, [rsi+228h]
0x18002245f  mov     rcx, rbx
0x180022462  mov     rax, [rax+80h]
0x180022469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002246e  mov     edi, eax
0x180022470  test    eax, eax
0x180022472  js      short loc_1800224E3
0x180022474  mov     rax, [rbx]
0x180022477  xor     edx, edx
0x180022479  mov     rcx, rbx
0x18002247c  mov     rax, [rax+78h]
0x180022480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022485  mov     ebx, eax
0x180022487  test    eax, eax
0x180022489  jns     short loc_1800224DF
0x18002248b  mov     rcx, [rbp+0E8h]; this
0x180022492  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180022499  mov     r9d, eax; char *
0x18002249c  mov     edx, 2FEh; void *
0x1800224a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800224a6  mov     eax, ebx
0x1800224a8  mov     r12, [rsp+1E0h+arg_18]
0x1800224b0  mov     r13, [rsp+1E0h+var_30]
0x1800224b8  mov     rcx, [rbp+0E0h+var_40]
0x1800224bf  xor     rcx, rsp; StackCookie
0x1800224c2  call    __security_check_cookie
0x1800224c7  add     rsp, 1B8h
0x1800224ce  pop     r15
0x1800224d0  pop     r14
0x1800224d2  pop     rdi
0x1800224d3  pop     rsi
0x1800224d4  pop     rbx
0x1800224d5  pop     rbp
0x1800224d6  retn
0x1800224d8  inc     eax
0x1800224da  jmp     loc_180022240
0x1800224df  xor     eax, eax
0x1800224e1  jmp     short loc_1800224A8
0x1800224e3  mov     rcx, [rbp+0E8h]; this
0x1800224ea  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800224f1  mov     r9d, edi; char *
0x1800224f4  mov     edx, 2FDh; void *
0x1800224f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800224fe  mov     eax, edi
0x180022500  jmp     short loc_1800224A8
0x180022502  mov     rcx, [rbp+0E8h]; this
0x180022509  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180022510  mov     r9d, r14d; char *
0x180022513  mov     edx, 2E2h; void *
0x180022518  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002251d  mov     eax, r14d
0x180022520  jmp     short loc_1800224A8
0x180022522  mov     edx, 14Fh; void *
0x180022527  mov     rcx, [rbp+0E8h]; this
0x18002252e  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180022535  mov     r9d, eax; char *
0x180022538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002253d  mov     rcx, [rsp+1E0h+hToken]
0x180022542  test    rcx, rcx
0x180022545  jz      short loc_180022553
0x180022547  mov     rax, [rcx]
0x18002254a  mov     rax, [rax+10h]
0x18002254e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022553  mov     rcx, [rbp+0E8h]; this
0x18002255a  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180022561  mov     r9d, edi; char *
0x180022564  mov     edx, 28Eh; void *
0x180022569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002256e  mov     eax, edi
0x180022570  jmp     loc_1800224B0
0x180022575  mov     rcx, [rbp+0E8h]; this
0x18002257c  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180022583  mov     r9d, edi; char *
0x180022586  mov     edx, 29Dh; void *
0x18002258b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022590  mov     eax, edi
0x180022592  jmp     loc_1800224A8
0x180022597  mov     rcx, [rbp+0E8h]; this
0x18002259e  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800225a5  mov     r9d, edi; char *
0x1800225a8  mov     edx, 299h; void *
0x1800225ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800225b2  mov     eax, edi
0x1800225b4  jmp     loc_1800224A8
0x1800225b9  mov     edx, 14Dh
0x1800225be  jmp     loc_180022527
0x1800225c3  mov     rcx, [rbp+0E8h]; this
0x1800225ca  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800225d1  mov     r9d, edi; char *
0x1800225d4  mov     edx, 29Fh; void *
0x1800225d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800225de  mov     eax, edi
0x1800225e0  jmp     loc_1800224A8
0x1800225e5  mov     rcx, [rbp+0E8h]; this
0x1800225ec  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800225f3  mov     r9d, edi; char *
0x1800225f6  mov     edx, 2EDh; void *
0x1800225fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022600  mov     eax, edi
0x180022602  jmp     loc_1800224A8
0x180022607  mov     rcx, [rsi+10h]
0x18002260b  mov     rcx, [rcx+48h]; void *
0x18002260f  call    ?IsAllowedToActivateAsUser@@YAJPEAX_K@Z; IsAllowedToActivateAsUser(void *,unsigned __int64)
0x180022614  mov     edi, eax
0x180022616  test    eax, eax
0x180022618  jns     loc_18002230F
0x18002261e  mov     rcx, [rbp+0E8h]; this
0x180022625  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002262c  mov     r9d, eax; char *
0x18002262f  mov     edx, 296h; void *
0x180022634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022639  mov     eax, edi
0x18002263b  jmp     loc_1800224B0
0x180022640  mov     rcx, [rbp+0E8h]; this
0x180022647  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002264e  mov     r9d, r14d; char *
0x180022651  mov     edx, 285h; void *
0x180022656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002265b  mov     eax, r14d
0x18002265e  jmp     loc_1800224B8
0x180022663  mov     rcx, [rbp+0E8h]; this
0x18002266a  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180022671  mov     r9d, edi; char *
0x180022674  mov     edx, 2EFh; void *
0x180022679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002267e  mov     eax, edi
0x180022680  jmp     loc_1800224A8
0x180022685  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002268a  jmp     loc_1800222AA
  ... truncated ...
```
