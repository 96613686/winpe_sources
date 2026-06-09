# IsOneDriveProvider(IStorageProviderInfo *)

- ea: `0x180290d20`
- end: `0x1802910ba`
- name: `?IsOneDriveProvider@@YA_NPEAUIStorageProviderInfo@@@Z`
- size: `922`
- prototype: `bool __fastcall(struct IStorageProviderInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18011323c`
- `0x180114ad0`

## callees

- `0x180008acc`
- `0x1801052f0`
- `0x180107ebc`
- `0x18013d330`
- `0x18013df8c`
- `0x180290d20`
- `0x180296d14`
- `0x180296d50`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180290f85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180290f85`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180290dcc`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180290dcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180291017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180290ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180291017`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180290e07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180290e07`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180290f1a`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180290f1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
bool __fastcall IsOneDriveProvider(struct IStorageProviderInfo *a1)
{
  __int64 v1; // rax
  int v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  bool v5; // zf
  __int64 v6; // rax
  int v7; // eax
  int SyncRootInfoByPath; // eax
  bool v10; // bl
  int v11; // ebx
  int ppv; // [rsp+20h] [rbp-498h]
  int ppva; // [rsp+20h] [rbp-498h]
  void *v14; // [rsp+38h] [rbp-480h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-478h] BYREF
  LPVOID v16; // [rsp+48h] [rbp-470h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-468h] BYREF
  __int64 v18; // [rsp+58h] [rbp-460h] BYREF
  char v19; // [rsp+60h] [rbp-458h]
  int v20; // [rsp+68h] [rbp-450h] BYREF
  _QWORD v21[3]; // [rsp+70h] [rbp-448h] BYREF
  int v22; // [rsp+88h] [rbp-430h]
  WCHAR String1[256]; // [rsp+8Ch] [rbp-42Ch] BYREF
  _BYTE v24[512]; // [rsp+28Ch] [rbp-22Ch] BYREF
  int v25; // [rsp+48Ch] [rbp-2Ch]
  char v26; // [rsp+490h] [rbp-28h]
  int v27; // [rsp+491h] [rbp-27h]
  __int16 v28; // [rsp+495h] [rbp-23h]
  char v29; // [rsp+497h] [rbp-21h]
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v16 = 0;
  v1 = *(_QWORD *)a1;
  p_pv = &v16;
  v18 = 0;
  v19 = 1;
  v2 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64 *))(v1 + 24))(a1, &v18);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"shell\\inc\\SyncRootUtils.h",
      (const char *)(unsigned int)v2,
      ppv);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
  v14 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl'::`2'::impl) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v3 = SHCoCreateInstance(0, &CLSID_SyncRootManager, 0, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v14);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"shell\\inc\\SyncRootUtils.h",
        (const char *)(unsigned int)v3,
        ppva);
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v4 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v14);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"shell\\inc\\SyncRootUtils.h",
        (const char *)(unsigned int)v4,
        ppva);
  }
  pv = 0;
  v5 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix>::GetImpl'::`2'::impl) == 0;
  v6 = *(_QWORD *)v14;
  p_pv = &pv;
  v18 = 0;
  v19 = 1;
  if ( v5 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, LPVOID, _QWORD, __int64 *))(v6 + 136))(v14, v16, 0, &v18);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"shell\\inc\\SyncRootUtils.h",
        (const char *)(unsigned int)v7,
        ppva);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
