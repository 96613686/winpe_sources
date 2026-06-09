# ActivateFromPropertiesPreamble(ActivationPropertiesIn *,IActivationPropertiesOut * *,ACTIVATION_PARAMS *)

- ea: `0x1800899b0`
- end: `0x18008b012`
- name: `?ActivateFromPropertiesPreamble@@YAJPEAVActivationPropertiesIn@@PEAPEAUIActivationPropertiesOut@@PEAUACTIVATION_PARAMS@@@Z`
- size: `5730`
- prototype: `__int64 __fastcall(struct ActivationPropertiesIn *, struct IActivationPropertiesOut **, struct ACTIVATION_PARAMS *, bool)`
- caller_count: `2`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f14c`
- `0x180098ff0`

## callees

- `0x180003064`
- `0x180003550`
- `0x180003654`
- `0x180003690`
- `0x180003cd0`
- `0x180004c80`
- `0x180004d20`
- `0x1800051f0`
- `0x180005c40`
- `0x1800081c0`
- `0x180008264`
- `0x180009700`
- `0x18000b428`
- `0x18000d4c4`
- `0x18000ff04`
- `0x180019840`
- `0x18001b670`
- `0x1800245b0`
- `0x180024cc4`
- `0x180028de4`
- `0x1800297e0`
- `0x18002ba28`
- `0x18002cad0`
- `0x18002ed28`
- `0x18002f8cc`
- `0x18003113c`
- `0x180031ae0`
- `0x18003b604`
- `0x1800430b0`
- `0x180043850`
- `0x18004af90`
- `0x18004c288`
- `0x180053e6c`
- `0x1800551f8`
- `0x180055260`
- `0x180059e50`
- `0x18005aae0`
- `0x180066010`
- `0x18006ca54`
- `0x180070180`
- `0x180075ba4`
- `0x180075ca0`
- `0x1800899b0`
- `0x18008e98c`
- `0x18009274c`
- `0x180098b54`
- `0x1800b27e0`
- `0x1800b37ec`
- `0x1800b4268`
- `0x1800f63d0`

## import_xrefs

- `ntdll!RtlQueryElevationFlags` at `0x18008a9dc`
- `ntdll!RtlQueryElevationFlags` at `0x18008a9dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089fab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089fab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a2e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008a422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008a422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a597`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18008a1ec`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18008a1ec`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008a2af`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008a2af`
- `ext-ms-win-com-ole32-l1-1-0!CoAicGetTokenForCOM` at `0x18008ab9f`
- `ext-ms-win-com-ole32-l1-1-0!CoAicGetTokenForCOM` at `0x18008ab9f`

## string_xrefs

- `0x18008a256`: `path:%ls`
- `0x18008a31b`: `path:%ls`
- `0x18008a278`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18008a314`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18008a101`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a3b5`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a48f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a4d1`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a5e5`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a84f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a9b3`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008aa52`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008abba`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008ac07`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008acd5`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008ad63`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008add8`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008af9d`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008afc4`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008a233`: `Software\Microsoft\WindowsRuntime\LegacyCLSID`
- `0x18008a26c`: `Software\Microsoft\WindowsRuntime\LegacyCLSID`
- `0x18008a99f`: `CLSCTX_DO_NOT_ELEVATE_SERVER is incompatible with elevated activation`
- `0x18008a47b`: `Unexpected remote WinRT activation attempt.`
- `0x18008a367`: `ActivatableClassId`

## pseudocode

