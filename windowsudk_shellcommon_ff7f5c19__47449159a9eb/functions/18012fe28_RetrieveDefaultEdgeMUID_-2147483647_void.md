# RetrieveDefaultEdgeMUID<-2147483647>(void)

- ea: `0x18012fe28`
- end: `0x180130013`
- name: `??$RetrieveDefaultEdgeMUID@$0?HPPPPPPP@@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d7808`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x18002522c`
- `0x180026860`
- `0x1800d971c`
- `0x18012fe28`
- `0x18013001c`
- `0x18015cb00`
- `0x18015d868`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012fe84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012febc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012fe84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012febc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012ff04`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012ff04`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012ff5c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012ff5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetrieveDefaultEdgeMUID<-2147483647>(__int64 a1)
{
  HKEY *phkResult; // rax
  HKEY *v3; // rax
  DWORD v4; // edi
  HKEY v6; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName[3]; // [rsp+74h] [rbp-8Ch] BYREF
  _BYTE v10[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v11; // [rsp+90h] [rbp-70h]
  WCHAR ValueName[256]; // [rsp+A0h] [rbp-60h] BYREF

  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Feeds", 0, 0x20019u, phkResult) )
    goto LABEL_13;
  cValues = 0;
  v6 = 0;
  v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v6);
  if ( !RegOpenKeyExW(hKey, L"MUID", 0, 0x20019u, v3)
    && !RegQueryInfoKeyW(v6, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0)
    && cValues > 1 )
  {
    v4 = 0;
    memset_0(ValueName, 0, sizeof(ValueName));
    while ( 1 )
    {
      cchValueName[0] = 256;
      if ( RegEnumValueW(v6, v4, ValueName, cchValueName, 0, 0, 0, 0) )
        goto LABEL_12;
      RegGetString(v10, v6, 0, ValueName);
      if ( v11 )
        goto LABEL_9;
      std::filesystem::path::~path((std::filesystem::path *)v10);
      ++v4;
    }
  }
  RegGetString(v10, hKey, 0, L"EdgeMUID");
  if ( !v11 )
  {
    std::filesystem::path::~path((std::filesystem::path *)v10);
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
LABEL_13:
    std::wstring::wstring(a1);
    goto LABEL_14;
  }
LABEL_9:
  std::wstring::wstring(a1, v10);
  std::filesystem::path::~path((std::filesystem::path *)v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x18012fe28  push    rbp
0x18012fe2a  push    rbx
0x18012fe2b  push    rsi
0x18012fe2c  push    rdi
0x18012fe2d  lea     rbp, [rsp-1B8h]
0x18012fe35  sub     rsp, 2B8h
0x18012fe3c  mov     rax, cs:__security_cookie
0x18012fe43  xor     rax, rsp
0x18012fe46  mov     [rbp+1D0h+var_30], rax
0x18012fe4d  mov     rbx, rcx
0x18012fe50  mov     [rsp+2D0h+hKey], rcx
0x18012fe55  xor     esi, esi
0x18012fe57  mov     [rsp+2D0h+hKey], rsi
0x18012fe5c  lea     rcx, [rsp+2D0h+hKey]
0x18012fe61  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18012fe66  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18012fe6b  mov     edi, 20019h
0x18012fe70  mov     r9d, edi; samDesired
0x18012fe73  xor     r8d, r8d; ulOptions
0x18012fe76  lea     rdx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18012fe7d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18012fe84  call    cs:__imp_RegOpenKeyExW
0x18012fe8a  test    eax, eax
0x18012fe8c  jnz     loc_18012FFE2
0x18012fe92  mov     [rsp+2D0h+cValues], esi
0x18012fe96  mov     [rsp+2D0h+var_270], rsi
0x18012fe9b  lea     rcx, [rsp+2D0h+var_270]
0x18012fea0  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18012fea5  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18012feaa  mov     r9d, edi; samDesired
0x18012fead  xor     r8d, r8d; ulOptions
0x18012feb0  lea     rdx, aMuid; "MUID"
0x18012feb7  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18012febc  call    cs:__imp_RegOpenKeyExW
0x18012fec2  test    eax, eax
0x18012fec4  jnz     loc_18012FFB0
0x18012feca  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18012fecf  mov     [rsp+2D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18012fed4  mov     [rsp+2D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18012fed9  mov     [rsp+2D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18012fede  lea     rax, [rsp+2D0h+cValues]
0x18012fee3  mov     [rsp+2D0h+lpcValues], rax; lpcValues
0x18012fee8  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18012feed  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18012fef2  mov     [rsp+2D0h+phkResult], rsi; lpcSubKeys
0x18012fef7  xor     r9d, r9d; lpReserved
0x18012fefa  xor     r8d, r8d; lpcchClass
0x18012fefd  xor     edx, edx; lpClass
0x18012feff  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18012ff04  call    cs:__imp_RegQueryInfoKeyW
0x18012ff0a  test    eax, eax
0x18012ff0c  jnz     loc_18012FFB0
0x18012ff12  cmp     [rsp+2D0h+cValues], 1
0x18012ff17  jbe     loc_18012FFB0
0x18012ff1d  mov     edi, esi
0x18012ff1f  xor     edx, edx; Val
0x18012ff21  mov     r8d, 200h; Size
0x18012ff27  lea     rcx, [rbp+1D0h+ValueName]; void *
0x18012ff2b  call    memset_0
0x18012ff30  mov     [rsp+2D0h+cchValueName], 100h
0x18012ff38  mov     [rsp+2D0h+lpcValues], rsi; lpcbData
0x18012ff3d  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpData
0x18012ff42  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpType
0x18012ff47  mov     [rsp+2D0h+phkResult], rsi; lpReserved
0x18012ff4c  lea     r9, [rsp+2D0h+cchValueName]; lpcchValueName
0x18012ff51  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x18012ff55  mov     edx, edi; dwIndex
0x18012ff57  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18012ff5c  call    cs:__imp_RegEnumValueW
0x18012ff62  test    eax, eax
0x18012ff64  jnz     short loc_18012FFD8
0x18012ff66  lea     r9, [rbp+1D0h+ValueName]
0x18012ff6a  xor     r8d, r8d
0x18012ff6d  mov     rdx, [rsp+2D0h+var_270]
0x18012ff72  lea     rcx, [rbp+1D0h+var_250]
0x18012ff76  call    ?RegGetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHKEY__@@PEB_W1@Z; RegGetString(HKEY__ *,wchar_t const *,wchar_t const *)
0x18012ff7b  cmp     [rbp+1D0h+var_240], rsi
0x18012ff7f  jnz     short loc_18012FF8E
0x18012ff81  lea     rcx, [rbp+1D0h+var_250]; this
0x18012ff85  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18012ff8a  inc     edi
0x18012ff8c  jmp     short loc_18012FF30
0x18012ff8e  lea     rdx, [rbp+1D0h+var_250]
0x18012ff92  mov     rcx, rbx
0x18012ff95  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18012ff9a  lea     rcx, [rbp+1D0h+var_250]; this
0x18012ff9e  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18012ffa3  nop
0x18012ffa4  lea     rcx, [rsp+2D0h+var_270]
0x18012ffa9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012ffae  jmp     short loc_18012FFEB
0x18012ffb0  lea     r9, aEdgemuid; "EdgeMUID"
0x18012ffb7  xor     r8d, r8d
0x18012ffba  mov     rdx, [rsp+2D0h+hKey]
0x18012ffbf  lea     rcx, [rbp+1D0h+var_250]
0x18012ffc3  call    ?RegGetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHKEY__@@PEB_W1@Z; RegGetString(HKEY__ *,wchar_t const *,wchar_t const *)
0x18012ffc8  cmp     [rbp+1D0h+var_240], rsi
0x18012ffcc  jnz     short loc_18012FF8E
0x18012ffce  lea     rcx, [rbp+1D0h+var_250]; this
0x18012ffd2  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18012ffd7  nop
0x18012ffd8  lea     rcx, [rsp+2D0h+var_270]
0x18012ffdd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012ffe2  mov     rcx, rbx
0x18012ffe5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012ffea  nop
0x18012ffeb  lea     rcx, [rsp+2D0h+hKey]
0x18012fff0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012fff5  mov     rax, rbx
0x18012fff8  mov     rcx, [rbp+1D0h+var_30]
0x18012ffff  xor     rcx, rsp; StackCookie
0x180130002  call    __security_check_cookie
0x180130007  add     rsp, 2B8h
0x18013000e  pop     rdi
0x18013000f  pop     rsi
0x180130010  pop     rbx
0x180130011  pop     rbp
0x180130012  retn
```
