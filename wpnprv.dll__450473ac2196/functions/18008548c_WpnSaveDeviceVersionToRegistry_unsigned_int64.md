# WpnSaveDeviceVersionToRegistry(unsigned __int64)

- ea: `0x18008548c`
- end: `0x180085601`
- name: `?WpnSaveDeviceVersionToRegistry@@YAX_K@Z`
- size: `373`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180074998`
- `0x180084cf0`

## callees

- `0x180007440`
- `0x180008b50`
- `0x18000d06c`
- `0x18000fe0c`
- `0x18001d108`
- `0x180033910`
- `0x180063934`
- `0x1800843ec`
- `0x18008548c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008553c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008553c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800855a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800855a9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800854e6`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800854e6`

## string_xrefs

- `0x1800854f7`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18008554d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800855ba`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WpnSaveDeviceVersionToRegistry(__int64 a1)
{
  void *v2; // rbx
  int PersistedRegistryLocationW; // eax
  LSTATUS v4; // eax
  const BYTE *v5; // rdx
  __int64 v6; // rax
  LSTATUS v7; // eax
  int dwOptions; // [rsp+20h] [rbp-39h]
  int dwOptionsa; // [rsp+20h] [rbp-39h]
  int v10; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  void *v12; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v13[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v10 = 260;
  v2 = operator new[](0x208u);
  v12 = v2;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"DeviceInfoDeviceVersion",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo\\DeviceVersion",
                                 v2,
                                 260);
  if ( PersistedRegistryLocationW < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)&v10);
  hKey = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v4,
      dwOptions);
  std::_Integral_to_string<unsigned short,unsigned __int64>(v13, a1);
  v5 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&v5[2 * v6] );
  v7 = RegSetValueExW(hKey, L"DeviceVersionValue", 0, 1u, v5, 2 * v6 + 2);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x753,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      dwOptionsa);
  std::wstring::_Tidy_deallocate(v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v12);
}

```

## disassembly

```asm
0x18008548c  push    rbp
0x18008548e  push    rbx
0x18008548f  push    rsi
0x180085490  push    rdi
0x180085491  lea     rbp, [rsp-3Fh]
0x180085496  sub     rsp, 98h
0x18008549d  mov     rax, cs:__security_cookie
0x1800854a4  xor     rax, rsp
0x1800854a7  mov     [rbp+57h+var_28], rax
0x1800854ab  mov     rdi, rcx
0x1800854ae  xor     esi, esi
0x1800854b0  mov     [rbp+57h+var_60], 104h
0x1800854b7  mov     ecx, 208h; unsigned __int64
0x1800854bc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800854c1  mov     rbx, rax
0x1800854c4  mov     [rbp+57h+var_50], rax
0x1800854c8  lea     rax, [rbp+57h+var_60]
0x1800854cc  mov     qword ptr [rsp+0B0h+dwOptions], rax; int
0x1800854d1  mov     r9d, [rbp+57h+var_60]
0x1800854d5  mov     r8, rbx
0x1800854d8  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800854df  lea     rcx, aDeviceinfodevi; "DeviceInfoDeviceVersion"
0x1800854e6  call    cs:__imp_GetPersistedRegistryLocationW
0x1800854ec  mov     rcx, [rbp+5Fh]; this
0x1800854f0  test    eax, eax
0x1800854f2  jns     short loc_180085509
0x1800854f4  mov     r9d, eax; char *
0x1800854f7  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800854fe  mov     edx, 73Ch; void *
0x180085503  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085509  mov     [rbp+57h+hKey], rsi
0x18008550d  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x180085512  lea     rax, [rbp+57h+hKey]
0x180085516  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18008551b  mov     [rsp+0B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180085520  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x180085528  mov     [rsp+0B0h+dwOptions], esi; int
0x18008552c  xor     r9d, r9d; lpClass
0x18008552f  xor     r8d, r8d; Reserved
0x180085532  mov     rdx, rbx; lpSubKey
0x180085535  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008553c  call    cs:__imp_RegCreateKeyExW
0x180085542  mov     rcx, [rbp+5Fh]; this
0x180085546  test    eax, eax
0x180085548  jns     short loc_18008555F
0x18008554a  mov     r9d, eax; char *
0x18008554d  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085554  mov     edx, 748h; void *
0x180085559  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008555f  mov     rdx, rdi
0x180085562  lea     rcx, [rbp+57h+var_48]
0x180085566  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18008556b  nop
0x18008556c  lea     rcx, [rbp+57h+var_48]
0x180085570  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085575  mov     rdx, rax
0x180085578  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008557c  inc     rax
0x18008557f  cmp     [rdx+rax*2], si
0x180085583  jnz     short loc_18008557C
0x180085585  lea     eax, ds:2[rax*2]
0x18008558c  mov     [rsp+0B0h+samDesired], eax; cbData
0x180085590  mov     qword ptr [rsp+0B0h+dwOptions], rdx; int
0x180085595  mov     r9d, 1; dwType
0x18008559b  xor     r8d, r8d; Reserved
0x18008559e  lea     rdx, aDeviceversionv; "DeviceVersionValue"
0x1800855a5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800855a9  call    cs:__imp_RegSetValueExW
0x1800855af  mov     rcx, [rbp+5Fh]; this
0x1800855b3  test    eax, eax
0x1800855b5  jns     short loc_1800855CC
0x1800855b7  mov     r9d, eax; char *
0x1800855ba  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800855c1  mov     edx, 753h; void *
0x1800855c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800855cc  lea     rcx, [rbp+57h+var_48]
0x1800855d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800855d5  nop
0x1800855d6  lea     rcx, [rbp+57h+hKey]
0x1800855da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800855df  nop
0x1800855e0  lea     rcx, [rbp+57h+var_50]
0x1800855e4  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1800855e9  mov     rcx, [rbp+57h+var_28]
0x1800855ed  xor     rcx, rsp; StackCookie
0x1800855f0  call    __security_check_cookie
0x1800855f5  add     rsp, 98h
0x1800855fc  pop     rdi
0x1800855fd  pop     rsi
0x1800855fe  pop     rbx
0x1800855ff  pop     rbp
0x180085600  retn
```
