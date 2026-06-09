# CBrokeredLauncher::CLaunchHelper::GetShellItemForDefaultBrowserForUrl(ushort const *,ushort const *)

- ea: `0x180058348`
- end: `0x180058636`
- name: `?GetShellItemForDefaultBrowserForUrl@CLaunchHelper@CBrokeredLauncher@@AEAA?AV?$ComPtr@UIShellItem@@@WRL@Microsoft@@PEBG0@Z`
- size: `750`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057574`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18003f59c`
- `0x18004966c`
- `0x180057544`
- `0x180058348`
- `0x18005863c`
- `0x1800586c0`
- `0x180058734`
- `0x18007b46c`
- `0x180111010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x18005844e`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x1800585c4`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18005844e`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x1800585c4`
- `OLEAUT32!__imp_SysAllocString` at `0x180058557`
- `OLEAUT32!__imp_SysAllocString` at `0x180058557`
- `OLEAUT32!__imp_VariantClear` at `0x18005854e`
- `OLEAUT32!__imp_VariantClear` at `0x180058590`
- `OLEAUT32!__imp_VariantClear` at `0x18005854e`
- `OLEAUT32!__imp_VariantClear` at `0x180058590`

## string_xrefs

- `0x1800583b5`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800583e2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058418`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005845f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800584bc`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058524`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800585a1`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800585d5`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void **__fastcall CBrokeredLauncher::CLaunchHelper::GetShellItemForDefaultBrowserForUrl(
        __int64 a1,
        void **a2,
        const WCHAR *a3,
        __int64 a4)
{
  int v7; // eax
  int v8; // eax
  struct IBindCtx *v9; // rdx
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // r8d
  int v12; // eax
  HRESULT v13; // eax
  void *v14; // rdi
  __int64 (__fastcall *v15)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD, OLECHAR **); // rbx
  int v19; // eax
  struct IBindCtx *v20; // rdx
  OLECHAR *v21; // rbx
  int v22; // ebx
  HRESULT v23; // eax
  int v25; // [rsp+20h] [rbp-59h]
  int v26[2]; // [rsp+30h] [rbp-49h] BYREF
  void *ppv; // [rsp+38h] [rbp-41h] BYREF
  int v28; // [rsp+40h] [rbp-39h]
  LPBC ppbc; // [rsp+48h] [rbp-31h] BYREF
  IBindCtx *pbc; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-21h] BYREF
  __int64 v32; // [rsp+60h] [rbp-19h]
  __int64 v33; // [rsp+68h] [rbp-11h]
  PCWSTR pszPath[3]; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v28 = 1;
  memset(pszPath, 0, sizeof(pszPath));
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(pszPath, a4, -1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA03,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v7,
      v25);
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(pszPath, L":");
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA04,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v8,
      v25);
  wil::ShellBindContextHelper::ShellBindContextHelper(&pbc, v9);
  if ( (*(_BYTE *)(a1 + 84) & 1) != 0 )
  {
    v12 = wil::ShellBindContextHelper::SetUInt32((wil::ShellBindContextHelper *)&pbc, v10, v11);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA09,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v12,
        v25);
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v13 = SHCreateItemFromParsingName(pszPath[0], pbc, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v13,
      v25);
  *(_QWORD *)v26 = 0;
  v14 = ppv;
  v15 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)ppv + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
  v16 = v15(v14, 0, &BHID_AssociationArray, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v16,
      (int)v26);
  psz = 0;
  v32 = 0;
  v33 = 0;
  v17 = *(_QWORD *)v26;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, OLECHAR **))(**(_QWORD **)v26 + 24LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
  v32 = -1;
  v33 = -1;
  v19 = v18(v17, 458756, 0, &psz);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA12,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v19,
      (int)v26);
  wil::ShellBindContextHelper::ShellBindContextHelper(&ppbc, v20);
  v21 = psz;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.llVal = (LONGLONG)SysAllocString(v21);
  if ( pvarg.llVal )
  {
    pvarg.vt = 8;
    v22 = wil::ShellBindContextHelper::Set((wil::ShellBindContextHelper *)&ppbc, L"ExplicitProgid", &pvarg);
  }
  else
  {
    v22 = -2147024882;
  }
  VariantClear(&pvarg);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA17,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v22,
      (int)v26);
  v23 = SHCreateItemFromParsingName(a3, ppbc, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a2);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v23,
      (int)v26);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppbc);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&pbc);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszPath);
  return a2;
}

