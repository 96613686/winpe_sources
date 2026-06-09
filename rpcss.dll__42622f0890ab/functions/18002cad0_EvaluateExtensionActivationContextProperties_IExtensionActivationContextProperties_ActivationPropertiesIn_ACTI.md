# EvaluateExtensionActivationContextProperties(IExtensionActivationContextProperties *,ActivationPropertiesIn *,ACTIVATION_PARAMS *)

- ea: `0x18002cad0`
- end: `0x18002d66f`
- name: `?EvaluateExtensionActivationContextProperties@@YAJPEAUIExtensionActivationContextProperties@@PEAVActivationPropertiesIn@@PEAUACTIVATION_PARAMS@@@Z`
- size: `2975`
- prototype: `__int64 __fastcall(struct IExtensionActivationContextProperties *, struct ActivationPropertiesIn *, struct ACTIVATION_PARAMS *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800899b0`

## callees

- `0x1800051f0`
- `0x18001ec28`
- `0x18002ba28`
- `0x18002cad0`
- `0x18002e578`
- `0x18002ed28`
- `0x18002f8cc`
- `0x180031ae0`
- `0x180059e18`
- `0x180059e50`
- `0x18008cd90`
- `0x18008e98c`
- `0x18008eefc`
- `0x1800b27e0`
- `0x1800b4890`
- `0x1800bd83c`
- `0x1800be1b0`
- `0x1800c6748`
- `0x1801081c8`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlQueryPackageClaims` at `0x18002d360`
- `ntdll!RtlQueryPackageClaims` at `0x18002d360`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002d016`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002d016`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002d493`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002d493`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d0a9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d445`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d4cb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d528`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d0a9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d445`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d4cb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d528`
- `KERNELBASE!GetApplicationUserModelIdFromToken` at `0x18002d30b`
- `KERNELBASE!GetApplicationUserModelIdFromToken` at `0x18002d30b`
- `KERNELBASE!GetPackageFullNameFromToken` at `0x18002d2d4`
- `KERNELBASE!GetPackageFullNameFromToken` at `0x18002d2d4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d075`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d075`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002d265`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002d265`

## string_xrefs

