# WpnGetDeviceVersionFromRegistry(unsigned __int64 *)

- ea: `0x180084cf0`
- end: `0x180084f80`
- name: `?WpnGetDeviceVersionFromRegistry@@YAXPEA_K@Z`
- size: `656`
- prototype: `void __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e2b0`

## callees

- `0x180007440`
- `0x180008294`
- `0x180008b50`
- `0x18000a518`
- `0x18000d06c`
- `0x18000fe0c`
- `0x18001d108`
- `0x180033254`
- `0x180033910`
- `0x18004e768`
- `0x180063934`
- `0x180066964`
- `0x180084598`
- `0x180084cf0`
- `0x18008548c`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180084f16`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180084f16`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180084f03`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180084f03`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x180084ef0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x180084ef0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180084ec0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180084ec0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084de7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084e8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084de7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084e8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084d8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084d8f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180084d48`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180084d48`

## string_xrefs

- `0x180084d59`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180084da0`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180084ea0`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WpnGetDeviceVersionFromRegistry(unsigned __int64 *a1)
{
  void *v2; // rbx
  int PersistedRegistryLocationW; // eax
  LSTATUS v4; // eax
  char *v5; // rdi
  unsigned __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  unsigned int ValueW; // eax
  _DWORD *v10; // rdi
  const wchar_t *v11; // rbx
  unsigned __int64 v12; // rax
  int phkResult; // [rsp+20h] [rbp-49h]
  unsigned int phkResulta; // [rsp+20h] [rbp-49h]
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  int v16; // [rsp+44h] [rbp-25h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-21h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-19h] BYREF
  void *v19; // [rsp+58h] [rbp-11h]
  __int64 v20; // [rsp+60h] [rbp-9h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-1h] BYREF
  void *v22; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v23[32]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v16 = 260;
  v2 = operator new[](0x208u);
  v22 = v2;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"DeviceInfoDeviceVersion",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo\\DeviceVersion",
                                 v2,
                                 260);
  if ( PersistedRegistryLocationW < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x760,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)&v16);
  hkey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v2, 0, 0x20019u, &hkey);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x768,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
  pcbData = 0;
  if ( RegGetValueW(hkey, 0, L"DeviceVersionValue", 2u, 0, 0, &pcbData) || !pcbData )
  {
    *a1 = 1;
    WpnSaveDeviceVersionToRegistry(1);
    goto LABEL_23;
  }
  std::vector<std::wstring>::vector<std::wstring>(&pvData);
  v5 = (char *)v19;
  v6 = ((_BYTE *)v19 - (_BYTE *)pvData) >> 1;
  if ( pcbData < v6 )
  {
    v7 = (char *)pvData + 2 * pcbData;
LABEL_13:
    v19 = v7;
    goto LABEL_14;
  }
  if ( pcbData > v6 )
  {
    if ( pcbData <= (unsigned __int64)((v20 - (__int64)pvData) >> 1) )
    {
      v8 = 2 * (pcbData - v6);
      memset_0(v19, 0, v8);
      v7 = &v5[v8];
      goto LABEL_13;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pvData, pcbData);
  }
LABEL_14:
  ValueW = RegGetValueW(hkey, 0, L"DeviceVersionValue", 2u, 0, pvData, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x778,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)ValueW,
      phkResulta);
  std::wstring::wstring(v23, pvData);
  v10 = (_DWORD *)_o__errno();
  v11 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  EndPtr = 0;
  *v10 = 0;
  v12 = wcstoull(v11, &EndPtr, 10);
  if ( v11 == EndPtr )
  {
    std::_Xinvalid_argument("invalid stoull argument");
    __debugbreak();
  }
  if ( *v10 == 34 )
  {
    std::_Xout_of_range("stoull argument out of range");
    __debugbreak();
  }
  *a1 = v12;
  std::wstring::_Tidy_deallocate(v23);
  if ( pvData )
    std::_Deallocate<16>(pvData, (const struct std::nothrow_t *)(2 * ((v20 - (__int64)pvData) >> 1)));
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v22);
}

