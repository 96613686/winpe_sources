# CreativeFramework::LockScreenCreativeConfigHelpers::GetLockScreenEnabled(ushort const *,bool *,bool *)

- ea: `0x18001c190`
- end: `0x18001c62b`
- name: `?GetLockScreenEnabled@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEA_N1@Z`
- size: `1179`
- prototype: `__int64 __fastcall(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, const unsigned __int16 *, bool *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035c94`

## callees

- `0x18000a24c`
- `0x18000acf0`
- `0x18000af00`
- `0x18000b700`
- `0x18000c410`
- `0x18001c020`
- `0x18001c07c`
- `0x18001c190`
- `0x18001c634`
- `0x18001c714`
- `0x18003729c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c41a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c590`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c5fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c41a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c590`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c5fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c3a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c45d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c3a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c45d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c4ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c54e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c4ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c259`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c2f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c259`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c2f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5af`

## string_xrefs

- `0x18001c278`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001c2d6`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001c33b`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001c3f5`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001c48d`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001c5df`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::GetLockScreenEnabled(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 *a2,
        bool *a3,
        bool *a4)
{
  int Setting; // eax
  bool v7; // dl
  CreativeFramework::Policy *v8; // rcx
  void *v9; // rbx
  unsigned __int64 v10; // r8
  LPVOID *cotaskmem_string_nothrow; // rax
  void *v12; // rsi
  unsigned __int16 **v14; // rdx
  int CurrentUserSidString; // eax
  unsigned int v16; // ebx
  int v17; // eax
  signed int v18; // esi
  WCHAR *v19; // rcx
  LPCWSTR v20; // r15
  LSTATUS v21; // eax
  bool v22; // sf
  int v23; // eax
  HKEY v24; // rcx
  LSTATUS v25; // eax
  int v26; // r14d
  __int64 v27; // rdx
  LSTATUS ValueW; // eax
  LSTATUS v29; // eax
  int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  int phkResultb; // [rsp+20h] [rbp-49h]
  int phkResultc; // [rsp+20h] [rbp-49h]
  DWORD v34; // [rsp+40h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  LPVOID v36; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-9h] BYREF
  LPCWSTR v39[9]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v41; // [rsp+D8h] [rbp+6Fh] BYREF
  bool *pvData; // [rsp+E0h] [rbp+77h] BYREF
  DWORD pcbData; // [rsp+E8h] [rbp+7Fh] BYREF

  pvData = a3;
  if ( a2 )
    *(_BYTE *)a2 = 0;
  LODWORD(pvData) = 0;
  Setting = CreativeFramework::ContentDeliveryManagerSettings::Details::GetSettingValue<unsigned long,16>(
              (_DWORD)this,
              (_DWORD)a2,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)&pvData);
  if ( Setting >= 0 )
  {
    if ( (_DWORD)pvData )
    {
      if ( a2 )
        *(_BYTE *)a2 = (_DWORD)pvData == 1;
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\ContentDeliveryManagerSettings.h",
      (const char *)(unsigned int)Setting,
      phkResult);
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  if ( !CreativeFramework::Policy::IsContentDeliverySkuPolicyAllowed(v8, v7) )
    return 0;
  v9 = 0;
  v36 = 0;
  if ( this )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)this + v10) );
    cotaskmem_string_nothrow = (LPVOID *)wil::make_cotaskmem_string_nothrow(
                                           (wil *)&pv,
                                           (const unsigned __int16 *)this,
                                           v10);
    v12 = 0;
    if ( &v36 != cotaskmem_string_nothrow )
    {
      v36 = *cotaskmem_string_nothrow;
      v9 = v36;
      *cotaskmem_string_nothrow = 0;
      v12 = v9;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v12 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)0x8007000ELL,
        phkResult);
      return 2147942414LL;
    }
    goto LABEL_23;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v36,
    0);
  CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
                           (CreativeFramework::LockScreenCreativeConfigHelpers *)&v36,
                           v14);
  v16 = CurrentUserSidString;
  if ( CurrentUserSidString >= 0 )
  {
    v9 = v36;
LABEL_23:
    memset(lpSubKey, 0, sizeof(lpSubKey));
    v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            lpSubKey,
            L"%s\\%s",
            v9,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager");
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)(unsigned int)v17,
        phkResult);
      v19 = (WCHAR *)lpSubKey[0];
      if ( !lpSubKey[0] )
      {
LABEL_26:
        if ( v9 )
          CoTaskMemFree(v9);
        return (unsigned int)v18;
      }
LABEL_25:
      CoTaskMemFree(v19);
      goto LABEL_26;
    }
    hKey = 0;
    v20 = lpSubKey[0];
    v21 = RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 9u, &hKey);
    v22 = v21 < 0;
    if ( v21 > 0 )
      v22 = 1;
    if ( v22 )
    {
      memset(v39, 0, 24);
      v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              v39,
              L"%s\\%s",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative",
              v9);
      v18 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13C,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
          (const char *)(unsigned int)v23,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v39);
        v24 = hKey;
        if ( !hKey )
        {
LABEL_35:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
          goto LABEL_26;
        }
LABEL_34:
        RegCloseKey(v24);
        goto LABEL_35;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v25 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v39[0], 0, 9u, &hKey);
      v18 = v25;
      if ( v25 > 0 )
        v18 = (unsigned __int16)v25 | 0x80070000;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v39);
      v26 = 0;
      if ( v18 < 0 )
      {
        v27 = 319;
        goto LABEL_40;
      }
    }
    else
    {
      v26 = 1;
    }
    LODWORD(pvData) = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, L"RotatingLockScreenEnabled", 0x10u, 0, &pvData, &pcbData);
    v18 = ValueW;
    if ( ValueW > 0 )
      v18 = (unsigned __int16)ValueW | 0x80070000;
    if ( v18 == -2147024894 )
    {
      LODWORD(pvData) = v26;
    }
    else if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)(unsigned int)v18,
        phkResultc);
      if ( hKey )
        RegCloseKey(hKey);
      if ( !v20 )
        goto LABEL_26;
      v19 = (WCHAR *)v20;
      goto LABEL_25;
    }
    v41 = 0;
    v34 = 4;
    v29 = RegGetValueW(hKey, 0, L"RotatingLockScreenOverlayEnabled", 0x10u, 0, &v41, &v34);
    v18 = v29;
    if ( v29 > 0 )
      v18 = (unsigned __int16)v29 | 0x80070000;
    if ( v18 == -2147024894 )
    {
      v41 = v26;
    }
    else if ( v18 < 0 )
    {
      v27 = 344;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)(unsigned int)v18,
        phkResultb);
      v24 = hKey;
      if ( !hKey )
        goto LABEL_35;
      goto LABEL_34;
    }
    if ( a2 )
      *(_BYTE *)a2 = (_DWORD)pvData != 0;
    if ( hKey )
      RegCloseKey(hKey);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( v9 )
      CoTaskMemFree(v9);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x129,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
    (const char *)(unsigned int)CurrentUserSidString,
    phkResult);
  if ( v36 )
    CoTaskMemFree(v36);
  return v16;
}

```

