# ActivateFromPropertiesPreamble(ActivationPropertiesIn *,IActivationPropertiesOut * *,ACTIVATION_PARAMS *)

- ea: `0x18008e54c`
- end: `0x18008fbe5`
- name: `?ActivateFromPropertiesPreamble@@YAJPEAVActivationPropertiesIn@@PEAPEAUIActivationPropertiesOut@@PEAUACTIVATION_PARAMS@@@Z`
- size: `5785`
- prototype: `__int64 __fastcall(struct ActivationPropertiesIn *, struct IActivationPropertiesOut **, struct ACTIVATION_PARAMS *)`
- caller_count: `2`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002518c`
- `0x18009e608`

## callees

- `0x180003194`
- `0x18000361c`
- `0x1800055c0`
- `0x180005664`
- `0x180005b40`
- `0x1800065a4`
- `0x180008b74`
- `0x180008c20`
- `0x18000a130`
- `0x18000b100`
- `0x18000fb8c`
- `0x180013db4`
- `0x18001eba0`
- `0x18001ecf0`
- `0x1800210f8`
- `0x1800221a0`
- `0x180024590`
- `0x180025950`
- `0x18002750c`
- `0x18002aa10`
- `0x18002e840`
- `0x18002efd4`
- `0x180030ed0`
- `0x18004335c`
- `0x1800522a0`
- `0x180053038`
- `0x1800535d0`
- `0x180053940`
- `0x180056d78`
- `0x180059b8c`
- `0x180059e9c`
- `0x18005b3e4`
- `0x18005b530`
- `0x18005eee0`
- `0x18005efe4`
- `0x18005fc50`
- `0x1800657e8`
- `0x180072c6c`
- `0x180073d40`
- `0x1800749b0`
- `0x18007a390`
- `0x18007a42c`
- `0x18008e54c`
- `0x1800938ec`
- `0x180095c0c`
- `0x18009e160`
- `0x1800b7ac0`
- `0x1800b8aec`
- `0x1800b9568`
- `0x1800fe374`

## import_xrefs

- `ntdll!RtlQueryElevationFlags` at `0x18008f5a2`
- `ntdll!RtlQueryElevationFlags` at `0x18008f5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008eb47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008eb47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ede9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ee94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ede9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ee94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008efdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008efdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f157`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18008ed8e`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18008ed8e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008ee5d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008ee5d`
- `ext-ms-win-com-ole32-l1-1-0!CoAicGetTokenForCOM` at `0x18008f76b`
- `ext-ms-win-com-ole32-l1-1-0!CoAicGetTokenForCOM` at `0x18008f76b`

## string_xrefs

- `0x18008eca3`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008ef6f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f04f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f091`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f1ab`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f415`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f579`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f61e`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f78c`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f7d9`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f8a7`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f935`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008f9aa`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008fb6f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008fb96`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18008ee04`: `path:%ls`
- `0x18008eed5`: `path:%ls`
- `0x18008ee26`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18008eece`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18008f565`: `CLSCTX_DO_NOT_ELEVATE_SERVER is incompatible with elevated activation`
- `0x18008f03b`: `Unexpected remote WinRT activation attempt.`
- `0x18008ef21`: `ActivatableClassId`
- `0x18008eddb`: `Software\Microsoft\WindowsRuntime\LegacyCLSID`
- `0x18008ee1a`: `Software\Microsoft\WindowsRuntime\LegacyCLSID`

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
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  void *v28; // rcx
  int ServerPath; // eax
  void *v30; // rbx
  struct ACTIVATION_PARAMS *v31; // rax
  struct ACTIVATION_PARAMS *v32; // rcx
  unsigned int TokenForRPCClient; // eax
  __int64 v34; // rcx
  struct ACTIVATION_PARAMS *v35; // rax
  const WCHAR *v36; // r12
  int ActivationFlags; // eax
  unsigned int v38; // r15d
  int ActivationClientCatalogFlags; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  LSTATUS v43; // eax
  __int64 v44; // rcx
  LSTATUS v45; // eax
  __int64 v46; // rdx
  unsigned __int64 v47; // r9
  int ComWinRTActivationProperties; // eax
  char *v49; // rdi
  HRESULT v50; // eax
  struct SerializableProperty *v51; // rdx
  int v52; // eax
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // r9
  void *v56; // rsi
  struct ACTIVATION_PARAMS *v57; // rbx
  __int64 (__fastcall *v58)(void *, char *); // rdi
  void *v59; // rsi
  struct ACTIVATION_PARAMS *v60; // rbx
  __int64 (__fastcall *v61)(void *, char *); // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  int v63; // eax
  __int64 v64; // rdx
  int ClassInfoForActivation; // eax
  unsigned __int64 v66; // r9
  __int64 v67; // rdx
  int UserContextFromActivationProperties; // eax
  int ProcessMitigationPolicyFromActivationProperties; // eax
  int PackageGraphPackagesFromActivationProperties; // eax
  struct ACTIVATION_PARAMS *v71; // rdx
  int ComDependencyMainPackageFamilyNamesFromActivationProperties; // eax
  struct ACTIVATION_PARAMS *v73; // rax
  struct IUnknown *v74; // r9
  int v75; // eax
  __int64 v76; // rdx
  void **v77; // rcx
  int v78; // eax
  __int64 v79; // rcx
  char v80; // bl
  int v81; // eax
  int TokenForCOM; // eax
  __int64 v83; // r9
  __int64 v84; // rdx
  unsigned int v85; // eax
  struct CToken *v86; // rcx
  int v87; // eax
  __int64 v88; // rdx
  int v89; // eax
  int v90; // eax
  bool v91; // bl
  int v92; // edi
  ActivationPropertiesIn *v93; // rcx
  int v94; // eax
  __int64 v95; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  char *v98; // [rsp+28h] [rbp-D8h]
  struct ACTIVATION_PARAMS *v99; // [rsp+60h] [rbp-A0h] BYREF
  bool v100[8]; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v101; // [rsp+70h] [rbp-90h] BYREF
  void *v102; // [rsp+78h] [rbp-88h] BYREF
  char v103; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v104; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v105; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v107; // [rsp+98h] [rbp-68h] BYREF
  char v108; // [rsp+A0h] [rbp-60h]
  int v109; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  void *v111; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v112; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v113[2]; // [rsp+C8h] [rbp-38h] BYREF
  void *v114; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v115; // [rsp+D8h] [rbp-28h] BYREF
  void *v116; // [rsp+E0h] [rbp-20h] BYREF
  struct IExtensionActivationContextProperties *v117; // [rsp+E8h] [rbp-18h] BYREF
  int v118; // [rsp+F0h] [rbp-10h] BYREF
  int v119; // [rsp+F4h] [rbp-Ch] BYREF
  struct CToken *v120; // [rsp+F8h] [rbp-8h] BYREF
  struct CProcess *v121; // [rsp+100h] [rbp+0h] BYREF
  __int64 v122; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v123; // [rsp+110h] [rbp+10h] BYREF
  void *v124; // [rsp+118h] [rbp+18h] BYREF
  void *v125; // [rsp+120h] [rbp+20h] BYREF
  __int64 v126; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v127[3]; // [rsp+130h] [rbp+30h] BYREF
  char v128; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall **v129)(); // [rsp+150h] [rbp+50h] BYREF
  _BYTE v130[48]; // [rsp+158h] [rbp+58h] BYREF
  struct ACTIVATION_PARAMS **v131; // [rsp+188h] [rbp+88h]
  OLECHAR sz[40]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  *a2 = 0;
  v99 = a3;
  v4 = a2;
  v124 = 0;
  v125 = 0;
  v116 = 0;
  v103 = 0;
  v114 = 0;
  *((_QWORD *)a3 + 3) = 0;
  *((_QWORD *)a3 + 1) = 0;
  *((_QWORD *)a3 + 2) = 0;
  v105 = (HKEY)a2;
  *((_QWORD *)a3 + 67) = 0;
  v129 = off_180115CE8;
  lpMem = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v130,
    (struct wil::details::IFailureCallback *)&v129,
    a3,
    a4);
  v128 = 1;
  v131 = &v99;
  v127[0] = &v103;
  v127[1] = &v99;
  v127[2] = &v124;
  v6 = v99;
  *((_QWORD *)a1 + 70) = v99;
  *((_QWORD *)v6 + 43) = a1;
  Interface = ActivationPropertiesIn::QueryInterface(a1, &IID_IScmRequestInfo, (void **)v99 + 47);
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
  Interface = ActivationPropertiesIn::QueryInterface(a1, &IID_ILegacyInfo, &v124);
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
  *((_QWORD *)v99 + 45) = lpMem;
  if ( *((_BYTE *)v99 + 188) )
  {
    *((_QWORD *)v99 + 1) = 0;
    lpMem = 0;
    *((_QWORD *)v99 + 13) = 0;
    *((_QWORD *)v99 + 12) = 0;
    *((_DWORD *)v99 + 60) = 0;
    *((_QWORD *)v99 + 3) = 0;
    *((_QWORD *)v99 + 10) = 0;
    ServerLocationInfo = ActivationPropertiesIn::GetServerLocationInfo(a1, (struct ServerLocationInfo **)&lpMem);
    ExplicitMainPackageFamilyNameFromActivationProperties = ServerLocationInfo;
    if ( ServerLocationInfo < 0 )
    {
      v10 = (unsigned int)ServerLocationInfo;
      v9 = 1004;
      goto LABEL_266;
    }
    v121 = 0;
    (*(void (__fastcall **)(LPVOID, struct CProcess **))(*(_QWORD *)lpMem + 32LL))(lpMem, &v121);
    if ( v121 )
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
    v115 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v99 + 47) + 32LL))(*((_QWORD *)v99 + 47), &v115);
    ExplicitMainPackageFamilyNameFromActivationProperties = v14;
    if ( v14 < 0 )
    {
      v10 = (unsigned int)v14;
      v9 = 1017;
      goto LABEL_266;
    }
    if ( !v115 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
      v9 = 1020;
      goto LABEL_265;
    }
    v16 = *(_QWORD *)(v115 + 16);
    v121 = 0;
    if ( CookieToPHPROCESSMap::Get(v15, v16, (void **)&v121) < 0 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024891;
      v9 = 1026;
      goto LABEL_265;
    }
    v17 = CheckLocalSecurity(*(RPC_BINDING_HANDLE *)v99, v121);
    *((_QWORD *)v99 + 1) = v17;
    if ( !*((_QWORD *)v99 + 1) )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024891;
      v9 = 1031;
      goto LABEL_265;
    }
    *((_QWORD *)v99 + 13) = *(_QWORD *)(v115 + 24);
    *((_DWORD *)v99 + 28) = *(_DWORD *)(v115 + 32);
    *((_QWORD *)v99 + 12) = *(_QWORD *)(v115 + 8);
    *((_DWORD *)v99 + 60) = *(_DWORD *)v115;
    v122 = 0;
    v18 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v124 + 32LL))(v124, &v122);
    ExplicitMainPackageFamilyNameFromActivationProperties = v18;
    if ( v18 < 0 )
    {
      v10 = (unsigned int)v18;
      v9 = 1041;
      goto LABEL_266;
    }
    if ( v122 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = CopyAuthInfo(
                                                                *(struct _COAUTHINFO **)(v122 + 16),
                                                                (struct _COAUTHINFO **)v99 + 3);
      SecurityInfo::freeCOAUTHINFO(*(struct _COAUTHINFO **)(v122 + 16));
      *(_QWORD *)(v122 + 16) = 0;
      if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
      {
        v9 = 1047;
        goto LABEL_265;
      }
    }
  }
  v19 = ActivationPropertiesIn::QueryInterface(a1, &IID_IServerLocationInfo, &v125);
  ExplicitMainPackageFamilyNameFromActivationProperties = v19;
  if ( v19 < 0 )
  {
    v10 = (unsigned int)v19;
    v9 = 1052;
    goto LABEL_266;
  }
  if ( (*(int (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)v125 + 40LL))(v125, 0, 0) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v20);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v125 + 16LL))(v125);
  v21 = ActivationPropertiesIn::QueryInterface(a1, &IID_ISpecialSystemProperties, &v116);
  ExplicitMainPackageFamilyNameFromActivationProperties = v21;
  if ( v21 < 0 )
  {
    v10 = (unsigned int)v21;
    v9 = 1057;
    goto LABEL_266;
  }
  if ( (*(int (__fastcall **)(void *, char *))(*(_QWORD *)v116 + 56LL))(v116, (char *)v99 + 192) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v22);
  if ( (*(int (__fastcall **)(void *, char *, char *, char *))(*(_QWORD *)v116 + 40LL))(
         v116,
         (char *)v99 + 400,
         (char *)v99 + 408,
         (char *)v99 + 404) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v23);
  v24 = *(_QWORD *)v116;
  if ( *((_BYTE *)v99 + 188) )
  {
    if ( (*(int (__fastcall **)(void *, __int64, _QWORD))(v24 + 136))(v116, 0xFFFFFFFFLL, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v25);
    *((_DWORD *)v99 + 104) = -1;
  }
  else if ( (*(int (__fastcall **)(void *, char *, char *))(v24 + 128))(v116, (char *)v99 + 416, (char *)v99 + 424) < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v26);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationPropertiesIn::QueryInterface(
                                                            a1,
                                                            &IID_IInstanceInfo,
                                                            &v114);
  if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
  {
    if ( ExplicitMainPackageFamilyNameFromActivationProperties != -2147467262 )
    {
      v9 = 1130;
      goto LABEL_265;
    }
    v31 = v99;
    if ( *((_DWORD *)v99 + 14) == 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v27);
      v31 = v99;
    }
    if ( !*((_DWORD *)v31 + 14) )
    {
      *((_DWORD *)v31 + 52) = -1;
      v31 = v99;
    }
    *((_DWORD *)v31 + 53) = 0;
  }
  else
  {
    v28 = v114;
    *((_QWORD *)v99 + 46) = v114;
    if ( !*((_BYTE *)v99 + 188) )
    {
      v126 = 0;
      (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)v114 + 80LL))(v114, &v126);
      if ( v126 )
      {
        ExplicitMainPackageFamilyNameFromActivationProperties = -2147024891;
        v9 = 1088;
        goto LABEL_265;
      }
    }
    if ( *((_DWORD *)v99 + 14) == 1 )
    {
      *((_DWORD *)v99 + 14) = 2;
      v123 = 0;
      (*(void (__fastcall **)(void *, unsigned __int16 **, char *))(*(_QWORD *)v114 + 64LL))(
        v114,
        &v123,
        (char *)v99 + 208);
      if ( *((_BYTE *)v99 + 188) )
      {
        lpMem = 0;
        ServerPath = GetServerPath(v123, (unsigned __int16 **)&lpMem);
        ExplicitMainPackageFamilyNameFromActivationProperties = ServerPath;
        if ( ServerPath < 0 )
        {
          v10 = (unsigned int)ServerPath;
          v9 = 1102;
          goto LABEL_266;
        }
        v30 = lpMem;
        if ( v123 != lpMem )
        {
          (*(void (__fastcall **)(void *, LPVOID, _QWORD))(*(_QWORD *)v114 + 56LL))(
            v114,
            lpMem,
            *((unsigned int *)v99 + 52));
          (*(void (__fastcall **)(void *, char *, char *))(*(_QWORD *)v114 + 64LL))(
            v114,
            (char *)v99 + 216,
            (char *)v99 + 208);
          HeapFree(g_hHeap, 0, v30);
        }
      }
      else
      {
        *((_QWORD *)v99 + 27) = v123;
      }
      (*(void (__fastcall **)(void *, char *))(*(_QWORD *)v114 + 48LL))(v114, (char *)v99 + 224);
      v103 = 1;
    }
    if ( *((_DWORD *)v99 + 14) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v28);
  }
  *(_OWORD *)((char *)v99 + 60) = v12[2];
  if ( *((_BYTE *)v99 + 188) )
    *((_DWORD *)v99 + 29) = 4;
  else
    *((_DWORD *)v99 + 29) = *((_DWORD *)v12 + 12);
  v32 = v99;
  *((_DWORD *)v99 + 49) = *((_DWORD *)v12 + 15);
  *((_QWORD *)v32 + 25) = *((_QWORD *)v12 + 9);
  if ( !*((_DWORD *)v99 + 14) && *((_DWORD *)v99 + 49) != 1 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
    v9 = 1145;
    goto LABEL_265;
  }
  *(_DWORD *)(*((_QWORD *)v99 + 19) + 4LL) = 1;
  **((_DWORD **)v99 + 20) = 0;
  **((_DWORD **)v99 + 21) = 0;
  *(_QWORD *)(*((_QWORD *)v99 + 21) + 8LL) = 0;
  TokenForRPCClient = LookupOrCreateTokenForRPCClient(
                        *(RPC_BINDING_HANDLE *)v99,
                        *((unsigned __int8 *)v99 + 188),
                        (struct CToken **)v99 + 2,
                        (int *)v99 + 8);
  if ( TokenForRPCClient )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = wil::details::in1diag3::Return_Win32(
                                                              retaddr,
                                                              (void *)0x482,
                                                              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                                                              (const char *)TokenForRPCClient,
                                                              phkResult);
LABEL_267:
    v128 = 0;
    lambda_107589f66759e6b050a5cb7c6a70f6ea_::operator()(v127);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v130);
    return (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
  }
  v35 = v99;
  v36 = &Class;
  if ( *((_DWORD *)v99 + 8) )
  {
    *((_QWORD *)v99 + 12) = &Class;
    v35 = v99;
  }
  if ( !*((_QWORD *)v35 + 2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v34);
  v104 = 0;
  ActivationFlags = ActivationPropertiesIn::GetActivationFlags(
                      (struct ActivationPropertiesIn *)((char *)a1 + 568),
                      &v104);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationFlags;
  if ( ActivationFlags < 0 )
  {
    v10 = (unsigned int)ActivationFlags;
    v9 = 1164;
    goto LABEL_266;
  }
  v38 = v104;
  *((_BYTE *)v99 + 432) = (v104 & 0x400) != 0;
  ActivationClientCatalogFlags = GetActivationClientCatalogFlags(
                                   v38,
                                   *((struct CProcess **)v99 + 1),
                                   *((struct CToken **)v99 + 2),
                                   (unsigned int *)v99 + 103);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationClientCatalogFlags;
  if ( ActivationClientCatalogFlags < 0 )
  {
    v10 = (unsigned int)ActivationClientCatalogFlags;
    v9 = 1170;
    goto LABEL_266;
  }
  if ( !*((_BYTE *)v99 + 432) )
  {
    BreakOnDebuggedClsid((const struct _GUID *)((char *)v99 + 60));
    if ( (*((_BYTE *)v99 + 116) & 4) != 0 )
    {
      UserContextFromActivationProperties = GetUserContextFromActivationProperties(
                                              a1,
                                              *((unsigned __int8 *)v99 + 188),
                                              (unsigned __int64 *)v99 + 63);
      ExplicitMainPackageFamilyNameFromActivationProperties = UserContextFromActivationProperties;
      if ( UserContextFromActivationProperties < 0 )
      {
        v10 = (unsigned int)UserContextFromActivationProperties;
        v9 = 1294;
        goto LABEL_266;
      }
      if ( *(_QWORD *)((char *)v99 + 60) == *(_QWORD *)&CLSID_PerAppRuntimeBroker.Data1
        && *(_QWORD *)((char *)v99 + 68) == *(_QWORD *)CLSID_PerAppRuntimeBroker.Data4 )
      {
        ProcessMitigationPolicyFromActivationProperties = GetProcessMitigationPolicyFromActivationProperties(
                                                            a1,
                                                            *((unsigned __int8 *)v99 + 188),
                                                            (struct tagBLOB **)v99 + 64);
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
      LODWORD(v107) = 0;
      BYTE4(v107) = 1;
      lpMem = (char *)v99 + 464;
      PackageGraphPackagesFromActivationProperties = GetPackageGraphPackagesFromActivationProperties(
                                                       a1,
                                                       *((_BYTE *)v99 + 188),
                                                       (unsigned int *)&v107,
                                                       (HSTRING **)v99 + 58);
      ExplicitMainPackageFamilyNameFromActivationProperties = PackageGraphPackagesFromActivationProperties;
      if ( BYTE4(v107) )
        *((_QWORD *)lpMem + 1) = (unsigned int)v107;
      if ( PackageGraphPackagesFromActivationProperties < 0 )
      {
        v10 = (unsigned int)PackageGraphPackagesFromActivationProperties;
        v9 = 1315;
        goto LABEL_266;
      }
      v71 = v99;
      if ( *((_QWORD *)v99 + 59) )
      {
        *((_DWORD *)v99 + 103) |= 0x2000u;
        v71 = v99;
      }
      LODWORD(v107) = 0;
      lpMem = (char *)v71 + 480;
      BYTE4(v107) = 1;
      ComDependencyMainPackageFamilyNamesFromActivationProperties = GetComDependencyMainPackageFamilyNamesFromActivationProperties(
                                                                      a1,
                                                                      *((_BYTE *)v71 + 188),
                                                                      (unsigned int *)&v107,
                                                                      (HSTRING **)v71 + 60);
      ExplicitMainPackageFamilyNameFromActivationProperties = ComDependencyMainPackageFamilyNamesFromActivationProperties;
      if ( BYTE4(v107) )
        *((_QWORD *)lpMem + 1) = (unsigned int)v107;
      if ( ComDependencyMainPackageFamilyNamesFromActivationProperties < 0 )
      {
        v10 = (unsigned int)ComDependencyMainPackageFamilyNamesFromActivationProperties;
        v9 = 1329;
        goto LABEL_266;
      }
      v107 = 0;
      v108 = 1;
      lpMem = (char *)v99 + 456;
      ExplicitMainPackageFamilyNameFromActivationProperties = GetExplicitMainPackageFamilyNameFromActivationProperties(
                                                                a1,
                                                                *((_BYTE *)v99 + 188),
                                                                &v107);
      wil::details::out_param_t<std::unique_ptr<unsigned short [0]>>::~out_param_t<std::unique_ptr<unsigned short [0]>>(&lpMem);
      if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
      {
        v9 = 1332;
        goto LABEL_265;
      }
    }
    goto LABEL_136;
  }
  if ( !*((_BYTE *)v99 + 188) || *((_BYTE *)v99 + 189) )
  {
    v111 = 0;
    v53 = ActivationPropertiesIn::QueryInterface(a1, &GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a, &v111);
    ExplicitMainPackageFamilyNameFromActivationProperties = v53;
    if ( v53 >= 0 )
    {
      v56 = v111;
      v57 = v99;
      v58 = *(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v111 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        (char *)v99 + 440,
        0);
      v53 = v58(v56, (char *)v57 + 440);
      ExplicitMainPackageFamilyNameFromActivationProperties = v53;
      if ( v53 >= 0 )
      {
        v59 = v111;
        v60 = v99;
        v61 = *(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v111 + 64LL);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          (char *)v99 + 448,
          0);
        v53 = v61(v59, (char *)v60 + 448);
        ExplicitMainPackageFamilyNameFromActivationProperties = v53;
        if ( v53 >= 0 )
        {
          if ( *((_QWORD *)v99 + 55) )
          {
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v111);
            v4 = (struct IActivationPropertiesOut **)v105;
            goto LABEL_129;
          }
          ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
          v54 = 1202;
          v55 = 2147942487LL;
LABEL_122:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v54,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
            (const char *)v55,
            phkResult);
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v111);
          goto LABEL_267;
        }
        v54 = 1197;
      }
      else
      {
        v54 = 1196;
      }
    }
    else
    {
      v54 = 1195;
    }
    v55 = (unsigned int)v53;
    goto LABEL_122;
  }
  if ( !(unsigned __int8)IsWinRTPerMachineSingleInstancingPresent(v99, v40, v41, v42)
    || !(unsigned int)RemoteWinRTActivation()
    || *(_QWORD *)((char *)v99 + 60) == *(_QWORD *)&GUID_NULL.Data1
    && *(_QWORD *)((char *)v99 + 68) == *(_QWORD *)GUID_NULL.Data4 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x4DF,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)0x8000FFFFLL,
      (int)"Unexpected remote WinRT activation attempt.",
      v98);
    goto LABEL_267;
  }
  hKey = 0;
  v43 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WindowsRuntime\\LegacyCLSID", 0, 0x20019u, &hKey);
  ExplicitMainPackageFamilyNameFromActivationProperties = v43;
  if ( v43 > 0 )
    ExplicitMainPackageFamilyNameFromActivationProperties = (unsigned __int16)v43 | 0x80070000;
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
    if ( StringFromGUID2((const GUID *const)((char *)v99 + 60), sz, 39) != 39 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v44);
    v105 = 0;
    v45 = RegOpenKeyExW(hKey, sz, 0, 0x20019u, &v105);
    ExplicitMainPackageFamilyNameFromActivationProperties = v45;
    if ( v45 > 0 )
      ExplicitMainPackageFamilyNameFromActivationProperties = (unsigned __int16)v45 | 0x80070000;
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
          (char *)v99 + 440,
          0);
        v100[0] = 0;
        ExplicitMainPackageFamilyNameFromActivationProperties = RegistryKey::ReadStringValueWorker<128,HSTRING__ *>(
                                                                  (RegistryKey *)&v105,
                                                                  (__int64)v100);
        if ( ExplicitMainPackageFamilyNameFromActivationProperties >= 0 && !*((_QWORD *)v99 + 55) )
          ExplicitMainPackageFamilyNameFromActivationProperties = -2147024883;
      }
    }
    RegistryKey::Close((RegistryKey *)&v105);
  }
  if ( ExplicitMainPackageFamilyNameFromActivationProperties == -2147024894 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147221164;
    v46 = 1233;
LABEL_102:
    v47 = (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
LABEL_103:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)v47,
      phkResult);
    RegistryKey::Close((RegistryKey *)&hKey);
    goto LABEL_267;
  }
  if ( ExplicitMainPackageFamilyNameFromActivationProperties == -2147024883 )
  {
    ExplicitMainPackageFamilyNameFromActivationProperties = -2147221165;
    v46 = 1234;
    goto LABEL_102;
  }
  if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
  {
    v46 = 1235;
    goto LABEL_102;
  }
  lpMem = 0;
  ComWinRTActivationProperties = ActivationPropertiesIn::GetComWinRTActivationProperties(
                                   a1,
                                   (struct ComWinRTActivationProperties **)&lpMem);
  ExplicitMainPackageFamilyNameFromActivationProperties = ComWinRTActivationProperties;
  if ( ComWinRTActivationProperties < 0 )
  {
    v47 = (unsigned int)ComWinRTActivationProperties;
    v46 = 1241;
    goto LABEL_103;
  }
  v49 = (char *)lpMem;
  v50 = WindowsDuplicateString(*((HSTRING *)v99 + 55), (HSTRING *)lpMem + 4);
  ExplicitMainPackageFamilyNameFromActivationProperties = v50;
  if ( v50 < 0 )
  {
    v47 = (unsigned int)v50;
    v46 = 1242;
    goto LABEL_103;
  }
  if ( v49 )
    v51 = (struct SerializableProperty *)(v49 + 8);
  else
    v51 = 0;
  v52 = ActivationProperties::AddSerializableIfs(a1, v51);
  ExplicitMainPackageFamilyNameFromActivationProperties = v52;
  if ( v52 < 0 )
  {
    v47 = (unsigned int)v52;
    v46 = 1243;
    goto LABEL_103;
  }
  RegistryKey::Close((RegistryKey *)&hKey);
LABEL_129:
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v99 + 55), 0);
  BreakOnDebuggedActivatableClassId(StringRawBuffer);
  if ( !*((_BYTE *)v99 + 188) )
  {
    v117 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
    v63 = ActivationPropertiesIn::QueryInterface(a1, &GUID_071742dc_587e_4930_81d5_8a7de8547529, (void **)&v117);
    ExplicitMainPackageFamilyNameFromActivationProperties = v63;
    if ( v63 < 0 )
    {
      v64 = 1273;
LABEL_132:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v63,
        phkResult);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
      goto LABEL_267;
    }
    v63 = EvaluateExtensionActivationContextProperties(v117, a1, v99);
    ExplicitMainPackageFamilyNameFromActivationProperties = v63;
    if ( v63 < 0 )
    {
      v64 = 1275;
      goto LABEL_132;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
  }
LABEL_136:
  v101 = 0;
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::reset(&v101);
  ClassInfoForActivation = TryGetClassInfoForActivation(v99, (struct IComClassInfo **)&v101);
  ExplicitMainPackageFamilyNameFromActivationProperties = ClassInfoForActivation;
  if ( ClassInfoForActivation < 0 )
  {
    v66 = (unsigned int)ClassInfoForActivation;
    v67 = 1337;
LABEL_262:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v67,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)v66,
      phkResult);
    goto LABEL_263;
  }
  v73 = v99;
  if ( !*((_BYTE *)v99 + 432) )
  {
    v74 = v101;
    if ( !v101 )
      goto LABEL_180;
    v112 = 0;
    v75 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v101->lpVtbl->QueryInterface)(
            v101,
            &GUID_430be197_0244_2f7b_80fd_c7c473983ad0,
            &v112);
    ExplicitMainPackageFamilyNameFromActivationProperties = v75;
    if ( v75 < 0 )
    {
      v76 = 1351;
LABEL_163:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v76,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v75,
        phkResult);
      v77 = (void **)&v112;
LABEL_164:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v77);
LABEL_263:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v101);
      goto LABEL_267;
    }
    v118 = 0;
    v75 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v112 + 24LL))(v112, &v118);
    ExplicitMainPackageFamilyNameFromActivationProperties = v75;
    if ( v75 < 0 )
    {
      v76 = 1354;
      goto LABEL_163;
    }
    if ( v118 == 2 )
    {
      v75 = CalculateActivationTargetSessionId((struct IComClassInfo *)v101, v99);
      ExplicitMainPackageFamilyNameFromActivationProperties = v75;
      if ( v75 < 0 )
      {
        v76 = 1374;
        goto LABEL_163;
      }
      v119 = 0;
      v75 = PerformDeferredPackageRegistrationForClassIfNecessary(
              *((struct CToken **)v99 + 2),
              (const struct _GUID *)((char *)v99 + 60),
              *((_DWORD *)v99 + 103) | *((_DWORD *)v99 + 29) & 0x17u,
              (struct IComClassInfo *)v101,
              *((_DWORD *)v99 + 32),
              &v119);
      ExplicitMainPackageFamilyNameFromActivationProperties = v75;
      if ( v75 < 0 )
      {
        v76 = 1379;
        goto LABEL_163;
      }
      if ( v119 )
      {
        wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::reset(&v101);
        v75 = TryGetClassInfoForActivation(v99, (struct IComClassInfo **)&v101);
        ExplicitMainPackageFamilyNameFromActivationProperties = v75;
        if ( v75 < 0 )
        {
          v76 = 1382;
          goto LABEL_163;
        }
      }
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v112);
    v73 = v99;
  }
  v74 = v101;
  if ( v101 )
  {
    v78 = ActivationPropertiesIn::SetClassInfo((struct ActivationPropertiesIn *)((char *)a1 + 584), v101);
    ExplicitMainPackageFamilyNameFromActivationProperties = v78;
    if ( v78 < 0 )
    {
      v66 = (unsigned int)v78;
      v67 = 1393;
      goto LABEL_262;
    }
    v74 = v101;
    v73 = v99;
  }
LABEL_180:
  if ( *((_DWORD *)v73 + 104) != -1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && (v38 & 0x8000000) != 0 )
    {
      ExplicitMainPackageFamilyNameFromActivationProperties = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x57D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x80070057LL,
        (int)"CLSCTX_DO_NOT_ELEVATE_SERVER is incompatible with elevated activation",
        v98);
      goto LABEL_263;
    }
    v105 = 0;
    *(_QWORD *)v113 = 0;
    lpMem = 0;
    v109 = 0;
    if ( (int)RtlQueryElevationFlags(&v109) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v79);
    if ( (v109 & 1) != 0 )
    {
      v80 = 1;
    }
    else
    {
      v80 = 0;
      *((_DWORD *)v99 + 104) = -1;
    }
    v73 = v99;
    if ( *((_DWORD *)v99 + 104) != -1 )
    {
      v104 = 0;
      if ( !v101 )
        goto LABEL_207;
      v102 = 0;
      v81 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, void **))v101->lpVtbl->QueryInterface)(
              v101,
              &GUID_0318b242_d086_4de9_b10c_2824a6ca1019,
              &v102);
      if ( v81 >= 0 )
      {
        (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v102 + 48LL))(v102, &v104);
        if ( v104 )
        {
          (*(void (__fastcall **)(void *, HKEY *))(*(_QWORD *)v102 + 56LL))(v102, &v105);
          (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v102 + 72LL))(v102, v113);
          (*(void (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v102 + 64LL))(v102, &lpMem);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x597,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)v81,
          phkResult);
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v102);
      if ( !v104 )
      {
LABEL_207:
        ExplicitMainPackageFamilyNameFromActivationProperties = -2146959337;
        v67 = 1442;
        goto LABEL_261;
      }
      if ( !v105 )
      {
        ExplicitMainPackageFamilyNameFromActivationProperties = -2146959339;
        v67 = 1443;
LABEL_261:
        v66 = (unsigned int)ExplicitMainPackageFamilyNameFromActivationProperties;
        goto LABEL_262;
      }
      v73 = v99;
    }
    if ( v80 )
    {
      v102 = 0;
      v120 = 0;
      if ( !(unsigned __int8)IsCoAicGetTokenForCOMPresent() )
      {
        ExplicitMainPackageFamilyNameFromActivationProperties = -2147467263;
        v84 = 1472;
        v83 = 2147500033LL;
        goto LABEL_205;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v102,
        0);
      if ( *(_QWORD *)v113 )
        LODWORD(v36) = v113[0];
      phkResult = (unsigned int)v36;
      TokenForCOM = CoAicGetTokenForCOM(
                      *((_QWORD *)v99 + 53),
                      *(_QWORD *)(*((_QWORD *)v99 + 1) + 32LL),
                      (char *)v99 + 60,
                      v105);
      ExplicitMainPackageFamilyNameFromActivationProperties = TokenForCOM;
      if ( TokenForCOM < 0 )
      {
        v83 = (unsigned int)TokenForCOM;
        v84 = 1468;
LABEL_205:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v84,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)v83,
          phkResult);
LABEL_206:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v102);
        goto LABEL_263;
      }
      if ( (char *)v102 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v85 = LookupOrCreateTokenFromHandle(v102, &v120);
        if ( v85 )
        {
          ExplicitMainPackageFamilyNameFromActivationProperties = wil::details::in1diag3::Return_Win32(
                                                                    retaddr,
                                                                    (void *)0x5C6,
                                                                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                                                                    (const char *)v85,
                                                                    (unsigned int)v36);
          goto LABEL_206;
        }
        v102 = 0;
        CToken::Release(*((CToken **)v99 + 2));
        v86 = v120;
        *((_QWORD *)v99 + 2) = v120;
        if ( !*((_QWORD *)v99 + 2) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v86);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v102);
      v73 = v99;
    }
    if ( *((_DWORD *)v73 + 104) != -1 )
    {
      *((_QWORD *)v73 + 13) = 0;
      *((_DWORD *)v99 + 28) = 0;
      v73 = v99;
    }
    v74 = v101;
  }
  if ( !*((_BYTE *)v73 + 188) && v74 )
  {
    v102 = 0;
    v87 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, void **))v74->lpVtbl->QueryInterface)(
            v74,
            &GUID_430be197_0244_2f7b_80fd_c7c473983ad0,
            &v102);
    ExplicitMainPackageFamilyNameFromActivationProperties = v87;
    if ( v87 < 0 )
    {
      v88 = 1510;
LABEL_221:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v88,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v87,
        phkResult);
LABEL_222:
      v77 = &v102;
      goto LABEL_164;
    }
    v109 = 0;
    v87 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v102 + 24LL))(v102, &v109);
    ExplicitMainPackageFamilyNameFromActivationProperties = v87;
    if ( v87 < 0 )
    {
      v88 = 1520;
      goto LABEL_221;
    }
    if ( !v109 )
    {
      v105 = 0;
      v89 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HKEY *))v101->lpVtbl->QueryInterface)(
              v101,
              &GUID_000001e2_0000_0000_c000_000000000046,
              &v105);
      ExplicitMainPackageFamilyNameFromActivationProperties = v89;
      if ( v89 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F5,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)v89,
          phkResult);
LABEL_229:
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v105);
        goto LABEL_222;
      }
      *(_QWORD *)v113 = 0;
      if ( (*(int (__fastcall **)(HKEY, GUID *, unsigned int *))(*(_QWORD *)v105 + 48LL))(
             v105,
             &GUID_000001ed_0000_0000_c000_000000000046,
             v113) < 0 )
      {
        v91 = 1;
      }
      else
      {
        v104 = 0;
        v90 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v113 + 80LL))(*(_QWORD *)v113, &v104);
        ExplicitMainPackageFamilyNameFromActivationProperties = v90;
        if ( v90 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5FA,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
            (const char *)(unsigned int)v90,
            phkResult);
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v113);
          goto LABEL_229;
        }
        v91 = 0;
        if ( v104 == 2 )
        {
          lpMem = 0;
          if ( (***(int (__fastcall ****)(_QWORD, GUID *, LPVOID *))v113)(
                 *(_QWORD *)v113,
                 &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680,
                 &lpMem) < 0 )
          {
            v91 = 1;
          }
          else
          {
            LODWORD(v120) = 0;
            (*(void (__fastcall **)(LPVOID, struct CToken **))(*(_QWORD *)lpMem + 192LL))(lpMem, &v120);
            v91 = ((unsigned __int16)v120 & 0x800) == 0;
          }
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&lpMem);
        }
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v113);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v105);
      if ( v91 )
      {
        v100[0] = 0;
        v87 = CToken::ImplicitlyActivateClassicAAAServersAsIU(*((CToken **)v99 + 2), v100);
        ExplicitMainPackageFamilyNameFromActivationProperties = v87;
        if ( v87 < 0 )
        {
          v88 = 1559;
          goto LABEL_221;
        }
        if ( v100[0] )
        {
          v87 = ActivationPropertiesIn::SetActivationFlags(
                  (struct ActivationPropertiesIn *)((char *)a1 + 584),
                  v38 | 0x80000);
          ExplicitMainPackageFamilyNameFromActivationProperties = v87;
          if ( v87 < 0 )
          {
            v88 = 1565;
            goto LABEL_221;
          }
        }
      }
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v102);
    v73 = v99;
  }
  v92 = 0;
  if ( !*((_DWORD *)v73 + 8) )
    *((_QWORD *)a1 + 77) = *(_QWORD *)(*((_QWORD *)v73 + 2) + 72LL);
  ExplicitMainPackageFamilyNameFromActivationProperties = ActivationPropertiesIn::SetStageAndIndex((char *)a1 + 576, 3);
  if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
  {
LABEL_260:
    v67 = 1580;
    goto LABEL_261;
  }
  while ( 1 )
  {
    v93 = (struct ActivationPropertiesIn *)((char *)a1 + 568);
    v94 = *((_DWORD *)v99 + 14)
        ? ActivationPropertiesIn::DelegateCreateInstance(v93, 0, v4)
        : ActivationPropertiesIn::DelegateGetClassObject(v93, v4);
    ExplicitMainPackageFamilyNameFromActivationProperties = v94;
    if ( v94 != -2147023659 )
      break;
    if ( v92 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v95);
LABEL_258:
      v67 = 1603;
      goto LABEL_261;
    }
    ExplicitMainPackageFamilyNameFromActivationProperties = ActivationPropertiesIn::SetStageAndIndex(
                                                              (char *)a1 + 576,
                                                              3);
    if ( ExplicitMainPackageFamilyNameFromActivationProperties < 0 )
      goto LABEL_260;
    v92 = 1;
  }
  if ( v94 < 0 )
    goto LABEL_258;
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v101);
  v128 = 0;
  lambda_107589f66759e6b050a5cb7c6a70f6ea_::operator()(v127);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v130);
  return 0;
}

```

