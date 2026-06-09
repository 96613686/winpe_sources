# _UpdateBioEnrollmentRegKey

- ea: `0x18006561c`
- end: `0x18006576e`
- name: `_UpdateBioEnrollmentRegKey`
- size: `338`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008f340`

## callees

- `0x180011d90`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180035d78`
- `0x18005388c`
- `0x18006561c`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800656f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006573e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800656f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006573e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065724`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065724`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800656c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800656c6`

## string_xrefs

- `0x180065719`: `EnrollmentCommitted`
- `0x18006565c`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`
- `0x1800656d5`: `onecore\ds\security\biometrics\service\server\asyncserveroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UpdateBioEnrollmentRegKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int WinBioRegistryLocation; // eax
  unsigned int v5; // ebx
  const WCHAR *v6; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  __int64 v9; // rdx
  int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  HKEY hKey; // [rsp+50h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp+1Fh] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  std::wstring::wstring(v15, a2, a3, a4);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v15);
  v5 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12BF,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      dwOptions);
    goto LABEL_12;
  }
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
  if ( Key )
  {
    v9 = 4811;
    goto LABEL_5;
  }
  *(_DWORD *)Data = 1;
  Key = RegSetValueExW(hKey, L"EnrollmentCommitted", 0, 4u, Data, 4u);
  if ( Key )
  {
    v9 = 4820;
LABEL_5:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\asyncserveroperations.cpp",
           (const char *)Key,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_12;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v5 = 0;
LABEL_12:
  std::wstring::_Tidy_deallocate(v15);
  return v5;
}

```

## disassembly

```asm
0x18006561c  mov     [rsp-8+arg_0], rbx
0x180065621  push    rbp
0x180065622  lea     rbp, [rsp-57h]
0x180065627  sub     rsp, 90h
0x18006562e  mov     rax, cs:__security_cookie
0x180065635  xor     rax, rsp
0x180065638  mov     [rbp+57h+var_10], rax
0x18006563c  lea     rcx, [rbp+57h+var_30]
0x180065640  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180065645  nop
0x180065646  lea     rcx, [rbp+57h+var_30]
0x18006564a  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x18006564f  mov     ebx, eax
0x180065651  test    eax, eax
0x180065653  jns     short loc_180065672
0x180065655  mov     rcx, [rbp+5Fh]; this
0x180065659  mov     r9d, eax; char *
0x18006565c  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x180065663  mov     edx, 12BFh; void *
0x180065668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006566d  jmp     loc_180065746
0x180065672  mov     [rbp+57h+hKey], 0
0x18006567a  lea     rcx, [rbp+57h+hKey]
0x18006567e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180065683  mov     r8, rax
0x180065686  lea     rcx, [rbp+57h+var_30]
0x18006568a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006568f  mov     rdx, rax; lpSubKey
0x180065692  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x18006569b  mov     [rsp+90h+phkResult], r8; phkResult
0x1800656a0  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800656a9  mov     [rsp+90h+samDesired], 2001Fh; samDesired
0x1800656b1  mov     [rsp+90h+dwOptions], 0; unsigned int
0x1800656b9  xor     r9d, r9d; lpClass
0x1800656bc  xor     r8d, r8d; Reserved
0x1800656bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800656c6  call    cs:__imp_RegCreateKeyExW
0x1800656cc  test    eax, eax
0x1800656ce  jz      short loc_1800656FB
0x1800656d0  mov     edx, 12CBh; void *
0x1800656d5  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\biometrics\\serv"...
0x1800656dc  mov     r9d, eax; char *
0x1800656df  mov     rcx, [rbp+5Fh]; this
0x1800656e3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800656e8  mov     ebx, eax
0x1800656ea  mov     rcx, [rbp+57h+hKey]; hKey
0x1800656ee  test    rcx, rcx
0x1800656f1  jz      short loc_180065746
0x1800656f3  call    cs:__imp_RegCloseKey
0x1800656f9  jmp     short loc_180065746
0x1800656fb  mov     dword ptr [rbp+57h+Data], 1
0x180065702  mov     r9d, 4; dwType
0x180065708  mov     [rsp+90h+samDesired], r9d; cbData
0x18006570d  lea     rax, [rbp+57h+Data]
0x180065711  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x180065716  xor     r8d, r8d; Reserved
0x180065719  lea     rdx, aEnrollmentcomm; "EnrollmentCommitted"
0x180065720  mov     rcx, [rbp+57h+hKey]; hKey
0x180065724  call    cs:__imp_RegSetValueExW
0x18006572a  test    eax, eax
0x18006572c  jz      short loc_180065735
0x18006572e  mov     edx, 12D4h
0x180065733  jmp     short loc_1800656D5
0x180065735  mov     rcx, [rbp+57h+hKey]; hKey
0x180065739  test    rcx, rcx
0x18006573c  jz      short loc_180065744
0x18006573e  call    cs:__imp_RegCloseKey
0x180065744  xor     ebx, ebx
0x180065746  lea     rcx, [rbp+57h+var_30]
0x18006574a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006574f  mov     eax, ebx
0x180065751  mov     rcx, [rbp+57h+var_10]
0x180065755  xor     rcx, rsp; StackCookie
0x180065758  call    __security_check_cookie
0x18006575d  mov     rbx, [rsp+90h+arg_0]
0x180065765  add     rsp, 90h
0x18006576c  pop     rbp
0x18006576d  retn
```
