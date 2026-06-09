# SetPreviousEndpointInRegistry(std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x1800849bc`
- end: `0x180084abf`
- name: `?SetPreviousEndpointInRegistry@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071e6c`

## callees

- `0x180007440`
- `0x180013294`
- `0x180013308`
- `0x180063934`
- `0x180066964`
- `0x1800849bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084a1e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084a1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a6d`

## string_xrefs

- `0x180084a30`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180084a7f`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SetPreviousEndpointInRegistry(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // eax
  const BYTE *v3; // rax
  unsigned int v4; // eax
  const char *v5; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  __int64 v9; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = a1;
  v9 = a1;
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  try
  {
    if ( v2 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x850,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)v2,
        dwOptions);
    v3 = (const BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr();
    v4 = RegSetValueExW(hKey, L"PreviousEndpoint", 0, 1u, v3, *(_DWORD *)(v1 + 16) + 1);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x858,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)v4,
        dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x85B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      v5);
    v1 = v9;
  }
  std::string::_Tidy_deallocate(v1);
}

```

## disassembly

```asm
0x1800849bc  mov     r11, rsp
0x1800849bf  push    rbx
0x1800849c0  sub     rsp, 70h
0x1800849c4  mov     rax, cs:__security_cookie
0x1800849cb  xor     rax, rsp
0x1800849ce  mov     [rsp+78h+var_18], rax
0x1800849d3  mov     rbx, rcx
0x1800849d6  mov     [r11-20h], rcx
0x1800849da  mov     qword ptr [r11-28h], 0
0x1800849e2  mov     qword ptr [r11-38h], 0
0x1800849ea  lea     rax, [r11-28h]
0x1800849ee  mov     [r11-40h], rax
0x1800849f2  mov     qword ptr [r11-48h], 0
0x1800849fa  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x180084a02  mov     [rsp+78h+dwOptions], 0; unsigned int
0x180084a0a  xor     r9d, r9d; lpClass
0x180084a0d  xor     r8d, r8d; Reserved
0x180084a10  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180084a17  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180084a1e  call    cs:__imp_RegCreateKeyExW
0x180084a24  mov     rcx, [rsp+78h]; this
0x180084a29  test    eax, eax
0x180084a2b  jz      short loc_180084A41
0x180084a2d  mov     r9d, eax; char *
0x180084a30  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084a37  mov     edx, 850h; void *
0x180084a3c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180084a41  mov     rcx, rbx
0x180084a44  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180084a49  mov     ecx, [rbx+10h]
0x180084a4c  mov     r9d, 1; dwType
0x180084a52  add     ecx, r9d
0x180084a55  mov     [rsp+78h+samDesired], ecx; cbData
0x180084a59  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int
0x180084a5e  xor     r8d, r8d; Reserved
0x180084a61  lea     rdx, aPreviousendpoi; "PreviousEndpoint"
0x180084a68  mov     rcx, [rsp+78h+hKey]; hKey
0x180084a6d  call    cs:__imp_RegSetValueExW
0x180084a73  mov     rcx, [rsp+78h]; this
0x180084a78  test    eax, eax
0x180084a7a  jz      short loc_180084A91
0x180084a7c  mov     r9d, eax; char *
0x180084a7f  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084a86  mov     edx, 858h; void *
0x180084a8b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180084a91  lea     rcx, [rsp+78h+hKey]
0x180084a96  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180084a9b  nop
0x180084a9c  jmp     short loc_180084AA3
0x180084a9e  mov     rbx, [rsp+78h+var_20]
0x180084aa3  mov     rcx, rbx
0x180084aa6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180084aab  nop
0x180084aac  mov     rcx, [rsp+78h+var_18]
0x180084ab1  xor     rcx, rsp; StackCookie
0x180084ab4  call    __security_check_cookie
0x180084ab9  add     rsp, 70h
0x180084abd  pop     rbx
0x180084abe  retn
```