```

## disassembly

```asm
0x180084cf0  push    rbp
0x180084cf2  push    rbx
0x180084cf3  push    rsi
0x180084cf4  push    rdi
0x180084cf5  lea     rbp, [rsp-3Fh]
0x180084cfa  sub     rsp, 0A8h
0x180084d01  mov     rax, cs:__security_cookie
0x180084d08  xor     rax, rsp
0x180084d0b  mov     [rbp+57h+var_28], rax
0x180084d0f  mov     rsi, rcx
0x180084d12  mov     [rbp+57h+var_7C], 104h
0x180084d19  mov     ecx, 208h; unsigned __int64
0x180084d1e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180084d23  mov     rbx, rax
0x180084d26  mov     [rbp+57h+var_50], rax
0x180084d2a  lea     rax, [rbp+57h+var_7C]
0x180084d2e  mov     [rsp+0C0h+phkResult], rax; int
0x180084d33  mov     r9d, [rbp+57h+var_7C]
0x180084d37  mov     r8, rbx
0x180084d3a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180084d41  lea     rcx, aDeviceinfodevi; "DeviceInfoDeviceVersion"
0x180084d48  call    cs:__imp_GetPersistedRegistryLocationW
0x180084d4e  mov     rcx, [rbp+5Fh]; this
0x180084d52  test    eax, eax
0x180084d54  jns     short loc_180084D6B
0x180084d56  mov     r9d, eax; char *
0x180084d59  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084d60  mov     edx, 760h; void *
0x180084d65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084d6b  mov     [rbp+57h+hkey], 0
0x180084d73  lea     rax, [rbp+57h+hkey]
0x180084d77  mov     [rsp+0C0h+phkResult], rax; int
0x180084d7c  mov     r9d, 20019h; samDesired
0x180084d82  xor     r8d, r8d; ulOptions
0x180084d85  mov     rdx, rbx; lpSubKey
0x180084d88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084d8f  call    cs:__imp_RegOpenKeyExW
0x180084d95  mov     rcx, [rbp+5Fh]; this
0x180084d99  test    eax, eax
0x180084d9b  jns     short loc_180084DB2
0x180084d9d  mov     r9d, eax; char *
0x180084da0  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084da7  mov     edx, 768h; void *
0x180084dac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084db2  mov     [rbp+57h+var_80], 0
0x180084db9  lea     rax, [rbp+57h+var_80]
0x180084dbd  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180084dc2  mov     [rsp+0C0h+pvData], 0; pvData
0x180084dcb  mov     [rsp+0C0h+phkResult], 0; pdwType
0x180084dd4  mov     r9d, 2; dwFlags
0x180084dda  lea     r8, aDeviceversionv; "DeviceVersionValue"
0x180084de1  xor     edx, edx; lpSubKey
0x180084de3  mov     rcx, [rbp+57h+hkey]; hkey
0x180084de7  call    cs:__imp_RegGetValueW
0x180084ded  test    eax, eax
0x180084def  jnz     loc_180084F47
0x180084df5  cmp     [rbp+57h+var_80], eax
0x180084df8  jz      loc_180084F47
0x180084dfe  lea     rcx, [rbp+57h+var_70]
0x180084e02  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180084e07  nop
0x180084e08  mov     ebx, [rbp+57h+var_80]
0x180084e0b  mov     rdi, [rbp+57h+var_68]
0x180084e0f  mov     rdx, [rbp+57h+var_70]
0x180084e13  mov     rcx, rdi
0x180084e16  sub     rcx, rdx
0x180084e19  sar     rcx, 1
0x180084e1c  cmp     rbx, rcx
0x180084e1f  jnb     short loc_180084E27
0x180084e21  lea     rax, [rdx+rbx*2]
0x180084e25  jmp     short loc_180084E5D
0x180084e27  jbe     short loc_180084E61
0x180084e29  mov     rax, [rbp+57h+var_60]
0x180084e2d  sub     rax, rdx
0x180084e30  sar     rax, 1
0x180084e33  cmp     rbx, rax
0x180084e36  jbe     short loc_180084E46
0x180084e38  mov     rdx, rbx
0x180084e3b  lea     rcx, [rbp+57h+var_70]
0x180084e3f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180084e44  jmp     short loc_180084E61
0x180084e46  sub     rbx, rcx
0x180084e49  add     rbx, rbx
0x180084e4c  mov     r8, rbx; Size
0x180084e4f  xor     edx, edx; Val
0x180084e51  mov     rcx, rdi; void *
0x180084e54  call    memset_0
0x180084e59  lea     rax, [rbx+rdi]
0x180084e5d  mov     [rbp+57h+var_68], rax
0x180084e61  mov     rax, [rbp+57h+var_70]
0x180084e65  lea     rcx, [rbp+57h+var_80]
0x180084e69  mov     [rsp+0C0h+pcbData], rcx; pcbData
0x180084e6e  mov     [rsp+0C0h+pvData], rax; pvData
0x180084e73  mov     [rsp+0C0h+phkResult], 0; unsigned int
0x180084e7c  mov     r9d, 2; dwFlags
0x180084e82  lea     r8, aDeviceversionv; "DeviceVersionValue"
0x180084e89  xor     edx, edx; lpSubKey
0x180084e8b  mov     rcx, [rbp+57h+hkey]; hkey
0x180084e8f  call    cs:__imp_RegGetValueW
0x180084e95  mov     rcx, [rbp+5Fh]; this
0x180084e99  test    eax, eax
0x180084e9b  jz      short loc_180084EB2
0x180084e9d  mov     r9d, eax; char *
0x180084ea0  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084ea7  mov     edx, 778h; void *
0x180084eac  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180084eb2  mov     rdx, [rbp+57h+var_70]
0x180084eb6  lea     rcx, [rbp+57h+var_48]
0x180084eba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180084ebf  nop
0x180084ec0  call    cs:__imp__o__errno
0x180084ec6  mov     rdi, rax
0x180084ec9  lea     rcx, [rbp+57h+var_48]
0x180084ecd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180084ed2  mov     rbx, rax
0x180084ed5  mov     [rbp+57h+EndPtr], 0
0x180084edd  mov     dword ptr [rdi], 0
0x180084ee3  mov     r8d, 0Ah; Radix
0x180084ee9  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x180084eed  mov     rcx, rax; String
0x180084ef0  call    cs:__imp_wcstoull
0x180084ef6  cmp     rbx, [rbp+57h+EndPtr]
0x180084efa  jnz     short loc_180084F0A
0x180084efc  lea     rcx, aInvalidStoullA; "invalid stoull argument"
0x180084f03  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x180084f09  int     3; Trap to Debugger
0x180084f0a  cmp     dword ptr [rdi], 22h ; '"'
0x180084f0d  jnz     short loc_180084F1D
0x180084f0f  lea     rcx, aStoullArgument; "stoull argument out of range"
0x180084f16  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180084f1c  int     3; Trap to Debugger
0x180084f1d  mov     [rsi], rax
0x180084f20  lea     rcx, [rbp+57h+var_48]
0x180084f24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180084f29  nop
0x180084f2a  mov     rcx, [rbp+57h+var_70]
0x180084f2e  test    rcx, rcx
0x180084f31  jz      short loc_180084F55
0x180084f33  mov     rdx, [rbp+57h+var_60]
0x180084f37  sub     rdx, rcx
0x180084f3a  sar     rdx, 1
0x180084f3d  add     rdx, rdx
0x180084f40  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180084f45  jmp     short loc_180084F55
0x180084f47  mov     ecx, 1; unsigned __int64
0x180084f4c  mov     [rsi], rcx
0x180084f4f  call    ?WpnSaveDeviceVersionToRegistry@@YAX_K@Z; WpnSaveDeviceVersionToRegistry(unsigned __int64)
0x180084f54  nop
0x180084f55  lea     rcx, [rbp+57h+hkey]
0x180084f59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180084f5e  nop
0x180084f5f  lea     rcx, [rbp+57h+var_50]
0x180084f63  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180084f68  mov     rcx, [rbp+57h+var_28]
0x180084f6c  xor     rcx, rsp; StackCookie
0x180084f6f  call    __security_check_cookie
0x180084f74  add     rsp, 0A8h
0x180084f7b  pop     rdi
0x180084f7c  pop     rsi
0x180084f7d  pop     rbx
0x180084f7e  pop     rbp
0x180084f7f  retn
```