- `0x18002cdc2`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002ce19`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002ce38`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002ce5d`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002ce89`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002ceab`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cecd`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cef9`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cf1b`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cf54`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cf76`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cf99`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002cfe5`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d02b`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d092`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d0e7`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d119`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d156`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d178`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d19a`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d1c9`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d1fe`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d233`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d2a1`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d2e9`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d31c`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d371`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d3fb`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d427`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d4a4`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d54d`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d595`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d5d8`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d603`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18002d654`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`

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
0x18002cad0  push    rbp
0x18002cad2  push    rbx
0x18002cad3  push    rsi
0x18002cad4  push    rdi
0x18002cad5  push    r14
0x18002cad7  push    r15
0x18002cad9  lea     rbp, [rsp-0B8h]
0x18002cae1  sub     rsp, 1B8h
0x18002cae8  mov     rax, cs:__security_cookie
0x18002caef  xor     rax, rsp
0x18002caf2  mov     [rbp+0E0h+var_40], rax
0x18002caf9  mov     rax, [rcx]
0x18002cafc  mov     rdi, rdx
0x18002caff  lea     rdx, [r8+1F8h]
0x18002cb06  mov     rsi, r8
0x18002cb09  mov     rbx, rcx
0x18002cb0c  mov     rax, [rax+20h]
0x18002cb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb15  mov     r14d, eax
0x18002cb18  test    eax, eax
0x18002cb1a  js      loc_18002CF6F
0x18002cb20  mov     rax, [rbx]
0x18002cb23  xor     edx, edx
0x18002cb25  mov     rcx, rbx
0x18002cb28  mov     rax, [rax+18h]
0x18002cb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb31  mov     r14d, eax
0x18002cb34  test    eax, eax
0x18002cb36  js      loc_18002D112
0x18002cb3c  mov     [rsp+1E0h+var_30], r13
0x18002cb44  xor     r13d, r13d
0x18002cb47  cmp     [rsi+1F8h], r13
0x18002cb4e  jnz     loc_18002CC2F
0x18002cb54  cmp     [rdi+2Ch], r13d
0x18002cb58  jz      loc_18002CC2F
0x18002cb5e  mov     r8d, [rdi+88h]
0x18002cb65  mov     eax, r13d
0x18002cb68  nop     dword ptr [rax+rax+00000000h]
0x18002cb70  cmp     eax, r8d
0x18002cb73  jnb     loc_18002CC2F
0x18002cb79  mov     edx, eax
0x18002cb7b  shl     rdx, 4
0x18002cb7f  add     rdx, [rdi+0A0h]
0x18002cb86  mov     rcx, [rdx]
0x18002cb89  sub     rcx, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1
0x18002cb90  jnz     short loc_18002CB9D
0x18002cb92  mov     rcx, [rdx+8]
0x18002cb96  sub     rcx, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4
0x18002cb9d  test    rcx, rcx
0x18002cba0  jnz     loc_18002CE07
0x18002cba6  movzx   r14d, byte ptr [rsi+0BCh]
0x18002cbae  lea     r8, [rsp+1E0h+hToken]; void **
0x18002cbb3  lea     rdx, _GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a; struct _GUID *
0x18002cbba  mov     [rsp+1E0h+hToken], r13
0x18002cbbf  mov     rcx, rdi; this
0x18002cbc2  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18002cbc7  mov     edi, eax
0x18002cbc9  test    eax, eax
0x18002cbcb  js      loc_18002D135
0x18002cbd1  test    r14b, r14b
0x18002cbd4  jnz     loc_18002CFB4
0x18002cbda  mov     rcx, [rsp+1E0h+hToken]
0x18002cbdf  lea     rdx, [rsi+1F8h]
0x18002cbe6  mov     rax, [rcx]
0x18002cbe9  mov     rax, [rax+20h]
0x18002cbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbf2  mov     edi, eax
0x18002cbf4  test    eax, eax
0x18002cbf6  js      loc_18002CEE8
0x18002cbfc  mov     rcx, [rsp+1E0h+hToken]
0x18002cc01  xor     edx, edx
0x18002cc03  mov     rax, [rcx]
0x18002cc06  mov     rax, [rax+18h]
0x18002cc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc0f  mov     edi, eax
0x18002cc11  test    eax, eax
0x18002cc13  js      loc_18002CE51
0x18002cc19  mov     rcx, [rsp+1E0h+hToken]
0x18002cc1e  test    rcx, rcx
0x18002cc21  jz      short loc_18002CC2F
0x18002cc23  mov     rax, [rcx]
0x18002cc26  mov     rax, [rax+10h]
0x18002cc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc2f  mov     rdx, [rsi+1F8h]; unsigned __int64
0x18002cc36  test    rdx, rdx
0x18002cc39  jnz     loc_18002CF36
0x18002cc3f  mov     rax, [rbx]
0x18002cc42  lea     rdx, [rsi+1F0h]
0x18002cc49  mov     rcx, rbx
0x18002cc4c  mov     [rsp+1E0h+arg_18], r12
0x18002cc54  mov     rax, [rax+30h]
0x18002cc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc5d  mov     edi, eax
0x18002cc5f  test    eax, eax
0x18002cc61  js      loc_18002CEC6
0x18002cc67  mov     rax, [rbx]
0x18002cc6a  xor     edx, edx
0x18002cc6c  mov     rcx, rbx
0x18002cc6f  mov     rax, [rax+28h]
0x18002cc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc78  mov     edi, eax
0x18002cc7a  test    eax, eax
0x18002cc7c  js      loc_18002D14F
0x18002cc82  mov     rax, [rbx]
0x18002cc85  lea     r14, [rsi+208h]
0x18002cc8c  mov     rdx, r14
0x18002cc8f  mov     rcx, rbx
0x18002cc92  mov     rax, [rax+40h]
0x18002cc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc9b  mov     edi, eax
0x18002cc9d  test    eax, eax
0x18002cc9f  js      loc_18002CEA4
0x18002cca5  mov     rax, [rbx]
0x18002cca8  lea     rdx, GUID_NULL
0x18002ccaf  mov     rcx, rbx
0x18002ccb2  mov     rax, [rax+38h]
0x18002ccb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccbb  mov     edi, eax
0x18002ccbd  test    eax, eax
0x18002ccbf  js      loc_18002CEF2
0x18002ccc5  mov     rax, [rbx]
0x18002ccc8  lea     rdx, [rbp+0E0h+var_158]
0x18002cccc  mov     rcx, rbx
0x18002cccf  mov     [rbp+0E0h+var_158], r13
0x18002ccd3  mov     rax, [rax+50h]
0x18002ccd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccdc  mov     edi, eax
0x18002ccde  test    eax, eax
0x18002cce0  js      loc_18002D171
0x18002cce6  mov     rax, [rbx]
0x18002cce9  xor     edx, edx
0x18002cceb  mov     rcx, rbx
0x18002ccee  mov     rax, [rax+48h]
0x18002ccf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccf7  mov     edi, eax
0x18002ccf9  test    eax, eax
0x18002ccfb  js      loc_18002D193
0x18002cd01  mov     r8, [rbp+0E0h+var_158]
0x18002cd05  test    r8, r8
0x18002cd08  jnz     loc_18002D1B5
0x18002cd0e  mov     rax, [rbx]
0x18002cd11  lea     rdx, [rsi+220h]
0x18002cd18  mov     rcx, rbx
0x18002cd1b  mov     rax, [rax+60h]
0x18002cd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd24  mov     r14d, eax
0x18002cd27  test    eax, eax
0x18002cd29  js      loc_18002CE31
0x18002cd2f  cmp     [rsi+220h], r13
0x18002cd36  jnz     loc_18002D588
0x18002cd3c  mov     rax, [rbx]
0x18002cd3f  lea     rdx, [rbp+0E0h+var_148]
0x18002cd43  mov     rcx, rbx
0x18002cd46  mov     [rbp+0E0h+var_148], r13
0x18002cd4a  mov     rax, [rax+70h]
0x18002cd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd53  mov     edi, eax
0x18002cd55  test    eax, eax
0x18002cd57  js      loc_18002CF14
0x18002cd5d  mov     rax, [rbx]
0x18002cd60  xor     edx, edx
0x18002cd62  mov     rcx, rbx
0x18002cd65  mov     rax, [rax+68h]
0x18002cd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd6e  mov     edi, eax
0x18002cd70  test    eax, eax
0x18002cd72  js      loc_18002CF92
0x18002cd78  mov     rdx, [rbp+0E0h+var_148]
0x18002cd7c  test    rdx, rdx
0x18002cd7f  jnz     loc_18002D5F3
0x18002cd85  mov     rax, [rbx]
0x18002cd88  lea     rdx, [rsi+228h]
0x18002cd8f  mov     rcx, rbx
0x18002cd92  mov     rax, [rax+80h]
0x18002cd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd9e  mov     edi, eax
0x18002cda0  test    eax, eax
0x18002cda2  js      short loc_18002CE12
0x18002cda4  mov     rax, [rbx]
0x18002cda7  xor     edx, edx
0x18002cda9  mov     rcx, rbx
0x18002cdac  mov     rax, [rax+78h]
0x18002cdb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdb5  mov     ebx, eax
0x18002cdb7  test    eax, eax
0x18002cdb9  jns     short loc_18002CE0E
0x18002cdbb  mov     rcx, [rbp+0E8h]; this
0x18002cdc2  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002cdc9  mov     r9d, eax; char *
0x18002cdcc  mov     edx, 2FEh; void *
0x18002cdd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdd6  mov     eax, ebx
0x18002cdd8  mov     r12, [rsp+1E0h+arg_18]
0x18002cde0  mov     r13, [rsp+1E0h+var_30]
0x18002cde8  mov     rcx, [rbp+0E0h+var_40]
0x18002cdef  xor     rcx, rsp; StackCookie
0x18002cdf2  call    __security_check_cookie
0x18002cdf7  add     rsp, 1B8h
0x18002cdfe  pop     r15
0x18002ce00  pop     r14
0x18002ce02  pop     rdi
0x18002ce03  pop     rsi
0x18002ce04  pop     rbx
0x18002ce05  pop     rbp
0x18002ce06  retn
0x18002ce07  inc     eax
0x18002ce09  jmp     loc_18002CB70
0x18002ce0e  xor     eax, eax
0x18002ce10  jmp     short loc_18002CDD8
0x18002ce12  mov     rcx, [rbp+0E8h]; this
0x18002ce19  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002ce20  mov     r9d, edi; char *
0x18002ce23  mov     edx, 2FDh; void *
0x18002ce28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce2d  mov     eax, edi
0x18002ce2f  jmp     short loc_18002CDD8
0x18002ce31  mov     rcx, [rbp+0E8h]; this
0x18002ce38  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002ce3f  mov     r9d, r14d; char *
0x18002ce42  mov     edx, 2E2h; void *
0x18002ce47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce4c  mov     eax, r14d
0x18002ce4f  jmp     short loc_18002CDD8
0x18002ce51  mov     edx, 14Fh; void *
0x18002ce56  mov     rcx, [rbp+0E8h]; this
0x18002ce5d  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002ce64  mov     r9d, eax; char *
0x18002ce67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce6c  mov     rcx, [rsp+1E0h+hToken]
0x18002ce71  test    rcx, rcx
0x18002ce74  jz      short loc_18002CE82
0x18002ce76  mov     rax, [rcx]
0x18002ce79  mov     rax, [rax+10h]
0x18002ce7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce82  mov     rcx, [rbp+0E8h]; this
0x18002ce89  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002ce90  mov     r9d, edi; char *
0x18002ce93  mov     edx, 28Eh; void *
0x18002ce98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce9d  mov     eax, edi
0x18002ce9f  jmp     loc_18002CDE0
0x18002cea4  mov     rcx, [rbp+0E8h]; this
0x18002ceab  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002ceb2  mov     r9d, edi; char *
0x18002ceb5  mov     edx, 29Dh; void *
0x18002ceba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cebf  mov     eax, edi
0x18002cec1  jmp     loc_18002CDD8
0x18002cec6  mov     rcx, [rbp+0E8h]; this
0x18002cecd  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002ced4  mov     r9d, edi; char *
0x18002ced7  mov     edx, 299h; void *
0x18002cedc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cee1  mov     eax, edi
0x18002cee3  jmp     loc_18002CDD8
0x18002cee8  mov     edx, 14Dh
0x18002ceed  jmp     loc_18002CE56
0x18002cef2  mov     rcx, [rbp+0E8h]; this
0x18002cef9  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002cf00  mov     r9d, edi; char *
0x18002cf03  mov     edx, 29Fh; void *
0x18002cf08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf0d  mov     eax, edi
0x18002cf0f  jmp     loc_18002CDD8
0x18002cf14  mov     rcx, [rbp+0E8h]; this
0x18002cf1b  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002cf22  mov     r9d, edi; char *
0x18002cf25  mov     edx, 2EDh; void *
0x18002cf2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf2f  mov     eax, edi
0x18002cf31  jmp     loc_18002CDD8
0x18002cf36  mov     rcx, [rsi+10h]
0x18002cf3a  mov     rcx, [rcx+48h]; void *
0x18002cf3e  call    ?IsAllowedToActivateAsUser@@YAJPEAX_K@Z; IsAllowedToActivateAsUser(void *,unsigned __int64)
0x18002cf43  mov     edi, eax
0x18002cf45  test    eax, eax
0x18002cf47  jns     loc_18002CC3F
0x18002cf4d  mov     rcx, [rbp+0E8h]; this
0x18002cf54  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002cf5b  mov     r9d, eax; char *
0x18002cf5e  mov     edx, 296h; void *
0x18002cf63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf68  mov     eax, edi
0x18002cf6a  jmp     loc_18002CDE0
0x18002cf6f  mov     rcx, [rbp+0E8h]; this
0x18002cf76  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002cf7d  mov     r9d, r14d; char *
0x18002cf80  mov     edx, 285h; void *
0x18002cf85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf8a  mov     eax, r14d
0x18002cf8d  jmp     loc_18002CDE8
0x18002cf92  mov     rcx, [rbp+0E8h]; this
0x18002cf99  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18002cfa0  mov     r9d, edi; char *
0x18002cfa3  mov     edx, 2EFh; void *
0x18002cfa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cfad  mov     eax, edi
0x18002cfaf  jmp     loc_18002CDD8
0x18002cfb4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002cfb9  jmp     loc_18002CBDA
  ... truncated ...
```
