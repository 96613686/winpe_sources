# CBrokeredLauncher::CLaunchHelper::_CheckRequirementsAndGetIShellItemForUri(Windows::Foundation::IUriRuntimeClass *,ushort const *,IShellItem * *)

- ea: `0x180057574`
- end: `0x180057930`
- name: `?_CheckRequirementsAndGetIShellItemForUri@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@PEBGPEAPEAUIShellItem@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(CBrokeredLauncher::CLaunchHelper *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, const unsigned __int16 *, struct IShellItem **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800570b4`
- `0x18006cbdc`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18004966c`
- `0x180057574`
- `0x180057938`
- `0x1800579c4`
- `0x180057b4c`
- `0x180058348`
- `0x180058734`
- `0x1800e806c`
- `0x180111010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x180057822`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x180057822`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180057720`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180057734`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180057720`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180057734`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800577ca`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800577ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180057627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800576c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180057627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800576c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005764b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800576de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005764b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800576de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800578f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800578f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057904`

## string_xrefs

- `0x1800575cb`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180057601`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180057666`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005769c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800576f6`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800577f0`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180057834`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180057882`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800578bb`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
__int64 __fastcall CBrokeredLauncher::CLaunchHelper::_CheckRequirementsAndGetIShellItemForUri(
        CBrokeredLauncher::CLaunchHelper *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        const unsigned __int16 *a3,
        struct IShellItem **a4)
{
  int v8; // eax
  int v9; // eax
  const WCHAR *StringRawBuffer; // r15
  int v11; // edi
  __int64 v12; // r9
  int v13; // eax
  const unsigned __int16 *v14; // rsi
  PCWSTR v15; // rax
  void **ShellItemForDefaultBrowserForUrl; // rax
  void *v17; // rcx
  const unsigned __int16 *v18; // rdx
  unsigned int v19; // r8d
  int v20; // eax
  HRESULT v21; // eax
  int IsUriLaunchAllowed; // eax
  int v23; // eax
  const char *v24; // r9
  void *v25; // rcx
  __int64 result; // rax
  int v27; // [rsp+20h] [rbp-58h]
  void *ppv; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+40h] [rbp-38h] BYREF
  void *v31; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  LPBC hasEmbedNull; // [rsp+80h] [rbp+8h] BYREF
  const unsigned __int16 *v34; // [rsp+90h] [rbp+18h] BYREF

  v34 = a3;
  LauncherDesktopProvider::CheckRequirementsAndGetIShellItemForUri<winrt::guid &,unsigned short const * &>(
    (char *)this + 100,
    &v34);
  try
  {
    if ( *((_BYTE *)this + 81) )
      v8 = CBrokeredLauncher::CLaunchHelper::_CheckCallerVisibilityAndContext(this);
    else
      v8 = 0;
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x716,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v8,
        v27);
    string = 0;
    v9 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 48LL))(
           a2,
           &string);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x719,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v9,
        v27);
    LODWORD(hasEmbedNull) = 0;
    WindowsStringHasEmbeddedNull(string, (BOOL *)&hasEmbedNull);
    if ( (_DWORD)hasEmbedNull )
    {
      StringRawBuffer = 0;
      v11 = -2147024809;
      v12 = 2147942487LL;
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = 0;
      v11 = -2147024809;
    }
    if ( (int)v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)v12,
        v27);
    v30 = 0;
    v13 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 88LL))(
            a2,
            &v30);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v13,
        v27);
    LODWORD(hasEmbedNull) = 0;
    WindowsStringHasEmbeddedNull(v30, (BOOL *)&hasEmbedNull);
    if ( (_DWORD)hasEmbedNull )
    {
      v14 = 0;
    }
    else
    {
      v14 = WindowsGetStringRawBuffer(v30, 0);
      v11 = 0;
    }
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x722,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v11,
        v27);
    ppv = 0;
    if ( !*((_QWORD *)this + 4)
      || StrCmpICW(a3, L"http") && StrCmpICW(a3, L"https")
      || !CBrokeredLauncher::CLaunchHelper::IgnoreAppUriHandlers(this) )
    {
      hasEmbedNull = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&hasEmbedNull);
      CreateBindCtx(0, &hasEmbedNull);
      if ( (*((_BYTE *)this + 84) & 1) != 0 )
      {
        v20 = wil::ShellBindContextHelper::SetUInt32((wil::ShellBindContextHelper *)&hasEmbedNull, v18, v19);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x731,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v20,
            v27);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v21 = SHCreateItemFromParsingName(StringRawBuffer, hasEmbedNull, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x733,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v21,
          v27);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&hasEmbedNull);
    }
    else
    {
      v15 = WindowsGetStringRawBuffer(string, 0);
      ShellItemForDefaultBrowserForUrl = (void **)CBrokeredLauncher::CLaunchHelper::GetShellItemForDefaultBrowserForUrl(
                                                    this,
                                                    &hasEmbedNull,
                                                    v15,
                                                    a3);
      v17 = 0;
      if ( &v31 != ShellItemForDefaultBrowserForUrl )
      {
        v17 = *ShellItemForDefaultBrowserForUrl;
        *ShellItemForDefaultBrowserForUrl = 0;
      }
      v31 = ppv;
      ppv = v17;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hasEmbedNull);
    }
    if ( *((_BYTE *)this + 82) )
      IsUriLaunchAllowed = CBrokeredLauncher::CLaunchHelper::_IsUriLaunchAllowed(
                             this,
                             (struct IShellItem *)ppv,
                             StringRawBuffer,
                             a3,
                             v14);
    else
      IsUriLaunchAllowed = 0;
    if ( IsUriLaunchAllowed < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x736,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)IsUriLaunchAllowed,
        v27);
    v23 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IShellItem **))ppv)(
            ppv,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            a4);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x737,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v23,
        v27);
    v25 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
    }
    if ( v30 )
      WindowsDeleteString(v30);
    if ( string )
      WindowsDeleteString(string);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(hasEmbedNull) = wil::details::in1diag3::Return_CaughtException(
                              retaddr,
                              (void *)0x73A,
                              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                              v24);
    return (unsigned int)hasEmbedNull;
  }
  return result;
}

```

