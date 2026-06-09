# BioTrustlet::ExistsSecureFpRegKey(void)

- ea: `0x180050bb0`
- end: `0x18005102a`
- name: `?ExistsSecureFpRegKey@BioTrustlet@@SA_NXZ`
- size: `1146`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050b4c`

## callees

- `0x18001434c`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x18002ab1c`
- `0x18002ad10`
- `0x180050bb0`
- `0x180056d14`
- `0x180068f60`
- `0x180069cc8`
- `0x18006e4c4`
- `0x1800b4cf4`
- `0x1800b50a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050ec9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050f26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050ec9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050f26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050dc2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050dc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050d66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050d66`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180050c4c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180050c4c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180050fc8`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180051005`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180050fc8`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180051005`
- `DEVOBJ!DevObjGetClassDevs` at `0x180050c87`
- `DEVOBJ!DevObjGetClassDevs` at `0x180050c87`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180050ef9`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180050ef9`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180050d2a`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180050d2a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180050ce3`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180050ce3`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180050e29`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180050e29`

## string_xrefs

- `0x180050cf9`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x180050fd8`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x180050c29`: `Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool BioTrustlet::ExistsSecureFpRegKey(void)
{
  __int64 DeviceInfoList; // rcx
  const char *v1; // r9
  __int64 v2; // rdx
  bool v3; // di
  unsigned int v4; // esi
  __int64 i; // r9
  __int64 v6; // rdx
  const char *v7; // r9
  __int64 v8; // rdx
  const WCHAR *v9; // rax
  HKEY v10; // r10
  void *v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  LSTATUS ValueW; // ebx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  bool v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+6Ch] [rbp-94h] BYREF
  _QWORD v27[2]; // [rsp+70h] [rbp-90h] BYREF
  char v28; // [rsp+80h] [rbp-80h]
  HKEY *p_hkey; // [rsp+88h] [rbp-78h]
  HKEY *v30; // [rsp+90h] [rbp-70h]
  char v31; // [rsp+98h] [rbp-68h]
  char v32[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+E0h] [rbp-20h]
  _OWORD v36[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v37[32]; // [rsp+120h] [rbp+20h] BYREF
  int *v38; // [rsp+160h] [rbp+60h]
  __int64 v39; // [rsp+168h] [rbp+68h]
  bool *v40; // [rsp+170h] [rbp+70h]
  __int64 v41; // [rsp+178h] [rbp+78h]
  _QWORD *v42; // [rsp+180h] [rbp+80h]
  __int64 v43; // [rsp+188h] [rbp+88h]
  _BYTE v44[512]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v21 = -1;
  v27[1] = &v21;
  v28 = 1;
  v34 = 0;
  v35 = 0;
  memset(v36, 0, sizeof(v36));
  std::wstring::wstring((__int64)v33, (__int64)L"WinBio");
  std::wstring::append(v33, L"\\");
  std::wstring::append(v33, L"Configurations");
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0);
  v21 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v2 = 472;
    goto LABEL_43;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16) )
  {
    v2 = 488;
LABEL_43:
    wil::details::in1diag3::Log_GetLastError(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
      v1);
    std::wstring::_Tidy_deallocate(v33);
    if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      DevObjDestroyDeviceInfoList(v21);
    return 0;
  }
  v3 = 0;
  v4 = 0;
  LODWORD(v34) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v21, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i); i = v4 )
  {
    v6 = v4++;
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    p_hkey = &hkey;
    v30 = &hKey;
    v31 = 1;
    LODWORD(v36[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v21, v6, v36) )
    {
      v8 = 524;
LABEL_7:
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
        v7);
      goto LABEL_26;
    }
    hKey = (HKEY)DevObjOpenDevRegKey(v21, v36, 1, 0, 1, 131097);
    if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v8 = 537;
      goto LABEL_7;
    }
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    if ( RegOpenKeyExW(v10, v9, 0, 0x20019u, &hkey) )
    {
      wil::details::in1diag3::Log_Win32(retaddr, v11, v12, v13, phkResult);
    }
    else
    {
      pvData = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"SecureFingerprint", 0x18u, 0, &pvData, &pcbData);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      {
        if ( !v3 )
          v3 = !ValueW && pvData == 1;
        memset_0(v44, 0, sizeof(v44));
        if ( !(unsigned int)DevObjGetDeviceInstanceId(v21, v36, v44, 256, 0) )
        {
          v8 = 571;
          goto LABEL_7;
        }
        if ( !ValueW && pvData == 1 )
        {
          std::wstring::wstring((__int64)v37, (__int64)v44);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
            v15,
            v32,
            v37);
          std::wstring::_Tidy_deallocate(v37);
          if ( (unsigned int)dword_18010F248 > 4 )
          {
            v27[0] = v44;
            v25 = 0;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              (__int64)&dword_18010F248,
              (__int64)&byte_1800F9D0F,
              v16,
              v17,
              (__int64)&v25,
              v27);
          }
        }
      }
      else if ( !ValueW && pvData == 1 )
      {
        v3 = 1;
        if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          RegCloseKey(hkey);
        if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          RegCloseKey(hKey);
        break;
      }
    }
