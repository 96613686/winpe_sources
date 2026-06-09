# CLockScreen::GetHistoryEntryAt(uint,IShellItem * *,IShellItem * *,ushort * *)

- ea: `0x180037e20`
- end: `0x18003832f`
- name: `?GetHistoryEntryAt@CLockScreen@@UEAAJIPEAPEAUIShellItem@@0PEAPEAG@Z`
- size: `1295`
- prototype: `int(CLockScreen *__hidden this, unsigned int, struct IShellItem **, struct IShellItem **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a490`
- `0x18000af00`
- `0x18000b3b0`
- `0x18000b700`
- `0x18000c1b8`
- `0x18000c410`
- `0x180026440`
- `0x1800343ec`
- `0x180035c94`
- `0x18003729c`
- `0x180037e20`
- `0x180038488`
- `0x18003c324`
- `0x18003ff34`
- `0x180042a08`
- `0x1800464f8`
- `0x18004ab6c`
- `0x18004ca2c`
- `0x1800b511c`
- `0x1800b7ac0`
- `0x1800b8804`
- `0x1800ed010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180037edf`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003801e`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800380f1`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800381d7`
- `SHELL32!SHCreateItemFromParsingName` at `0x180038276`
- `SHELL32!SHCreateItemFromParsingName` at `0x180037edf`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003801e`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800380f1`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800381d7`
- `SHELL32!SHCreateItemFromParsingName` at `0x180038276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382fa`

## string_xrefs