## disassembly

```asm
0x180057574  mov     rax, rsp
0x180057577  mov     [rax+10h], rbx
0x18005757b  mov     [rax+20h], rsi
0x18005757f  mov     [rax+18h], r8
0x180057583  push    rdi
0x180057584  push    r12
0x180057586  push    r13
0x180057588  push    r14
0x18005758a  push    r15
0x18005758c  sub     rsp, 50h
0x180057590  mov     r12, r9
0x180057593  mov     r14, r8
0x180057596  mov     rsi, rdx
0x180057599  mov     rbx, rcx
0x18005759c  add     rcx, 64h ; 'd'
0x1800575a0  lea     rdx, [rax+18h]
0x1800575a4  call    ??$CheckRequirementsAndGetIShellItemForUri@AEAUguid@winrt@@AEAPEBG@LauncherDesktopProvider@@SAXAEAUguid@winrt@@AEAPEBG@Z; LauncherDesktopProvider::CheckRequirementsAndGetIShellItemForUri<winrt::guid &,ushort const * &>(winrt::guid &,ushort const * &)
0x1800575a9  xor     r13d, r13d
0x1800575ac  cmp     [rbx+51h], r13b
0x1800575b0  jz      short loc_1800575BC
0x1800575b2  mov     rcx, rbx; this
0x1800575b5  call    ?_CheckCallerVisibilityAndContext@CLaunchHelper@CBrokeredLauncher@@AEAAJXZ; CBrokeredLauncher::CLaunchHelper::_CheckCallerVisibilityAndContext(void)
0x1800575ba  jmp     short loc_1800575BF
0x1800575bc  mov     eax, r13d
0x1800575bf  mov     rcx, [rsp+78h]; this
0x1800575c4  test    eax, eax
0x1800575c6  jns     short loc_1800575DC
0x1800575c8  mov     r9d, eax; char *
0x1800575cb  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800575d2  mov     edx, 716h; void *
0x1800575d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800575dc  mov     [rsp+78h+string], r13
0x1800575e1  mov     rax, [rsi]
0x1800575e4  lea     rdx, [rsp+78h+string]
0x1800575e9  mov     rcx, rsi
0x1800575ec  mov     rax, [rax+30h]
0x1800575f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800575f5  mov     rcx, [rsp+78h]; this
0x1800575fa  test    eax, eax
0x1800575fc  jns     short loc_180057612
0x1800575fe  mov     r9d, eax; char *
0x180057601  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180057608  mov     edx, 719h; void *
0x18005760d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057612  mov     dword ptr [rsp+78h+hasEmbedNull], r13d
0x18005761a  lea     rdx, [rsp+78h+hasEmbedNull]; hasEmbedNull
0x180057622  mov     rcx, [rsp+78h+string]; string
0x180057627  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18005762d  cmp     dword ptr [rsp+78h+hasEmbedNull], r13d
0x180057635  jz      short loc_180057644
0x180057637  mov     r15, r13
0x18005763a  mov     edi, 80070057h
0x18005763f  mov     r9d, edi
0x180057642  jmp     short loc_18005765C
0x180057644  xor     edx, edx; length
0x180057646  mov     rcx, [rsp+78h+string]; string
0x18005764b  call    cs:__imp_WindowsGetStringRawBuffer
0x180057651  mov     r15, rax
0x180057654  mov     r9d, r13d; char *
0x180057657  mov     edi, 80070057h
0x18005765c  mov     rcx, [rsp+78h]; this
0x180057661  test    r9d, r9d
0x180057664  jns     short loc_180057677
0x180057666  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005766d  mov     edx, 71Ch; void *
0x180057672  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057677  mov     [rsp+78h+var_38], r13
0x18005767c  mov     rax, [rsi]
0x18005767f  lea     rdx, [rsp+78h+var_38]
0x180057684  mov     rcx, rsi
0x180057687  mov     rax, [rax+58h]
0x18005768b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057690  mov     rcx, [rsp+78h]; this
0x180057695  test    eax, eax
0x180057697  jns     short loc_1800576AD
0x180057699  mov     r9d, eax; char *
0x18005769c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800576a3  mov     edx, 71Fh; void *
0x1800576a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800576ad  mov     dword ptr [rsp+78h+hasEmbedNull], r13d
0x1800576b5  lea     rdx, [rsp+78h+hasEmbedNull]; hasEmbedNull
0x1800576bd  mov     rcx, [rsp+78h+var_38]; string
0x1800576c2  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800576c8  cmp     dword ptr [rsp+78h+hasEmbedNull], r13d
0x1800576d0  jz      short loc_1800576D7
0x1800576d2  mov     rsi, r13
0x1800576d5  jmp     short loc_1800576EA
0x1800576d7  xor     edx, edx; length
0x1800576d9  mov     rcx, [rsp+78h+var_38]; string
0x1800576de  call    cs:__imp_WindowsGetStringRawBuffer
0x1800576e4  mov     rsi, rax
0x1800576e7  mov     edi, r13d
0x1800576ea  mov     rcx, [rsp+78h]; this
0x1800576ef  test    edi, edi
0x1800576f1  jns     short loc_180057707
0x1800576f3  mov     r9d, edi; char *
0x1800576f6  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800576fd  mov     edx, 722h; void *
0x180057702  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057707  mov     [rsp+78h+ppv], r13
0x18005770c  cmp     [rbx+20h], r13
0x180057710  jz      loc_1800577AB
0x180057716  lea     rdx, pszStr2; "http"
0x18005771d  mov     rcx, r14; pszStr1
0x180057720  call    cs:__imp_StrCmpICW
0x180057726  test    eax, eax
0x180057728  jz      short loc_18005773E
0x18005772a  lea     rdx, aHttps_0; "https"
0x180057731  mov     rcx, r14; pszStr1
0x180057734  call    cs:__imp_StrCmpICW
0x18005773a  test    eax, eax
0x18005773c  jnz     short loc_1800577AB
0x18005773e  mov     rcx, rbx; this
0x180057741  call    ?IgnoreAppUriHandlers@CLaunchHelper@CBrokeredLauncher@@AEAA_NXZ; CBrokeredLauncher::CLaunchHelper::IgnoreAppUriHandlers(void)
0x180057746  test    al, al
0x180057748  jz      short loc_1800577AB
0x18005774a  xor     edx, edx; length
0x18005774c  mov     rcx, [rsp+78h+string]; string
0x180057751  call    cs:__imp_WindowsGetStringRawBuffer
0x180057757  mov     r9, r14
0x18005775a  mov     r8, rax
0x18005775d  lea     rdx, [rsp+78h+hasEmbedNull]
0x180057765  mov     rcx, rbx
0x180057768  call    ?GetShellItemForDefaultBrowserForUrl@CLaunchHelper@CBrokeredLauncher@@AEAA?AV?$ComPtr@UIShellItem@@@WRL@Microsoft@@PEBG0@Z; CBrokeredLauncher::CLaunchHelper::GetShellItemForDefaultBrowserForUrl(ushort const *,ushort const *)
0x18005776d  mov     rcx, r13
0x180057770  lea     rdx, [rsp+78h+var_30]
0x180057775  cmp     rdx, rax
0x180057778  jz      short loc_180057780
0x18005777a  mov     rcx, [rax]
0x18005777d  mov     [rax], r13
0x180057780  mov     rax, [rsp+78h+ppv]
0x180057785  mov     [rsp+78h+var_30], rax
0x18005778a  mov     [rsp+78h+ppv], rcx
0x18005778f  lea     rcx, [rsp+78h+var_30]
0x180057794  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180057799  lea     rcx, [rsp+78h+hasEmbedNull]
0x1800577a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800577a6  jmp     loc_180057853
0x1800577ab  mov     [rsp+78h+hasEmbedNull], r13
0x1800577b3  lea     rcx, [rsp+78h+hasEmbedNull]
0x1800577bb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800577c0  lea     rdx, [rsp+78h+hasEmbedNull]; ppbc
0x1800577c8  xor     ecx, ecx; reserved
0x1800577ca  call    cs:__imp_CreateBindCtx
0x1800577d0  nop
0x1800577d1  test    byte ptr [rbx+54h], 1
0x1800577d5  jz      short loc_180057801
0x1800577d7  lea     rcx, [rsp+78h+hasEmbedNull]; this
0x1800577df  call    ?SetUInt32@ShellBindContextHelper@wil@@QEAAJPEBGI@Z; wil::ShellBindContextHelper::SetUInt32(ushort const *,uint)
0x1800577e4  mov     rcx, [rsp+78h]; this
0x1800577e9  test    eax, eax
0x1800577eb  jns     short loc_180057801
0x1800577ed  mov     r9d, eax; char *
0x1800577f0  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800577f7  mov     edx, 731h; void *
0x1800577fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057801  lea     rcx, [rsp+78h+ppv]
0x180057806  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005780b  lea     r9, [rsp+78h+ppv]; ppv
0x180057810  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180057817  mov     rdx, [rsp+78h+hasEmbedNull]; pbc
0x18005781f  mov     rcx, r15; pszPath
0x180057822  call    cs:__imp_SHCreateItemFromParsingName
0x180057828  mov     rcx, [rsp+78h]; this
0x18005782d  test    eax, eax
0x18005782f  jns     short loc_180057846
0x180057831  mov     r9d, eax; char *
0x180057834  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005783b  mov     edx, 733h; void *
0x180057840  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057846  lea     rcx, [rsp+78h+hasEmbedNull]
0x18005784e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180057853  cmp     [rbx+52h], r13b
0x180057857  jz      short loc_180057873
0x180057859  mov     qword ptr [rsp+78h+var_58], rsi; unsigned __int16 *
0x18005785e  mov     r9, r14; unsigned __int16 *
0x180057861  mov     r8, r15; unsigned __int16 *
0x180057864  mov     rdx, [rsp+78h+ppv]; struct IShellItem *
0x180057869  mov     rcx, rbx; this
0x18005786c  call    ?_IsUriLaunchAllowed@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEBG11@Z; CBrokeredLauncher::CLaunchHelper::_IsUriLaunchAllowed(IShellItem *,ushort const *,ushort const *,ushort const *)
0x180057871  jmp     short loc_180057876
0x180057873  mov     eax, r13d
0x180057876  mov     rcx, [rsp+78h]; this
0x18005787b  test    eax, eax
0x18005787d  jns     short loc_180057894
0x18005787f  mov     r9d, eax; char *
0x180057882  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180057889  mov     edx, 736h; void *
0x18005788e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057894  mov     rcx, [rsp+78h+ppv]
0x180057899  mov     rax, [rcx]
0x18005789c  mov     r8, r12
0x18005789f  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800578a6  mov     rax, [rax]
0x1800578a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578ae  nop
0x1800578af  mov     rcx, [rsp+78h]; this
0x1800578b4  test    eax, eax
0x1800578b6  jns     short loc_1800578CD
0x1800578b8  mov     r9d, eax; char *
0x1800578bb  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800578c2  mov     edx, 737h; void *
0x1800578c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800578cd  mov     rcx, [rsp+78h+ppv]
0x1800578d2  test    rcx, rcx
0x1800578d5  jz      short loc_1800578E9
0x1800578d7  mov     [rsp+78h+ppv], r13
0x1800578dc  mov     rax, [rcx]
0x1800578df  mov     rax, [rax+10h]
0x1800578e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578e8  nop
0x1800578e9  mov     rcx, [rsp+78h+var_38]; string
0x1800578ee  test    rcx, rcx
0x1800578f1  jz      short loc_1800578FA
0x1800578f3  call    cs:__imp_WindowsDeleteString
0x1800578f9  nop
0x1800578fa  mov     rcx, [rsp+78h+string]; string
0x1800578ff  test    rcx, rcx
0x180057902  jz      short loc_18005790A
0x180057904  call    cs:__imp_WindowsDeleteString
0x18005790a  xor     eax, eax
0x18005790c  jmp     short loc_180057915
0x18005790e  mov     eax, dword ptr [rsp+78h+hasEmbedNull]
0x180057915  lea     r11, [rsp+78h+var_28]
0x18005791a  mov     rbx, [r11+38h]
0x18005791e  mov     rsi, [r11+48h]
0x180057922  mov     rsp, r11
0x180057925  pop     r15
0x180057927  pop     r14
0x180057929  pop     r13
0x18005792b  pop     r12
0x18005792d  pop     rdi
0x18005792e  retn
```
