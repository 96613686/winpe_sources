# CPostBootReminder::Add(_tagSHELLREMINDER const *)

- ea: `0x1803b8450`
- end: `0x1803b866b`
- name: `?Add@CPostBootReminder@@UEAAJPEBU_tagSHELLREMINDER@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(CPostBootReminder *__hidden this, const struct _tagSHELLREMINDER *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f05c`
- `0x1800a715c`
- `0x1800a7264`
- `0x180233280`
- `0x1803b8450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1803b8494`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1803b8494`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1803b84f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1803b84f1`
- `SHLWAPI!__imp_SHCreatePropertyBagOnRegKey` at `0x1803b852e`
- `SHLWAPI!__imp_SHCreatePropertyBagOnRegKey` at `0x1803b852e`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b8550`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b856a`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b8584`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b859e`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b85b8`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b8550`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b856a`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b8584`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b859e`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1803b85b8`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b85e7`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b85fc`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b8611`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b8626`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b85e7`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b85fc`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b8611`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1803b8626`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1803b85d2`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1803b85d2`

## string_xrefs

- `0x1803b85c7`: `Clsid`

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
0x1803b8450  mov     [rsp-8+arg_0], rbx
0x1803b8455  mov     [rsp-8+arg_10], rdi
0x1803b845a  push    rbp
0x1803b845b  mov     rbp, rsp
0x1803b845e  sub     rsp, 70h
0x1803b8462  mov     rax, cs:__security_cookie
0x1803b8469  xor     rax, rsp
0x1803b846c  mov     [rbp+var_8], rax
0x1803b8470  mov     rbx, rdx
0x1803b8473  mov     edi, 80004005h
0x1803b8478  mov     [rbp+phkResult], 0
0x1803b8480  xor     edx, edx
0x1803b8482  lea     rcx, [rbp+phkResult]
0x1803b8486  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1803b848b  lea     rdx, [rbp+phkResult]; phkResult
0x1803b848f  mov     ecx, 20006h; samDesired
0x1803b8494  call    cs:__imp_RegOpenCurrentUser
0x1803b849a  test    eax, eax
0x1803b849c  jnz     loc_1803B8642
0x1803b84a2  mov     [rbp+var_18], 0
0x1803b84aa  xor     edx, edx
0x1803b84ac  lea     rcx, [rbp+var_18]
0x1803b84b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1803b84b5  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x1803b84be  lea     rax, [rbp+var_18]
0x1803b84c2  mov     [rsp+70h+var_38], rax; phkResult
0x1803b84c7  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1803b84d0  mov     [rsp+70h+samDesired], 20006h; samDesired
0x1803b84d8  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1803b84e0  xor     r9d, r9d; lpClass
0x1803b84e3  xor     r8d, r8d; Reserved
0x1803b84e6  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1803b84ed  mov     rcx, [rbp+phkResult]; hKey
0x1803b84f1  call    cs:__imp_RegCreateKeyExW
0x1803b84f7  test    eax, eax
0x1803b84f9  jnz     loc_1803B8638
0x1803b84ff  mov     [rbp+propBag], 0
0x1803b8507  lea     rcx, [rbp+propBag]
0x1803b850b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803b8510  lea     rax, [rbp+propBag]
0x1803b8514  mov     qword ptr [rsp+70h+dwOptions], rax
0x1803b8519  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1803b8520  mov     r8d, 1001h
0x1803b8526  mov     rdx, [rbx+8]
0x1803b852a  mov     rcx, [rbp+var_18]
0x1803b852e  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x1803b8534  test    eax, eax
0x1803b8536  js      loc_1803B862C
0x1803b853c  mov     r8, [rbx+10h]; value
0x1803b8540  test    r8, r8
0x1803b8543  jz      short loc_1803B8556
0x1803b8545  lea     rdx, aTitle_0; "Title"
0x1803b854c  mov     rcx, [rbp+propBag]; propBag
0x1803b8550  call    cs:__imp_PSPropertyBag_WriteStr
0x1803b8556  mov     r8, [rbx+18h]; value
0x1803b855a  test    r8, r8
0x1803b855d  jz      short loc_1803B8570
0x1803b855f  lea     rdx, aText_1; "Text"
0x1803b8566  mov     rcx, [rbp+propBag]; propBag
0x1803b856a  call    cs:__imp_PSPropertyBag_WriteStr
0x1803b8570  mov     r8, [rbx+20h]; value
0x1803b8574  test    r8, r8
0x1803b8577  jz      short loc_1803B858A
0x1803b8579  lea     rdx, aTooltip; "ToolTip"
0x1803b8580  mov     rcx, [rbp+propBag]; propBag
0x1803b8584  call    cs:__imp_PSPropertyBag_WriteStr
0x1803b858a  mov     r8, [rbx+28h]; value
0x1803b858e  test    r8, r8
0x1803b8591  jz      short loc_1803B85A4
0x1803b8593  lea     rdx, aIconresource; "IconResource"
0x1803b859a  mov     rcx, [rbp+propBag]; propBag
0x1803b859e  call    cs:__imp_PSPropertyBag_WriteStr
0x1803b85a4  mov     r8, [rbx+30h]; value
0x1803b85a8  test    r8, r8
0x1803b85ab  jz      short loc_1803B85BE
0x1803b85ad  lea     rdx, aShellexecute; "ShellExecute"
0x1803b85b4  mov     rcx, [rbp+propBag]; propBag
0x1803b85b8  call    cs:__imp_PSPropertyBag_WriteStr
0x1803b85be  mov     r8, [rbx+38h]; value
0x1803b85c2  test    r8, r8
0x1803b85c5  jz      short loc_1803B85D8
0x1803b85c7  lea     rdx, aClsid_0; "Clsid"
0x1803b85ce  mov     rcx, [rbp+propBag]; propBag
0x1803b85d2  call    cs:__imp_PSPropertyBag_WriteGUID
0x1803b85d8  mov     r8d, [rbx+40h]; value
0x1803b85dc  lea     rdx, aShowtime; "ShowTime"
0x1803b85e3  mov     rcx, [rbp+propBag]; propBag
0x1803b85e7  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803b85ed  mov     r8d, [rbx+44h]; value
0x1803b85f1  lea     rdx, aRetryinterval; "RetryInterval"
0x1803b85f8  mov     rcx, [rbp+propBag]; propBag
0x1803b85fc  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803b8602  mov     r8d, [rbx+48h]; value
0x1803b8606  lea     rdx, aRetrycount; "RetryCount"
0x1803b860d  mov     rcx, [rbp+propBag]; propBag
0x1803b8611  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803b8617  mov     r8d, [rbx+4Ch]; value
0x1803b861b  lea     rdx, aTypeflags; "TypeFlags"
0x1803b8622  mov     rcx, [rbp+propBag]; propBag
0x1803b8626  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1803b862c  xor     edi, edi
0x1803b862e  lea     rcx, [rbp+propBag]
0x1803b8632  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803b8637  nop
0x1803b8638  lea     rcx, [rbp+var_18]
0x1803b863c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1803b8641  nop
0x1803b8642  lea     rcx, [rbp+phkResult]
0x1803b8646  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1803b864b  mov     eax, edi
0x1803b864d  mov     rcx, [rbp+var_8]
0x1803b8651  xor     rcx, rsp; StackCookie
0x1803b8654  call    __security_check_cookie
0x1803b8659  lea     r11, [rsp+70h+var_s0]
0x1803b865e  mov     rbx, [r11+10h]
0x1803b8662  mov     rdi, [r11+20h]
0x1803b8666  mov     rsp, r11
0x1803b8669  pop     rbp
0x1803b866a  retn
```
