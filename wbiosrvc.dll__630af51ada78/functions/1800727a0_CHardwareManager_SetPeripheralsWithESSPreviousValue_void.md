# CHardwareManager::SetPeripheralsWithESSPreviousValue(void)

- ea: `0x1800727a0`
- end: `0x1800728d9`
- name: `?SetPeripheralsWithESSPreviousValue@CHardwareManager@@SAJXZ`
- size: `313`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800579a0`
- `0x180072448`

## callees

- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180026b28`
- `0x180027438`
- `0x180035d78`
- `0x18003f2dc`
- `0x180068f60`
- `0x1800727a0`
- `0x180072d58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800728aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800728aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007287f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007287f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072848`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072848`

## string_xrefs

- `0x1800727fd`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180072895`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CHardwareManager::SetPeripheralsWithESSPreviousValue(void)
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  int WinBioRegistryLocation; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // rax
  PHKEY v6; // r8
  unsigned int v7; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  BYTE Data[8]; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v16[24]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  BioPolicy::Refresh((BioPolicy *)v16);
  *(_DWORD *)Data = v16[2 * (int)BioPolicy::Values::make_index(10)];
  std::wstring::wstring(v15, v0, v1, v2);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v15);
  v4 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFB4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      phkResult);
    goto LABEL_10;
  }
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x2001Fu, v6);
  v8 = retaddr;
  if ( v7 )
  {
    v9 = 4032;
  }
  else
  {
    v7 = RegSetValueExW(hKey, L"PeripheralsWithESSPreviousValue", 0, 4u, Data, 4u);
    v8 = retaddr;
    if ( !v7 )
      goto LABEL_8;
    v9 = 4042;
  }
  wil::details::in1diag3::_Log_Win32(
    v8,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
    (const char *)v7,
    phkResulta);
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_10:
  std::wstring::_Tidy_deallocate(v15);
  return v4;
}

```

## disassembly

```asm
0x1800727a0  mov     [rsp-8+arg_0], rbx
0x1800727a5  push    rbp
0x1800727a6  lea     rbp, [rsp-57h]
0x1800727ab  sub     rsp, 0D0h
0x1800727b2  mov     rax, cs:__security_cookie
0x1800727b9  xor     rax, rsp
0x1800727bc  mov     [rbp+57h+var_10], rax
0x1800727c0  lea     rcx, [rbp+57h+var_70]; this
0x1800727c4  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x1800727c9  mov     ecx, 0Ah
0x1800727ce  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x1800727d3  movsxd  rcx, eax
0x1800727d6  mov     eax, [rbp+rcx*8+57h+var_70]
0x1800727da  mov     dword ptr [rbp+57h+Data], eax
0x1800727dd  lea     rcx, [rbp+57h+var_90]
0x1800727e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800727e6  nop
0x1800727e7  lea     rcx, [rbp+57h+var_90]
0x1800727eb  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800727f0  mov     ebx, eax
0x1800727f2  mov     rcx, [rbp+5Fh]; this
0x1800727f6  test    eax, eax
0x1800727f8  jns     short loc_180072813
0x1800727fa  mov     r9d, eax; char *
0x1800727fd  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180072804  mov     edx, 0FB4h; void *
0x180072809  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007280e  jmp     loc_1800728B1
0x180072813  mov     [rbp+57h+hKey], 0
0x18007281b  lea     rcx, [rbp+57h+hKey]
0x18007281f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180072824  mov     r8, rax
0x180072827  lea     rcx, [rbp+57h+var_90]
0x18007282b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072830  mov     rdx, rax; lpSubKey
0x180072833  mov     [rsp+0D0h+phkResult], r8; phkResult
0x180072838  mov     r9d, 2001Fh; samDesired
0x18007283e  xor     r8d, r8d; ulOptions
0x180072841  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072848  call    cs:__imp_RegOpenKeyExW
0x18007284e  mov     rcx, [rbp+5Fh]
0x180072852  test    eax, eax
0x180072854  jz      short loc_18007285D
0x180072856  mov     edx, 0FC0h
0x18007285b  jmp     short loc_180072892
0x18007285d  mov     r9d, 4; dwType
0x180072863  mov     [rsp+0D0h+cbData], r9d; cbData
0x180072868  lea     rax, [rbp+57h+Data]
0x18007286c  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180072871  xor     r8d, r8d; Reserved
0x180072874  lea     rdx, aPeripheralswit; "PeripheralsWithESSPreviousValue"
0x18007287b  mov     rcx, [rbp+57h+hKey]; hKey
0x18007287f  call    cs:__imp_RegSetValueExW
0x180072885  mov     rcx, [rbp+5Fh]; this
0x180072889  test    eax, eax
0x18007288b  jz      short loc_1800728A1
0x18007288d  mov     edx, 0FCAh; void *
0x180072892  mov     r9d, eax; char *
0x180072895  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x18007289c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800728a1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800728a5  test    rcx, rcx
0x1800728a8  jz      short loc_1800728B1
0x1800728aa  call    cs:__imp_RegCloseKey
0x1800728b0  nop
0x1800728b1  lea     rcx, [rbp+57h+var_90]
0x1800728b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800728ba  mov     eax, ebx
0x1800728bc  mov     rcx, [rbp+57h+var_10]
0x1800728c0  xor     rcx, rsp; StackCookie
0x1800728c3  call    __security_check_cookie
0x1800728c8  mov     rbx, [rsp+0D0h+arg_0]
0x1800728d0  add     rsp, 0D0h
0x1800728d7  pop     rbp
0x1800728d8  retn
```