```c
__int64 __fastcall ActivateFromPropertiesPreamble(
        struct ActivationPropertiesIn *a1,
        struct IActivationPropertiesOut **a2,
        struct ACTIVATION_PARAMS *a3,
        bool a4)
{
  struct IActivationPropertiesOut **v4; // rsi
  struct ACTIVATION_PARAMS *v6; // rax
  int Interface; // eax
  signed int ExplicitMainPackageFamilyNameFromActivationProperties; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  int InstantiationInfo; // eax
  _OWORD *v12; // rdi
  int ServerLocationInfo; // eax
  int v14; // eax
  CookieToPHPROCESSMap *v15; // rcx
  unsigned __int64 v16; // rdx
  struct CProcess *v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int ServerPath; // eax
  void *v23; // rbx
  struct ACTIVATION_PARAMS *v24; // rax
  struct ACTIVATION_PARAMS *v25; // rcx
  unsigned int TokenForRPCClient; // eax
  struct ACTIVATION_PARAMS *v27; // rax
  const WCHAR *v28; // r12
  int ActivationFlags; // eax
  unsigned int v30; // r15d
  int ActivationClientCatalogFlags; // eax
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  __int64 v34; // rdx
  unsigned __int64 v35; // r9
  int ComWinRTActivationProperties; // eax
  char *v37; // rdi
  HRESULT v38; // eax
  struct SerializableProperty *v39; // rdx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r9
  void *v44; // rsi
  struct ACTIVATION_PARAMS *v45; // rbx
  __int64 (__fastcall *v46)(void *, char *); // rdi
  void *v47; // rsi
  struct ACTIVATION_PARAMS *v48; // rbx
  __int64 (__fastcall *v49)(void *, char *); // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  int v51; // eax
  __int64 v52; // rdx
  int ClassInfoForActivation; // eax
  unsigned __int64 v54; // r9
  __int64 v55; // rdx
  int UserContextFromActivationProperties; // eax
  int ProcessMitigationPolicyFromActivationProperties; // eax
  int PackageGraphPackagesFromActivationProperties; // eax
  struct ACTIVATION_PARAMS *v59; // rdx
  int ComDependencyMainPackageFamilyNamesFromActivationProperties; // eax
  struct ACTIVATION_PARAMS *v61; // rax
  struct IUnknown *v62; // r9
  int v63; // eax
  __int64 v64; // rdx
  void **v65; // rcx
  int v66; // eax
  char v67; // bl
  int v68; // eax
  int TokenForCOM; // eax
  __int64 v70; // r9
  __int64 v71; // rdx
  unsigned int v72; // eax
  int v73; // eax
  __int64 v74; // rdx
  int v75; // eax
  int v76; // eax
  bool v77; // bl
  int v78; // edi
  ActivationPropertiesIn *v79; // rcx
  int v80; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  char *v83; // [rsp+28h] [rbp-D8h]
  struct ACTIVATION_PARAMS *v84; // [rsp+60h] [rbp-A0h] BYREF
  bool v85[8]; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v86; // [rsp+70h] [rbp-90h] BYREF
  void *v87; // [rsp+78h] [rbp-88h] BYREF
  char v88; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v89; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v90; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v92; // [rsp+98h] [rbp-68h] BYREF
  char v93; // [rsp+A0h] [rbp-60h]
  int v94; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  void *v96; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v97; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v98[2]; // [rsp+C8h] [rbp-38h] BYREF
  void *v99; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v100; // [rsp+D8h] [rbp-28h] BYREF
  void *v101; // [rsp+E0h] [rbp-20h] BYREF
  struct IExtensionActivationContextProperties *v102; // [rsp+E8h] [rbp-18h] BYREF
  int v103; // [rsp+F0h] [rbp-10h] BYREF
  int v104; // [rsp+F4h] [rbp-Ch] BYREF
  struct CToken *v105; // [rsp+F8h] [rbp-8h] BYREF
  struct CProcess *v106; // [rsp+100h] [rbp+0h] BYREF
  __int64 v107; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v108; // [rsp+110h] [rbp+10h] BYREF
  void *v109; // [rsp+118h] [rbp+18h] BYREF
  void *v110; // [rsp+120h] [rbp+20h] BYREF
  __int64 v111; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v112[3]; // [rsp+130h] [rbp+30h] BYREF
  char v113; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall **v114)(); // [rsp+150h] [rbp+50h] BYREF
  _BYTE v115[48]; // [rsp+158h] [rbp+58h] BYREF
  struct ACTIVATION_PARAMS **v116; // [rsp+188h] [rbp+88h]
  OLECHAR sz[40]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  *a2 = 0;
  v84 = a3;
  v4 = a2;
  v109 = 0;
  v110 = 0;
  v101 = 0;
  v88 = 0;
  v99 = 0;
  *((_QWORD *)a3 + 3) = 0;
  *((_QWORD *)a3 + 1) = 0;
  *((_QWORD *)a3 + 2) = 0;
  v90 = (HKEY)a2;
  *((_QWORD *)a3 + 67) = 0;
  v114 = &off_18010C2C8;
  lpMem = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v115,
    (struct wil::details::IFailureCallback *)&v114,
    a3,
    a4);
  v113 = 1;
  v116 = &v84;
  v112[0] = &v88;
  v112[1] = &v84;
  v112[2] = &v109;
  v6 = v84;
  *((_QWORD *)a1 + 70) = v84;
  *((_QWORD *)v6 + 43) = a1;
  Interface = ActivationPropertiesIn::QueryInterface(a1, &IID_IScmRequestInfo, (void **)v84 + 47);
  ExplicitMainPackageFamilyNameFromActivationProperties = Interface;
  if ( Interface < 0 )
  {
    v9 = 990;
LABEL_5:
    v10 = (unsigned int)Interface;
LABEL_266:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)v10,
      phkResult);
    goto LABEL_267;
  }
  Interface = ActivationPropertiesIn::QueryInterface(a1, &IID_ILegacyInfo, &v109);
  ExplicitMainPackageFamilyNameFromActivationProperties = Interface;
  if ( Interface < 0 )
  {
    v9 = 991;
    goto LABEL_5;
  }
  InstantiationInfo = ActivationPropertiesIn::GetInstantiationInfo(a1, (struct InstantiationInfo **)&lpMem);
  ExplicitMainPackageFamilyNameFromActivationProperties = InstantiationInfo;
  if ( InstantiationInfo < 0 )
  {
    v10 = (unsigned int)InstantiationInfo;
    v9 = 992;
    goto LABEL_266;
  }
  v12 = lpMem;
  *((_QWORD *)v84 + 45) = lpMem;
  if ( *((_BYTE *)v84 + 188) )
  {
    *((_QWORD *)v84 + 1) = 0;
    lpMem = 0;
    *((_QWORD *)v84 + 13) = 0;
    *((_QWORD *)v84 + 12) = 0;
    *((_DWORD *)v84 + 60) = 0;
    *((_QWORD *)v84 + 3) = 0;
    *((_QWORD *)v84 + 10) = 0;
    ServerLocationInfo = ActivationPropertiesIn::GetServerLocationInfo(a1, (struct ServerLocationInfo **)&lpMem);
    ExplicitMainPackageFamilyNameFromActivationProperties = ServerLocationInfo;
    if ( ServerLocationInfo < 0 )
    {
      v10 = (unsigned int)ServerLocationInfo;
      v9 = 1004;
      goto LABEL_266;
    }
    v106 = 0;
    (*(void (__fastcall **)(LPVOID, struct CProcess **))(*(_QWORD *)lpMem + 32LL))(lpMem, &v106);
    if ( v106 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
      v9 = 1012;
LABEL_265:
      v10 = (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
      goto LABEL_266;
    }
  }
  else
  {
    v100 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v84 + 47) + 32LL))(*((_QWORD *)v84 + 47), &v100);
    ExplicitMainPackageFamilyNameFromActivationProperties = v14;
    if ( v14 < 0 )
    {
      v10 = (unsigned int)v14;
      v9 = 1017;
      goto LABEL_266;
    }
    if ( !v100 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
      v9 = 1020;
      goto LABEL_265;
    }
    v16 = *(_QWORD *)(v100 + 16);
    v106 = 0;
    if ( CookieToPHPROCESSMap::Get(v15, v16, (void **)&v106) < 0 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024891;
      v9 = 1026;
      goto LABEL_265;
    }
    v17 = CheckLocalSecurity(*(RPC_BINDING_HANDLE *)v84, v106);
    *((_QWORD *)v84 + 1) = v17;
    if ( !*((_QWORD *)v84 + 1) )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024891;
      v9 = 1031;
      goto LABEL_265;
    }
    *((_QWORD *)v84 + 13) = *(_QWORD *)(v100 + 24);
    *((_DWORD *)v84 + 28) = *(_DWORD *)(v100 + 32);
    *((_QWORD *)v84 + 12) = *(_QWORD *)(v100 + 8);
    *((_DWORD *)v84 + 60) = *(_DWORD *)v100;
    v107 = 0;
    v18 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v109 + 32LL))(v109, &v107);
    ExplicitMainPackageFamilyNameFromActivationProperties = v18;
    if ( v18 < 0 )
    {
      v10 = (unsigned int)v18;
      v9 = 1041;
      goto LABEL_266;
    }
    if ( v107 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = CopyAuthInfo(
                                                                *(struct _COAUTHINFO **)(v107 + 16),
                                                                (struct _COAUTHINFO **)v84 + 3);
      SecurityInfo::freeCOAUTHINFO(*(struct _COAUTHINFO **)(v107 + 16));
      *(_QWORD *)(v107 + 16) = 0;
      if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
      {
        v9 = 1047;
        goto LABEL_265;
      }
    }
  }
  v19 = ActivationPropertiesIn::QueryInterface(a1, &IID_IServerLocationInfo, &v110);
  ExplicitMainPackageFamilyNameFromActivationProperties = v19;
  if ( v19 < 0 )
  {
    v10 = (unsigned int)v19;
    v9 = 1052;
    goto LABEL_266;
  }
  if ( (*(int (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)v110 + 40LL))(v110, 0, 0) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  (*(void (__fastcall **)(void *))(*(_QWORD *)v110 + 16LL))(v110);
  v20 = ActivationPropertiesIn::QueryInterface(a1, &IID_ISpecialSystemProperties, &v101);
  ExplicitMainPackageFamilyNameFromActivationProperties = v20;
  if ( v20 < 0 )
  {
    v10 = (unsigned int)v20;
    v9 = 1057;
    goto LABEL_266;
  }
  if ( (*(int (__fastcall **)(void *, char *))(*(_QWORD *)v101 + 56LL))(v101, (char *)v84 + 192) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (*(int (__fastcall **)(void *, char *, char *, char *))(*(_QWORD *)v101 + 40LL))(
         v101,
         (char *)v84 + 400,
         (char *)v84 + 408,
         (char *)v84 + 404) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v21 = *(_QWORD *)v101;
  if ( *((_BYTE *)v84 + 188) )
  {
    if ( (*(int (__fastcall **)(void *, __int64, _QWORD))(v21 + 136))(v101, 0xFFFFFFFFLL, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    *((_DWORD *)v84 + 104) = -1;
  }
  else if ( (*(int (__fastcall **)(void *, char *, char *))(v21 + 128))(v101, (char *)v84 + 416, (char *)v84 + 424) < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v101 + 16LL))(v101);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationPropertiesIn::QueryInterface(
                                                            a1,
                                                            &IID_IInstanceInfo,
                                                            &v99);
  if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
  {
    if ( ExplicitMainPackageFamilyNameFromActivationProperties != -2147467262 )
    {
      v9 = 1130;
      goto LABEL_265;
    }
    v24 = v84;
    if ( *((_DWORD *)v84 + 14) == 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v24 = v84;
    }
    if ( !*((_DWORD *)v24 + 14) )
    {
      *((_DWORD *)v24 + 52) = -1;
      v24 = v84;
    }
    *((_DWORD *)v24 + 53) = 0;
  }
  else
  {
    *((_QWORD *)v84 + 46) = v99;
    if ( !*((_BYTE *)v84 + 188) )
    {
      v111 = 0;
      (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)v99 + 80LL))(v99, &v111);
      if ( v111 )
      {
        ExplicitMainPackageFamilyNameFromActivationProperties = -2147024891;
        v9 = 1088;
        goto LABEL_265;
      }
    }
    if ( *((_DWORD *)v84 + 14) == 1 )
    {
      *((_DWORD *)v84 + 14) = 2;
      v108 = 0;
      (*(void (__fastcall **)(void *, unsigned __int16 **, char *))(*(_QWORD *)v99 + 64LL))(
        v99,
        &v108,
        (char *)v84 + 208);
      if ( *((_BYTE *)v84 + 188) )
      {
        lpMem = 0;
        ServerPath = GetServerPath(v108, (unsigned __int16 **)&lpMem);
        ExplicitMainPackageFamilyNameFromActivationProperties = ServerPath;
        if ( ServerPath < 0 )
        {
          v10 = (unsigned int)ServerPath;
          v9 = 1102;
          goto LABEL_266;
        }
        v23 = lpMem;
        if ( v108 != lpMem )
        {
          (*(void (__fastcall **)(void *, LPVOID, _QWORD))(*(_QWORD *)v99 + 56LL))(
            v99,
            lpMem,
            *((unsigned int *)v84 + 52));
          (*(void (__fastcall **)(void *, char *, char *))(*(_QWORD *)v99 + 64LL))(
            v99,
            (char *)v84 + 216,
            (char *)v84 + 208);
          HeapFree(g_hHeap, 0, v23);
        }
      }
      else
      {
        *((_QWORD *)v84 + 27) = v108;
      }
      (*(void (__fastcall **)(void *, char *))(*(_QWORD *)v99 + 48LL))(v99, (char *)v84 + 224);
      v88 = 1;
    }
    if ( *((_DWORD *)v84 + 14) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *(_OWORD *)((char *)v84 + 60) = v12[2];
  if ( *((_BYTE *)v84 + 188) )
    *((_DWORD *)v84 + 29) = 4;
  else
    *((_DWORD *)v84 + 29) = *((_DWORD *)v12 + 12);
  v25 = v84;
  *((_DWORD *)v84 + 49) = *((_DWORD *)v12 + 15);
  *((_QWORD *)v25 + 25) = *((_QWORD *)v12 + 9);
  if ( !*((_DWORD *)v84 + 14) && *((_DWORD *)v84 + 49) != 1 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
    v9 = 1145;
    goto LABEL_265;
  }
  *(_DWORD *)(*((_QWORD *)v84 + 19) + 4LL) = 1;
  **((_DWORD **)v84 + 20) = 0;
  **((_DWORD **)v84 + 21) = 0;
  *(_QWORD *)(*((_QWORD *)v84 + 21) + 8LL) = 0;
  TokenForRPCClient = LookupOrCreateTokenForRPCClient(
                        *(RPC_BINDING_HANDLE *)v84,
                        *((unsigned __int8 *)v84 + 188),
                        (struct CToken **)v84 + 2,
                        (int *)v84 + 8);
  if ( TokenForRPCClient )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = wil::details::in1diag3::Return_Win32(
                                                              retaddr,
                                                              (void *)0x482,
                                                              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                                                              (const char *)TokenForRPCClient,
                                                              phkResult);
LABEL_267:
    v113 = 0;
    lambda_107589f66759e6b050a5cb7c6a70f6ea_::operator()(v112);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v115);
    return (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
  }
  v27 = v84;
  v28 = &Class;
  if ( *((_DWORD *)v84 + 8) )
  {
    *((_QWORD *)v84 + 12) = &Class;
    v27 = v84;
  }
  if ( !*((_QWORD *)v27 + 2) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v89 = 0;
  ActivationFlags = ActivationPropertiesIn::GetActivationFlags(
                      (struct ActivationPropertiesIn *)((char *)a1 + 568),
                      &v89);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationFlags;
  if ( ActivationFlags < 0 )
  {
    v10 = (unsigned int)ActivationFlags;
    v9 = 1164;
    goto LABEL_266;
  }
  v30 = v89;
  *((_BYTE *)v84 + 432) = (v89 & 0x400) != 0;
  ActivationClientCatalogFlags = GetActivationClientCatalogFlags(
                                   v30,
                                   *((struct CProcess **)v84 + 1),
                                   *((struct CToken **)v84 + 2),
                                   (unsigned int *)v84 + 103);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationClientCatalogFlags;
  if ( ActivationClientCatalogFlags < 0 )
  {
    v10 = (unsigned int)ActivationClientCatalogFlags;
    v9 = 1170;
    goto LABEL_266;
  }
  if ( !*((_BYTE *)v84 + 432) )
  {
    BreakOnDebuggedClsid((const struct _GUID *)((char *)v84 + 60));
    if ( (*((_BYTE *)v84 + 116) & 4) != 0 )
    {
      UserContextFromActivationProperties = GetUserContextFromActivationProperties(
                                              a1,
                                              *((unsigned __int8 *)v84 + 188),
                                              (unsigned __int64 *)v84 + 63);
      ExplicitMainPackageFamilyNameFromActivationProperties = UserContextFromActivationProperties;
      if ( UserContextFromActivationProperties < 0 )
      {
        v10 = (unsigned int)UserContextFromActivationProperties;
        v9 = 1294;
        goto LABEL_266;
      }
      if ( *(_QWORD *)((char *)v84 + 60) == *(_QWORD *)&CLSID_PerAppRuntimeBroker.Data1
        && *(_QWORD *)((char *)v84 + 68) == *(_QWORD *)CLSID_PerAppRuntimeBroker.Data4 )
      {
        ProcessMitigationPolicyFromActivationProperties = GetProcessMitigationPolicyFromActivationProperties(
                                                            a1,
                                                            *((unsigned __int8 *)v84 + 188),
                                                            (struct tagBLOB **)v84 + 64);
        ExplicitMainPackageFamilyNameFromActivationProperties = ProcessMitigationPolicyFromActivationProperties;
        if ( ProcessMitigationPolicyFromActivationProperties < 0 )
        {
          v10 = (unsigned int)ProcessMitigationPolicyFromActivationProperties;
          v9 = 1307;
          goto LABEL_266;
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      LODWORD(v92) = 0;
      BYTE4(v92) = 1;
      lpMem = (char *)v84 + 464;
      PackageGraphPackagesFromActivationProperties = GetPackageGraphPackagesFromActivationProperties(
                                                       a1,
                                                       *((_BYTE *)v84 + 188),
                                                       (unsigned int *)&v92,
                                                       (HSTRING **)v84 + 58);
      ExplicitMainPackageFamilyNameFromActivationProperties = PackageGraphPackagesFromActivationProperties;
      if ( BYTE4(v92) )
        *((_QWORD *)lpMem + 1) = (unsigned int)v92;
      if ( PackageGraphPackagesFromActivationProperties < 0 )
      {
        v10 = (unsigned int)PackageGraphPackagesFromActivationProperties;
        v9 = 1315;
        goto LABEL_266;
      }
      v59 = v84;
      if ( *((_QWORD *)v84 + 59) )
      {
        *((_DWORD *)v84 + 103) |= 0x2000u;
        v59 = v84;
      }
      LODWORD(v92) = 0;
      lpMem = (char *)v59 + 480;
      BYTE4(v92) = 1;
      ComDependencyMainPackageFamilyNamesFromActivationProperties = GetComDependencyMainPackageFamilyNamesFromActivationProperties(
                                                                      a1,
                                                                      *((_BYTE *)v59 + 188),
                                                                      (unsigned int *)&v92,
                                                                      (HSTRING **)v59 + 60);
      ExplicitMainPackageFamilyNameFromActivationProperties = ComDependencyMainPackageFamilyNamesFromActivationProperties;
      if ( BYTE4(v92) )
        *((_QWORD *)lpMem + 1) = (unsigned int)v92;
      if ( ComDependencyMainPackageFamilyNamesFromActivationProperties < 0 )
      {
        v10 = (unsigned int)ComDependencyMainPackageFamilyNamesFromActivationProperties;
        v9 = 1329;
        goto LABEL_266;
      }
      v92 = 0;
      v93 = 1;
      lpMem = (char *)v84 + 456;
      ExplicitMainPackageFamilyNameFromActivationProperties = GetExplicitMainPackageFamilyNameFromActivationProperties(
                                                                a1,
                                                                *((_BYTE *)v84 + 188),
                                                                &v92);
      wil::details::out_param_t<std::unique_ptr<unsigned short [0]>>::~out_param_t<std::unique_ptr<unsigned short [0]>>(&lpMem);
      if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
      {
        v9 = 1332;
        goto LABEL_265;
      }
    }
    goto LABEL_136;
  }
  if ( !*((_BYTE *)v84 + 188) || *((_BYTE *)v84 + 189) )
  {
    v96 = 0;
    v41 = ActivationPropertiesIn::QueryInterface(a1, &GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a, &v96);
    ExplicitMainPackageFamilyNameFromActivationProperties = v41;
    if ( v41 >= 0 )
    {
      v44 = v96;
      v45 = v84;
      v46 = *(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v96 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        (char *)v84 + 440,
        0);
      v41 = v46(v44, (char *)v45 + 440);
      ExplicitMainPackageFamilyNameFromActivationProperties = v41;
      if ( v41 >= 0 )
      {
        v47 = v96;
        v48 = v84;
        v49 = *(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v96 + 64LL);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          (char *)v84 + 448,
          0);
        v41 = v49(v47, (char *)v48 + 448);
        ExplicitMainPackageFamilyNameFromActivationProperties = v41;
        if ( v41 >= 0 )
        {
          if ( *((_QWORD *)v84 + 55) )
          {
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v96);
            v4 = (struct IActivationPropertiesOut **)v90;
            goto LABEL_129;
          }
          ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
          v42 = 1202;
          v43 = 2147942487LL;
LABEL_122:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v42,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
            (const char *)v43,
            phkResult);
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v96);
          goto LABEL_267;
        }
        v42 = 1197;
      }
      else
      {
        v42 = 1196;
      }
    }
    else
    {
      v42 = 1195;
    }
    v43 = (unsigned int)v41;
    goto LABEL_122;
  }
  if ( !(unsigned __int8)IsWinRTPerMachineSingleInstancingPresent()
    || !(unsigned int)RemoteWinRTActivation()
    || *(_QWORD *)((char *)v84 + 60) == *(_QWORD *)&GUID_NULL.Data1
    && *(_QWORD *)((char *)v84 + 68) == *(_QWORD *)GUID_NULL.Data4 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x4DF,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)0x8000FFFFLL,
      (int)"Unexpected remote WinRT activation attempt.",
      v83);
    goto LABEL_267;
  }
  hKey = 0;
  v32 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WindowsRuntime\\LegacyCLSID", 0, 0x20019u, &hKey);
  ExplicitMainPackageFamilyNameFromActivationProperties = v32;
  if ( v32 > 0 )
    ExplicitMainPackageFamilyNameFromActivationProperties = (unsigned __int16)v32 | 0x80070000;
  if ( ExplicitMainPackageFamilyNameFromActivationProperties != -2147024894 )
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\com\\combase\\inc\\RegistryKey.hpp",
      (const char *)(unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties,
      (__int64)"path:%ls",
      (const char *)L"Software\\Microsoft\\WindowsRuntime\\LegacyCLSID");
  if ( ExplicitMainPackageFamilyNameFromActivationProperties >= 0 )
  {
    if ( StringFromGUID2((const GUID *const)((char *)v84 + 60), sz, 39) != 39 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v90 = 0;
    v33 = RegOpenKeyExW(hKey, sz, 0, 0x20019u, &v90);
    ExplicitMainPackageFamilyNameFromActivationProperties = v33;
    if ( v33 > 0 )
      ExplicitMainPackageFamilyNameFromActivationProperties = (unsigned __int16)v33 | 0x80070000;
    if ( ExplicitMainPackageFamilyNameFromActivationProperties != -2147024894 )
    {
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecore\\com\\combase\\inc\\RegistryKey.hpp",
        (const char *)(unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties,
        (__int64)"path:%ls",
        (const char *)sz);
      if ( ExplicitMainPackageFamilyNameFromActivationProperties >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          (char *)v84 + 440,
          0);
        v85[0] = 0;
        ExplicitMainPackageFamilyNameFromActivationProperties = RegistryKey::ReadStringValueWorker<128,HSTRING__ *>(
                                                                  (RegistryKey *)&v90,
                                                                  (__int64)v85);
        if ( ExplicitMainPackageFamilyNameFromActivationProperties >= 0 && !*((_QWORD *)v84 + 55) )
          ExplicitMainPackageFamilyNameFromActivationProperties = -2147024883;
      }
    }
    RegistryKey::Close((RegistryKey *)&v90);
  }
  if ( ExplicitMainPackageFamilyNameFromActivationProperties == -2147024894 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147221164;
    v34 = 1233;
LABEL_102:
    v35 = (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
LABEL_103:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)v35,
      phkResult);
    RegistryKey::Close((RegistryKey *)&hKey);
    goto LABEL_267;
  }
  if ( ExplicitMainPackageFamilyNameFromActivationProperties == -2147024883 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147221165;
    v34 = 1234;
    goto LABEL_102;
  }
  if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
  {
    v34 = 1235;
    goto LABEL_102;
  }
  lpMem = 0;
  ComWinRTActivationProperties = ActivationPropertiesIn::GetComWinRTActivationProperties(
                                   a1,
                                   (struct ComWinRTActivationProperties **)&lpMem);
  ExplicitMainPackageFamilyNameFromActivationProperties = ComWinRTActivationProperties;
  if ( ComWinRTActivationProperties < 0 )
  {
    v35 = (unsigned int)ComWinRTActivationProperties;
    v34 = 1241;
    goto LABEL_103;
  }
  v37 = (char *)lpMem;
  v38 = WindowsDuplicateString(*((HSTRING *)v84 + 55), (HSTRING *)lpMem + 4);
  ExplicitMainPackageFamilyNameFromActivationProperties = v38;
  if ( v38 < 0 )
  {
    v35 = (unsigned int)v38;
    v34 = 1242;
    goto LABEL_103;
  }
  if ( v37 )
    v39 = (struct SerializableProperty *)(v37 + 8);
  else
    v39 = 0;
  v40 = ActivationProperties::AddSerializableIfs(a1, v39);
  ExplicitMainPackageFamilyNameFromActivationProperties = v40;
  if ( v40 < 0 )
  {
    v35 = (unsigned int)v40;
    v34 = 1243;
    goto LABEL_103;
  }
  RegistryKey::Close((RegistryKey *)&hKey);
LABEL_129:
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v84 + 55), 0);
  BreakOnDebuggedActivatableClassId(StringRawBuffer);
  if ( !*((_BYTE *)v84 + 188) )
  {
    v102 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
    v51 = ActivationPropertiesIn::QueryInterface(a1, &GUID_071742dc_587e_4930_81d5_8a7de8547529, (void **)&v102);
    ExplicitMainPackageFamilyNameFromActivationProperties = v51;
    if ( v51 < 0 )
    {
      v52 = 1273;
LABEL_132:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v52,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v51,
        phkResult);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
      goto LABEL_267;
    }
    v51 = EvaluateExtensionActivationContextProperties(v102, a1, v84);
    ExplicitMainPackageFamilyNameFromActivationProperties = v51;
    if ( v51 < 0 )
    {
      v52 = 1275;
      goto LABEL_132;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  }
LABEL_136:
  v86 = 0;
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::reset(&v86);
  ClassInfoForActivation = TryGetClassInfoForActivation(v84, (struct IComClassInfo **)&v86);
  ExplicitMainPackageFamilyNameFromActivationProperties = ClassInfoForActivation;
  if ( ClassInfoForActivation < 0 )
  {
    v54 = (unsigned int)ClassInfoForActivation;
    v55 = 1337;
LABEL_262:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)v54,
      phkResult);
    goto LABEL_263;
  }
  v61 = v84;
  if ( !*((_BYTE *)v84 + 432) )
  {
    v62 = v86;
    if ( !v86 )
      goto LABEL_180;
    v97 = 0;
    v63 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v86->lpVtbl->QueryInterface)(
            v86,
            &GUID_430be197_0244_2f7b_80fd_c7c473983ad0,
            &v97);
    ExplicitMainPackageFamilyNameFromActivationProperties = v63;
    if ( v63 < 0 )
    {
      v64 = 1351;
LABEL_163:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v63,
        phkResult);
      v65 = (void **)&v97;
LABEL_164:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v65);
LABEL_263:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v86);
      goto LABEL_267;
    }
    v103 = 0;
    v63 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v97 + 24LL))(v97, &v103);
    ExplicitMainPackageFamilyNameFromActivationProperties = v63;
    if ( v63 < 0 )
    {
      v64 = 1354;
      goto LABEL_163;
    }
    if ( v103 == 2 )
    {
      v63 = CalculateActivationTargetSessionId((struct IComClassInfo *)v86, v84);
      ExplicitMainPackageFamilyNameFromActivationProperties = v63;
      if ( v63 < 0 )
      {
        v64 = 1374;
        goto LABEL_163;
      }
      v104 = 0;
      v63 = PerformDeferredPackageRegistrationForClassIfNecessary(
              *((struct CToken **)v84 + 2),
              (const struct _GUID *)((char *)v84 + 60),
              *((_DWORD *)v84 + 103) | *((_DWORD *)v84 + 29) & 0x17u,
              (struct IComClassInfo *)v86,
              *((_DWORD *)v84 + 32),
              &v104);
      ExplicitMainPackageFamilyNameFromActivationProperties = v63;
      if ( v63 < 0 )
      {
        v64 = 1379;
        goto LABEL_163;
      }
      if ( v104 )
      {
        wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::reset(&v86);
        v63 = TryGetClassInfoForActivation(v84, (struct IComClassInfo **)&v86);
        ExplicitMainPackageFamilyNameFromActivationProperties = v63;
        if ( v63 < 0 )
        {
          v64 = 1382;
          goto LABEL_163;
        }
      }
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v97);
    v61 = v84;
  }
  v62 = v86;
  if ( v86 )
  {
    v66 = ActivationPropertiesIn::SetClassInfo((struct ActivationPropertiesIn *)((char *)a1 + 584), v86);
    ExplicitMainPackageFamilyNameFromActivationProperties = v66;
    if ( v66 < 0 )
    {
      v54 = (unsigned int)v66;
      v55 = 1393;
      goto LABEL_262;
    }
    v62 = v86;
    v61 = v84;
  }
LABEL_180:
  if ( *((_DWORD *)v61 + 104) != -1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && (v30 & 0x8000000) != 0 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x57D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        (int)"CLSCTX_DO_NOT_ELEVATE_SERVER is incompatible with elevated activation",
        v83);
      goto LABEL_263;
    }
    v90 = 0;
    *(_QWORD *)v98 = 0;
    lpMem = 0;
    v94 = 0;
    if ( (int)RtlQueryElevationFlags(&v94) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (v94 & 1) != 0 )
    {
      v67 = 1;
    }
    else
    {
      v67 = 0;
      *((_DWORD *)v84 + 104) = -1;
    }
    v61 = v84;
    if ( *((_DWORD *)v84 + 104) != -1 )
    {
      v89 = 0;
      if ( !v86 )
        goto LABEL_207;
      v87 = 0;
      v68 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, void **))v86->lpVtbl->QueryInterface)(
              v86,
              &GUID_0318b242_d086_4de9_b10c_2824a6ca1019,
              &v87);
      if ( v68 >= 0 )
      {
        (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v87 + 48LL))(v87, &v89);
        if ( v89 )
        {
          (*(void (__fastcall **)(void *, HKEY *))(*(_QWORD *)v87 + 56LL))(v87, &v90);
          (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v87 + 72LL))(v87, v98);
          (*(void (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v87 + 64LL))(v87, &lpMem);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x597,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)v68,
          phkResult);
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v87);
      if ( !v89 )
      {
LABEL_207:
        ExplicitMainPackageFamilyNameFromActivationProperties = -2146959337;
        v55 = 1442;
        goto LABEL_261;
      }
      if ( !v90 )
      {
        ExplicitMainPackageFamilyNameFromActivationProperties = -2146959339;
        v55 = 1443;
LABEL_261:
        v54 = (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
        goto LABEL_262;
      }
      v61 = v84;
    }
    if ( v67 )
    {
      v87 = 0;
      v105 = 0;
      if ( !(unsigned __int8)IsCoAicGetTokenForCOMPresent() )
      {
        ExplicitMainPackageFamilyNameFromActivationProperties = -2147467263;
        v71 = 1472;
        v70 = 2147500033LL;
        goto LABEL_205;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v87,
        0);
      if ( *(_QWORD *)v98 )
        LODWORD(v28) = v98[0];
      phkResult = (unsigned int)v28;
      TokenForCOM = CoAicGetTokenForCOM(
                      *((_QWORD *)v84 + 53),
                      *(_QWORD *)(*((_QWORD *)v84 + 1) + 32LL),
                      (char *)v84 + 60,
                      v90);
      ExplicitMainPackageFamilyNameFromActivationProperties = TokenForCOM;
      if ( TokenForCOM < 0 )
      {
        v70 = (unsigned int)TokenForCOM;
        v71 = 1468;
LABEL_205:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v71,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)v70,
          phkResult);
LABEL_206:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v87);
        goto LABEL_263;
      }
      if ( (char *)v87 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v72 = LookupOrCreateTokenFromHandle(v87, &v105);
        if ( v72 )
        {
          ExplicitMainPackageFamilyNameFromActivationProperties = wil::details::in1diag3::Return_Win32(
                                                                    retaddr,
                                                                    (void *)0x5C6,
                                                                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                                                                    (const char *)v72,
                                                                    (unsigned int)v28);
          goto LABEL_206;
        }
        v87 = 0;
        CToken::Release(*((CToken **)v84 + 2));
        *((_QWORD *)v84 + 2) = v105;
        if ( !*((_QWORD *)v84 + 2) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v87);
      v61 = v84;
    }
    if ( *((_DWORD *)v61 + 104) != -1 )
    {
      *((_QWORD *)v61 + 13) = 0;
      *((_DWORD *)v84 + 28) = 0;
      v61 = v84;
    }
    v62 = v86;
  }
  if ( !*((_BYTE *)v61 + 188) && v62 )
  {
    v87 = 0;
    v73 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, void **))v62->lpVtbl->QueryInterface)(
            v62,
            &GUID_430be197_0244_2f7b_80fd_c7c473983ad0,
            &v87);
    ExplicitMainPackageFamilyNameFromActivationProperties = v73;
    if ( v73 < 0 )
    {
      v74 = 1510;
LABEL_221:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v74,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v73,
        phkResult);
LABEL_222:
      v65 = &v87;
      goto LABEL_164;
    }
    v94 = 0;
    v73 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v87 + 24LL))(v87, &v94);
    ExplicitMainPackageFamilyNameFromActivationProperties = v73;
    if ( v73 < 0 )
    {
      v74 = 1520;
      goto LABEL_221;
    }
    if ( !v94 )
    {
      v90 = 0;
      v75 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HKEY *))v86->lpVtbl->QueryInterface)(
              v86,
              &GUID_000001e2_0000_0000_c000_000000000046,
              &v90);
      ExplicitMainPackageFamilyNameFromActivationProperties = v75;
      if ( v75 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F5,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)v75,
          phkResult);
LABEL_229:
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v90);
        goto LABEL_222;
      }
      *(_QWORD *)v98 = 0;
      if ( (*(int (__fastcall **)(HKEY, GUID *, unsigned int *))(*(_QWORD *)v90 + 48LL))(
             v90,
             &GUID_000001ed_0000_0000_c000_000000000046,
             v98) < 0 )
      {
        v77 = 1;
      }
      else
      {
        v89 = 0;
        v76 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v98 + 80LL))(*(_QWORD *)v98, &v89);
        ExplicitMainPackageFamilyNameFromActivationProperties = v76;
        if ( v76 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5FA,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
            (const char *)(unsigned int)v76,
            phkResult);
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v98);
          goto LABEL_229;
        }
        v77 = 0;
        if ( v89 == 2 )
        {
          lpMem = 0;
          if ( (***(int (__fastcall ****)(_QWORD, GUID *, LPVOID *))v98)(
                 *(_QWORD *)v98,
                 &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680,
                 &lpMem) < 0 )
          {
            v77 = 1;
          }
          else
          {
            LODWORD(v105) = 0;
            (*(void (__fastcall **)(LPVOID, struct CToken **))(*(_QWORD *)lpMem + 192LL))(lpMem, &v105);
            v77 = ((unsigned __int16)v105 & 0x800) == 0;
          }
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&lpMem);
        }
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v98);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v90);
      if ( v77 )
      {
        v85[0] = 0;
        v73 = CToken::ImplicitlyActivateClassicAAAServersAsIU(*((CToken **)v84 + 2), v85);
        ExplicitMainPackageFamilyNameFromActivationProperties = v73;
        if ( v73 < 0 )
        {
          v74 = 1559;
          goto LABEL_221;
        }
        if ( v85[0] )
        {
          v73 = ActivationPropertiesIn::SetActivationFlags(
                  (struct ActivationPropertiesIn *)((char *)a1 + 584),
                  v30 | 0x80000);
          ExplicitMainPackageFamilyNameFromActivationProperties = v73;
          if ( v73 < 0 )
          {
            v74 = 1565;
            goto LABEL_221;
          }
        }
      }
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v87);
    v61 = v84;
  }
  v78 = 0;
  if ( !*((_DWORD *)v61 + 8) )
    *((_QWORD *)a1 + 77) = *(_QWORD *)(*((_QWORD *)v61 + 2) + 72LL);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationPropertiesIn::SetStageAndIndex((char *)a1 + 576, 3);
  if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
  {
LABEL_260:
    v55 = 1580;
    goto LABEL_261;
  }
  while ( 1 )
  {
    v79 = (struct ActivationPropertiesIn *)((char *)a1 + 568);
    v80 = *((_DWORD *)v84 + 14)
        ? ActivationPropertiesIn::DelegateCreateInstance(v79, 0, v4)
        : ActivationPropertiesIn::DelegateGetClassObject(v79, v4);
    ExplicitMainPackageFamilyNameFromActivationProperties = v80;
    if ( v80 != -2147023659 )
      break;
    if ( v78 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_258:
      v55 = 1603;
      goto LABEL_261;
    }
    ExplicitMainPackageFamilyNameFromActivationProperties = ActivationPropertiesIn::SetStageAndIndex(
                                                              (char *)a1 + 576,
                                                              3);
    if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
      goto LABEL_260;
    v78 = 1;
  }
  if ( v80 < 0 )
    goto LABEL_258;
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v86);
  v113 = 0;
  lambda_107589f66759e6b050a5cb7c6a70f6ea_::operator()(v112);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v115);
  return 0;
}

```