- `0x180038238`: `LandscapeAssetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLockScreen::GetHistoryEntryAt(
        CLockScreen *this,
        int a2,
        struct IShellItem **a3,
        struct IShellItem **a4,
        const WCHAR *ppv)
{
  CLockScreen *v8; // r12
  unsigned __int16 **v9; // r15
  bool IsSpecificLockScreenLogonImageForced; // al
  bool v11; // dl
  bool v12; // r13
  HRESULT LockScreenHistoryOrderInternal; // edi
  const WCHAR *v14; // rbx
  int Entry; // ebx
  HRESULT v16; // eax
  struct IShellItem *v17; // rcx
  int v18; // eax
  const WCHAR *v19; // rbx
  HRESULT v20; // eax
  struct IShellItem *v21; // rcx
  char v22; // r12
  CLockScreenHistory::CLockScreenHistoryEntry *v23; // rbx
  unsigned int v24; // edx
  void **v25; // rbx
  unsigned __int16 **v26; // r12
  unsigned int v27; // edx
  CLockScreenHistory::CLockScreenHistoryEntry *v28; // rbx
  int v29; // r9d
  struct IShellItem *v30; // rcx
  int v32; // [rsp+20h] [rbp-38h]
  int v33; // [rsp+20h] [rbp-38h]
  unsigned int *v34; // [rsp+28h] [rbp-30h]
  CLockScreenHistory::CLockScreenHistoryEntry *v35; // [rsp+30h] [rbp-28h] BYREF
  PCWSTR v36; // [rsp+38h] [rbp-20h] BYREF
  __int64 v37; // [rsp+40h] [rbp-18h]
  __int64 v38; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  void *v42; // [rsp+B0h] [rbp+58h] BYREF
  PCWSTR pszPath; // [rsp+B8h] [rbp+60h] BYREF

  v8 = this;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = (unsigned __int16 **)ppv;
  if ( ppv )
    *(_QWORD *)ppv = 0;
  pszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPath,
    0);
  IsSpecificLockScreenLogonImageForced = CLockScreen::_s_IsSpecificLockScreenLogonImageForced((unsigned __int16 **)&pszPath);
  v12 = IsSpecificLockScreenLogonImageForced;
  if ( a2 )
    goto LABEL_45;
  LockScreenHistoryOrderInternal = 0;
  if ( !IsSpecificLockScreenLogonImageForced )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
    if ( !CLockScreen::_s_IsSpotlightEnabled(0) )
    {
      if ( CLockScreen::_s_IsSpotlight() )
      {
        if ( a3 )
        {
          v36 = 0;
          v37 = 0;
          v38 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
          v37 = -1;
          v38 = -1;
          LockScreenHistoryOrderInternal = SHRegAllocData(
                                             HKEY_CURRENT_USER,
                                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\\Creative",
                                             L"LandscapeAssetPath",
                                             v29,
                                             (void **)&v36,
                                             v34);
          if ( LockScreenHistoryOrderInternal >= 0 )
          {
            ppv = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
            LockScreenHistoryOrderInternal = SHCreateItemFromParsingName(
                                               v36,
                                               0,
                                               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                               (void **)&ppv);
            if ( LockScreenHistoryOrderInternal >= 0 )
            {
              v30 = (struct IShellItem *)ppv;
              if ( ppv )
              {
                (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)ppv + 8LL))(ppv);
                v30 = (struct IShellItem *)ppv;
              }
              *a3 = v30;
              LockScreenHistoryOrderInternal = 0;
              if ( a4 )
              {
                ppv = 0;
                *a4 = v30;
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
        }
        else
        {
          LockScreenHistoryOrderInternal = -2147024809;
        }
        goto LABEL_71;
      }
      goto LABEL_45;
    }
    if ( !a3 )
    {
      LockScreenHistoryOrderInternal = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F5,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)0x80070057LL,
        v32);
      goto LABEL_71;
    }
    v36 = 0;
    v37 = 0;
    v38 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
    v37 = -1;
    v38 = -1;
    v18 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(0, 0, (DWORD *)&v36, 0, 0);
    if ( v18 >= 0 )
    {
      v19 = v36;
      if ( v36 && *v36 )
      {
        v42 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        v20 = SHCreateItemFromParsingName(v19, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v42);
        Entry = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9FA,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)v20,
            v33);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
LABEL_27:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
          goto LABEL_72;
        }
        v21 = (struct IShellItem *)v42;
        if ( v42 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 8LL))(v42);
          v21 = (struct IShellItem *)v42;
        }
        *a3 = v21;
        if ( a4 )
        {
          v42 = 0;
          *a4 = v21;
        }
        v22 = 1;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        goto LABEL_43;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F7,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v18,
        v33);
    }
    ppv = 0;
    Entry = CLockScreenHistory::_GetEntry(
              (CLockScreen *)((char *)v8 + 88),
              0x5Au,
              (struct CLockScreenHistory::CLockScreenHistoryEntry **)&ppv);
    if ( Entry < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA06,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)Entry,
        v33);
      goto LABEL_27;
    }
    v22 = 0;
    v23 = (CLockScreenHistory::CLockScreenHistoryEntry *)ppv;
    LockScreenHistoryOrderInternal = SHCreateItemFromParsingName(
                                       ppv + 289,
                                       0,
                                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                       (void **)a3);
    if ( LockScreenHistoryOrderInternal >= 0 )
    {
      if ( a4 )
        CLockScreenHistory::CLockScreenHistoryEntry::GetOriginalFile(v23, a4);
      if ( v9 )
        CLockScreenHistory::CLockScreenHistoryEntry::GetDetails(v23, v9);
      v22 = 1;
    }
    if ( v23 )
      CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(v23, v24);
LABEL_43:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
    if ( v22 )
      goto LABEL_71;
    v8 = this;
LABEL_45:
    CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(
      (CLockScreenHistory::CSynchronizedOperation *)&v36,
      v11);
    v25 = (void **)((char *)v8 + 88);
    LockScreenHistoryOrderInternal = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreen *)((char *)v8 + 88));
    if ( LockScreenHistoryOrderInternal < 0 )
      goto LABEL_70;
    ppv = 0;
    LockScreenHistoryOrderInternal = CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(
                                       *v25,
                                       !v12,
                                       (unsigned __int16 **)&ppv);
    if ( LockScreenHistoryOrderInternal < 0 )
      goto LABEL_70;
    v35 = 0;
    v26 = (unsigned __int16 **)ppv;
    LockScreenHistoryOrderInternal = CLockScreenHistory::_GetEntry((CLockScreenHistory *)v25, ppv[a2], &v35);
    if ( LockScreenHistoryOrderInternal < 0 )
    {
LABEL_69:
      CoTaskMemFree(v26);
LABEL_70:
      CLockScreenHistory::CSynchronizedOperation::~CSynchronizedOperation((CLockScreenHistory::CSynchronizedOperation *)&v36);
      goto LABEL_71;
    }
    v28 = v35;
    if ( a3 )
    {
      LockScreenHistoryOrderInternal = SHCreateItemFromParsingName(
                                         (PCWSTR)v35 + 289,
                                         0,
                                         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                         (void **)a3);
      if ( LockScreenHistoryOrderInternal < 0 )
      {
LABEL_67:
        if ( v28 )
          CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(v28, v27);
        goto LABEL_69;
      }
    }
    else
    {
      LockScreenHistoryOrderInternal = 0;
    }
    if ( a4 )
      CLockScreenHistory::CLockScreenHistoryEntry::GetOriginalFile(v28, a4);
    if ( v9 )
      CLockScreenHistory::CLockScreenHistoryEntry::GetDetails(v28, v9);
    goto LABEL_67;
  }
  v14 = pszPath;
  if ( pszPath )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v16 = SHCreateItemFromParsingName(v14, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&ppv);
    Entry = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9EB,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v16,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      goto LABEL_72;
    }
    v17 = (struct IShellItem *)ppv;
    if ( ppv )
    {
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)ppv + 8LL))(ppv);
      v17 = (struct IShellItem *)ppv;
    }
    *a3 = v17;
    if ( a4 )
    {
      ppv = 0;
      *a4 = v17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_71:
    Entry = LockScreenHistoryOrderInternal;
    goto LABEL_72;
  }
  Entry = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9E9,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)0x80004003LL,
    v32);
LABEL_72:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x180037e20  mov     [rsp-40h+arg_8], edx
0x180037e24  mov     [rsp-40h+arg_0], rcx
0x180037e29  push    rbp
0x180037e2a  push    rbx
0x180037e2b  push    rsi
0x180037e2c  push    rdi
0x180037e2d  push    r12
0x180037e2f  push    r13
0x180037e31  push    r14
0x180037e33  push    r15
0x180037e35  mov     rbp, rsp
0x180037e38  sub     rsp, 58h
0x180037e3c  mov     rsi, r9
0x180037e3f  mov     r14, r8
0x180037e42  mov     ebx, edx
0x180037e44  mov     r12, rcx
0x180037e47  xor     edi, edi
0x180037e49  test    r8, r8
0x180037e4c  jz      short loc_180037E51
0x180037e4e  mov     [r8], rdi
0x180037e51  test    rsi, rsi
0x180037e54  jz      short loc_180037E59
0x180037e56  mov     [r9], rdi
0x180037e59  mov     r15, [rbp+ppv]
0x180037e5d  test    r15, r15
0x180037e60  jz      short loc_180037E65
0x180037e62  mov     [r15], rdi
0x180037e65  mov     [rbp+pszPath], rdi
0x180037e69  xor     edx, edx
0x180037e6b  lea     rcx, [rbp+pszPath]
0x180037e6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037e74  lea     rcx, [rbp+pszPath]; unsigned __int16 **
0x180037e78  call    ?_s_IsSpecificLockScreenLogonImageForced@CLockScreen@@KA_NPEAPEAG@Z; CLockScreen::_s_IsSpecificLockScreenLogonImageForced(ushort * *)
0x180037e7d  mov     r13b, al
0x180037e80  test    ebx, ebx
0x180037e82  jnz     loc_18003814A
0x180037e88  xor     ebx, ebx
0x180037e8a  mov     edi, ebx
0x180037e8c  test    al, al
0x180037e8e  jz      loc_180037F4D
0x180037e94  mov     rbx, [rbp+pszPath]
0x180037e98  xor     r15d, r15d
0x180037e9b  test    rbx, rbx
0x180037e9e  jnz     short loc_180037EC2
0x180037ea0  mov     rcx, [rbp+40h]; this
0x180037ea4  mov     ebx, 80004003h
0x180037ea9  mov     r9d, ebx; char *
0x180037eac  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180037eb3  mov     edx, 9E9h; void *
0x180037eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037ebd  jmp     loc_180038312
0x180037ec2  mov     [rbp+ppv], r15
0x180037ec6  lea     rcx, [rbp+ppv]
0x180037eca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037ecf  lea     r9, [rbp+ppv]; ppv
0x180037ed3  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180037eda  xor     edx, edx; pbc
0x180037edc  mov     rcx, rbx; pszPath
0x180037edf  call    cs:__imp_SHCreateItemFromParsingName
0x180037ee6  nop     dword ptr [rax+rax+00h]
0x180037eeb  mov     ebx, eax
0x180037eed  test    eax, eax
0x180037eef  jns     short loc_180037F17
0x180037ef1  mov     rcx, [rbp+40h]; this
0x180037ef5  mov     r9d, eax; char *
0x180037ef8  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180037eff  mov     edx, 9EBh; void *
0x180037f04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f09  lea     rcx, [rbp+ppv]
0x180037f0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037f12  jmp     loc_180038312
0x180037f17  mov     rcx, [rbp+ppv]
0x180037f1b  test    rcx, rcx
0x180037f1e  jz      short loc_180037F30
0x180037f20  mov     rax, [rcx]
0x180037f23  mov     rax, [rax+8]
0x180037f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f2c  mov     rcx, [rbp+ppv]
0x180037f30  mov     [r14], rcx
0x180037f33  test    rsi, rsi
0x180037f36  jz      short loc_180037F3F
0x180037f38  mov     [rbp+ppv], r15
0x180037f3c  mov     [rsi], rcx
0x180037f3f  lea     rcx, [rbp+ppv]
0x180037f43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037f48  jmp     loc_180038310
0x180037f4d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x180037f54  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180037f59  xor     ecx, ecx; this
0x180037f5b  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x180037f60  test    al, al
0x180037f62  jz      loc_1800381F2
0x180037f68  test    r14, r14
0x180037f6b  jnz     short loc_180037F8F
0x180037f6d  mov     rcx, [rbp+40h]; this
0x180037f71  mov     edi, 80070057h
0x180037f76  mov     r9d, edi; char *
0x180037f79  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180037f80  mov     edx, 9F5h; void *
0x180037f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f8a  jmp     loc_180038310
0x180037f8f  mov     [rbp+var_20], rbx
0x180037f93  mov     [rbp+var_18], rbx
0x180037f97  mov     [rbp+var_10], rbx
0x180037f9b  lea     rcx, [rbp+var_20]
0x180037f9f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037fa4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037fa8  mov     [rbp+var_18], rax
0x180037fac  mov     [rbp+var_10], rax
0x180037fb0  mov     [rsp+58h+var_38], rbx; int
0x180037fb5  xor     r9d, r9d; unsigned __int16 **
0x180037fb8  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180037fbc  xor     edx, edx; unsigned __int16 *
0x180037fbe  xor     ecx, ecx; this
0x180037fc0  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x180037fc5  mov     rcx, [rbp+40h]; this
0x180037fc9  test    eax, eax
0x180037fcb  jns     short loc_180037FE6
0x180037fcd  mov     r9d, eax; char *
0x180037fd0  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180037fd7  mov     edx, 9F7h; void *
0x180037fdc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037fe1  jmp     loc_18003809B
0x180037fe6  mov     rbx, [rbp+var_20]
0x180037fea  xor     eax, eax
0x180037fec  test    rbx, rbx
0x180037fef  jz      loc_180038099
0x180037ff5  cmp     [rbx], ax
0x180037ff8  jz      loc_180038099
0x180037ffe  xor     r12d, r12d
0x180038001  mov     [rbp+arg_10], r12
0x180038005  lea     rcx, [rbp+arg_10]
0x180038009  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003800e  lea     r9, [rbp+arg_10]; ppv
0x180038012  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180038019  xor     edx, edx; pbc
0x18003801b  mov     rcx, rbx; pszPath
0x18003801e  call    cs:__imp_SHCreateItemFromParsingName
0x180038025  nop     dword ptr [rax+rax+00h]
0x18003802a  mov     ebx, eax
0x18003802c  test    eax, eax
0x18003802e  jns     short loc_180038060
0x180038030  mov     rcx, [rbp+40h]; this
0x180038034  mov     r9d, eax; char *
0x180038037  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18003803e  mov     edx, 9FAh; void *
0x180038043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038048  lea     rcx, [rbp+arg_10]
0x18003804c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038051  nop
0x180038052  lea     rcx, [rbp+var_20]
0x180038056  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003805b  jmp     loc_180038312
0x180038060  mov     rcx, [rbp+arg_10]
0x180038064  test    rcx, rcx
0x180038067  jz      short loc_180038079
0x180038069  mov     rax, [rcx]
0x18003806c  mov     rax, [rax+8]
0x180038070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038075  mov     rcx, [rbp+arg_10]
0x180038079  mov     [r14], rcx
0x18003807c  test    rsi, rsi
0x18003807f  jz      short loc_180038088
0x180038081  mov     [rbp+arg_10], r12
0x180038085  mov     [rsi], rcx
0x180038088  mov     r12b, 1
0x18003808b  lea     rcx, [rbp+arg_10]
0x18003808f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038094  jmp     loc_180038134
0x180038099  xor     ebx, ebx
0x18003809b  mov     [rbp+ppv], rbx
0x18003809f  mov     edx, 5Ah ; 'Z'; unsigned __int16
0x1800380a4  lea     rcx, [r12+58h]; this
0x1800380a9  lea     r8, [rbp+ppv]; struct CLockScreenHistory::CLockScreenHistoryEntry **
0x1800380ad  call    ?_GetEntry@CLockScreenHistory@@IEAAJGPEAPEAVCLockScreenHistoryEntry@1@@Z; CLockScreenHistory::_GetEntry(ushort,CLockScreenHistory::CLockScreenHistoryEntry * *)
0x1800380b2  mov     ebx, eax
0x1800380b4  xor     eax, eax
0x1800380b6  test    ebx, ebx
0x1800380b8  jns     short loc_1800380D7
0x1800380ba  mov     rcx, [rbp+40h]; this
0x1800380be  mov     r9d, ebx; char *
0x1800380c1  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800380c8  mov     edx, 0A06h; void *
0x1800380cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800380d2  jmp     loc_180038052
0x1800380d7  mov     r12b, al
0x1800380da  mov     rbx, [rbp+ppv]
0x1800380de  lea     rcx, [rbx+242h]; pszPath
0x1800380e5  mov     r9, r14; ppv
0x1800380e8  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800380ef  xor     edx, edx; pbc
0x1800380f1  call    cs:__imp_SHCreateItemFromParsingName
0x1800380f8  nop     dword ptr [rax+rax+00h]
0x1800380fd  mov     edi, eax
0x1800380ff  test    eax, eax
0x180038101  js      short loc_180038126
0x180038103  test    rsi, rsi
0x180038106  jz      short loc_180038113
0x180038108  mov     rdx, rsi; struct IShellItem **
0x18003810b  mov     rcx, rbx; this
0x18003810e  call    ?GetOriginalFile@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAPEAUIShellItem@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetOriginalFile(IShellItem * *)
0x180038113  test    r15, r15
0x180038116  jz      short loc_180038123
0x180038118  mov     rdx, r15; unsigned __int16 **
0x18003811b  mov     rcx, rbx; this
0x18003811e  call    ?GetDetails@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAPEAG@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetDetails(ushort * *)
0x180038123  mov     r12b, 1
0x180038126  test    rbx, rbx
0x180038129  jz      short loc_180038134
0x18003812b  mov     rcx, rbx; this
0x18003812e  call    ??_GCLockScreenHistoryEntry@CLockScreenHistory@@QEAAPEAXI@Z; CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(uint)
0x180038133  nop
0x180038134  lea     rcx, [rbp+var_20]
0x180038138  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003813d  test    r12b, r12b
0x180038140  jnz     loc_180038310
0x180038146  mov     r12, [rbp+arg_0]
0x18003814a  lea     rcx, [rbp+var_20]; this
0x18003814e  call    ??0CSynchronizedOperation@CLockScreenHistory@@QEAA@_N@Z; CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(bool)
0x180038153  nop
0x180038154  lea     rbx, [r12+58h]
0x180038159  mov     rcx, rbx; this
0x18003815c  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x180038161  mov     edi, eax
0x180038163  xor     eax, eax
0x180038165  test    edi, edi
0x180038167  js      loc_180038307
0x18003816d  mov     [rbp+ppv], rax
0x180038171  xor     r13b, 1
0x180038175  lea     r8, [rbp+ppv]; unsigned __int16 **
0x180038179  mov     dl, r13b; bool
0x18003817c  mov     rcx, [rbx]; void *
0x18003817f  call    ?_s_GetLockScreenHistoryOrderInternal@CLockScreenHistory@@KAJPEAX_NPEAPEAG@Z; CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *,bool,ushort * *)
0x180038184  mov     edi, eax
0x180038186  xor     r13d, r13d
0x180038189  test    eax, eax
0x18003818b  js      loc_180038307
0x180038191  mov     [rbp+var_28], r13
0x180038195  mov     edx, [rbp+arg_8]
0x180038198  lea     r8, [rbp+var_28]; struct CLockScreenHistory::CLockScreenHistoryEntry **
0x18003819c  mov     r12, [rbp+ppv]
0x1800381a0  movzx   edx, word ptr [r12+rdx*2]; unsigned __int16
0x1800381a5  mov     rcx, rbx; this
0x1800381a8  call    ?_GetEntry@CLockScreenHistory@@IEAAJGPEAPEAVCLockScreenHistoryEntry@1@@Z; CLockScreenHistory::_GetEntry(ushort,CLockScreenHistory::CLockScreenHistoryEntry * *)
0x1800381ad  mov     edi, eax
0x1800381af  test    eax, eax
0x1800381b1  js      loc_1800382F7
0x1800381b7  mov     rbx, [rbp+var_28]
0x1800381bb  test    r14, r14
0x1800381be  jz      loc_1800382C7
0x1800381c4  lea     rcx, [rbx+242h]; pszPath
0x1800381cb  mov     r9, r14; ppv
0x1800381ce  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800381d5  xor     edx, edx; pbc
0x1800381d7  call    cs:__imp_SHCreateItemFromParsingName
0x1800381de  nop     dword ptr [rax+rax+00h]
0x1800381e3  mov     edi, eax
0x1800381e5  test    eax, eax
0x1800381e7  js      loc_1800382EA
0x1800381ed  jmp     loc_1800382CA
0x1800381f2  call    ?_s_IsSpotlight@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlight(void)
0x1800381f7  test    al, al
0x1800381f9  jz      loc_18003814A
0x1800381ff  test    r14, r14
0x180038202  jnz     short loc_18003820E
0x180038204  mov     edi, 80070057h
0x180038209  jmp     loc_180038310
0x18003820e  mov     [rbp+var_20], rbx
0x180038212  mov     [rbp+var_18], rbx
0x180038216  mov     [rbp+var_10], rbx
0x18003821a  lea     rcx, [rbp+var_20]
0x18003821e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180038223  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038227  mov     [rbp+var_18], rax
0x18003822b  mov     [rbp+var_10], rax
0x18003822f  lea     rax, [rbp+var_20]
0x180038233  mov     [rsp+58h+var_38], rax; void **
0x180038238  lea     r8, ?c_landscapeAssetPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "LandscapeAssetPath"
0x18003823f  lea     rdx, ?c_lockScreenCreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038246  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18003824d  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180038252  mov     edi, eax
0x180038254  test    eax, eax
0x180038256  js      short loc_1800382BC
0x180038258  mov     [rbp+ppv], rbx
0x18003825c  lea     rcx, [rbp+ppv]
0x180038260  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038265  lea     r9, [rbp+ppv]; ppv
0x180038269  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180038270  xor     edx, edx; pbc
0x180038272  mov     rcx, [rbp+var_20]; pszPath
0x180038276  call    cs:__imp_SHCreateItemFromParsingName
0x18003827d  nop     dword ptr [rax+rax+00h]
0x180038282  mov     edi, eax
0x180038284  test    eax, eax
0x180038286  js      short loc_1800382B2
0x180038288  mov     rcx, [rbp+ppv]
0x18003828c  test    rcx, rcx
0x18003828f  jz      short loc_1800382A1
0x180038291  mov     rax, [rcx]
  ... truncated ...
```