## disassembly

```asm
0x18001c190  mov     [rsp-8+arg_10], r8
0x18001c195  push    rbp
0x18001c196  push    rbx
0x18001c197  push    rsi
0x18001c198  push    rdi
0x18001c199  push    r12
0x18001c19b  push    r14
0x18001c19d  push    r15
0x18001c19f  lea     rbp, [rsp-27h]
0x18001c1a4  sub     rsp, 90h
0x18001c1ab  mov     rdi, rdx
0x18001c1ae  mov     rsi, rcx
0x18001c1b1  test    rdx, rdx
0x18001c1b4  jz      short loc_18001C1B9
0x18001c1b6  mov     byte ptr [rdx], 0
0x18001c1b9  xor     r12d, r12d
0x18001c1bc  mov     dword ptr [rbp+57h+arg_10], r12d
0x18001c1c0  lea     rax, [rbp+57h+arg_10]
0x18001c1c4  mov     [rsp+0C0h+phkResult], rax; int
0x18001c1c9  call    ??$GetSettingValue@K$0BA@@Details@ContentDeliveryManagerSettings@CreativeFramework@@YAJPEAUHKEY__@@PEBG1_NPEAKK@Z; CreativeFramework::ContentDeliveryManagerSettings::Details::GetSettingValue<ulong,16>(HKEY__ *,ushort const *,ushort const *,bool,ulong *,ulong)
0x18001c1ce  test    eax, eax
0x18001c1d0  jns     loc_18001C294
0x18001c1d6  mov     rcx, [rbp+5Fh]; this
0x18001c1da  mov     r9d, eax; char *
0x18001c1dd  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Conte"...
0x18001c1e4  mov     edx, 1B3h; void *
0x18001c1e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c1ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18001c1f5  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18001c1fa  call    ?IsContentDeliverySkuPolicyAllowed@Policy@CreativeFramework@@YA_N_N@Z; CreativeFramework::Policy::IsContentDeliverySkuPolicyAllowed(bool)
0x18001c1ff  test    al, al
0x18001c201  jz      loc_18001C5BB
0x18001c207  mov     rbx, r12
0x18001c20a  mov     [rbp+57h+var_70], rbx
0x18001c20e  test    rsi, rsi
0x18001c211  jz      loc_18001C2B5
0x18001c217  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001c21e  xchg    ax, ax
0x18001c220  inc     r8; unsigned __int64
0x18001c223  cmp     word ptr [rsi+r8*2], 0
0x18001c229  jnz     short loc_18001C220
0x18001c22b  mov     rdx, rsi; unsigned __int16 *
0x18001c22e  lea     rcx, [rbp+57h+pv]; this
0x18001c232  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001c237  mov     rsi, r12
0x18001c23a  lea     rcx, [rbp+57h+var_70]
0x18001c23e  cmp     rcx, rax
0x18001c241  jz      short loc_18001C250
0x18001c243  mov     rbx, [rax]
0x18001c246  mov     [rbp+57h+var_70], rbx
0x18001c24a  mov     [rax], r12
0x18001c24d  mov     rsi, rbx
0x18001c250  mov     rcx, [rbp+57h+pv]; pv
0x18001c254  test    rcx, rcx
0x18001c257  jz      short loc_18001C265
0x18001c259  call    cs:__imp_CoTaskMemFree
0x18001c260  nop     dword ptr [rax+rax+00h]
0x18001c265  test    rsi, rsi
0x18001c268  jnz     loc_18001C308
0x18001c26e  mov     rcx, [rbp+5Fh]; this
0x18001c272  mov     r9d, 8007000Eh; char *
0x18001c278  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001c27f  mov     edx, 124h; void *
0x18001c284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c289  nop
0x18001c28a  mov     eax, 8007000Eh
0x18001c28f  jmp     loc_18001C5BD
0x18001c294  mov     eax, dword ptr [rbp+57h+arg_10]
0x18001c297  test    eax, eax
0x18001c299  jz      loc_18001C1EE
0x18001c29f  cmp     eax, 1
0x18001c2a2  setz    al
0x18001c2a5  test    rdi, rdi
0x18001c2a8  jz      loc_18001C5BB
0x18001c2ae  mov     [rdi], al
0x18001c2b0  jmp     loc_18001C5BB
0x18001c2b5  xor     edx, edx
0x18001c2b7  lea     rcx, [rbp+57h+var_70]
0x18001c2bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001c2c0  lea     rcx, [rbp+57h+var_70]; this
0x18001c2c4  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x18001c2c9  mov     ebx, eax
0x18001c2cb  test    eax, eax
0x18001c2cd  jns     short loc_18001C304
0x18001c2cf  mov     rcx, [rbp+5Fh]; this
0x18001c2d3  mov     r9d, eax; char *
0x18001c2d6  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001c2dd  mov     edx, 129h; void *
0x18001c2e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2e7  nop
0x18001c2e8  mov     rcx, [rbp+57h+var_70]; pv
0x18001c2ec  test    rcx, rcx
0x18001c2ef  jz      short loc_18001C2FD
0x18001c2f1  call    cs:__imp_CoTaskMemFree
0x18001c2f8  nop     dword ptr [rax+rax+00h]
0x18001c2fd  mov     eax, ebx
0x18001c2ff  jmp     loc_18001C5BD
0x18001c304  mov     rbx, [rbp+57h+var_70]
0x18001c308  mov     [rbp+57h+lpSubKey], r12
0x18001c30c  mov     [rbp+57h+var_58], r12
0x18001c310  mov     [rbp+57h+var_50], r12
0x18001c314  lea     r9, ?c_contentDeliveryManagerKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c31b  mov     r8, rbx
0x18001c31e  lea     rdx, aSS_1; "%s\\%s"
0x18001c325  lea     rcx, [rbp+57h+lpSubKey]
0x18001c329  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001c32e  mov     esi, eax
0x18001c330  test    eax, eax
0x18001c332  jns     short loc_18001C37E
0x18001c334  mov     rcx, [rbp+5Fh]; this
0x18001c338  mov     r9d, eax; char *
0x18001c33b  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001c342  mov     edx, 12Dh; void *
0x18001c347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c34c  nop
0x18001c34d  mov     rcx, [rbp+57h+lpSubKey]; pv
0x18001c351  test    rcx, rcx
0x18001c354  jz      short loc_18001C363
0x18001c356  call    cs:__imp_CoTaskMemFree
0x18001c35d  nop     dword ptr [rax+rax+00h]
0x18001c362  nop
0x18001c363  test    rbx, rbx
0x18001c366  jz      short loc_18001C377
0x18001c368  mov     rcx, rbx; pv
0x18001c36b  call    cs:__imp_CoTaskMemFree
0x18001c372  nop     dword ptr [rax+rax+00h]
0x18001c377  mov     eax, esi
0x18001c379  jmp     loc_18001C5BD
0x18001c37e  mov     [rbp+57h+hKey], r12
0x18001c382  lea     rax, [rbp+57h+hKey]
0x18001c386  mov     [rsp+0C0h+phkResult], rax; int
0x18001c38b  mov     r9d, 9; samDesired
0x18001c391  xor     r8d, r8d; ulOptions
0x18001c394  mov     r15, [rbp+57h+lpSubKey]
0x18001c398  mov     rdx, r15; lpSubKey
0x18001c39b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001c3a2  call    cs:__imp_RegOpenKeyExW
0x18001c3a9  nop     dword ptr [rax+rax+00h]
0x18001c3ae  test    eax, eax
0x18001c3b0  jle     short loc_18001C3BC
0x18001c3b2  movzx   eax, ax
0x18001c3b5  or      eax, 80070000h
0x18001c3ba  test    eax, eax
0x18001c3bc  jns     loc_18001C4B3
0x18001c3c2  mov     [rbp+57h+var_48], r12
0x18001c3c6  mov     [rbp+57h+var_40], r12
0x18001c3ca  mov     [rbp+57h+var_38], r12
0x18001c3ce  mov     r9, rbx
0x18001c3d1  lea     r8, ?c_logonUICreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c3d8  lea     rdx, aSS_1; "%s\\%s"
0x18001c3df  lea     rcx, [rbp+57h+var_48]
0x18001c3e3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001c3e8  mov     esi, eax
0x18001c3ea  test    eax, eax
0x18001c3ec  jns     short loc_18001C435
0x18001c3ee  mov     rcx, [rbp+5Fh]; this
0x18001c3f2  mov     r9d, eax; char *
0x18001c3f5  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001c3fc  mov     edx, 13Ch; void *
0x18001c401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c406  nop
0x18001c407  lea     rcx, [rbp+57h+var_48]
0x18001c40b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001c410  nop
0x18001c411  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c415  test    rcx, rcx
0x18001c418  jz      short loc_18001C427
0x18001c41a  call    cs:__imp_RegCloseKey
0x18001c421  nop     dword ptr [rax+rax+00h]
0x18001c426  nop
0x18001c427  lea     rcx, [rbp+57h+lpSubKey]
0x18001c42b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001c430  jmp     loc_18001C363
0x18001c435  xor     edx, edx
0x18001c437  lea     rcx, [rbp+57h+hKey]
0x18001c43b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001c440  lea     rax, [rbp+57h+hKey]
0x18001c444  mov     [rsp+0C0h+phkResult], rax; int
0x18001c449  mov     r9d, 9; samDesired
0x18001c44f  xor     r8d, r8d; ulOptions
0x18001c452  mov     rdx, [rbp+57h+var_48]; lpSubKey
0x18001c456  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c45d  call    cs:__imp_RegOpenKeyExW
0x18001c464  nop     dword ptr [rax+rax+00h]
0x18001c469  mov     esi, eax
0x18001c46b  test    eax, eax
0x18001c46d  jle     short loc_18001C478
0x18001c46f  movzx   esi, ax
0x18001c472  or      esi, 80070000h
0x18001c478  lea     rcx, [rbp+57h+var_48]
0x18001c47c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001c481  mov     r14d, r12d
0x18001c484  test    esi, esi
0x18001c486  jns     short loc_18001C4B9
0x18001c488  mov     edx, 13Fh; void *
0x18001c48d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001c494  mov     r9d, esi; char *
0x18001c497  mov     rcx, [rbp+5Fh]; this
0x18001c49b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c4a0  nop
0x18001c4a1  mov     rcx, [rbp+57h+hKey]
0x18001c4a5  test    rcx, rcx
0x18001c4a8  jz      loc_18001C427
0x18001c4ae  jmp     loc_18001C41A
0x18001c4b3  mov     r14d, 1
0x18001c4b9  mov     dword ptr [rbp+57h+arg_10], r12d
0x18001c4bd  mov     [rbp+57h+arg_18], 4
0x18001c4c4  lea     rax, [rbp+57h+arg_18]
0x18001c4c8  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001c4cd  lea     rax, [rbp+57h+arg_10]
0x18001c4d1  mov     [rsp+0C0h+pvData], rax; pvData
0x18001c4d6  mov     [rsp+0C0h+phkResult], r12; int
0x18001c4db  mov     r9d, 10h; dwFlags
0x18001c4e1  lea     r8, ?c_lockScreenEnabledName@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "RotatingLockScreenEnabled"
0x18001c4e8  xor     edx, edx; lpSubKey
0x18001c4ea  mov     rcx, [rbp+57h+hKey]; hkey
0x18001c4ee  call    cs:__imp_RegGetValueW
0x18001c4f5  nop     dword ptr [rax+rax+00h]
0x18001c4fa  mov     esi, eax
0x18001c4fc  test    eax, eax
0x18001c4fe  jle     short loc_18001C509
0x18001c500  movzx   esi, ax
0x18001c503  or      esi, 80070000h
0x18001c509  cmp     esi, 80070002h
0x18001c50f  jnz     loc_18001C5D0
0x18001c515  mov     dword ptr [rbp+57h+arg_10], r14d
0x18001c519  mov     [rbp+57h+arg_8], r12d
0x18001c51d  mov     [rbp+57h+var_80], 4
0x18001c524  lea     rax, [rbp+57h+var_80]
0x18001c528  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001c52d  lea     rax, [rbp+57h+arg_8]
0x18001c531  mov     [rsp+0C0h+pvData], rax; pvData
0x18001c536  mov     [rsp+0C0h+phkResult], r12; pdwType
0x18001c53b  mov     r9d, 10h; dwFlags
0x18001c541  lea     r8, ?c_lockScreenOverlayEnabledName@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "RotatingLockScreenOverlayEnabled"
0x18001c548  xor     edx, edx; lpSubKey
0x18001c54a  mov     rcx, [rbp+57h+hKey]; hkey
0x18001c54e  call    cs:__imp_RegGetValueW
0x18001c555  nop     dword ptr [rax+rax+00h]
0x18001c55a  mov     esi, eax
0x18001c55c  test    eax, eax
0x18001c55e  jle     short loc_18001C569
0x18001c560  movzx   esi, ax
0x18001c563  or      esi, 80070000h
0x18001c569  cmp     esi, 80070002h
0x18001c56f  jnz     loc_18001C618
0x18001c575  mov     [rbp+57h+arg_8], r14d
0x18001c579  cmp     dword ptr [rbp+57h+arg_10], 0
0x18001c57d  setnz   al
0x18001c580  test    rdi, rdi
0x18001c583  jz      short loc_18001C587
0x18001c585  mov     [rdi], al
0x18001c587  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c58b  test    rcx, rcx
0x18001c58e  jz      short loc_18001C59D
0x18001c590  call    cs:__imp_RegCloseKey
0x18001c597  nop     dword ptr [rax+rax+00h]
0x18001c59c  nop
0x18001c59d  lea     rcx, [rbp+57h+lpSubKey]
0x18001c5a1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001c5a6  nop
0x18001c5a7  test    rbx, rbx
0x18001c5aa  jz      short loc_18001C5BB
0x18001c5ac  mov     rcx, rbx; pv
0x18001c5af  call    cs:__imp_CoTaskMemFree
0x18001c5b6  nop     dword ptr [rax+rax+00h]
0x18001c5bb  xor     eax, eax
0x18001c5bd  add     rsp, 90h
0x18001c5c4  pop     r15
0x18001c5c6  pop     r14
0x18001c5c8  pop     r12
0x18001c5ca  pop     rdi
0x18001c5cb  pop     rsi
0x18001c5cc  pop     rbx
0x18001c5cd  pop     rbp
0x18001c5ce  retn
0x18001c5d0  test    esi, esi
0x18001c5d2  jns     loc_18001C519
0x18001c5d8  mov     rcx, [rbp+5Fh]; this
0x18001c5dc  mov     r9d, esi; char *
0x18001c5df  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001c5e6  mov     edx, 14Bh; void *
0x18001c5eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5f0  nop
0x18001c5f1  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c5f5  test    rcx, rcx
0x18001c5f8  jz      short loc_18001C607
0x18001c5fa  call    cs:__imp_RegCloseKey
0x18001c601  nop     dword ptr [rax+rax+00h]
0x18001c606  nop
0x18001c607  test    r15, r15
0x18001c60a  jz      loc_18001C363
0x18001c610  mov     rcx, r15
0x18001c613  jmp     loc_18001C356
0x18001c618  test    esi, esi
0x18001c61a  jns     loc_18001C579
0x18001c620  mov     edx, 158h
0x18001c625  jmp     loc_18001C48D
```