LABEL_26:
    if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  if ( (unsigned int)dword_18010F248 > 4 )
  {
    v27[0] = v4;
    v20 = v3;
    v25 = 0;
    v42 = v27;
    v43 = 8;
    v40 = &v20;
    v41 = 1;
    v38 = &v25;
    v39 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18010F248, byte_1800F9D59);
  }
  std::wstring::_Tidy_deallocate(v33);
  if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList(v21);
  return v3;
}

```

## disassembly

```asm
0x180050bb0  push    rbp
0x180050bb2  push    rbx
0x180050bb3  push    rsi
0x180050bb4  push    rdi
0x180050bb5  push    r15
0x180050bb7  lea     rbp, [rsp-2A0h]
0x180050bbf  sub     rsp, 3A0h
0x180050bc6  mov     rax, cs:__security_cookie
0x180050bcd  xor     rax, rsp
0x180050bd0  mov     [rbp+2C0h+var_30], rax
0x180050bd7  or      r15, 0FFFFFFFFFFFFFFFFh
0x180050bdb  mov     [rsp+3C0h+var_378], r15
0x180050be0  lea     rax, [rsp+3C0h+var_378]
0x180050be5  mov     [rsp+3C0h+var_348], rax
0x180050bea  mov     [rbp+2C0h+var_340], 1
0x180050bee  xorps   xmm0, xmm0
0x180050bf1  movups  [rbp+2C0h+var_2F0], xmm0
0x180050bf5  movups  [rbp+2C0h+var_2E0], xmm0
0x180050bf9  xorps   xmm1, xmm1
0x180050bfc  movups  [rbp+2C0h+var_2D0], xmm1
0x180050c00  movups  [rbp+2C0h+var_2C0], xmm1
0x180050c04  movups  [rbp+2C0h+var_2B0], xmm1
0x180050c08  lea     rdx, aWinbio; "WinBio"
0x180050c0f  lea     rcx, [rbp+2C0h+var_310]
0x180050c13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050c18  nop
0x180050c19  lea     rdx, asc_1800DC1E4; "\\"
0x180050c20  lea     rcx, [rbp+2C0h+var_310]
0x180050c24  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180050c29  lea     rdx, aConfigurations; "Configurations"
0x180050c30  lea     rcx, [rbp+2C0h+var_310]
0x180050c34  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180050c39  mov     [rsp+3C0h+phkResult], 0
0x180050c42  xor     r9d, r9d
0x180050c45  xor     r8d, r8d
0x180050c48  xor     edx, edx
0x180050c4a  xor     ecx, ecx
0x180050c4c  call    cs:__imp_DevObjCreateDeviceInfoList
0x180050c52  mov     rcx, rax
0x180050c55  mov     [rsp+3C0h+var_378], rax
0x180050c5a  dec     rax
0x180050c5d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180050c61  ja      loc_180050FD3
0x180050c67  mov     [rsp+3C0h+pvData], 0
0x180050c70  mov     [rsp+3C0h+phkResult], 0
0x180050c79  lea     r9d, [r15+11h]
0x180050c7d  xor     r8d, r8d
0x180050c80  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180050c87  call    cs:__imp_DevObjGetClassDevs
0x180050c8d  test    eax, eax
0x180050c8f  jnz     short loc_180050C9B
0x180050c91  mov     edx, 1E8h
0x180050c96  jmp     loc_180050FD8
0x180050c9b  xor     dil, dil
0x180050c9e  xor     esi, esi
0x180050ca0  mov     dword ptr [rbp+2C0h+var_2F0], 20h ; ' '
0x180050ca7  xor     r9d, r9d
0x180050caa  jmp     loc_180050EE2
0x180050caf  mov     edx, esi
0x180050cb1  inc     esi
0x180050cb3  mov     [rsp+3C0h+hKey], r15
0x180050cb8  mov     [rsp+3C0h+hkey], r15
0x180050cbd  lea     rax, [rsp+3C0h+hkey]
0x180050cc2  mov     [rbp+2C0h+var_338], rax
0x180050cc6  lea     rax, [rsp+3C0h+hKey]
0x180050ccb  mov     [rbp+2C0h+var_330], rax
0x180050ccf  mov     [rbp+2C0h+var_328], 1
0x180050cd3  mov     dword ptr [rbp+2C0h+var_2D0], 30h ; '0'
0x180050cda  lea     r8, [rbp+2C0h+var_2D0]
0x180050cde  mov     rcx, [rsp+3C0h+var_378]
0x180050ce3  call    cs:__imp_DevObjEnumDeviceInfo
0x180050ce9  test    eax, eax
0x180050ceb  jnz     short loc_180050D0A
0x180050ced  mov     edx, 20Ch; void *
0x180050cf2  mov     rcx, [rbp+2C8h]; this
0x180050cf9  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180050d00  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180050d05  jmp     loc_180050EBF
0x180050d0a  mov     dword ptr [rsp+3C0h+pvData], 20019h
0x180050d12  mov     dword ptr [rsp+3C0h+phkResult], 1
0x180050d1a  xor     r9d, r9d
0x180050d1d  lea     r8d, [r9+1]
0x180050d21  lea     rdx, [rbp+2C0h+var_2D0]
0x180050d25  mov     rcx, [rsp+3C0h+var_378]
0x180050d2a  call    cs:__imp_DevObjOpenDevRegKey
0x180050d30  mov     r10, rax
0x180050d33  mov     [rsp+3C0h+hKey], rax
0x180050d38  cmp     rax, r15
0x180050d3b  jnz     short loc_180050D44
0x180050d3d  mov     edx, 219h
0x180050d42  jmp     short loc_180050CF2
0x180050d44  lea     rcx, [rbp+2C0h+var_310]
0x180050d48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050d4d  mov     rdx, rax; lpSubKey
0x180050d50  lea     rax, [rsp+3C0h+hkey]
0x180050d55  mov     [rsp+3C0h+phkResult], rax; unsigned int
0x180050d5a  mov     r9d, 20019h; samDesired
0x180050d60  xor     r8d, r8d; ulOptions
0x180050d63  mov     rcx, r10; hKey
0x180050d66  call    cs:__imp_RegOpenKeyExW
0x180050d6c  test    eax, eax
0x180050d6e  jz      short loc_180050D81
0x180050d70  mov     rcx, [rbp+2C8h]; this
0x180050d77  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180050d7c  jmp     loc_180050EBF
0x180050d81  mov     [rsp+3C0h+var_370], 0
0x180050d89  mov     [rsp+3C0h+var_354], 4
0x180050d91  lea     rax, [rsp+3C0h+var_354]
0x180050d96  mov     [rsp+3C0h+pcbData], rax; pcbData
0x180050d9b  lea     rax, [rsp+3C0h+var_370]
0x180050da0  mov     [rsp+3C0h+pvData], rax; pvData
0x180050da5  mov     [rsp+3C0h+phkResult], 0; pdwType
0x180050dae  mov     r9d, 18h; dwFlags
0x180050db4  lea     r8, aSecurefingerpr; "SecureFingerprint"
0x180050dbb  xor     edx, edx; lpSubKey
0x180050dbd  mov     rcx, [rsp+3C0h+hkey]; hkey
0x180050dc2  call    cs:__imp_RegGetValueW
0x180050dc8  mov     ebx, eax
0x180050dca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180050dd1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180050dd6  test    al, al
0x180050dd8  jz      loc_180050EB4
0x180050dde  test    dil, dil
0x180050de1  jnz     short loc_180050DF6
0x180050de3  test    ebx, ebx
0x180050de5  jnz     short loc_180050DF3
0x180050de7  cmp     [rsp+3C0h+var_370], 1
0x180050dec  jnz     short loc_180050DF3
0x180050dee  mov     dil, 1
0x180050df1  jmp     short loc_180050DF6
0x180050df3  xor     dil, dil
0x180050df6  xor     edx, edx; Val
0x180050df8  mov     r8d, 200h; Size
0x180050dfe  lea     rcx, [rbp+2C0h+var_230]; void *
0x180050e05  call    memset_0
0x180050e0a  mov     [rsp+3C0h+phkResult], 0
0x180050e13  mov     r9d, 100h
0x180050e19  lea     r8, [rbp+2C0h+var_230]
0x180050e20  lea     rdx, [rbp+2C0h+var_2D0]
0x180050e24  mov     rcx, [rsp+3C0h+var_378]
0x180050e29  call    cs:__imp_DevObjGetDeviceInstanceId
0x180050e2f  test    eax, eax
0x180050e31  jnz     short loc_180050E3D
0x180050e33  mov     edx, 23Bh
0x180050e38  jmp     loc_180050CF2
0x180050e3d  test    ebx, ebx
0x180050e3f  jnz     short loc_180050EBF
0x180050e41  cmp     [rsp+3C0h+var_370], 1
0x180050e46  jnz     short loc_180050EBF
0x180050e48  lea     rdx, [rbp+2C0h+var_230]
0x180050e4f  lea     rcx, [rbp+2C0h+var_2A0]
0x180050e53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050e58  nop
0x180050e59  lea     r8, [rbp+2C0h+var_2A0]
0x180050e5d  lea     rdx, [rbp+2C0h+var_320]
0x180050e61  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x180050e66  nop
0x180050e67  lea     rcx, [rbp+2C0h+var_2A0]
0x180050e6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050e70  mov     eax, cs:dword_18010F248
0x180050e76  cmp     eax, 4
0x180050e79  jbe     short loc_180050EBF
0x180050e7b  lea     rax, [rbp+2C0h+var_230]
0x180050e82  mov     [rsp+3C0h+var_350], rax
0x180050e87  mov     [rsp+3C0h+var_358], ebx
0x180050e8b  lea     rax, [rsp+3C0h+var_350]
0x180050e90  mov     [rsp+3C0h+pvData], rax
0x180050e95  lea     rax, [rsp+3C0h+var_358]
0x180050e9a  mov     [rsp+3C0h+phkResult], rax
0x180050e9f  lea     rdx, byte_1800F9D0F
0x180050ea6  lea     rcx, dword_18010F248
0x180050ead  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180050eb2  jmp     short loc_180050EBF
0x180050eb4  test    ebx, ebx
0x180050eb6  jnz     short loc_180050EBF
0x180050eb8  cmp     [rsp+3C0h+var_370], 1
0x180050ebd  jz      short loc_180050F09
0x180050ebf  mov     rcx, [rsp+3C0h+hkey]; hKey
0x180050ec4  cmp     rcx, r15
0x180050ec7  jz      short loc_180050ECF
0x180050ec9  call    cs:__imp_RegCloseKey
0x180050ecf  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180050ed4  cmp     rcx, r15
0x180050ed7  jz      short loc_180050EDF
0x180050ed9  call    cs:__imp_RegCloseKey
0x180050edf  mov     r9d, esi
0x180050ee2  lea     rax, [rbp+2C0h+var_2F0]
0x180050ee6  mov     [rsp+3C0h+phkResult], rax
0x180050eeb  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180050ef2  xor     edx, edx
0x180050ef4  mov     rcx, [rsp+3C0h+var_378]
0x180050ef9  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180050eff  test    eax, eax
0x180050f01  jnz     loc_180050CAF
0x180050f07  jmp     short loc_180050F2C
0x180050f09  mov     dil, 1
0x180050f0c  mov     rcx, [rsp+3C0h+hkey]; hKey
0x180050f11  cmp     rcx, r15
0x180050f14  jz      short loc_180050F1C
0x180050f16  call    cs:__imp_RegCloseKey
0x180050f1c  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180050f21  cmp     rcx, r15
0x180050f24  jz      short loc_180050F2C
0x180050f26  call    cs:__imp_RegCloseKey
0x180050f2c  mov     eax, cs:dword_18010F248
0x180050f32  cmp     eax, 4
0x180050f35  jbe     short loc_180050FAF
0x180050f37  mov     eax, esi
0x180050f39  mov     [rsp+3C0h+var_350], rax
0x180050f3e  mov     [rsp+3C0h+var_380], dil
0x180050f43  mov     [rsp+3C0h+var_358], 0
0x180050f4b  lea     rax, [rsp+3C0h+var_350]
0x180050f50  mov     [rbp+2C0h+var_240], rax
0x180050f57  mov     [rbp+2C0h+var_238], 8
0x180050f62  lea     rax, [rsp+3C0h+var_380]
0x180050f67  mov     [rbp+2C0h+var_250], rax
0x180050f6b  mov     [rbp+2C0h+var_248], 1
0x180050f73  lea     rax, [rsp+3C0h+var_358]
0x180050f78  mov     [rbp+2C0h+var_260], rax
0x180050f7c  mov     [rbp+2C0h+var_258], 4
0x180050f84  lea     rax, [rbp+2C0h+var_280]
0x180050f88  mov     [rsp+3C0h+pvData], rax
0x180050f8d  mov     dword ptr [rsp+3C0h+phkResult], 5
0x180050f95  xor     r9d, r9d
0x180050f98  xor     r8d, r8d
0x180050f9b  lea     rdx, byte_1800F9D59
0x180050fa2  lea     rcx, dword_18010F248
0x180050fa9  call    _tlgWriteTransfer_EventWriteTransfer
0x180050fae  nop
0x180050faf  lea     rcx, [rbp+2C0h+var_310]
0x180050fb3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050fb8  nop
0x180050fb9  mov     rcx, [rsp+3C0h+var_378]
0x180050fbe  lea     rdx, [rcx-1]
0x180050fc2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180050fc6  ja      short loc_180050FCE
0x180050fc8  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180050fce  mov     al, dil
0x180050fd1  jmp     short loc_18005100D
0x180050fd3  mov     edx, 1D8h; void *
0x180050fd8  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180050fdf  mov     rcx, [rbp+2C8h]; this
0x180050fe6  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180050feb  nop
0x180050fec  lea     rcx, [rbp+2C0h+var_310]
0x180050ff0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050ff5  nop
0x180050ff6  mov     rcx, [rsp+3C0h+var_378]
0x180050ffb  lea     rax, [rcx-1]
0x180050fff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180051003  ja      short loc_18005100B
0x180051005  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18005100b  xor     al, al
0x18005100d  mov     rcx, [rbp+2C0h+var_30]
0x180051014  xor     rcx, rsp; StackCookie
0x180051017  call    __security_check_cookie
0x18005101c  add     rsp, 3A0h
0x180051023  pop     r15
0x180051025  pop     rdi
0x180051026  pop     rsi
0x180051027  pop     rbx
0x180051028  pop     rbp
0x180051029  retn
```