## disassembly

```asm
0x18008e54c  mov     [rsp-8+arg_18], rbx
0x18008e551  push    rbp
0x18008e552  push    rsi
0x18008e553  push    rdi
0x18008e554  push    r12
0x18008e556  push    r13
0x18008e558  push    r14
0x18008e55a  push    r15
0x18008e55c  lea     rbp, [rsp-0F0h]
0x18008e564  sub     rsp, 1F0h
0x18008e56b  mov     rax, cs:__security_cookie
0x18008e572  xor     rax, rsp
0x18008e575  mov     [rbp+120h+var_40], rax
0x18008e57c  mov     qword ptr [rdx], 0
0x18008e583  lea     rax, off_180115CE8
0x18008e58a  mov     [rsp+220h+var_1C0], r8
0x18008e58f  mov     rsi, rdx
0x18008e592  mov     [rbp+120h+var_108], 0
0x18008e59a  mov     r14, rcx
0x18008e59d  mov     [rbp+120h+var_100], 0
0x18008e5a5  lea     rcx, [rbp+120h+var_C8]; this
0x18008e5a9  mov     [rbp+120h+var_140], 0
0x18008e5b1  mov     [rbp+120h+var_1A0], 0
0x18008e5b5  mov     [rbp+120h+var_150], 0
0x18008e5bd  mov     qword ptr [r8+18h], 0
0x18008e5c5  mov     qword ptr [r8+8], 0
0x18008e5cd  mov     qword ptr [r8+10h], 0
0x18008e5d5  mov     [rbp+120h+var_198], rdx
0x18008e5d9  lea     rdx, [rbp+120h+var_D0]; struct wil::details::IFailureCallback *
0x18008e5dd  mov     qword ptr [r8+218h], 0
0x18008e5e8  mov     [rbp+120h+var_D0], rax
0x18008e5ec  mov     [rbp+120h+lpMem], 0
0x18008e5f4  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18008e5f9  lea     rax, [rsp+220h+var_1C0]
0x18008e5fe  mov     [rbp+120h+var_D8], 1
0x18008e602  mov     [rbp+120h+var_98], rax
0x18008e609  lea     rdx, IID_IScmRequestInfo; struct _GUID *
0x18008e610  lea     rax, [rbp+120h+var_1A0]
0x18008e614  mov     rcx, r14; this
0x18008e617  mov     [rbp+120h+var_F0], rax
0x18008e61b  lea     rax, [rsp+220h+var_1C0]
0x18008e620  mov     [rbp+120h+var_E8], rax
0x18008e624  lea     rax, [rbp+120h+var_108]
0x18008e628  mov     [rbp+120h+var_E0], rax
0x18008e62c  mov     rax, [rsp+220h+var_1C0]
0x18008e631  mov     [r14+230h], rax
0x18008e638  mov     [rax+158h], r14
0x18008e63f  mov     r8, [rsp+220h+var_1C0]
0x18008e644  add     r8, 178h; void **
0x18008e64b  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18008e650  mov     ebx, eax
0x18008e652  test    eax, eax
0x18008e654  jns     short loc_18008E65D
0x18008e656  mov     edx, 3DEh
0x18008e65b  jmp     short loc_18008E67B
0x18008e65d  lea     r8, [rbp+120h+var_108]; void **
0x18008e661  mov     rcx, r14; this
0x18008e664  lea     rdx, IID_ILegacyInfo; struct _GUID *
0x18008e66b  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18008e670  mov     ebx, eax
0x18008e672  test    eax, eax
0x18008e674  jns     short loc_18008E683
0x18008e676  mov     edx, 3DFh
0x18008e67b  mov     r9d, eax
0x18008e67e  jmp     loc_18008FB8F
0x18008e683  lea     rdx, [rbp+120h+lpMem]; struct InstantiationInfo **
0x18008e687  mov     rcx, r14; this
0x18008e68a  call    ?GetInstantiationInfo@ActivationPropertiesIn@@QEAAJPEAPEAVInstantiationInfo@@@Z; ActivationPropertiesIn::GetInstantiationInfo(InstantiationInfo * *)
0x18008e68f  mov     ebx, eax
0x18008e691  test    eax, eax
0x18008e693  jns     short loc_18008E6A2
0x18008e695  mov     r9d, eax
0x18008e698  mov     edx, 3E0h
0x18008e69d  jmp     loc_18008FB8F
0x18008e6a2  mov     rax, [rsp+220h+var_1C0]
0x18008e6a7  mov     rdi, [rbp+120h+lpMem]
0x18008e6ab  mov     [rax+168h], rdi
0x18008e6b2  mov     rcx, [rsp+220h+var_1C0]
0x18008e6b7  cmp     byte ptr [rcx+0BCh], 0
0x18008e6be  jz      loc_18008E76C
0x18008e6c4  mov     qword ptr [rcx+8], 0
0x18008e6cc  lea     rdx, [rbp+120h+lpMem]; struct ServerLocationInfo **
0x18008e6d0  mov     rax, [rsp+220h+var_1C0]
0x18008e6d5  mov     rcx, r14; this
0x18008e6d8  mov     [rbp+120h+lpMem], 0
0x18008e6e0  mov     qword ptr [rax+68h], 0
0x18008e6e8  mov     rax, [rsp+220h+var_1C0]
0x18008e6ed  mov     qword ptr [rax+60h], 0
0x18008e6f5  mov     rax, [rsp+220h+var_1C0]
0x18008e6fa  mov     dword ptr [rax+0F0h], 0
0x18008e704  mov     rax, [rsp+220h+var_1C0]
0x18008e709  mov     qword ptr [rax+18h], 0
0x18008e711  mov     rax, [rsp+220h+var_1C0]
0x18008e716  mov     qword ptr [rax+50h], 0
0x18008e71e  call    ?GetServerLocationInfo@ActivationPropertiesIn@@QEAAJPEAPEAVServerLocationInfo@@@Z; ActivationPropertiesIn::GetServerLocationInfo(ServerLocationInfo * *)
0x18008e723  mov     ebx, eax
0x18008e725  test    eax, eax
0x18008e727  jns     short loc_18008E736
0x18008e729  mov     r9d, eax
0x18008e72c  mov     edx, 3ECh
0x18008e731  jmp     loc_18008FB8F
0x18008e736  mov     rcx, [rbp+120h+lpMem]
0x18008e73a  lea     rdx, [rbp+120h+var_120]
0x18008e73e  mov     [rbp+120h+var_120], 0
0x18008e746  mov     rax, [rcx]
0x18008e749  mov     rax, [rax+20h]
0x18008e74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e752  cmp     [rbp+120h+var_120], 0
0x18008e757  jz      loc_18008E8C3
0x18008e75d  mov     ebx, 80070057h
0x18008e762  mov     edx, 3F4h
0x18008e767  jmp     loc_18008FB8C
0x18008e76c  mov     [rbp+120h+var_148], 0
0x18008e774  lea     rdx, [rbp+120h+var_148]
0x18008e778  mov     rcx, [rcx+178h]
0x18008e77f  mov     rax, [rcx]
0x18008e782  mov     rax, [rax+20h]
0x18008e786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e78b  mov     ebx, eax
0x18008e78d  test    eax, eax
0x18008e78f  jns     short loc_18008E79E
0x18008e791  mov     r9d, eax
0x18008e794  mov     edx, 3F9h
0x18008e799  jmp     loc_18008FB8F
0x18008e79e  mov     rdx, [rbp+120h+var_148]
0x18008e7a2  test    rdx, rdx
0x18008e7a5  jnz     short loc_18008E7B6
0x18008e7a7  mov     ebx, 80070057h
0x18008e7ac  mov     edx, 3FCh
0x18008e7b1  jmp     loc_18008FB8C
0x18008e7b6  mov     rdx, [rdx+10h]; unsigned __int64
0x18008e7ba  lea     r8, [rbp+120h+var_120]; void **
0x18008e7be  mov     [rbp+120h+var_120], 0
0x18008e7c6  call    ?Get@CookieToPHPROCESSMap@@QEAAJ_KAEAPEAX@Z; CookieToPHPROCESSMap::Get(unsigned __int64,void * &)
0x18008e7cb  test    eax, eax
0x18008e7cd  jns     short loc_18008E7DE
0x18008e7cf  mov     ebx, 80070005h
0x18008e7d4  mov     edx, 402h
0x18008e7d9  jmp     loc_18008FB8C
0x18008e7de  mov     rcx, [rsp+220h+var_1C0]
0x18008e7e3  mov     rdx, [rbp+120h+var_120]; struct CProcess *
0x18008e7e7  mov     rcx, [rcx]; Binding
0x18008e7ea  call    ?CheckLocalSecurity@@YAPEAVCProcess@@PEAX0@Z; CheckLocalSecurity(void *,void *)
0x18008e7ef  mov     rcx, [rsp+220h+var_1C0]
0x18008e7f4  mov     [rcx+8], rax
0x18008e7f8  mov     rdx, [rsp+220h+var_1C0]
0x18008e7fd  cmp     qword ptr [rdx+8], 0
0x18008e802  jnz     short loc_18008E813
0x18008e804  mov     ebx, 80070005h
0x18008e809  mov     edx, 407h
0x18008e80e  jmp     loc_18008FB8C
0x18008e813  mov     rax, [rbp+120h+var_148]
0x18008e817  mov     rcx, [rax+18h]
0x18008e81b  mov     [rdx+68h], rcx
0x18008e81f  lea     rdx, [rbp+120h+var_118]
0x18008e823  mov     rax, [rbp+120h+var_148]
0x18008e827  mov     ecx, [rax+20h]
0x18008e82a  mov     rax, [rsp+220h+var_1C0]
0x18008e82f  mov     [rax+70h], ecx
0x18008e832  mov     rax, [rbp+120h+var_148]
0x18008e836  mov     rcx, [rax+8]
0x18008e83a  mov     rax, [rsp+220h+var_1C0]
0x18008e83f  mov     [rax+60h], rcx
0x18008e843  mov     rax, [rbp+120h+var_148]
0x18008e847  mov     ecx, [rax]
0x18008e849  mov     rax, [rsp+220h+var_1C0]
0x18008e84e  mov     [rax+0F0h], ecx
0x18008e854  mov     rcx, [rbp+120h+var_108]
0x18008e858  mov     [rbp+120h+var_118], 0
0x18008e860  mov     rax, [rcx]
0x18008e863  mov     rax, [rax+20h]
0x18008e867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e86c  mov     ebx, eax
0x18008e86e  test    eax, eax
0x18008e870  jns     short loc_18008E87F
0x18008e872  mov     r9d, eax
0x18008e875  mov     edx, 411h
0x18008e87a  jmp     loc_18008FB8F
0x18008e87f  mov     rcx, [rbp+120h+var_118]
0x18008e883  test    rcx, rcx
0x18008e886  jz      short loc_18008E8C3
0x18008e888  mov     rdx, [rsp+220h+var_1C0]
0x18008e88d  mov     rcx, [rcx+10h]; struct _COAUTHINFO *
0x18008e891  add     rdx, 18h; struct _COAUTHINFO **
0x18008e895  call    ?CopyAuthInfo@@YAJPEAU_COAUTHINFO@@PEAPEAU1@@Z; CopyAuthInfo(_COAUTHINFO *,_COAUTHINFO * *)
0x18008e89a  mov     rcx, [rbp+120h+var_118]
0x18008e89e  mov     ebx, eax
0x18008e8a0  mov     rcx, [rcx+10h]; lpMem
0x18008e8a4  call    ?freeCOAUTHINFO@SecurityInfo@@SAXPEAU_COAUTHINFO@@@Z; SecurityInfo::freeCOAUTHINFO(_COAUTHINFO *)
0x18008e8a9  mov     rcx, [rbp+120h+var_118]
0x18008e8ad  mov     qword ptr [rcx+10h], 0
0x18008e8b5  test    ebx, ebx
0x18008e8b7  jns     short loc_18008E8C3
0x18008e8b9  mov     edx, 417h
0x18008e8be  jmp     loc_18008FB8C
0x18008e8c3  lea     r8, [rbp+120h+var_100]; void **
0x18008e8c7  mov     rcx, r14; this
0x18008e8ca  lea     rdx, IID_IServerLocationInfo; struct _GUID *
0x18008e8d1  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18008e8d6  mov     ebx, eax
0x18008e8d8  test    eax, eax
0x18008e8da  jns     short loc_18008E8E9
0x18008e8dc  mov     r9d, eax
0x18008e8df  mov     edx, 41Ch
0x18008e8e4  jmp     loc_18008FB8F
0x18008e8e9  mov     rcx, [rbp+120h+var_100]
0x18008e8ed  xor     r8d, r8d
0x18008e8f0  xor     edx, edx
0x18008e8f2  mov     rax, [rcx]
0x18008e8f5  mov     rax, [rax+28h]
0x18008e8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8fe  test    eax, eax
0x18008e900  jns     short loc_18008E907
0x18008e902  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e907  mov     rcx, [rbp+120h+var_100]
0x18008e90b  mov     rax, [rcx]
0x18008e90e  mov     rax, [rax+10h]
0x18008e912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e917  lea     r8, [rbp+120h+var_140]; void **
0x18008e91b  mov     rcx, r14; this
0x18008e91e  lea     rdx, IID_ISpecialSystemProperties; struct _GUID *
0x18008e925  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18008e92a  mov     ebx, eax
0x18008e92c  test    eax, eax
0x18008e92e  jns     short loc_18008E93D
0x18008e930  mov     r9d, eax
0x18008e933  mov     edx, 421h
0x18008e938  jmp     loc_18008FB8F
0x18008e93d  mov     rcx, [rbp+120h+var_140]
0x18008e941  mov     rdx, [rsp+220h+var_1C0]
0x18008e946  add     rdx, 0C0h
0x18008e94d  mov     rax, [rcx]
0x18008e950  mov     rax, [rax+38h]
0x18008e954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e959  test    eax, eax
0x18008e95b  jns     short loc_18008E962
0x18008e95d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e962  mov     rdx, [rsp+220h+var_1C0]
0x18008e967  mov     rcx, [rbp+120h+var_140]
0x18008e96b  lea     r9, [rdx+194h]
0x18008e972  mov     rax, [rcx]
0x18008e975  lea     r8, [rdx+198h]
0x18008e97c  add     rdx, 190h
0x18008e983  mov     rax, [rax+28h]
0x18008e987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e98c  test    eax, eax
0x18008e98e  jns     short loc_18008E995
0x18008e990  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e995  mov     rdx, [rsp+220h+var_1C0]
0x18008e99a  or      r15d, 0FFFFFFFFh
0x18008e99e  mov     rcx, [rbp+120h+var_140]
0x18008e9a2  cmp     byte ptr [rdx+0BCh], 0
0x18008e9a9  mov     rax, [rcx]
0x18008e9ac  jz      short loc_18008E9D7
0x18008e9ae  mov     rax, [rax+88h]
0x18008e9b5  xor     r8d, r8d
0x18008e9b8  mov     edx, r15d
0x18008e9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9c0  test    eax, eax
0x18008e9c2  jns     short loc_18008E9C9
0x18008e9c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e9c9  mov     rax, [rsp+220h+var_1C0]
0x18008e9ce  mov     [rax+1A0h], r15d
0x18008e9d5  jmp     short loc_18008E9FA
0x18008e9d7  mov     rax, [rax+80h]
0x18008e9de  lea     r8, [rdx+1A8h]
0x18008e9e5  add     rdx, 1A0h
0x18008e9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9f1  test    eax, eax
0x18008e9f3  jns     short loc_18008E9FA
0x18008e9f5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e9fa  mov     rcx, [rbp+120h+var_140]
0x18008e9fe  mov     rax, [rcx]
0x18008ea01  mov     rax, [rax+10h]
0x18008ea05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea0a  lea     r8, [rbp+120h+var_150]; void **
0x18008ea0e  mov     rcx, r14; this
0x18008ea11  lea     rdx, IID_IInstanceInfo; struct _GUID *
0x18008ea18  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18008ea1d  mov     ebx, eax
0x18008ea1f  test    eax, eax
0x18008ea21  js      loc_18008EB92
0x18008ea27  mov     rax, [rsp+220h+var_1C0]
0x18008ea2c  mov     rcx, [rbp+120h+var_150]
0x18008ea30  mov     [rax+170h], rcx
0x18008ea37  mov     rax, [rsp+220h+var_1C0]
0x18008ea3c  cmp     byte ptr [rax+0BCh], 0
0x18008ea43  jnz     short loc_18008EA77
0x18008ea45  mov     rcx, [rbp+120h+var_150]
0x18008ea49  lea     rdx, [rbp+120h+var_F8]
0x18008ea4d  mov     [rbp+120h+var_F8], 0
0x18008ea55  mov     rax, [rcx]
0x18008ea58  mov     rax, [rax+50h]
0x18008ea5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea61  cmp     [rbp+120h+var_F8], 0
0x18008ea66  jz      short loc_18008EA77
0x18008ea68  mov     ebx, 80070005h
0x18008ea6d  mov     edx, 440h
0x18008ea72  jmp     loc_18008FB8C
0x18008ea77  mov     rax, [rsp+220h+var_1C0]
  ... truncated ...
```
