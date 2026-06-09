# EnumerateValidRegisteredWebKeys(std::function<void (HKEY__ *)>)

- ea: `0x18045cb3c`
- end: `0x18045cd48`
- name: `?EnumerateValidRegisteredWebKeys@@YAXV?$function@$$A6AXPEAUHKEY__@@@Z@std@@@Z`
- size: `524`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18045ded0`
- `0x18045df18`
- `0x18045e3fc`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x180021c00`
- `0x180026860`
- `0x18006bb58`
- `0x1800d971c`
- `0x18015cb00`
- `0x18045cb3c`
- `0x18045dfcc`
- `0x18045f3dc`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18045cd41`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18045cd41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18045cb98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18045cc92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18045cb98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18045cc92`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18045cbea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18045cbea`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18045cc3a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18045cc3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnumerateValidRegisteredWebKeys(__int64 a1)
{
  HKEY *phkResult; // rax
  DWORD v3; // esi
  DWORD i; // ebx
  WCHAR *v5; // r8
  WCHAR *v6; // rax
  HKEY *v7; // rax
  const WCHAR *v8; // rdx
  __int64 v9; // rcx
  __int64 result; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  DWORD cSubKeys; // [rsp+60h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-31h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-29h] BYREF
  __int64 v16; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v17[2]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v18[32]; // [rsp+90h] [rbp-9h] BYREF
  LPWSTR lpName[2]; // [rsp+B0h] [rbp+17h] BYREF
  int v20; // [rsp+C0h] [rbp+27h]
  unsigned __int64 v21; // [rsp+C8h] [rbp+2Fh]

  v17[1] = a1;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedWebView",
          1u,
          0x20019u,
          phkResult) )
  {
    cbMaxSubKeyLen = 0;
    cSubKeys = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
    {
      std::wstring::wstring(lpName);
      std::wstring::resize(lpName, cbMaxSubKeyLen + 1);
      v3 = 2 * v20;
      for ( i = 0; i < cSubKeys; ++i )
      {
        v5 = (WCHAR *)lpName;
        if ( v21 > 7 )
          v5 = lpName[0];
        if ( !RegEnumKeyW(hKey, i, v5, v3) )
        {
          v6 = (WCHAR *)std::wstring::wstring(v18, lpName);
          if ( IsValidWebViewKey(hKey, v6) )
          {
            v16 = 0;
            v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v16);
            v8 = (const WCHAR *)lpName;
            if ( v21 > 7 )
              v8 = lpName[0];
            if ( !RegOpenKeyExW(hKey, v8, 0, 0x20019u, v7) )
            {
              v17[0] = v16;
              v9 = *(_QWORD *)(a1 + 56);
              if ( !v9 )
              {
                std::_Xbad_function_call();
                JUMPOUT(0x18045CD48LL);
              }
              (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 16LL))(v9, v17);
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
          }
          else
          {
            RegistryHelpers::TryDeleteVolatileRegistryKey(hKey, (LPCWSTR)lpName);
            --cSubKeys;
            --i;
          }
        }
      }
      std::filesystem::path::~path((std::filesystem::path *)lpName);
    }
  }
  result = wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v12 = *(_QWORD *)(a1 + 56);
  if ( v12 )
  {
    LOBYTE(v11) = v12 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 32LL))(v12, v11);
    *(_QWORD *)(a1 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18045cb3c  mov     [rsp-8+arg_8], rbx
0x18045cb41  mov     [rsp-8+arg_10], rsi
0x18045cb46  push    rbp
0x18045cb47  push    rdi
0x18045cb48  push    r14
0x18045cb4a  lea     rbp, [rsp-47h]
0x18045cb4f  sub     rsp, 0E0h
0x18045cb56  mov     rax, cs:__security_cookie
0x18045cb5d  xor     rax, rsp
0x18045cb60  mov     [rbp+57h+var_20], rax
0x18045cb64  mov     rdi, rcx
0x18045cb67  mov     [rbp+57h+var_68], rcx
0x18045cb6b  xor     r14d, r14d
0x18045cb6e  mov     [rbp+57h+hKey], r14
0x18045cb72  lea     rcx, [rbp+57h+hKey]
0x18045cb76  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18045cb7b  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18045cb80  mov     r9d, 20019h; samDesired
0x18045cb86  lea     r8d, [r14+1]; ulOptions
0x18045cb8a  lea     rdx, aSoftwareMicros_51; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18045cb91  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18045cb98  call    cs:__imp_RegOpenKeyExW
0x18045cb9e  test    eax, eax
0x18045cba0  jnz     loc_18045CCF4
0x18045cba6  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18045cbaa  mov     [rbp+57h+cSubKeys], r14d
0x18045cbae  mov     [rsp+0F0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18045cbb3  mov     [rsp+0F0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18045cbb8  mov     [rsp+0F0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18045cbbd  mov     [rsp+0F0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18045cbc2  mov     [rsp+0F0h+lpcValues], r14; lpcValues
0x18045cbc7  mov     [rsp+0F0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18045cbcc  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18045cbd0  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18045cbd5  lea     rax, [rbp+57h+cSubKeys]
0x18045cbd9  mov     [rsp+0F0h+phkResult], rax; lpcSubKeys
0x18045cbde  xor     r9d, r9d; lpReserved
0x18045cbe1  xor     r8d, r8d; lpcchClass
0x18045cbe4  xor     edx, edx; lpClass
0x18045cbe6  mov     rcx, [rbp+57h+hKey]; hKey
0x18045cbea  call    cs:__imp_RegQueryInfoKeyW
0x18045cbf0  test    eax, eax
0x18045cbf2  jnz     loc_18045CCF4
0x18045cbf8  lea     rcx, [rbp+57h+lpName]
0x18045cbfc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18045cc01  nop
0x18045cc02  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x18045cc05  inc     edx
0x18045cc07  lea     rcx, [rbp+57h+lpName]
0x18045cc0b  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18045cc10  mov     eax, [rbp+57h+var_30]
0x18045cc13  lea     esi, [rax+rax]
0x18045cc16  mov     ebx, r14d
0x18045cc19  cmp     [rbp+57h+cSubKeys], r14d
0x18045cc1d  jbe     loc_18045CCEA
0x18045cc23  lea     r8, [rbp+57h+lpName]
0x18045cc27  cmp     [rbp+57h+var_28], 7
0x18045cc2c  cmova   r8, [rbp+57h+lpName]; lpName
0x18045cc31  mov     r9d, esi; cchName
0x18045cc34  mov     edx, ebx; dwIndex
0x18045cc36  mov     rcx, [rbp+57h+hKey]; hKey
0x18045cc3a  call    cs:__imp_RegEnumKeyW
0x18045cc40  test    eax, eax
0x18045cc42  jnz     loc_18045CCDF
0x18045cc48  lea     rdx, [rbp+57h+lpName]
0x18045cc4c  lea     rcx, [rbp+57h+var_60]
0x18045cc50  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18045cc55  mov     rdx, rax; lpSubKey
0x18045cc58  mov     rcx, [rbp+57h+hKey]; hKey
0x18045cc5c  call    ?IsValidWebViewKey@@YA_NPEAUHKEY__@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; IsValidWebViewKey(HKEY__ *,std::wstring)
0x18045cc61  test    al, al
0x18045cc63  jz      short loc_18045CCCD
0x18045cc65  mov     [rbp+57h+var_78], r14
0x18045cc69  lea     rcx, [rbp+57h+var_78]
0x18045cc6d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18045cc72  lea     rdx, [rbp+57h+lpName]
0x18045cc76  cmp     [rbp+57h+var_28], 7
0x18045cc7b  cmova   rdx, [rbp+57h+lpName]; lpSubKey
0x18045cc80  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18045cc85  mov     r9d, 20019h; samDesired
0x18045cc8b  xor     r8d, r8d; ulOptions
0x18045cc8e  mov     rcx, [rbp+57h+hKey]; hKey
0x18045cc92  call    cs:__imp_RegOpenKeyExW
0x18045cc98  test    eax, eax
0x18045cc9a  jnz     short loc_18045CCC2
0x18045cc9c  mov     rax, [rbp+57h+var_78]
0x18045cca0  mov     [rbp+57h+var_70], rax
0x18045cca4  mov     rcx, [rdi+38h]
0x18045cca8  test    rcx, rcx
0x18045ccab  jz      loc_18045CD41
0x18045ccb1  mov     rax, [rcx]
0x18045ccb4  lea     rdx, [rbp+57h+var_70]
0x18045ccb8  mov     rax, [rax+10h]
0x18045ccbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045ccc1  nop
0x18045ccc2  lea     rcx, [rbp+57h+var_78]
0x18045ccc6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18045cccb  jmp     short loc_18045CCDF
0x18045cccd  lea     rdx, [rbp+57h+lpName]; lpSubKey
0x18045ccd1  mov     rcx, [rbp+57h+hKey]; hKey
0x18045ccd5  call    RegistryHelpers__TryDeleteVolatileRegistryKey
0x18045ccda  dec     [rbp+57h+cSubKeys]
0x18045ccdd  dec     ebx
0x18045ccdf  inc     ebx
0x18045cce1  cmp     ebx, [rbp+57h+cSubKeys]
0x18045cce4  jb      loc_18045CC23
0x18045ccea  lea     rcx, [rbp+57h+lpName]; this
0x18045ccee  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045ccf3  nop
0x18045ccf4  lea     rcx, [rbp+57h+hKey]
0x18045ccf8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18045ccfd  nop
0x18045ccfe  mov     rcx, [rdi+38h]
0x18045cd02  test    rcx, rcx
0x18045cd05  jz      short loc_18045CD1D
0x18045cd07  mov     rax, [rcx]
0x18045cd0a  cmp     rcx, rdi
0x18045cd0d  setnz   dl
0x18045cd10  mov     rax, [rax+20h]
0x18045cd14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045cd19  mov     [rdi+38h], r14
0x18045cd1d  mov     rcx, [rbp+57h+var_20]
0x18045cd21  xor     rcx, rsp; StackCookie
0x18045cd24  call    __security_check_cookie
0x18045cd29  lea     r11, [rsp+0F0h+var_10]
0x18045cd31  mov     rbx, [r11+28h]
0x18045cd35  mov     rsi, [r11+30h]
0x18045cd39  mov     rsp, r11
0x18045cd3c  pop     r14
0x18045cd3e  pop     rdi
0x18045cd3f  pop     rbp
0x18045cd40  retn
0x18045cd41  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18045cd47  nop
```
