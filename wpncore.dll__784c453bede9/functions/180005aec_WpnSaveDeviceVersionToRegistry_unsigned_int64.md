# WpnSaveDeviceVersionToRegistry(unsigned __int64)

- ea: `0x180005aec`
- end: `0x180005c93`
- name: `?WpnSaveDeviceVersionToRegistry@@YAX_K@Z`
- size: `423`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000568c`

## callees

- `0x180005aec`
- `0x18000e5f4`
- `0x180013360`
- `0x18009bcbc`
- `0x1800b99f0`
- `0x1800bc49c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c6c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005b9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005b9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005c0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c62`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005b49`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005b49`

## string_xrefs

- `0x180005b5a`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180005bb0`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180005c1c`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WpnSaveDeviceVersionToRegistry()
{
  WCHAR *v0; // rbx
  int PersistedRegistryLocationW; // eax
  LSTATUS Key; // eax
  const BYTE *v3; // rdx
  __int64 v4; // rax
  LSTATUS v5; // eax
  int dwOptions; // [rsp+20h] [rbp-19h]
  int dwOptionsa; // [rsp+20h] [rbp-19h]
  int v8; // [rsp+50h] [rbp+17h] BYREF
  HKEY hKey[2]; // [rsp+58h] [rbp+1Fh] BYREF
  BYTE *lpData[3]; // [rsp+68h] [rbp+2Fh] BYREF
  unsigned __int64 v11; // [rsp+80h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v8 = 260;
  v0 = (WCHAR *)operator new[](0x208u);
  hKey[1] = (HKEY)v0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"DeviceInfoDeviceVersion",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo\\DeviceVersion",
                                 v0,
                                 260);
  if ( PersistedRegistryLocationW < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)&v8);
  hKey[0] = 0;
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0, 0, 0xF003Fu, 0, hKey, 0);
  if ( Key < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)Key,
      dwOptions);
  std::_Integral_to_string<unsigned short,unsigned __int64>(lpData);
  v3 = (const BYTE *)lpData;
  if ( v11 > 7 )
    v3 = lpData[0];
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&v3[2 * v4] );
  v5 = RegSetValueExW(hKey[0], L"DeviceVersionValue", 0, 1u, v3, 2 * v4 + 2);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x753,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v5,
      dwOptionsa);
  if ( v11 > 7 )
    std::_Deallocate<16>(lpData[0], 2 * v11 + 2);
  lpData[2] = 0;
  v11 = 7;
  LOWORD(lpData[0]) = 0;
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  CoTaskMemFree(v0);
}

```

## disassembly

