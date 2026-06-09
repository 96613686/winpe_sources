# CPostBootReminder::Add(_tagSHELLREMINDER const *)

- ea: `0x1803e0c30`
- end: `0x1803e0e9a`
- name: `?Add@CPostBootReminder@@UEAAJPEBU_tagSHELLREMINDER@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(CPostBootReminder *__hidden this, const struct _tagSHELLREMINDER *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f6cc`
- `0x1800a2f24`
- `0x1800a4ff8`
- `0x180249490`
- `0x1803e0c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1803e0c74`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1803e0c74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1803e0cd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1803e0cd7`
- `SHLWAPI!__imp_SHCreatePropertyBagOnRegKey` at `0x1803e0d1a`
- `SHLWAPI!__imp_SHCreatePropertyBagOnRegKey` at `0x1803e0d1a`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0d42`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0d62`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0d82`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0da2`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0dc2`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0d42`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0d62`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0d82`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0da2`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803e0dc2`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0dfd`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0e18`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0e33`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0e4e`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0dfd`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0e18`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0e33`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803e0e4e`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1803e0de2`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1803e0de2`

## string_xrefs

- `0x1803e0dd7`: `Clsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPostBootReminder::Add(CPostBootReminder *this, const struct _tagSHELLREMINDER *a2)
{
  unsigned int v3; // edi
  const WCHAR *v4; // r8
  const WCHAR *v5; // r8
  const WCHAR *v6; // r8
  const WCHAR *v7; // r8
  const WCHAR *v8; // r8
  const GUID *v9; // r8
  IPropertyBag *propBag; // [rsp+50h] [rbp-20h] BYREF
  HKEY v12; // [rsp+58h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-10h] BYREF

  v3 = -2147467259;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  if ( !RegOpenCurrentUser(0x20006u, &phkResult) )
  {
    v12 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    if ( !RegCreateKeyExW(
            phkResult,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PostBootReminders",
            0,
            0,
            0,
            0x20006u,
            0,
            &v12,
            0) )
    {
      propBag = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&propBag);
      if ( (int)SHCreatePropertyBagOnRegKey(
                  v12,
                  *((_QWORD *)a2 + 1),
                  4097,
                  &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                  &propBag) >= 0 )
      {
        v4 = (const WCHAR *)*((_QWORD *)a2 + 2);
        if ( v4 )
          PSPropertyBag_WriteStr(propBag, L"Title", v4);
        v5 = (const WCHAR *)*((_QWORD *)a2 + 3);
        if ( v5 )
          PSPropertyBag_WriteStr(propBag, L"Text", v5);
        v6 = (const WCHAR *)*((_QWORD *)a2 + 4);
        if ( v6 )
          PSPropertyBag_WriteStr(propBag, L"ToolTip", v6);
        v7 = (const WCHAR *)*((_QWORD *)a2 + 5);
        if ( v7 )
          PSPropertyBag_WriteStr(propBag, L"IconResource", v7);
        v8 = (const WCHAR *)*((_QWORD *)a2 + 6);
        if ( v8 )
          PSPropertyBag_WriteStr(propBag, L"ShellExecute", v8);
        v9 = (const GUID *)*((_QWORD *)a2 + 7);
        if ( v9 )
          PSPropertyBag_WriteGUID(propBag, L"Clsid", v9);
        PSPropertyBag_WriteDWORD(propBag, L"ShowTime", *((_DWORD *)a2 + 16));
        PSPropertyBag_WriteDWORD(propBag, L"RetryInterval", *((_DWORD *)a2 + 17));
        PSPropertyBag_WriteDWORD(propBag, L"RetryCount", *((_DWORD *)a2 + 18));
        PSPropertyBag_WriteDWORD(propBag, L"TypeFlags", *((_DWORD *)a2 + 19));
      }
      v3 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&propBag);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v3;
}

