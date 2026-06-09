# CEssStateManager::SetNonEssSensorsBlocked(bool)

- ea: `0x180073dac`
- end: `0x180073edc`
- name: `?SetNonEssSensorsBlocked@CEssStateManager@@SAJ_N@Z`
- size: `304`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180074224`

## callees

- `0x180011d90`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x18005388c`
- `0x180068f60`
- `0x180073dac`
- `0x180074380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073eab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073eab`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180073e85`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180073e85`

## string_xrefs

- `0x180073dff`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`
- `0x180073e3b`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEssStateManager::SetNonEssSensorsBlocked(unsigned __int8 a1)
{
  int v1; // edi
  int WinBioRegistryLocation; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rdx
  bool v8; // zf
  unsigned int lpData; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  int Data; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v13[2]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v1 = a1;
  v13[0] = 0;
  v13[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v13[0]) = 0;
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v13);
  v3 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      lpData);
    goto LABEL_14;
  }
  hKey = 0;
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v6 = wil::reg::create_unique_key_nothrow(v5, v4, &hKey);
  if ( v6 )
  {
    v7 = 91;
    goto LABEL_5;
  }
  Data = v1;
  v6 = RegSetKeyValueW(hKey, 0, L"NonEssSensorsBlocked", 4u, &Data, 4u);
  v8 = v6 == 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v8 = v6 == 0;
  }
  if ( !v8 )
  {
    v7 = 97;
LABEL_5:
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
           (const char *)(unsigned int)v6,
           lpData);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_14;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v3 = 0;
LABEL_14:
  std::wstring::_Tidy_deallocate(v13);
  return v3;
}

```

## disassembly

```asm
0x180073dac  mov     [rsp-8+arg_0], rbx
0x180073db1  mov     [rsp-8+arg_8], rdi
0x180073db6  push    rbp
0x180073db7  mov     rbp, rsp
0x180073dba  sub     rsp, 70h
0x180073dbe  mov     rax, cs:__security_cookie
0x180073dc5  xor     rax, rsp
0x180073dc8  mov     [rbp+var_10], rax
0x180073dcc  movzx   edi, cl
0x180073dcf  xorps   xmm0, xmm0
0x180073dd2  movups  [rbp+var_30], xmm0
0x180073dd6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180073dde  movdqu  [rbp+var_20], xmm1
0x180073de3  xor     eax, eax
0x180073de5  mov     word ptr [rbp+var_30], ax
0x180073de9  lea     rcx, [rbp+var_30]
0x180073ded  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180073df2  mov     ebx, eax
0x180073df4  test    eax, eax
0x180073df6  jns     short loc_180073E15
0x180073df8  mov     rcx, [rbp+8]; this
0x180073dfc  mov     r9d, eax; char *
0x180073dff  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073e06  mov     edx, 54h ; 'T'; void *
0x180073e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073e10  jmp     loc_180073EB3
0x180073e15  mov     [rbp+hKey], 0
0x180073e1d  lea     rcx, [rbp+var_30]
0x180073e21  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180073e26  mov     rdx, rax
0x180073e29  lea     r8, [rbp+hKey]
0x180073e2d  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180073e32  test    eax, eax
0x180073e34  jz      short loc_180073E61
0x180073e36  mov     edx, 5Bh ; '['; void *
0x180073e3b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073e42  mov     r9d, eax; char *
0x180073e45  mov     rcx, [rbp+8]; this
0x180073e49  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180073e4e  mov     ebx, eax
0x180073e50  mov     rcx, [rbp+hKey]; hKey
0x180073e54  test    rcx, rcx
0x180073e57  jz      short loc_180073EB3
0x180073e59  call    cs:__imp_RegCloseKey
0x180073e5f  jmp     short loc_180073EB3
0x180073e61  mov     [rbp+Data], edi
0x180073e64  mov     r9d, 4; dwType
0x180073e6a  mov     [rsp+70h+cbData], r9d; cbData
0x180073e6f  lea     rax, [rbp+Data]
0x180073e73  mov     [rsp+70h+lpData], rax; lpData
0x180073e78  lea     r8, aNonesssensorsb; "NonEssSensorsBlocked"
0x180073e7f  xor     edx, edx; lpSubKey
0x180073e81  mov     rcx, [rbp+hKey]; hKey
0x180073e85  call    cs:__imp_RegSetKeyValueW
0x180073e8b  test    eax, eax
0x180073e8d  jle     short loc_180073E99
0x180073e8f  movzx   eax, ax
0x180073e92  or      eax, 80070000h
0x180073e97  test    eax, eax
0x180073e99  jz      short loc_180073EA2
0x180073e9b  mov     edx, 61h ; 'a'
0x180073ea0  jmp     short loc_180073E3B
0x180073ea2  mov     rcx, [rbp+hKey]; hKey
0x180073ea6  test    rcx, rcx
0x180073ea9  jz      short loc_180073EB1
0x180073eab  call    cs:__imp_RegCloseKey
0x180073eb1  xor     ebx, ebx
0x180073eb3  lea     rcx, [rbp+var_30]
0x180073eb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073ebc  mov     eax, ebx
0x180073ebe  mov     rcx, [rbp+var_10]
0x180073ec2  xor     rcx, rsp; StackCookie
0x180073ec5  call    __security_check_cookie
0x180073eca  lea     r11, [rsp+70h+var_s0]
0x180073ecf  mov     rbx, [r11+10h]
0x180073ed3  mov     rdi, [r11+18h]
0x180073ed7  mov     rsp, r11
0x180073eda  pop     rbp
0x180073edb  retn
```
