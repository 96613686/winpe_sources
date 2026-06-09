# CEssStateManager::SetEnableEssPreviousValue(void)

- ea: `0x180073c84`
- end: `0x180073da3`
- name: `?SetEnableEssPreviousValue@CEssStateManager@@SA?AW4EssState@BioPolicy@@XZ`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800730ec`
- `0x180073538`

## callees

- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180026b28`
- `0x180027438`
- `0x180068f60`
- `0x180072d58`
- `0x180073c84`
- `0x180074380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073d74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073d74`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180073d3c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180073d3c`

## string_xrefs

- `0x180073d5e`: `onecore\ds\security\biometrics\service\server\essstatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CEssStateManager::SetEnableEssPreviousValue()
{
  unsigned int v0; // ebx
  int WinBioRegistryLocation; // eax
  wil::details::in1diag3 *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-59h]
  unsigned int Data; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  _OWORD v10[2]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v11[24]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  BioPolicy::Refresh((BioPolicy *)v11);
  v0 = v11[2 * (int)BioPolicy::Values::make_index(11)];
  v10[0] = 0;
  v10[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v10[0]) = 0;
  hKey = 0;
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v10);
  v2 = retaddr;
  if ( WinBioRegistryLocation )
  {
    v3 = 63;
LABEL_9:
    wil::details::in1diag3::_Log_Win32(
      v2,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\essstatemanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      lpData);
    goto LABEL_10;
  }
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
  WinBioRegistryLocation = wil::reg::create_unique_key_nothrow(v5, v4, &hKey);
  v2 = retaddr;
  if ( WinBioRegistryLocation )
  {
    v3 = 68;
    goto LABEL_9;
  }
  Data = v0;
  WinBioRegistryLocation = RegSetKeyValueW(hKey, 0, L"EnableESSPreviousValue", 4u, &Data, 4u);
  if ( WinBioRegistryLocation > 0 )
    WinBioRegistryLocation = (unsigned __int16)WinBioRegistryLocation | 0x80070000;
  v2 = retaddr;
  if ( WinBioRegistryLocation )
  {
    v3 = 73;
    goto LABEL_9;
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(v10);
  return v0;
}

```

## disassembly

```asm
0x180073c84  mov     [rsp-8+arg_0], rbx
0x180073c89  push    rbp
0x180073c8a  lea     rbp, [rsp-57h]
0x180073c8f  sub     rsp, 0D0h
0x180073c96  mov     rax, cs:__security_cookie
0x180073c9d  xor     rax, rsp
0x180073ca0  mov     [rbp+57h+var_10], rax
0x180073ca4  lea     rcx, [rbp+57h+var_70]; this
0x180073ca8  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x180073cad  mov     ecx, 0Bh
0x180073cb2  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x180073cb7  movsxd  rcx, eax
0x180073cba  mov     ebx, [rbp+rcx*8+57h+var_70]
0x180073cbe  xorps   xmm0, xmm0
0x180073cc1  movups  [rbp+57h+var_90], xmm0
0x180073cc5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180073ccd  movdqu  [rbp+57h+var_80], xmm1
0x180073cd2  xor     eax, eax
0x180073cd4  mov     word ptr [rbp+57h+var_90], ax
0x180073cd8  mov     [rbp+57h+hKey], rax
0x180073cdc  lea     rcx, [rbp+57h+var_90]
0x180073ce0  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180073ce5  mov     rcx, [rbp+5Fh]
0x180073ce9  test    eax, eax
0x180073ceb  jz      short loc_180073CF4
0x180073ced  mov     edx, 3Fh ; '?'
0x180073cf2  jmp     short loc_180073D5B
0x180073cf4  lea     rcx, [rbp+57h+var_90]
0x180073cf8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180073cfd  mov     rdx, rax
0x180073d00  lea     r8, [rbp+57h+hKey]
0x180073d04  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180073d09  mov     rcx, [rbp+5Fh]
0x180073d0d  test    eax, eax
0x180073d0f  jz      short loc_180073D18
0x180073d11  mov     edx, 44h ; 'D'
0x180073d16  jmp     short loc_180073D5B
0x180073d18  mov     [rbp+57h+Data], ebx
0x180073d1b  mov     r9d, 4; dwType
0x180073d21  mov     [rsp+0D0h+cbData], r9d; cbData
0x180073d26  lea     rax, [rbp+57h+Data]
0x180073d2a  mov     [rsp+0D0h+lpData], rax; unsigned int
0x180073d2f  lea     r8, aEnableessprevi; "EnableESSPreviousValue"
0x180073d36  xor     edx, edx; lpSubKey
0x180073d38  mov     rcx, [rbp+57h+hKey]; hKey
0x180073d3c  call    cs:__imp_RegSetKeyValueW
0x180073d42  test    eax, eax
0x180073d44  jle     short loc_180073D4E
0x180073d46  movzx   eax, ax
0x180073d49  or      eax, 80070000h
0x180073d4e  mov     rcx, [rbp+5Fh]; this
0x180073d52  test    eax, eax
0x180073d54  jz      short loc_180073D6B
0x180073d56  mov     edx, 49h ; 'I'; void *
0x180073d5b  mov     r9d, eax; char *
0x180073d5e  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\biometrics\\serv"...
0x180073d65  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180073d6a  nop
0x180073d6b  mov     rcx, [rbp+57h+hKey]; hKey
0x180073d6f  test    rcx, rcx
0x180073d72  jz      short loc_180073D7B
0x180073d74  call    cs:__imp_RegCloseKey
0x180073d7a  nop
0x180073d7b  lea     rcx, [rbp+57h+var_90]
0x180073d7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073d84  mov     eax, ebx
0x180073d86  mov     rcx, [rbp+57h+var_10]
0x180073d8a  xor     rcx, rsp; StackCookie
0x180073d8d  call    __security_check_cookie
0x180073d92  mov     rbx, [rsp+0D0h+arg_0]
0x180073d9a  add     rsp, 0D0h
0x180073da1  pop     rbp
0x180073da2  retn
```