```asm
0x180005aec  mov     [rsp-8+arg_0], rbx
0x180005af1  mov     [rsp-8+arg_8], rdi
0x180005af6  push    rbp
0x180005af7  lea     rbp, [rsp-57h]
0x180005afc  sub     rsp, 90h
0x180005b03  mov     rax, cs:__security_cookie
0x180005b0a  xor     rax, rsp
0x180005b0d  mov     [rbp+57h+var_8], rax
0x180005b11  xor     edi, edi
0x180005b13  mov     [rbp+57h+var_40], 104h
0x180005b1a  mov     ecx, 208h; unsigned __int64
0x180005b1f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005b24  mov     rbx, rax
0x180005b27  mov     [rbp+57h+var_30], rax
0x180005b2b  lea     rax, [rbp+57h+var_40]
0x180005b2f  mov     qword ptr [rsp+90h+dwOptions], rax; int
0x180005b34  mov     r9d, [rbp+57h+var_40]
0x180005b38  mov     r8, rbx
0x180005b3b  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180005b42  lea     rcx, aDeviceinfodevi; "DeviceInfoDeviceVersion"
0x180005b49  call    cs:__imp_GetPersistedRegistryLocationW
0x180005b4f  mov     rcx, [rbp+5Fh]; this
0x180005b53  test    eax, eax
0x180005b55  jns     short loc_180005B6C
0x180005b57  mov     r9d, eax; char *
0x180005b5a  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005b61  mov     edx, 73Ch; void *
0x180005b66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005b6c  mov     [rbp+57h+hKey], rdi
0x180005b70  mov     [rsp+90h+lpdwDisposition], rdi; lpdwDisposition
0x180005b75  lea     rax, [rbp+57h+hKey]
0x180005b79  mov     [rsp+90h+phkResult], rax; phkResult
0x180005b7e  mov     [rsp+90h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180005b83  mov     [rsp+90h+samDesired], 0F003Fh; samDesired
0x180005b8b  mov     [rsp+90h+dwOptions], edi; int
0x180005b8f  xor     r9d, r9d; lpClass
0x180005b92  xor     r8d, r8d; Reserved
0x180005b95  mov     rdx, rbx; lpSubKey
0x180005b98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005b9f  call    cs:__imp_RegCreateKeyExW
0x180005ba5  mov     rcx, [rbp+5Fh]; this
0x180005ba9  test    eax, eax
0x180005bab  jns     short loc_180005BC2
0x180005bad  mov     r9d, eax; char *
0x180005bb0  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005bb7  mov     edx, 748h; void *
0x180005bbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005bc2  lea     rcx, [rbp+57h+lpData]
0x180005bc6  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x180005bcb  nop
0x180005bcc  lea     rdx, [rbp+57h+lpData]
0x180005bd0  cmp     [rbp+57h+var_10], 7
0x180005bd5  cmova   rdx, [rbp+57h+lpData]
0x180005bda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005bde  inc     rax
0x180005be1  cmp     [rdx+rax*2], di
0x180005be5  jnz     short loc_180005BDE
0x180005be7  lea     eax, ds:2[rax*2]
0x180005bee  mov     [rsp+90h+samDesired], eax; cbData
0x180005bf2  mov     qword ptr [rsp+90h+dwOptions], rdx; int
0x180005bf7  mov     r9d, 1; dwType
0x180005bfd  xor     r8d, r8d; Reserved
0x180005c00  lea     rdx, ValueName; "DeviceVersionValue"
0x180005c07  mov     rcx, [rbp+57h+hKey]; hKey
0x180005c0b  call    cs:__imp_RegSetValueExW
0x180005c11  mov     rcx, [rbp+5Fh]; this
0x180005c15  test    eax, eax
0x180005c17  jns     short loc_180005C2E
0x180005c19  mov     r9d, eax; char *
0x180005c1c  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005c23  mov     edx, 753h; void *
0x180005c28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005c2e  mov     rdx, [rbp+57h+var_10]
0x180005c32  cmp     rdx, 7
0x180005c36  jbe     short loc_180005C49
0x180005c38  lea     rdx, ds:2[rdx*2]
0x180005c40  mov     rcx, [rbp+57h+lpData]
0x180005c44  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005c49  mov     [rbp+57h+var_18], rdi
0x180005c4d  mov     [rbp+57h+var_10], 7
0x180005c55  mov     word ptr [rbp+57h+lpData], di
0x180005c59  mov     rcx, [rbp+57h+hKey]; hKey
0x180005c5d  test    rcx, rcx
0x180005c60  jz      short loc_180005C69
0x180005c62  call    cs:__imp_RegCloseKey
0x180005c68  nop
0x180005c69  mov     rcx, rbx; pv
0x180005c6c  call    cs:__imp_CoTaskMemFree
0x180005c72  mov     rcx, [rbp+57h+var_8]
0x180005c76  xor     rcx, rsp; StackCookie
0x180005c79  call    __security_check_cookie
0x180005c7e  lea     r11, [rsp+90h+var_s0]
0x180005c86  mov     rbx, [r11+10h]
0x180005c8a  mov     rdi, [r11+18h]
0x180005c8e  mov     rsp, r11
0x180005c91  pop     rbp
0x180005c92  retn
```