LABEL_9:
    memset(v21, 0, sizeof(v21));
    v22 = 0;
    memset_0(String1, 0, sizeof(String1));
    memset_0(v24, 0, sizeof(v24));
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v20 = 0;
    SyncRootInfoByPath = CfGetSyncRootInfoByPath(pv, 1, v21, 1064, &v20);
    if ( (int)(SyncRootInfoByPath + 0x80000000) < 0 || SyncRootInfoByPath == -2147024662 )
    {
      v10 = CompareStringOrdinal(String1, 8, L"onedrive", -1, 1) == 2;
      if ( pv )
        CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      if ( v16 )
        CoTaskMemFree(v16);
      return v10;
    }
    else
    {
      if ( pv )
        CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      if ( v16 )
        CoTaskMemFree(v16);
      return 0;
    }
  }
  v11 = (*(__int64 (__fastcall **)(void *, LPVOID, _QWORD, __int64 *))(v6 + 136))(v14, v16, 0, &v18);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
  if ( v11 != -2147023728 )
  {
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"shell\\inc\\SyncRootUtils.h",
        (const char *)(unsigned int)v11,
        ppva);
    goto LABEL_9;
  }
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  if ( v16 )
    CoTaskMemFree(v16);
  return 0;
}

```

## disassembly

```asm
0x180290d20  push    rbx
0x180290d22  sub     rsp, 4B0h
0x180290d29  mov     rax, cs:__security_cookie
0x180290d30  xor     rax, rsp
0x180290d33  mov     [rsp+4B8h+var_18], rax
0x180290d3b  mov     [rsp+4B8h+var_488], 0
0x180290d40  mov     [rsp+4B8h+var_470], 0
0x180290d49  mov     rax, [rcx]
0x180290d4c  lea     rdx, [rsp+4B8h+var_470]
0x180290d51  mov     [rsp+4B8h+var_468], rdx
0x180290d56  mov     [rsp+4B8h+var_460], 0
0x180290d5f  mov     [rsp+4B8h+var_458], 1
0x180290d64  lea     rdx, [rsp+4B8h+var_460]
0x180290d69  mov     rax, [rax+18h]
0x180290d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180290d72  mov     rcx, [rsp+4B8h]; this
0x180290d7a  test    eax, eax
0x180290d7c  js      loc_180291051
0x180290d82  lea     rcx, [rsp+4B8h+var_468]
0x180290d87  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180290d8c  mov     [rsp+4B8h+var_480], 0
0x180290d95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61110674@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674> `wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl(void)'::`2'::impl
0x180290d9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(void)
0x180290da1  lea     rcx, [rsp+4B8h+var_480]
0x180290da6  test    al, al
0x180290da8  jz      short loc_180290DE4
0x180290daa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180290daf  lea     rax, [rsp+4B8h+var_480]
0x180290db4  mov     qword ptr [rsp+4B8h+ppv], rax; int
0x180290db9  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180290dc0  xor     r8d, r8d; pUnkOuter
0x180290dc3  lea     rdx, CLSID_SyncRootManager; pclsid
0x180290dca  xor     ecx, ecx; pszCLSID
0x180290dcc  call    cs:__imp_SHCoCreateInstance
0x180290dd2  mov     rcx, [rsp+4B8h]; this
0x180290dda  test    eax, eax
0x180290ddc  js      loc_180291066
0x180290de2  jmp     short loc_180290E1D
0x180290de4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180290de9  lea     rax, [rsp+4B8h+var_480]
0x180290dee  mov     qword ptr [rsp+4B8h+ppv], rax; int
0x180290df3  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180290dfa  xor     edx, edx; pUnkOuter
0x180290dfc  lea     r8d, [rdx+1]; dwClsContext
0x180290e00  lea     rcx, CLSID_SyncRootManager; rclsid
0x180290e07  call    cs:__imp_CoCreateInstance
0x180290e0d  mov     rcx, [rsp+4B8h]; this
0x180290e15  test    eax, eax
0x180290e17  js      loc_18029107A
0x180290e1d  mov     [rsp+4B8h+pv], 0
0x180290e26  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix> `wil::Feature<__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix>::GetImpl(void)'::`2'::impl
0x180290e2d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirstTabLaunchErrorNotFoundFix>::__private_IsEnabled(void)
0x180290e32  mov     rcx, [rsp+4B8h+var_480]
0x180290e37  lea     rdx, [rsp+4B8h+pv]
0x180290e3c  test    al, al
0x180290e3e  mov     rax, [rcx]
0x180290e41  mov     [rsp+4B8h+var_468], rdx
0x180290e46  mov     [rsp+4B8h+var_460], 0
0x180290e4f  mov     [rsp+4B8h+var_458], 1
0x180290e54  jnz     loc_180290FC4
0x180290e5a  lea     r9, [rsp+4B8h+var_460]
0x180290e5f  xor     r8d, r8d
0x180290e62  mov     rdx, [rsp+4B8h+var_470]
0x180290e67  mov     rax, [rax+88h]
0x180290e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180290e73  mov     rcx, [rsp+4B8h]; this
0x180290e7b  test    eax, eax
0x180290e7d  js      loc_18029108F
0x180290e83  lea     rcx, [rsp+4B8h+var_468]
0x180290e88  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180290e8d  xor     eax, eax
0x180290e8f  mov     [rsp+4B8h+var_448], rax
0x180290e94  mov     [rsp+4B8h+var_440], rax
0x180290e99  mov     [rsp+4B8h+var_438], rax
0x180290ea1  mov     [rsp+4B8h+var_430], eax
0x180290ea8  mov     ebx, 200h
0x180290ead  mov     r8d, ebx; Size
0x180290eb0  xor     edx, edx; Val
0x180290eb2  lea     rcx, [rsp+4B8h+String1]; void *
0x180290eba  call    memset_0
0x180290ebf  mov     r8d, ebx; Size
0x180290ec2  xor     edx, edx; Val
0x180290ec4  lea     rcx, [rsp+4B8h+var_22C]; void *
0x180290ecc  call    memset_0
0x180290ed1  xor     eax, eax
0x180290ed3  mov     [rsp+4B8h+var_2C], eax
0x180290eda  mov     [rsp+4B8h+var_28], al
0x180290ee1  mov     [rsp+4B8h+var_27], eax
0x180290ee8  mov     [rsp+4B8h+var_23], ax
0x180290ef0  mov     [rsp+4B8h+var_21], al
0x180290ef7  mov     [rsp+4B8h+var_450], eax
0x180290efb  lea     rax, [rsp+4B8h+var_450]
0x180290f00  mov     qword ptr [rsp+4B8h+ppv], rax
0x180290f05  mov     r9d, 428h
0x180290f0b  lea     r8, [rsp+4B8h+var_448]
0x180290f10  mov     edx, 1
0x180290f15  mov     rcx, [rsp+4B8h+pv]
0x180290f1a  call    cs:__imp_CfGetSyncRootInfoByPath
0x180290f20  mov     edx, 80000000h
0x180290f25  lea     ecx, [rax+rdx]
0x180290f28  test    edx, ecx
0x180290f2a  jnz     short loc_180290F66
0x180290f2c  cmp     eax, 800700EAh
0x180290f31  jz      short loc_180290F66
0x180290f33  mov     rcx, [rsp+4B8h+pv]; pv
0x180290f38  test    rcx, rcx
0x180290f3b  jz      short loc_180290F44
0x180290f3d  call    cs:__imp_CoTaskMemFree
0x180290f43  nop
0x180290f44  lea     rcx, [rsp+4B8h+var_480]
0x180290f49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180290f4e  nop
0x180290f4f  mov     rcx, [rsp+4B8h+var_470]; pv
0x180290f54  test    rcx, rcx
0x180290f57  jz      short loc_180290F5F
0x180290f59  call    cs:__imp_CoTaskMemFree
0x180290f5f  xor     al, al
0x180290f61  jmp     loc_180291038
0x180290f66  mov     [rsp+4B8h+ppv], 1; bIgnoreCase
0x180290f6e  or      r9d, 0FFFFFFFFh; cchCount2
0x180290f72  lea     r8, aOnedrive; "onedrive"
0x180290f79  lea     edx, [r9+9]; cchCount1
0x180290f7d  lea     rcx, [rsp+4B8h+String1]; lpString1
0x180290f85  call    cs:__imp_CompareStringOrdinal
0x180290f8b  cmp     eax, 2
0x180290f8e  setz    bl
0x180290f91  mov     [rsp+4B8h+var_488], bl
0x180290f95  mov     rcx, [rsp+4B8h+pv]; pv
0x180290f9a  test    rcx, rcx
0x180290f9d  jz      short loc_180290FA6
0x180290f9f  call    cs:__imp_CoTaskMemFree
0x180290fa5  nop
0x180290fa6  lea     rcx, [rsp+4B8h+var_480]
0x180290fab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180290fb0  nop
0x180290fb1  mov     rcx, [rsp+4B8h+var_470]; pv
0x180290fb6  test    rcx, rcx
0x180290fb9  jz      short loc_180290FC2
0x180290fbb  call    cs:__imp_CoTaskMemFree
0x180290fc1  nop
0x180290fc2  jmp     short loc_180291036
0x180290fc4  lea     r9, [rsp+4B8h+var_460]
0x180290fc9  xor     r8d, r8d
0x180290fcc  mov     rdx, [rsp+4B8h+var_470]
0x180290fd1  mov     rax, [rax+88h]
0x180290fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180290fdd  mov     ebx, eax
0x180290fdf  lea     rcx, [rsp+4B8h+var_468]
0x180290fe4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180290fe9  cmp     ebx, 80070490h
0x180290fef  jnz     short loc_180291021
0x180290ff1  mov     rcx, [rsp+4B8h+pv]; pv
0x180290ff6  test    rcx, rcx
0x180290ff9  jz      short loc_180291002
0x180290ffb  call    cs:__imp_CoTaskMemFree
0x180291001  nop
0x180291002  lea     rcx, [rsp+4B8h+var_480]
0x180291007  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029100c  nop
0x18029100d  mov     rcx, [rsp+4B8h+var_470]; pv
0x180291012  test    rcx, rcx
0x180291015  jz      short loc_18029101D
0x180291017  call    cs:__imp_CoTaskMemFree
0x18029101d  xor     al, al
0x18029101f  jmp     short loc_180291038
0x180291021  mov     rcx, [rsp+4B8h]; this
0x180291029  test    ebx, ebx
0x18029102b  js      short loc_1802910A4
0x18029102d  jmp     loc_180290E8D
0x180291032  mov     bl, [rsp+4B8h+var_488]
0x180291036  mov     al, bl
0x180291038  mov     rcx, [rsp+4B8h+var_18]
0x180291040  xor     rcx, rsp; StackCookie
0x180291043  call    __security_check_cookie
0x180291048  add     rsp, 4B0h
0x18029104f  pop     rbx
0x180291050  retn
0x180291051  mov     r9d, eax; char *
0x180291054  lea     r8, aShellIncSyncro; "shell\\inc\\SyncRootUtils.h"
0x18029105b  mov     edx, 2Ah ; '*'; void *
0x180291060  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180291066  mov     r9d, eax; char *
0x180291069  lea     r8, aShellIncSyncro; "shell\\inc\\SyncRootUtils.h"
0x180291070  mov     edx, 2Fh ; '/'; void *
0x180291075  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029107a  mov     r9d, eax; char *
0x18029107d  lea     r8, aShellIncSyncro; "shell\\inc\\SyncRootUtils.h"
0x180291084  mov     edx, 33h ; '3'; void *
0x180291089  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029108f  mov     r9d, eax; char *
0x180291092  lea     r8, aShellIncSyncro; "shell\\inc\\SyncRootUtils.h"
0x180291099  mov     edx, 42h ; 'B'; void *
0x18029109e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802910a4  mov     r9d, ebx; char *
0x1802910a7  lea     r8, aShellIncSyncro; "shell\\inc\\SyncRootUtils.h"
0x1802910ae  mov     edx, 3Eh ; '>'; void *
0x1802910b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