```

## disassembly

```asm
0x180058348  mov     [rsp-8+arg_8], rdx
0x18005834d  push    rbp
0x18005834e  push    rbx
0x18005834f  push    rsi
0x180058350  push    rdi
0x180058351  push    r12
0x180058353  push    r14
0x180058355  lea     rbp, [rsp-2Fh]
0x18005835a  sub     rsp, 0A8h
0x180058361  mov     r14, r8
0x180058364  mov     rsi, rdx
0x180058367  mov     rbx, rcx
0x18005836a  mov     [rbp+57h+var_90], 0
0x180058371  mov     qword ptr [rdx], 0
0x180058378  mov     [rbp+57h+var_90], 1
0x18005837f  mov     [rbp+57h+pszPath], 0
0x180058387  mov     [rbp+57h+var_58], 0
0x18005838f  mov     [rbp+57h+var_50], 0
0x180058397  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005839b  mov     r8, r12
0x18005839e  mov     rdx, r9
0x1800583a1  lea     rcx, [rbp+57h+pszPath]
0x1800583a5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800583aa  mov     rcx, [rbp+5Fh]; this
0x1800583ae  test    eax, eax
0x1800583b0  jns     short loc_1800583C7
0x1800583b2  mov     r9d, eax; char *
0x1800583b5  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800583bc  mov     edx, 0A03h; void *
0x1800583c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800583c7  lea     rdx, asc_18012A25C; ":"
0x1800583ce  lea     rcx, [rbp+57h+pszPath]
0x1800583d2  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x1800583d7  mov     rcx, [rbp+5Fh]; this
0x1800583db  test    eax, eax
0x1800583dd  jns     short loc_1800583F4
0x1800583df  mov     r9d, eax; char *
0x1800583e2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800583e9  mov     edx, 0A04h; void *
0x1800583ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800583f4  lea     rcx, [rbp+57h+pbc]; ppbc
0x1800583f8  call    ??0ShellBindContextHelper@wil@@QEAA@PEAUIBindCtx@@@Z; wil::ShellBindContextHelper::ShellBindContextHelper(IBindCtx *)
0x1800583fd  nop
0x1800583fe  test    byte ptr [rbx+54h], 1
0x180058402  jz      short loc_18005842A
0x180058404  lea     rcx, [rbp+57h+pbc]; this
0x180058408  call    ?SetUInt32@ShellBindContextHelper@wil@@QEAAJPEBGI@Z; wil::ShellBindContextHelper::SetUInt32(ushort const *,uint)
0x18005840d  mov     rcx, [rbp+5Fh]; this
0x180058411  test    eax, eax
0x180058413  jns     short loc_18005842A
0x180058415  mov     r9d, eax; char *
0x180058418  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005841f  mov     edx, 0A09h; void *
0x180058424  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005842a  mov     [rbp+57h+ppv], 0
0x180058432  lea     rcx, [rbp+57h+ppv]
0x180058436  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005843b  lea     r9, [rbp+57h+ppv]; ppv
0x18005843f  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180058446  mov     rdx, [rbp+57h+pbc]; pbc
0x18005844a  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18005844e  call    cs:__imp_SHCreateItemFromParsingName
0x180058454  mov     rcx, [rbp+5Fh]; this
0x180058458  test    eax, eax
0x18005845a  jns     short loc_180058471
0x18005845c  mov     r9d, eax; char *
0x18005845f  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058466  mov     edx, 0A0Ch; void *
0x18005846b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058471  mov     qword ptr [rbp+57h+var_A0], 0
0x180058479  mov     rdi, [rbp+57h+ppv]
0x18005847d  mov     rax, [rdi]
0x180058480  mov     rbx, [rax+18h]
0x180058484  lea     rcx, [rbp+57h+var_A0]
0x180058488  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005848d  lea     rax, [rbp+57h+var_A0]
0x180058491  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180058496  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x18005849d  lea     r8, BHID_AssociationArray
0x1800584a4  xor     edx, edx
0x1800584a6  mov     rcx, rdi
0x1800584a9  mov     rax, rbx
0x1800584ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584b1  mov     rcx, [rbp+5Fh]; this
0x1800584b5  test    eax, eax
0x1800584b7  jns     short loc_1800584CE
0x1800584b9  mov     r9d, eax; char *
0x1800584bc  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800584c3  mov     edx, 0A0Fh; void *
0x1800584c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800584ce  mov     [rbp+57h+psz], 0
0x1800584d6  mov     [rbp+57h+var_70], 0
0x1800584de  mov     [rbp+57h+var_68], 0
0x1800584e6  mov     rdi, qword ptr [rbp+57h+var_A0]
0x1800584ea  mov     rax, [rdi]
0x1800584ed  mov     rbx, [rax+18h]
0x1800584f1  lea     rcx, [rbp+57h+psz]
0x1800584f5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800584fa  mov     [rbp+57h+var_70], r12
0x1800584fe  mov     [rbp+57h+var_68], r12
0x180058502  lea     r9, [rbp+57h+psz]
0x180058506  xor     r8d, r8d
0x180058509  mov     edx, 70004h
0x18005850e  mov     rcx, rdi
0x180058511  mov     rax, rbx
0x180058514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058519  mov     rcx, [rbp+5Fh]; this
0x18005851d  test    eax, eax
0x18005851f  jns     short loc_180058536
0x180058521  mov     r9d, eax; char *
0x180058524  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005852b  mov     edx, 0A12h; void *
0x180058530  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058536  lea     rcx, [rbp+57h+ppbc]; ppbc
0x18005853a  call    ??0ShellBindContextHelper@wil@@QEAA@PEAUIBindCtx@@@Z; wil::ShellBindContextHelper::ShellBindContextHelper(IBindCtx *)
0x18005853f  nop
0x180058540  mov     rbx, [rbp+57h+psz]
0x180058544  xor     eax, eax
0x180058546  mov     word ptr [rbp+57h+pvarg], ax
0x18005854a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005854e  call    cs:__imp_VariantClear
0x180058554  mov     rcx, rbx; psz
0x180058557  call    cs:__imp_SysAllocString
0x18005855d  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180058561  test    rax, rax
0x180058564  jz      short loc_180058587
0x180058566  mov     eax, 8
0x18005856b  mov     word ptr [rbp+57h+pvarg], ax
0x18005856f  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x180058573  lea     rdx, aExplicitprogid; "ExplicitProgid"
0x18005857a  lea     rcx, [rbp+57h+ppbc]; this
0x18005857e  call    ?Set@ShellBindContextHelper@wil@@QEAAJPEBGAEBUtagVARIANT@@@Z; wil::ShellBindContextHelper::Set(ushort const *,tagVARIANT const &)
0x180058583  mov     ebx, eax
0x180058585  jmp     short loc_18005858C
0x180058587  mov     ebx, 8007000Eh
0x18005858c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180058590  call    cs:__imp_VariantClear
0x180058596  mov     rcx, [rbp+5Fh]; this
0x18005859a  test    ebx, ebx
0x18005859c  jns     short loc_1800585B3
0x18005859e  mov     r9d, ebx; char *
0x1800585a1  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800585a8  mov     edx, 0A17h; void *
0x1800585ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800585b3  mov     r9, rsi; ppv
0x1800585b6  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800585bd  mov     rdx, [rbp+57h+ppbc]; pbc
0x1800585c1  mov     rcx, r14; pszPath
0x1800585c4  call    cs:__imp_SHCreateItemFromParsingName
0x1800585ca  mov     rcx, [rbp+5Fh]; this
0x1800585ce  test    eax, eax
0x1800585d0  jns     short loc_1800585E7
0x1800585d2  mov     r9d, eax; char *
0x1800585d5  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800585dc  mov     edx, 0A1Ch; void *
0x1800585e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800585e7  lea     rcx, [rbp+57h+ppbc]
0x1800585eb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800585f0  nop
0x1800585f1  lea     rcx, [rbp+57h+psz]
0x1800585f5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800585fa  nop
0x1800585fb  lea     rcx, [rbp+57h+var_A0]
0x1800585ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058604  nop
0x180058605  lea     rcx, [rbp+57h+ppv]
0x180058609  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005860e  nop
0x18005860f  lea     rcx, [rbp+57h+pbc]
0x180058613  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180058618  nop
0x180058619  lea     rcx, [rbp+57h+pszPath]
0x18005861d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180058622  mov     rax, rsi
0x180058625  add     rsp, 0A8h
0x18005862c  pop     r14
0x18005862e  pop     r12
0x180058630  pop     rdi
0x180058631  pop     rsi
0x180058632  pop     rbx
0x180058633  pop     rbp
0x180058634  retn
```