```

## disassembly

```asm
0x1803e0c30  mov     [rsp-8+arg_0], rbx
0x1803e0c35  mov     [rsp-8+arg_10], rdi
0x1803e0c3a  push    rbp
0x1803e0c3b  mov     rbp, rsp
0x1803e0c3e  sub     rsp, 70h
0x1803e0c42  mov     rax, cs:__security_cookie
0x1803e0c49  xor     rax, rsp
0x1803e0c4c  mov     [rbp+var_8], rax
0x1803e0c50  mov     rbx, rdx
0x1803e0c53  mov     edi, 80004005h
0x1803e0c58  mov     [rbp+phkResult], 0
0x1803e0c60  xor     edx, edx
0x1803e0c62  lea     rcx, [rbp+phkResult]
0x1803e0c66  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1803e0c6b  lea     rdx, [rbp+phkResult]; phkResult
0x1803e0c6f  mov     ecx, 20006h; samDesired
0x1803e0c74  call    cs:__imp_RegOpenCurrentUser
0x1803e0c7b  nop     dword ptr [rax+rax+00h]
0x1803e0c80  test    eax, eax
0x1803e0c82  jnz     loc_1803E0E70
0x1803e0c88  mov     [rbp+var_18], 0
0x1803e0c90  xor     edx, edx
0x1803e0c92  lea     rcx, [rbp+var_18]
0x1803e0c96  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1803e0c9b  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x1803e0ca4  lea     rax, [rbp+var_18]
0x1803e0ca8  mov     [rsp+70h+var_38], rax; phkResult
0x1803e0cad  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1803e0cb6  mov     [rsp+70h+samDesired], 20006h; samDesired
0x1803e0cbe  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1803e0cc6  xor     r9d, r9d; lpClass
0x1803e0cc9  xor     r8d, r8d; Reserved
0x1803e0ccc  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1803e0cd3  mov     rcx, [rbp+phkResult]; hKey
0x1803e0cd7  call    cs:__imp_RegCreateKeyExW
0x1803e0cde  nop     dword ptr [rax+rax+00h]
0x1803e0ce3  test    eax, eax
0x1803e0ce5  jnz     loc_1803E0E66
0x1803e0ceb  mov     [rbp+propBag], 0
0x1803e0cf3  lea     rcx, [rbp+propBag]
0x1803e0cf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e0cfc  lea     rax, [rbp+propBag]
0x1803e0d00  mov     qword ptr [rsp+70h+dwOptions], rax
0x1803e0d05  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1803e0d0c  mov     r8d, 1001h
0x1803e0d12  mov     rdx, [rbx+8]
0x1803e0d16  mov     rcx, [rbp+var_18]
0x1803e0d1a  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x1803e0d21  nop     dword ptr [rax+rax+00h]
0x1803e0d26  test    eax, eax
0x1803e0d28  js      loc_1803E0E5A
0x1803e0d2e  mov     r8, [rbx+10h]; value
0x1803e0d32  test    r8, r8
0x1803e0d35  jz      short loc_1803E0D4E
0x1803e0d37  lea     rdx, aTitle_0; "Title"
0x1803e0d3e  mov     rcx, [rbp+propBag]; propBag
0x1803e0d42  call    cs:__imp_PSPropertyBag_WriteStr
0x1803e0d49  nop     dword ptr [rax+rax+00h]
0x1803e0d4e  mov     r8, [rbx+18h]; value
0x1803e0d52  test    r8, r8
0x1803e0d55  jz      short loc_1803E0D6E
0x1803e0d57  lea     rdx, aText_1; "Text"
0x1803e0d5e  mov     rcx, [rbp+propBag]; propBag
0x1803e0d62  call    cs:__imp_PSPropertyBag_WriteStr
0x1803e0d69  nop     dword ptr [rax+rax+00h]
0x1803e0d6e  mov     r8, [rbx+20h]; value
0x1803e0d72  test    r8, r8
0x1803e0d75  jz      short loc_1803E0D8E
0x1803e0d77  lea     rdx, aTooltip; "ToolTip"
0x1803e0d7e  mov     rcx, [rbp+propBag]; propBag
0x1803e0d82  call    cs:__imp_PSPropertyBag_WriteStr
0x1803e0d89  nop     dword ptr [rax+rax+00h]
0x1803e0d8e  mov     r8, [rbx+28h]; value
0x1803e0d92  test    r8, r8
0x1803e0d95  jz      short loc_1803E0DAE
0x1803e0d97  lea     rdx, aIconresource; "IconResource"
0x1803e0d9e  mov     rcx, [rbp+propBag]; propBag
0x1803e0da2  call    cs:__imp_PSPropertyBag_WriteStr
0x1803e0da9  nop     dword ptr [rax+rax+00h]
0x1803e0dae  mov     r8, [rbx+30h]; value
0x1803e0db2  test    r8, r8
0x1803e0db5  jz      short loc_1803E0DCE
0x1803e0db7  lea     rdx, aShellexecute; "ShellExecute"
0x1803e0dbe  mov     rcx, [rbp+propBag]; propBag
0x1803e0dc2  call    cs:__imp_PSPropertyBag_WriteStr
0x1803e0dc9  nop     dword ptr [rax+rax+00h]
0x1803e0dce  mov     r8, [rbx+38h]; value
0x1803e0dd2  test    r8, r8
0x1803e0dd5  jz      short loc_1803E0DEE
0x1803e0dd7  lea     rdx, aClsid_0; "Clsid"
0x1803e0dde  mov     rcx, [rbp+propBag]; propBag
0x1803e0de2  call    cs:__imp_PSPropertyBag_WriteGUID
0x1803e0de9  nop     dword ptr [rax+rax+00h]
0x1803e0dee  mov     r8d, [rbx+40h]; value
0x1803e0df2  lea     rdx, aShowtime; "ShowTime"
0x1803e0df9  mov     rcx, [rbp+propBag]; propBag
0x1803e0dfd  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803e0e04  nop     dword ptr [rax+rax+00h]
0x1803e0e09  mov     r8d, [rbx+44h]; value
0x1803e0e0d  lea     rdx, aRetryinterval; "RetryInterval"
0x1803e0e14  mov     rcx, [rbp+propBag]; propBag
0x1803e0e18  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803e0e1f  nop     dword ptr [rax+rax+00h]
0x1803e0e24  mov     r8d, [rbx+48h]; value
0x1803e0e28  lea     rdx, aRetrycount; "RetryCount"
0x1803e0e2f  mov     rcx, [rbp+propBag]; propBag
0x1803e0e33  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803e0e3a  nop     dword ptr [rax+rax+00h]
0x1803e0e3f  mov     r8d, [rbx+4Ch]; value
0x1803e0e43  lea     rdx, aTypeflags; "TypeFlags"
0x1803e0e4a  mov     rcx, [rbp+propBag]; propBag
0x1803e0e4e  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803e0e55  nop     dword ptr [rax+rax+00h]
0x1803e0e5a  xor     edi, edi
0x1803e0e5c  lea     rcx, [rbp+propBag]
0x1803e0e60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803e0e65  nop
0x1803e0e66  lea     rcx, [rbp+var_18]
0x1803e0e6a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1803e0e6f  nop
0x1803e0e70  lea     rcx, [rbp+phkResult]
0x1803e0e74  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1803e0e79  mov     eax, edi
0x1803e0e7b  mov     rcx, [rbp+var_8]
0x1803e0e7f  xor     rcx, rsp; StackCookie
0x1803e0e82  call    __security_check_cookie
0x1803e0e87  lea     r11, [rsp+70h+var_s0]
0x1803e0e8c  mov     rbx, [r11+10h]
0x1803e0e90  mov     rdi, [r11+20h]
0x1803e0e94  mov     rsp, r11
0x1803e0e97  pop     rbp
0x1803e0e98  retn
```
