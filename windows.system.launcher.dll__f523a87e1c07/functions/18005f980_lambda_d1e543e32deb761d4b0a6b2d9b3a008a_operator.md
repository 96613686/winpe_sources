# _lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()

- ea: `0x18005f980`
- end: `0x18005fb0e`
- name: `_lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801044a0`

## callees

- `0x18001d10c`
- `0x18003440c`
- `0x18003a0d0`
- `0x18003f59c`
- `0x180043a38`
- `0x18005f980`
- `0x18005fb14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fa37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005faa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fa37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005faa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fa02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fa69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fa02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fa69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fa59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fa59`

## string_xrefs

- `0x18005f9b1`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()(__int64 a1)
{
  unsigned int v2; // ebx
  HKEY v4; // rbx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+28h] BYREF
  char v10; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         L"Configs");
  if ( (v2 & 0x80000000) != 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  v4 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
    RegCloseKey(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
  }
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    if ( lpSubKey[0] )
      CoTaskMemFree((LPVOID)lpSubKey[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v6 = RegOpenKeyExW(hKey, **(LPCWSTR **)(a1 + 8), 0, 0x20019u, &phkResult);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  **(_BYTE **)(a1 + 16) = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18005f980  push    rbp
0x18005f982  push    rbx
0x18005f983  push    rsi
0x18005f984  mov     rbp, rsp
0x18005f987  sub     rsp, 50h
0x18005f98b  mov     rsi, rcx
0x18005f98e  mov     [rbp+hKey], 0
0x18005f996  mov     [rbp+lpSubKey], 0
0x18005f99e  mov     [rbp+var_18], 0
0x18005f9a6  mov     [rbp+var_10], 0
0x18005f9ae  mov     r8, [rcx]
0x18005f9b1  lea     r9, aConfigs; "Configs"
0x18005f9b8  mov     r8, [r8+8]
0x18005f9bc  lea     rdx, aSS; "%s\\%s"
0x18005f9c3  lea     rcx, [rbp+lpSubKey]
0x18005f9c7  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18005f9cc  mov     ebx, eax
0x18005f9ce  test    eax, eax
0x18005f9d0  jns     short loc_18005F9ED
0x18005f9d2  lea     rcx, [rbp+lpSubKey]
0x18005f9d6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005f9db  nop
0x18005f9dc  lea     rcx, [rbp+hKey]
0x18005f9e0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005f9e5  nop
0x18005f9e6  mov     eax, ebx
0x18005f9e8  jmp     loc_18005FB06
0x18005f9ed  mov     rbx, [rbp+hKey]
0x18005f9f1  test    rbx, rbx
0x18005f9f4  jz      short loc_18005FA12
0x18005f9f6  lea     rcx, [rbp+arg_10]; this
0x18005f9fa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005f9ff  mov     rcx, rbx; hKey
0x18005fa02  call    cs:__imp_RegCloseKey
0x18005fa08  lea     rcx, [rbp+arg_10]; this
0x18005fa0c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005fa11  nop
0x18005fa12  mov     [rbp+hKey], 0
0x18005fa1a  lea     rax, [rbp+hKey]
0x18005fa1e  mov     [rsp+50h+phkResult], rax; phkResult
0x18005fa23  mov     r9d, 20019h; samDesired
0x18005fa29  xor     r8d, r8d; ulOptions
0x18005fa2c  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18005fa30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005fa37  call    cs:__imp_RegOpenKeyExW
0x18005fa3d  mov     ebx, eax
0x18005fa3f  test    eax, eax
0x18005fa41  jz      short loc_18005FA75
0x18005fa43  jle     short loc_18005FA4E
0x18005fa45  movzx   ebx, ax
0x18005fa48  or      ebx, 80070000h
0x18005fa4e  cmp     [rbp+lpSubKey], 0
0x18005fa53  jz      short loc_18005FA60
0x18005fa55  mov     rcx, [rbp+lpSubKey]; pv
0x18005fa59  call    cs:__imp_CoTaskMemFree
0x18005fa5f  nop
0x18005fa60  mov     rcx, [rbp+hKey]; hKey
0x18005fa64  test    rcx, rcx
0x18005fa67  jz      short loc_18005FA70
0x18005fa69  call    cs:__imp_RegCloseKey
0x18005fa6f  nop
0x18005fa70  jmp     loc_18005F9E6
0x18005fa75  mov     [rbp+arg_8], 0
0x18005fa7d  xor     edx, edx
0x18005fa7f  lea     rcx, [rbp+arg_8]
0x18005fa83  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005fa88  mov     rdx, [rsi+8]
0x18005fa8c  lea     rax, [rbp+arg_8]
0x18005fa90  mov     [rsp+50h+phkResult], rax; phkResult
0x18005fa95  mov     r9d, 20019h; samDesired
0x18005fa9b  xor     r8d, r8d; ulOptions
0x18005fa9e  mov     rdx, [rdx]; lpSubKey
0x18005faa1  mov     rcx, [rbp+hKey]; hKey
0x18005faa5  call    cs:__imp_RegOpenKeyExW
0x18005faab  mov     ebx, eax
0x18005faad  test    eax, eax
0x18005faaf  jz      short loc_18005FADF
0x18005fab1  jle     short loc_18005FABC
0x18005fab3  movzx   ebx, ax
0x18005fab6  or      ebx, 80070000h
0x18005fabc  lea     rcx, [rbp+arg_8]
0x18005fac0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fac5  nop
0x18005fac6  lea     rcx, [rbp+lpSubKey]
0x18005faca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005facf  nop
0x18005fad0  lea     rcx, [rbp+hKey]
0x18005fad4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fad9  nop
0x18005fada  jmp     loc_18005F9E6
0x18005fadf  mov     rax, [rsi+10h]
0x18005fae3  mov     byte ptr [rax], 1
0x18005fae6  lea     rcx, [rbp+arg_8]
0x18005faea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005faef  nop
0x18005faf0  lea     rcx, [rbp+lpSubKey]
0x18005faf4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005faf9  nop
0x18005fafa  lea     rcx, [rbp+hKey]
0x18005fafe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fb03  nop
0x18005fb04  xor     eax, eax
0x18005fb06  add     rsp, 50h
0x18005fb0a  pop     rsi
0x18005fb0b  pop     rbx
0x18005fb0c  pop     rbp
0x18005fb0d  retn
```