## disassembly

```asm
0x1800899b0  mov     [rsp-8+arg_18], rbx
0x1800899b5  push    rbp
0x1800899b6  push    rsi
0x1800899b7  push    rdi
0x1800899b8  push    r12
0x1800899ba  push    r13
0x1800899bc  push    r14
0x1800899be  push    r15
0x1800899c0  lea     rbp, [rsp-0F0h]
0x1800899c8  sub     rsp, 1F0h
0x1800899cf  mov     rax, cs:__security_cookie
0x1800899d6  xor     rax, rsp
0x1800899d9  mov     [rbp+120h+var_40], rax
0x1800899e0  mov     qword ptr [rdx], 0
0x1800899e7  lea     rax, off_18010C2C8
0x1800899ee  mov     [rsp+220h+var_1C0], r8
0x1800899f3  mov     rsi, rdx
0x1800899f6  mov     [rbp+120h+var_108], 0
0x1800899fe  mov     r14, rcx
0x180089a01  mov     [rbp+120h+var_100], 0
0x180089a09  lea     rcx, [rbp+120h+var_C8]; this
0x180089a0d  mov     [rbp+120h+var_140], 0
0x180089a15  mov     [rbp+120h+var_1A0], 0
0x180089a19  mov     [rbp+120h+var_150], 0
0x180089a21  mov     qword ptr [r8+18h], 0
0x180089a29  mov     qword ptr [r8+8], 0
0x180089a31  mov     qword ptr [r8+10h], 0
0x180089a39  mov     [rbp+120h+var_198], rdx
0x180089a3d  lea     rdx, [rbp+120h+var_D0]; struct wil::details::IFailureCallback *
0x180089a41  mov     qword ptr [r8+218h], 0
0x180089a4c  mov     [rbp+120h+var_D0], rax
0x180089a50  mov     [rbp+120h+lpMem], 0
0x180089a58  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180089a5d  lea     rax, [rsp+220h+var_1C0]
0x180089a62  mov     [rbp+120h+var_D8], 1
0x180089a66  mov     [rbp+120h+var_98], rax
0x180089a6d  lea     rdx, IID_IScmRequestInfo; struct _GUID *
0x180089a74  lea     rax, [rbp+120h+var_1A0]
0x180089a78  mov     rcx, r14; this
0x180089a7b  mov     [rbp+120h+var_F0], rax
0x180089a7f  lea     rax, [rsp+220h+var_1C0]
0x180089a84  mov     [rbp+120h+var_E8], rax
0x180089a88  lea     rax, [rbp+120h+var_108]
0x180089a8c  mov     [rbp+120h+var_E0], rax
0x180089a90  mov     rax, [rsp+220h+var_1C0]
0x180089a95  mov     [r14+230h], rax
0x180089a9c  mov     [rax+158h], r14
0x180089aa3  mov     r8, [rsp+220h+var_1C0]
0x180089aa8  add     r8, 178h; void **
0x180089aaf  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x180089ab4  mov     ebx, eax
0x180089ab6  test    eax, eax
0x180089ab8  jns     short loc_180089AC1
0x180089aba  mov     edx, 3DEh
0x180089abf  jmp     short loc_180089ADF
0x180089ac1  lea     r8, [rbp+120h+var_108]; void **
0x180089ac5  mov     rcx, r14; this
0x180089ac8  lea     rdx, IID_ILegacyInfo; struct _GUID *
0x180089acf  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x180089ad4  mov     ebx, eax
0x180089ad6  test    eax, eax
0x180089ad8  jns     short loc_180089AE7
0x180089ada  mov     edx, 3DFh
0x180089adf  mov     r9d, eax
0x180089ae2  jmp     loc_18008AFBD
0x180089ae7  lea     rdx, [rbp+120h+lpMem]; struct InstantiationInfo **
0x180089aeb  mov     rcx, r14; this
0x180089aee  call    ?GetInstantiationInfo@ActivationPropertiesIn@@QEAAJPEAPEAVInstantiationInfo@@@Z; ActivationPropertiesIn::GetInstantiationInfo(InstantiationInfo * *)
0x180089af3  mov     ebx, eax
0x180089af5  test    eax, eax
0x180089af7  jns     short loc_180089B06
0x180089af9  mov     r9d, eax
0x180089afc  mov     edx, 3E0h
0x180089b01  jmp     loc_18008AFBD
0x180089b06  mov     rax, [rsp+220h+var_1C0]
0x180089b0b  mov     rdi, [rbp+120h+lpMem]
0x180089b0f  mov     [rax+168h], rdi
0x180089b16  mov     rcx, [rsp+220h+var_1C0]
0x180089b1b  cmp     byte ptr [rcx+0BCh], 0
0x180089b22  jz      loc_180089BD0
0x180089b28  mov     qword ptr [rcx+8], 0
0x180089b30  lea     rdx, [rbp+120h+lpMem]; struct ServerLocationInfo **
0x180089b34  mov     rax, [rsp+220h+var_1C0]
0x180089b39  mov     rcx, r14; this
0x180089b3c  mov     [rbp+120h+lpMem], 0
0x180089b44  mov     qword ptr [rax+68h], 0
0x180089b4c  mov     rax, [rsp+220h+var_1C0]
0x180089b51  mov     qword ptr [rax+60h], 0
0x180089b59  mov     rax, [rsp+220h+var_1C0]
0x180089b5e  mov     dword ptr [rax+0F0h], 0
0x180089b68  mov     rax, [rsp+220h+var_1C0]
0x180089b6d  mov     qword ptr [rax+18h], 0
0x180089b75  mov     rax, [rsp+220h+var_1C0]
0x180089b7a  mov     qword ptr [rax+50h], 0
0x180089b82  call    ?GetServerLocationInfo@ActivationPropertiesIn@@QEAAJPEAPEAVServerLocationInfo@@@Z; ActivationPropertiesIn::GetServerLocationInfo(ServerLocationInfo * *)
0x180089b87  mov     ebx, eax
0x180089b89  test    eax, eax
0x180089b8b  jns     short loc_180089B9A
0x180089b8d  mov     r9d, eax
0x180089b90  mov     edx, 3ECh
0x180089b95  jmp     loc_18008AFBD
0x180089b9a  mov     rcx, [rbp+120h+lpMem]
0x180089b9e  lea     rdx, [rbp+120h+var_120]
0x180089ba2  mov     [rbp+120h+var_120], 0
0x180089baa  mov     rax, [rcx]
0x180089bad  mov     rax, [rax+20h]
0x180089bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089bb6  cmp     [rbp+120h+var_120], 0
0x180089bbb  jz      loc_180089D27
0x180089bc1  mov     ebx, 80070057h
0x180089bc6  mov     edx, 3F4h
0x180089bcb  jmp     loc_18008AFBA
0x180089bd0  mov     [rbp+120h+var_148], 0
0x180089bd8  lea     rdx, [rbp+120h+var_148]
0x180089bdc  mov     rcx, [rcx+178h]
0x180089be3  mov     rax, [rcx]
0x180089be6  mov     rax, [rax+20h]
0x180089bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089bef  mov     ebx, eax
0x180089bf1  test    eax, eax
0x180089bf3  jns     short loc_180089C02
0x180089bf5  mov     r9d, eax
0x180089bf8  mov     edx, 3F9h
0x180089bfd  jmp     loc_18008AFBD
0x180089c02  mov     rdx, [rbp+120h+var_148]
0x180089c06  test    rdx, rdx
0x180089c09  jnz     short loc_180089C1A
0x180089c0b  mov     ebx, 80070057h
0x180089c10  mov     edx, 3FCh
0x180089c15  jmp     loc_18008AFBA
0x180089c1a  mov     rdx, [rdx+10h]; unsigned __int64
0x180089c1e  lea     r8, [rbp+120h+var_120]; void **
0x180089c22  mov     [rbp+120h+var_120], 0
0x180089c2a  call    ?Get@CookieToPHPROCESSMap@@QEAAJ_KAEAPEAX@Z; CookieToPHPROCESSMap::Get(unsigned __int64,void * &)
0x180089c2f  test    eax, eax
0x180089c31  jns     short loc_180089C42
0x180089c33  mov     ebx, 80070005h
0x180089c38  mov     edx, 402h
0x180089c3d  jmp     loc_18008AFBA
0x180089c42  mov     rcx, [rsp+220h+var_1C0]
0x180089c47  mov     rdx, [rbp+120h+var_120]; struct CProcess *
0x180089c4b  mov     rcx, [rcx]; Binding
0x180089c4e  call    ?CheckLocalSecurity@@YAPEAVCProcess@@PEAX0@Z; CheckLocalSecurity(void *,void *)
0x180089c53  mov     rcx, [rsp+220h+var_1C0]
0x180089c58  mov     [rcx+8], rax
0x180089c5c  mov     rdx, [rsp+220h+var_1C0]
0x180089c61  cmp     qword ptr [rdx+8], 0
0x180089c66  jnz     short loc_180089C77
0x180089c68  mov     ebx, 80070005h
0x180089c6d  mov     edx, 407h
0x180089c72  jmp     loc_18008AFBA
0x180089c77  mov     rax, [rbp+120h+var_148]
0x180089c7b  mov     rcx, [rax+18h]
0x180089c7f  mov     [rdx+68h], rcx
0x180089c83  lea     rdx, [rbp+120h+var_118]
0x180089c87  mov     rax, [rbp+120h+var_148]
0x180089c8b  mov     ecx, [rax+20h]
0x180089c8e  mov     rax, [rsp+220h+var_1C0]
0x180089c93  mov     [rax+70h], ecx
0x180089c96  mov     rax, [rbp+120h+var_148]
0x180089c9a  mov     rcx, [rax+8]
0x180089c9e  mov     rax, [rsp+220h+var_1C0]
0x180089ca3  mov     [rax+60h], rcx
0x180089ca7  mov     rax, [rbp+120h+var_148]
0x180089cab  mov     ecx, [rax]
0x180089cad  mov     rax, [rsp+220h+var_1C0]
0x180089cb2  mov     [rax+0F0h], ecx
0x180089cb8  mov     rcx, [rbp+120h+var_108]
0x180089cbc  mov     [rbp+120h+var_118], 0
0x180089cc4  mov     rax, [rcx]
0x180089cc7  mov     rax, [rax+20h]
0x180089ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089cd0  mov     ebx, eax
0x180089cd2  test    eax, eax
0x180089cd4  jns     short loc_180089CE3
0x180089cd6  mov     r9d, eax
0x180089cd9  mov     edx, 411h
0x180089cde  jmp     loc_18008AFBD
0x180089ce3  mov     rcx, [rbp+120h+var_118]
0x180089ce7  test    rcx, rcx
0x180089cea  jz      short loc_180089D27
0x180089cec  mov     rdx, [rsp+220h+var_1C0]
0x180089cf1  mov     rcx, [rcx+10h]; struct _COAUTHINFO *
0x180089cf5  add     rdx, 18h; struct _COAUTHINFO **
0x180089cf9  call    ?CopyAuthInfo@@YAJPEAU_COAUTHINFO@@PEAPEAU1@@Z; CopyAuthInfo(_COAUTHINFO *,_COAUTHINFO * *)
0x180089cfe  mov     rcx, [rbp+120h+var_118]
0x180089d02  mov     ebx, eax
0x180089d04  mov     rcx, [rcx+10h]; lpMem
0x180089d08  call    ?freeCOAUTHINFO@SecurityInfo@@SAXPEAU_COAUTHINFO@@@Z; SecurityInfo::freeCOAUTHINFO(_COAUTHINFO *)
0x180089d0d  mov     rcx, [rbp+120h+var_118]
0x180089d11  mov     qword ptr [rcx+10h], 0
0x180089d19  test    ebx, ebx
0x180089d1b  jns     short loc_180089D27
0x180089d1d  mov     edx, 417h
0x180089d22  jmp     loc_18008AFBA
0x180089d27  lea     r8, [rbp+120h+var_100]; void **
0x180089d2b  mov     rcx, r14; this
0x180089d2e  lea     rdx, IID_IServerLocationInfo; struct _GUID *
0x180089d35  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x180089d3a  mov     ebx, eax
0x180089d3c  test    eax, eax
0x180089d3e  jns     short loc_180089D4D
0x180089d40  mov     r9d, eax
0x180089d43  mov     edx, 41Ch
0x180089d48  jmp     loc_18008AFBD
0x180089d4d  mov     rcx, [rbp+120h+var_100]
0x180089d51  xor     r8d, r8d
0x180089d54  xor     edx, edx
0x180089d56  mov     rax, [rcx]
0x180089d59  mov     rax, [rax+28h]
0x180089d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d62  test    eax, eax
0x180089d64  jns     short loc_180089D6B
0x180089d66  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089d6b  mov     rcx, [rbp+120h+var_100]
0x180089d6f  mov     rax, [rcx]
0x180089d72  mov     rax, [rax+10h]
0x180089d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d7b  lea     r8, [rbp+120h+var_140]; void **
0x180089d7f  mov     rcx, r14; this
0x180089d82  lea     rdx, IID_ISpecialSystemProperties; struct _GUID *
0x180089d89  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x180089d8e  mov     ebx, eax
0x180089d90  test    eax, eax
0x180089d92  jns     short loc_180089DA1
0x180089d94  mov     r9d, eax
0x180089d97  mov     edx, 421h
0x180089d9c  jmp     loc_18008AFBD
0x180089da1  mov     rcx, [rbp+120h+var_140]
0x180089da5  mov     rdx, [rsp+220h+var_1C0]
0x180089daa  add     rdx, 0C0h
0x180089db1  mov     rax, [rcx]
0x180089db4  mov     rax, [rax+38h]
0x180089db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089dbd  test    eax, eax
0x180089dbf  jns     short loc_180089DC6
0x180089dc1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089dc6  mov     rdx, [rsp+220h+var_1C0]
0x180089dcb  mov     rcx, [rbp+120h+var_140]
0x180089dcf  lea     r9, [rdx+194h]
0x180089dd6  mov     rax, [rcx]
0x180089dd9  lea     r8, [rdx+198h]
0x180089de0  add     rdx, 190h
0x180089de7  mov     rax, [rax+28h]
0x180089deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089df0  test    eax, eax
0x180089df2  jns     short loc_180089DF9
0x180089df4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089df9  mov     rdx, [rsp+220h+var_1C0]
0x180089dfe  or      r15d, 0FFFFFFFFh
0x180089e02  mov     rcx, [rbp+120h+var_140]
0x180089e06  cmp     byte ptr [rdx+0BCh], 0
0x180089e0d  mov     rax, [rcx]
0x180089e10  jz      short loc_180089E3B
0x180089e12  mov     rax, [rax+88h]
0x180089e19  xor     r8d, r8d
0x180089e1c  mov     edx, r15d
0x180089e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e24  test    eax, eax
0x180089e26  jns     short loc_180089E2D
0x180089e28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089e2d  mov     rax, [rsp+220h+var_1C0]
0x180089e32  mov     [rax+1A0h], r15d
0x180089e39  jmp     short loc_180089E5E
0x180089e3b  mov     rax, [rax+80h]
0x180089e42  lea     r8, [rdx+1A8h]
0x180089e49  add     rdx, 1A0h
0x180089e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e55  test    eax, eax
0x180089e57  jns     short loc_180089E5E
0x180089e59  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089e5e  mov     rcx, [rbp+120h+var_140]
0x180089e62  mov     rax, [rcx]
0x180089e65  mov     rax, [rax+10h]
0x180089e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e6e  lea     r8, [rbp+120h+var_150]; void **
0x180089e72  mov     rcx, r14; this
0x180089e75  lea     rdx, IID_IInstanceInfo; struct _GUID *
0x180089e7c  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x180089e81  mov     ebx, eax
0x180089e83  test    eax, eax
0x180089e85  js      loc_180089FF0
0x180089e8b  mov     rax, [rsp+220h+var_1C0]
0x180089e90  mov     rcx, [rbp+120h+var_150]
0x180089e94  mov     [rax+170h], rcx
0x180089e9b  mov     rax, [rsp+220h+var_1C0]
0x180089ea0  cmp     byte ptr [rax+0BCh], 0
0x180089ea7  jnz     short loc_180089EDB
0x180089ea9  mov     rcx, [rbp+120h+var_150]
0x180089ead  lea     rdx, [rbp+120h+var_F8]
0x180089eb1  mov     [rbp+120h+var_F8], 0
0x180089eb9  mov     rax, [rcx]
0x180089ebc  mov     rax, [rax+50h]
0x180089ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089ec5  cmp     [rbp+120h+var_F8], 0
0x180089eca  jz      short loc_180089EDB
0x180089ecc  mov     ebx, 80070005h
0x180089ed1  mov     edx, 440h
0x180089ed6  jmp     loc_18008AFBA
0x180089edb  mov     rax, [rsp+220h+var_1C0]
  ... truncated ...
```
